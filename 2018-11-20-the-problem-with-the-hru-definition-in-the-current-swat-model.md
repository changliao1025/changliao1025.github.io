---
layout: post
title: The problem with the HRU definition in the current SWAT model
date: 2018-11-20 18:29:00.000000000 -08:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- HRU
- Model Calibration
- SWAT
- Watershed Hydrology
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
permalink: "/2018/11/20/the-problem-with-the-hru-definition-in-the-current-swat-model/"
---
Model calibration is a critical step in most numerical simulations, including hydrology simulations.

While I am conducting the model calibration for a SWAT model in one of my current projects, I found there are several issues in current methods.

In SWAT, a watershed is represented by a list of Hydrologic Response Unit (HRU), which is the smallest unit that has the same hydrologic property.

Besides, a watershed is also divided into a list of subbasin using watershed delineation process.  
In the end, a watershed is actually represented using the following structure.  
[![]({{ site.baseurl }}/assets/f9475-watershed.png?w=300)](https://changliao.files.wordpress.com/2018/11/f9475-watershed.png)  
Figure 1. The structure of a watershed in SWAT model.

The HRU is commonly defined using land cover, soil type and slope.

On the other side, data and parameters are usually assigned using different levels. For example, an unique ID is assigned to each HRU and some parameters are assigned to subbasin.

In reality, when two HRUs share the same land cover, soil and slope type, they are supposed to have the same hydrologic characteristics. However, in SWAT, because these HRUs are located in different subbasin, they are not calibrated simultaneously. For example, in Figure 1, the two HRUs in light blue color have the same physical properties but located in different subbasins. The SWAT inputs and calibration cannot guarantee they will have the same parameters.

This issue will cause several problem for the model calibration and simulation. First, it will create unnecessary parameters, which slow down the calibration efficiency. For example, if we have 10 subbasin, 5 land cover types, 5 soil types and 5 slope types. If we just consider physical properties, we should have a maximum of 125 parameters. But if we follow SWAT method, that is 1250 potential parameters!

Second, because it does not follow physical meaning, the parameter coming from the same type of HRU could differ significantly.

Maybe it is time to reconsider the subbasin-HRU structure for watershed hydrology for better modeling.

