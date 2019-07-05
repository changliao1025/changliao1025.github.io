---
layout: post
title: 'Ecosystem modeling: challenges in simulating the dissolved organic carbon'
date: 2017-02-13 21:52:00.000000000 -08:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- DOC
- GIS
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
permalink: "/2017/02/13/ecosystem-modeling-challenges-in-simulating-the-dissolved-organic-carbon/"
---
Dissolved Organic Carbon (DOC) is an important carbon budget within ecosystem, especially for aquatic ecosystem including oceanic ecosystem.

Conventional DOC investigations mainly focus on DOC measurements in either soil profile or stream discharge. These measurements generally cannot explain where does DOC come from and how much DOC will be exported into the ocean. However, these studies have provided much insights of what biogeochemical processes are responsible for DOC dynamics.

So the question is can we quantitatively estimate DOC in terrestrial ecosystem based on existing knowledge.

I will provide more information on this topic in the coming months.

There are a few processes need to be simulated following the path of DOC.

1. DOC production, consumption, and transportation on surface (mainly in litter);
2. DOC production, consumption and transportation in subsurface (mainly in soil);
3. DOC consumption and transportation in hydrological network;
4. In some scenarios, DOC transportation in groundwater movements.

For section 3, there are some widely established approach to simulate solute transportation in stream. For example, the MT3D-USGS provides the one-dimensional advection-dispersion equation to solve the transport in stream network.

Assuming we have a fully distributed watershed hydrology model, each stream segment is represented by a number of stream reaches.

[![]({{ site.baseurl }}/assets/057eb-stream_transport.jpg?w=300)](https://changliao.files.wordpress.com/2017/02/057eb-stream_transport.jpg)

In order to estimate DOC transport in each stream reach, we need an accurate estimate of stream flow and associated DOC concentration. Three or four type of flow play a role in this process.

1. Over land surface runoff
2. Soil zone inter flow
3. Open channel flow
4. Potential groundwater flow

These flow may have completely different type of proprieties including flow rate and travel time.&nbsp;

And the spatial resolution also plays an important role since all time related processes must be linked to grid size.

