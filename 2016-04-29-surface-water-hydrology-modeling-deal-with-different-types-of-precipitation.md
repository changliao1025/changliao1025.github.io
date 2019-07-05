---
layout: post
title: 'Surface water hydrology modeling: deal with different types of precipitation'
date: 2016-04-29 23:54:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- Precipitation
- PRMS
- Snow
- SWAT
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
permalink: "/2016/04/29/surface-water-hydrology-modeling-deal-with-different-types-of-precipitation/"
---
In surface water hydrology, precipitation is one of the most important components.  
However, withing most hydrology models, it is unclear of how precipitation is actually represented.  
For example, in a typical water cycle illustration from [Wiki](https://en.wikipedia.org/wiki/Precipitation), precipitation is described as

 ![]({{ site.baseurl }}/assets/Water_cycle.png)

Here is the question, what form does precipitation actually take when it falls to land surface?

Water can be in either liquid (water, rain), solid(ice, snow) or gas(water vapor) forms. How about precipitation? Surely most of time precipitation is either rain of snow. In some cases, it takes form in hail, etc.

Since the physical proprieties of water and snow are significantly different, it is necessary to distinguish them within surface water hydrology models.

In some scenarios, rain and snow may co-exist in a [mixed precipitation](https://en.wikipedia.org/wiki/Rain_and_snow_mixed) event. In this case, surface water hydrology models need to deal with both of them. The difficulty is how to manage the two-phase mass and energy balance.

A complete comparison of how different models deal with this scenario will be presented later.

**Updates: 21, January 2017**  
**After reviewing some typical surface hydrology model, I decided to use the following scheme in my ecosystem model.**  
**This approach uses the maximum and minimum temperature and two parameters to decide the precipitation type.**  
**When it is a mixture event, a linear method is used estimate the portion of rain or snow in precipitation.**

[![]({{ site.baseurl }}/assets/a06af-snow_or_rain.jpg?w=300)](https://changliao.files.wordpress.com/2016/04/a06af-snow_or_rain.jpg)

Copy right of &nbsp;Purdue University. Please contact me if you want to use this figure. Thanks.

