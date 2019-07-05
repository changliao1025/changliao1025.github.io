---
layout: post
title: Some thoughts on respiration and the role of microbe
date: 2018-04-16 02:34:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- Decomposition
- Heterotrophic Respiration
- Mineralization
- Soil Respiration
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
permalink: "/2018/04/16/some-thoughts-on-respiration-and-the-role-of-microbe/"
---
I was recently upgrading some components within the [**ECO3D**](http://www.eco3d.net/p/welcome.html)&nbsp;model, specifically the carbon pool and fluxes in vegetation, litter and soil.

The overall scheme of these components are illustrated in Figure 1:

[![]({{ site.baseurl }}/assets/69d04-carbon-pool.png?w=300)](https://changliao.files.wordpress.com/2018/04/69d04-carbon-pool.png)

Figure 1. The carbon pool and flux.

While it is well-known that the incoming carbon flux is mainly from photosynthesis process, which is also been well studied, the challenge is the outgoing carbon flux.

Without considering wildfire, etc., disturbance, " **respiration**" is generally considered the major pathway through which carbon is released back into the atmosphere. However, for individual site, horizontal carbon flux (DOC and DIC, etc.) is also important but it only services as a transport pathway.

In most terrestrial ecosystem modeling, respiration is broken into autotrophic respiration and heterotrophic respiration (Figure 2).

[![]({{ site.baseurl }}/assets/ed642-respiration.png?w=300)](https://changliao.files.wordpress.com/2018/04/ed642-respiration.png)

Figure 2. Respiration in terrestrial ecosystem.

Fundamentally, respiration is a biological and biochemical process occurs in cellular level. And it is assumed to convert organic component to energy, which the opposite process of photosynthesis.

In different fields, these processes are often labeled "soil respiration", "decomposition", "mineralization" and "immobilization", etc., which causes lots of confusion for researchers from different background.

Here I am trying to identify the major pathway and difference between these processes.

First, though respiration occurs at cellular level, we need to understand where these cells are located. For autotrophic respiration, which is usually consisted of maintenance respiration and growth respiration throughout the vegetation, it takes places within the vegetation canopy, stem and root. And the rate of respiration is controlled by the nutrient availability within vegetation and climate factors.

For heterotrophic respiration, it usually takes place within microbe, which uses this process to obtain energy. Along with this process, large organic carbon molecular maybe decomposed into small molecular and carbon dioxide/water will be produced. In another word, this respiration process is linked with decomposition process. In some cases, small inorganic carbon may be produced and the respiration is also coupled with the so called "mineralization".

As a result, heterotrophic respiration is always linked with decomposition and mineralization but they are not exchangeable because they all have different focus under different context. For example, when litter is decomposed in the early stage due to physical process such as heat, it is generally not considered as respiration or mineralization.&nbsp;

Because of its dependency of microbe activity on temperature, these processes are often modeled using a Q10 function. However, care must be taken to consider the board definition of decomposition and other factors. Other than that, when modeling these processes, we must make sure they share the same characteristics because they are possibly taking place within the same cellular level.

