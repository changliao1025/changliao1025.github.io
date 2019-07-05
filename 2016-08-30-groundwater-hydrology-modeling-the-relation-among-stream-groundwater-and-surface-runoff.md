---
layout: post
title: 'Groundwater hydrology modeling: the relation among stream, groundwater and
  surface runoff'
date: 2016-08-30 20:17:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- MODFLOW
- Stream Discharge
- Surface Runoff
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
permalink: "/2016/08/30/groundwater-hydrology-modeling-the-relation-among-stream-groundwater-and-surface-runoff/"
---
Stream discharge is an important component in hydrology. Yet stream discharge is commonly studied in surface hydrology. In recent decades, it has been recognized that groundwater also interact with stream water throughout the year.

In groundwater modeling, stream routing is explicitly modeled as a groundwater boundary condition.  
In general, several data are required for a successful simulation. Here I will only discuss a little bit related to water itself, to say, what kind of sink or source of the water in stream routing should be considered.

First, a stream segment/reach may received upstream discharge.

Second, a stream can also receive direct precipitation from the sky. But this term is usually omitted some the total amount may not be significant.

Third, a stream may also lose water from evaporation. Similar to direct precipitation, this term is usually omitted as well.

Forth, stream also receive later flow, it can be surface runoff and subsurface runoff (soil zone inter-flow). Many studies have shown that subsurface runoff account for more than 50% of the horizontal water flow. This term should be carefully estimated. However, surface runoff is also important during precipitation or snowmelt events.

Fifth, groundwater upwelling or stream leakage. This is the process stream water gain or lose water.

Below is an example of simulation stream discharge rates VS observed ones.

[![]({{ site.baseurl }}/assets/577f0-verification_scatter.png?w=300)](https://changliao.files.wordpress.com/2016/08/577f0-verification_scatter.png)

So there are still some questions.&nbsp;

First, in winter time, what should be well constrained since simulated discharge rates are much higher than observed rates?

