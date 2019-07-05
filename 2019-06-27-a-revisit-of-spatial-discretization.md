---
layout: post
title: A revisit of spatial discretization
date: 2019-06-27 21:16:50.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- Spatial Discretization
meta:
  _oembed_3eb37867f9a41e376250ffa39b6dcb6f: "{{unknown}}"
  _oembed_b7ffb4eff8081dac580c7c588bc9f50a: "{{unknown}}"
  _oembed_b02aff7d55726cb2edacfda4e45d20ae: "{{unknown}}"
  _publicize_job_id: '32259748665'
  timeline_notification: '1561670213'
  _oembed_e1f12b687856f1dde08045451c7e03bb: "{{unknown}}"
  _wp_old_slug: an-revisit-of-spatial-discretization
author:
  login: changliao
  email: changliao1025@outlook.com
  display_name: Chang Liao
  first_name: ''
  last_name: ''
permalink: "/2019/06/27/a-revisit-of-spatial-discretization/"
---
<!-- wp:paragraph -->

Discretization by definition from [Wikipedia](https://en.wikipedia.org/wiki/Discretization): In&nbsp;[applied mathematics](https://en.wikipedia.org/wiki/Applied_mathematics),&nbsp; **discretization** &nbsp;is the process of transferring&nbsp;[continuous](https://en.wikipedia.org/wiki/Continuous_function)&nbsp;functions, models, variables, and equations into&nbsp;[discrete](https://en.wiktionary.org/wiki/discrete)&nbsp;counterparts. This process is usually carried out as a first step toward making them suitable for numerical evaluation and implementation on digital computers.

<!-- /wp:paragraph -->

<!-- wp:paragraph -->

Now we add "spatial" to the term. The first intuitive definition is the **discretization** of functions in the spatial domain.

<!-- /wp:paragraph -->

<!-- wp:paragraph -->

There are two elements in this description: functions and spatial domain.

<!-- /wp:paragraph -->

<!-- wp:paragraph -->

For functions, we often refer to integral or ODEs/PDEs in numerical simulations. If these functions involve with gradient information, then they depend on spatial domain, which is how gradient is calculated.

<!-- /wp:paragraph -->

<!-- wp:paragraph -->

For spatial domain, we often refer to mesh or grid. And mesh can generally be classified into structured and unstructured grid.

<!-- /wp:paragraph -->

<!-- wp:paragraph -->

In practice, we have spent great effects on both aspects of the spatial discretization: mesh and corresponding function solvers.

<!-- /wp:paragraph -->

<!-- wp:paragraph -->

In Earth science, lots of functions involve with gradient. For example, gas exchange depends on pressure gradient or concentration gradient. As a result, Our spatial discretization is always associated with mesh grid.

<!-- /wp:paragraph -->

<!-- wp:paragraph -->

Many studies have developed methods to solve equations using the finite difference method (FDM), the finite volume method (FVM) and the finite element method (FEM). However, many of them have not considered the effects of mesh grid on these solvers. For example, most models use array to represent spatial domain. In this case, water flow at any location can only flow to 4 directions. However, in reality, water can flow to any direction because Earth has no discretization. The problem is how can we represent a direction if it is 30 degree?

<!-- /wp:paragraph -->

<!-- wp:paragraph -->

We need a better way to represent the spatial domain decomposition. We can improve the resolution. We can also use unstructured grid such as TIN. Ideally, we need a mesh that matches with reality. In my opinion, adaptive hexagon grid mesh is closest.

<!-- /wp:paragraph -->

<!-- wp:list -->

- It can cover the sphere. 
- It proves consistent connectivity. 
- It provides less assumption. 
- It also provide 6 flow directions.

<!-- /wp:list -->

<!-- wp:paragraph -->

Without a solid mesh grid, the simulation which relies on mesh may contain great uncertainty. And these uncertainty may be even larger than the uncertainty caused by FDM/FVM/FEM and algorithms.

<!-- /wp:paragraph -->

<!-- wp:paragraph -->

http://www.thermopedia.com/content/9172/

<!-- /wp:paragraph -->

