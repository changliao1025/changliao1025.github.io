---
layout: post
title: 'Ecosystem modeling: a question of chicken or eggs?'
date: 2016-06-02 14:31:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- CLM
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
permalink: "/2016/06/02/ecosystem-modeling-a-question-of-chicken-or-eggs/"
---
Ecosystem modeling generally include three conceptual components: inputs, algorithm and outputs.  
For example, we usually need precipitation to estimate surface runoff.  
On the other hand, sometimes some outputs are also considered as inputs for other models. For example, vegetation dynamics also change the surface albedo and therefore the incoming radiation.  
In another word, the feedback among different processes are often too complex that we generally have to ignore some feedback processes.

The reason is that our computer simulation MUST have a starting point and a sequence of algorithms in order to run the simulation.  
For some well-designed models, the differences between different starting points are not significant when using the numerical approach. However, it is a best practice to put all the algorithms in the right orders.

For example, in surface hydrology, the generally order of the water flow is like this: precipitation-\>interception-\>snow-\>infiltration-\>overland runoff-\>stream flow, etc. In some case, groundwater also plays a role in this process.  
If you map these processes to the actual physical world, these processes occur in the following places: atmosphere-\>canopy-\>land surface-\>soil-\>stream channel. etc.  
Therefore, even though most of the processes occur simultaneously, we still need to break them down due to the time discretization scheme. If you have input data at a second resolution, following above order will not produce any different outputs compared with a different order. But if the time resolution is daily, monthly, or annually, the differences will increase significantly.

Even though the algorithms are placed under a logic order such as water flow, how to design them in a computer program remains unclear. First, in most computer program developments, dependency relationship among components do not always reflect these logical orders. For example, a typical vegetation&nbsp;is consist of canopy, stem and root. However, processes occur in these parts are usually at different time scale and environmental conditions, which makes the dependency relationship of these processes are usually much distorted in computation programs.

I will provide a real live example for review here:  
The[Community Land Model](http://www.cgd.ucar.edu/tss/clm/) (CLM) is a widely used ecosystem model.  
The core part of the processes simulated has a following order in CLM 4.0.

[![]({{ site.baseurl }}/assets/36cfa-clm.png)](https://changliao.files.wordpress.com/2016/06/36cfa-clm.png)

On the left are the names of the processes or modules, on the right are brief description of them. It appears that the general workflow is from top to bottom. But the question remains unresolved, whether this is the appropriate order for all of these processes. For example, what if the albedo is estimated ahead of the soil flux since energy budget will be potentially different if albedo chanages from snow are considered.

