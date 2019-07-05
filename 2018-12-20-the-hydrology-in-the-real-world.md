---
layout: post
title: The hydrology in the real world
date: 2018-12-20 19:35:00.000000000 -08:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- ESM
- Hydrological Modeling
- Hydrology
- Lake
- Stream
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
permalink: "/2018/12/20/the-hydrology-in-the-real-world/"
---
Below is a region of interest from Global Lakes and Wetlands Database ([link](https://www.worldwildlife.org/pages/global-lakes-and-wetlands-database)).

[![]({{ site.baseurl }}/assets/70092-lake_stream.png?w=300)](https://changliao.files.wordpress.com/2018/12/70092-lake_stream.png)

My question is how can we represent them in the Earth System Model?

To understand the challenge, we need to know how hydrology features are represented in current modeling work.

In an ideal scenario when there is no lake, stream network are the dominant hydrology features.

To date, most existing hydrology simulations are conducted at relatively large spatial domain. As a result, the spatial resolution of such simulation is limited to hundred to thousand of meters. Sometimes it is impossible to capture some features under this resolution.

On the other hand, the land is never homogeneous and lots of local depressions are visible. These local depressions are removed in most hydrological model.

When there are lakes, the situation gets complicated. There are several challenges we will face:

1. A lake may changed its boundary depending on water storage;
2. A lake may or may not have an outlet;
3. A lake itself is a local depression, so should we remove it or not?

I will provide more details in the near future how we can consider lake in a Earth System Model.

