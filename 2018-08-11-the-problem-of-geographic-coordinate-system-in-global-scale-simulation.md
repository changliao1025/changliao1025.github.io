---
layout: post
title: The problem of geographic coordinate system in global scale simulation
date: 2018-08-11 21:13:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- ECO3D
- GCS
- GIS
- Google Map
- Heat Equation
- Hexagon
- Numerical Simulation
meta:
  _publicize_pending: '1'
  restapi_import_id: 5caaaa8cc3ef2
  _import_original_post_id: '0'
author:
  login: changliao
  email: changliao1025@outlook.com
  display_name: Chang Liao
  first_name: ''
  last_name: ''
permalink: "/2018/08/11/the-problem-of-geographic-coordinate-system-in-global-scale-simulation/"
---
Earlier I have discussed some **[idea](https://www.changliao.us/2017/06/spatial-datasets-operations-006.html)** about the hexagon-based grid system. Now I have provided some tests and materials to support this project.

90% percent of global maps you can find online are using the&nbsp;geographic coordinate system ([GCS](https://en.wikipedia.org/wiki/Geographic_coordinate_system)). You can try to search "global map" in [Google image](https://www.google.com/search?hl=en&tbm=isch&source=hp&biw=1277&bih=688&ei=WkhvW8qKJ4TesAW915yAAw&q=global+map&oq=global+&gs_l=img.3.0.35i39k1j0l9.1747.2687.0.4513.9.9.0.0.0.0.127.697.0j6.6.0....0...1ac.1.64.img..3.6.696.0...0.NzMugjEpFdI).

There might be 9% of them are using various map projection.

The reason why there are so many different ways to represent the Earth is that Earth is NOT flat. Google know it so they changed the Google Map recently.

So these are some basic GIS knowledge but you can also learn it from this video.

[youtube=https://www.youtube.com/watch?v=kIID5FDi2JQ&w=320&h=266]

While it is generally OK to view these types of global map for daily usage, it can cause problems for large scale to global scale simulations.

In Earth science, GCS is most commonly used as the grid system for terrestrial ecosystem simulations. For example, a 1\* 1 degree grid will discrete the global into a 360 \* 180 matrix.

However, it will be problematic for several reasons.  
For example, the area at different regions are not the same. For example. a 0.5\* 0.5 grid cell is about 50\*50km in Amazon whereas it is about 50\*25km in Alaska, only half the size of the former one.

To illustrate the difference, let's use a classical 2D heat equation I found from [here](https://scipython.com/book/chapter-7-matplotlib/examples/the-two-dimensional-diffusion-equation/):  
First, we run the simulation with the uniformly dx = dy, which present longitude and latitude in our case. The results are like this:

[![]({{ site.baseurl }}/assets/acb15-figure_2.png?w=300)](https://changliao.files.wordpress.com/2018/08/acb15-figure_2.png)

Then we changed to dy = 2 dx:&nbsp;

[![]({{ site.baseurl }}/assets/96b44-figure_1.png?w=300)](https://changliao.files.wordpress.com/2018/08/96b44-figure_1.png)

Last, we changed to dx = 2 dy:

[![]({{ site.baseurl }}/assets/f9536-figure_3.png?w=300)](https://changliao.files.wordpress.com/2018/08/f9536-figure_3.png)

If you look closer, you will see the differences. When the grid geometry is not uniform, the simulated heat distribution is also not uniform in spatial.

Now let's get back to GCS in global simulation. Because the grid geometry changes from tropic to pole regions, the simulations are likely affected as well.

Next, I will show you some results of global scale hydrologic simulation.

