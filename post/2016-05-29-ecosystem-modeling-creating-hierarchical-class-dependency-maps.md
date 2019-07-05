---
layout: post
title: 'Ecosystem modeling: creating hierarchical class dependency maps'
date: 2016-05-29 16:09:00.000000000 -07:00
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
permalink: "/2016/05/29/ecosystem-modeling-creating-hierarchical-class-dependency-maps/"
---
Having a visual class dependency map could significantly help you to better understand the structure of a complex ecosystem model. For example, a group in University of Tennessee published a web-based [structure tree](http://web.ornl.gov/~7xw/CLM_Overview.html) of the Community Land Model.

From the perspective of model development, a dependency map also increase your productivity and performance.

There are many approach to produce such a map. For example, if you are using Visual Studio IDE in Windows environment, you can try the built-in [Architecture](https://msdn.microsoft.com/en-us/library/dd409453.aspx)[](https://msdn.microsoft.com/en-us/library/dd409453.aspx)tool. And it will generate beautiful maps.

If you prefer to use open source alternatives, you can try [Doxygen](http://www.stack.nl/~dimitri/doxygen/). It may be already installed in many Linux distributions. You can also use the Window version.

Below is an example my current ecosystem model structure:

[![]({{ site.baseurl }}/assets/dc169-classecosystem __coll__ graph.png?w=300)](https://changliao.files.wordpress.com/2016/05/dc169-classecosystem __coll__ graph.png)

Doxygen also has lots of other features you can try out.

