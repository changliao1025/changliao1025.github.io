---
layout: post
title: 'Ecosystem modeling: model evaluation of current implementation in ECO3D 1.0'
date: 2017-04-06 03:02:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- DOC
- GIPL
- MODFLOW
- PRMS
- TEM
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
permalink: "/2017/04/06/ecosystem-modeling-model-evaluation-of-current-implementation-in-eco3d-1-0/"
---
As I am preparing my defense, the first version of ECOSYSTEM 1.0 in my thesis was finally completed. Looking forward to the next chapter of my life, I thought it is time to evaluate the ECOSYSTEM 1.0 to see what it is capable of and what still needs to be improved or expanded in the near future.

First, here is a brief introduction of the ECOSYSTEM model:  
ECOSYSTEM is a three-dimensional water and carbon cycle terrestrial ecosystem model. Within ECOSYSTEM model, water and carbon cycle are seamlessly coupled. The water cycle is developed based on the [PRMS](https://wwwbrr.cr.usgs.gov/projects/SW_MoWS/PRMS.html),&nbsp;and the carbon cycle is developed based on [TEM](http://ecosystems.mbl.edu/TEM/). The core idea behind the coupling is that both water and carbon (potentially nitrogen and others) fluxes can flow in a three-dimensional domain, and that is exactly one of the reasons why dissolved organic carbon (DOC) can be observed in stream water.

A lot of improvements have been made upon the original PRMS and TEM models. For example, I have added a new litter pool to consider the carbon pool, DOC leaching from the litter.

Even though model calibration of such kind of watershed hydrology-alike ecosystem model takes much effort, my initial model evaluation based on stream discharge, snow cover, GPP/NPP and DOC has shown that the three-dimensional approach have great potential. A good example could be something like the [Riparian zone](https://en.wikipedia.org/wiki/Riparian_zone). I am also observing significant differences in soil moisture due to lateral water flow.

The ECOSYSTEM model is completely developed using C++11 with OpenMP enabled. A preview of the model [structure](http://www.changliao.us/2016/05/ecosystem-modeling-000.html)was introduced in one of my early posts. One of the advantages of using C++ is that it's relatively easy to manage based on model structure, especially for models with sophisticated data I/O and flow.

Moreover, when I designed the ECOSYSTEM, a plugin approach/concept is used, which means that new processes can be easily added following the structure. This is also the same concept used in [MODFLOW](https://water.usgs.gov/ogw/modflow/)and PRMS.

With ECOSYSTEM, we can answer quite a few questions, including but not limited to:

1. How is surface hydrology responding to climate?
2. How is surface hydrology responding to land-use and land-cover change (e.g., wildfire)?
3. What is the role of lateral flow in soil moisture?
4. What is the role of lateral flow in carbon cycle?
5. What about DOC dynamics?

However, due to the time constrain, I haven't implemented some other important processes into the ECOSYSTEM model currently. And potentially I will keep working on this project and finish a newer version when time is right.

Here are a few processes that need to be added or improved in future development:

1. Groundwater flow is currently improved but not as good as MODFLOW, but it may be unnecessary to actually implement MODFLOW within ECOSYSTEM;
2. Soil water has different types of reservoirs, but the concept of layered model may improve vertical profile, which is also important for thermal process;
3. Soil thermal is currently simplified, it could be coupled with soil water using algorithm from TEM or other similar model such as [GIPL](http://permafrost.gi.alaska.edu/content/modeling);
4. Three-dimensional heat transport is missing, but with soil thermal (or even groundwater flow), it could be implemented;
5. Snow model currently does not consider heat from soil. A better layered snow model such as&nbsp;[Snowpack](https://www.openhub.net/p/snowpack)can replace the current one;
6. A dynamical stream network may be added, which means the hydrology networks vary with &nbsp;time;
7. Carbon and nitrogen coupling;
8. Thermokarst lake modeling is missing;
9. With thermal and soil carbon module, a new permafrost carbon release module could be implemented.

Hopefully, the last list will be shorted or even gone within one year.

