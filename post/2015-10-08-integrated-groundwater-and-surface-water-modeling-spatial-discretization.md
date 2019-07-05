---
layout: post
title: 'Integrated groundwater and surface water modeling: spatial discretization'
date: 2015-10-08 13:37:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- Groundwater
- MODFLOW
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
permalink: "/2015/10/08/integrated-groundwater-and-surface-water-modeling-spatial-discretization/"
---
Numerical simulations have to break time and space into increments. For example, weather predictions are usually modeled in hours or days and maps are produced with resolution.

In contrast, our real world is always behaving continuously. For example, temperature always evolves with time continuously.

We are also interested in a three dimensional simulation instead of 1D or 2D. The real world itself is 3D though we constantly forget that. It is just doesn't benefit much if we had a 3D temperature map.

For other types of simulation, however, 3D could provides much better solutions.  
Groundwater flow, as an example, is best simulated with 3D numerical simulation.

The spatial discretization is always a challenge for groundwater modeling. Horizontal and vertical discretization are always coupled together. For example, in a flat grassland with homogeneous hydrologic proprieties, the horizontal discretization becomes less important. However, if the surface elevation changes drastically, the horizontal discretization matters.

Imagine a cheese cake with multi-layers, if it is placed on the table, no matter how you cut it into pieces, the cake will look exactly the same as long as you don't part the pieces.

[![]({{ site.baseurl }}/assets/2875b-spatial_discretization1.png?w=300)](https://changliao.files.wordpress.com/2015/10/2875b-spatial_discretization1.png)

However, if we lean the table to certain angle and consider the pieces are adjusted to sit vertically in their same positions, the system may changes dramatically: the top layer on the higher position no longer touch others; the cheese in the lower layer may mix the neighbor cake layer!

[![]({{ site.baseurl }}/assets/be811-spatial_discretization2.png?w=300)](https://changliao.files.wordpress.com/2015/10/be811-spatial_discretization2.png)

So what might be the solution? We need better space discretization to minimize the space distortion.

Let's still consider the cake example, if there is only one layer, just the cake, it might be acceptable as long as we don't flip the table. In other words, if we have thick layers, horizontal discretization becomes less important. However, when we have thin layers, fine horizontal discretization can reduce the distortion. If we cut the cake into many pieces, then top might always stick with top.

Wait, if we cut the cake to fine, what if we can't even eat it?  
Like if we have fine grid, such as 0.1m, that we can't even run the simulation since we may have 1Billion grid!

Therefore, a compromise has to be made in order to make things work.

Several options are:   
Bring horizontal grid into the similar scale with vertical layer to avoid distortion;   
Use unstructured grid instead of uniform grid to reduce computational demand. 

Besides, careful selection or definition of the layered cake and table also plays an important role!

