---
layout: post
title: 'Ecosystem modeling: a review on spatial resolution and lateral flow'
date: 2017-03-30 00:01:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags: []
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
permalink: "/2017/03/30/ecosystem-modeling-a-review-on-spatial-resolution-and-lateral-flow/"
---
We all agree that lateral flow is important in hydrology, but why most ecosystem models do not consider lateral flow?

The answer is usually related to spatial resolution. In a large scale or global scale GCM model simulation, the spatial resolution is usually&nbsp;$0.5^{\circ} \times 0.5^{\circ}$. At this resolution, lateral flow is usually&nbsp;negligible compared with vertical fluxes.

However, this procedure usually causes problems in mass balance. First, without lateral flow, freshwater into the ocean cannot be estimated accurately. Second, dissolved nutrients into the oceanic systems cannot be estimated.

So the question is at what resolution do we actually MUST consider lateral flow?

The answer depends on the fluxes you are looking into. For example, if you are looking into water flow, it it more than likely you have to always consider it, especially at regional scale. If you are looking into carbon/nitrogen fluxes, the problem will become slightly complicated.

First, we will need to evaluate what lateral fluxes are expressed in equations.  
For water flow in a simplified grid cell:

$  
\begin{align}\frac{\partial Water}{\partial t} & = Rain + Snowmelt &nbsp;- Evaportranspiration \\  
& +&nbsp;Groundwater\_{upwelling} - Groundwater\_{recharge} \\  
& + Runoff\_{in} - Runoff\_{out}  
\end{align}  
$

For carbon fluxes:

$  
\begin{align}\frac{\partial C\_{pool}}{\partial t} & = Photosynthesis\\  
& - Resipiration\_{autotrophic} &nbsp;- &nbsp;Resipiration\_{heterotrophic} \\  
& +&nbsp; Carbon\_{in} - Carbon\_{out}  
\end{align}  
$

Due to the fact that terms on the right hand side are often associated with water condition, it is therefore difficult to determine how sensitive these processes are affected by lateral flow. For example, if photosynthesis algorithm is based on soil moisture, it is likely Photosynthesis maybe affected by lateral flow, but the uncertainty range could be within $5\%$ or more. Or dissolved carbon that flows through water flow is about $1\%$ of the other terms.

Therefore, it is our responsibility to check how sensitive our models/algorithms are to the lateral flow. So far, I have not seen much work conducted in this direction. I am planning to conduct some research using my three-dimensional ecosystem modeling.

