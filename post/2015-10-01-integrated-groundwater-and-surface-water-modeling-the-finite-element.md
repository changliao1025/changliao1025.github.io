---
layout: post
title: 'Integrated groundwater and surface water modeling: the finite element'
date: 2015-10-01 00:58:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- MODFLOW
- PRMS
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
permalink: "/2015/10/01/integrated-groundwater-and-surface-water-modeling-the-finite-element/"
---
Numerical simulations of groundwater and surface water movements are essentially dealing with the finite element in the spatial domain.

This finite element could be in a variety of forms including cubic, node and pixel. This depends upon the methods used to conceptualize this physical world.

The dimension of these finite elements varies as well since they are characterized by spatial resolution.

For spatial distributed hydrologic models, regardless of groundwater or surface water models, these finite elements interact with each other governed by derived continuity equations such as Richard's equation.

Consequently, in most groundwater models, the finite element would interact with 6 neighbors in a 3D model. However, in a spatial distributed surface water model, the finite element may interact with 8 neighbors or 4 neighbors. Even within one model, different assumptions are possibly made in different scenarios.&nbsp;

Then the question is are these assumptions contradict each other? Or why it should have 8 neighbor instead of 4 and so on?

Let's first take a look at some real life examples using some existing models. For groundwater modeling, in MODFLOW, which is one of the most widely used groundwater models, each finite element can interact with 4 horizontal neighbors and 2 vertical neighbors. So there are 6 neighbors in total. Similarly for surface modeling, in SWAT/PRMS, each finite element can interact with 4 or 8 neighbors.&nbsp;

A close look at some watershed delineation process will unveil that even though water flow direction is predefined using digital elevation model (DEM) aspect, flow itself in fact is distributed in more than one direction using fractions.&nbsp;

An important reference of how this flow direction is produced is explained here:

[http://help.arcgis.com/EN/arcgisdesktop/10.0/help/index.html#//009z00000063000000.htm](http://help.arcgis.com/EN/arcgisdesktop/10.0/help/index.html#//009z00000063000000.htm)

Now it looks plausible that 8 neighbor would better describe the flow path than 4 neighbors. But why?

And why this is not implemented in groundwater modeling? Also what plays a factor in these assumptions? (spatial resolution?)

The following figure is retrieved from watershed delineation process. So will it become an issue that there are a few pixels that belong to 8 neighbor, but not 4 neighbor?

[![]({{ site.baseurl }}/assets/8be07-d8.png?w=300)](https://changliao.files.wordpress.com/2015/10/8be07-d8.png)

Certainly in surface water hydrology, water flow can be like this. But for groundwater modeling, this is usually not allowed if this type of pixels are on the boundary.&nbsp;

In fact, some watershed utilities indeed use 4 neighbors instead of 8 neighbors.

Complexity doesn't always performance better than simplicity. But sometimes complexity is a compromise between simplicity and limitation.

No matter what assumptions or strategies are made, govern equation only cares about mass balance and energy balance. As long as these laws are not violated, the models are usually reliable. However, this is also a common issue in integrated hydrologic model. And as our model continues to increase in processes and resolution, the possibility of encountering this type of issue increases as well.

