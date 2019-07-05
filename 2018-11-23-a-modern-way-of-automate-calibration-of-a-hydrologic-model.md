---
layout: post
title: A modern way of automate calibration of a hydrologic model
date: 2018-11-23 08:06:00.000000000 -08:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- Model Calibration
- PEST
- Python
- SWAT
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
permalink: "/2018/11/23/a-modern-way-of-automate-calibration-of-a-hydrologic-model/"
---
Calibration of hydrologic model can be tedious, that is why we spent great efforts to automate this process. And sometimes we need some tool that is universal, reusable, so that we don't have to re-invent the wheel again and again.

Today I want to introduce a very effective framework to conduct a hydrologic model calibration. I call it framework because you can apply this method to any model and use any of your preferred language in some steps.

Here is the framework:

Let me explain what is going on:

[![]({{ site.baseurl }}/assets/91dee-interface.png)](https://changliao.files.wordpress.com/2018/11/91dee-interface.png)

1. PEST generate new parameter file based on a simple template;
2. PEST call Python interface to start model simulation;
3. Python interface translates parameter file to model input files;
4. Python interface launches SWAT simulation;
5. Python interface extracts results; and
6. PEST analyzes result and updates parameters.

A few highlights here:
1. This is an example for a SWAT model, and you can change it to any model you are calibrating;
2. I used Python, but you can also use any other language such as C/C++ or even bash;
3. I used PEST, this is the only requirement you cannot find many good alternatives.
4. You can launch as many SWAT simulations as you want in parallel manner.

Here are some more details:

PEST is a model-independent parameter estimation package. You are welcome to check its user manual to obtain its mathematical background. One of the highlights is that it supports both local and global optimization.

PEST is very flexible when it interacts with model I/O, however, it is still not convenient enough. For example, if the model produces binary result instead of text-based, it won't work well.

If you only use PEST without the interface, you will have something like this:

[![]({{ site.baseurl }}/assets/424e7-interface_old.png)](https://changliao.files.wordpress.com/2018/11/424e7-interface_old.png)

The differences and difficulties are:

1. You will have to prepare 10-100 times more template files depending on the model complexity;
2. You will have to read the results directly using PEST in a much more complicated way;
3. You may have trouble with slave directory forwarding because no all model I/O are friendly designed.

That is why I introduced Python as an interface between model simulation and PEST. Python can be considered as an agent to prepare simulation and extract final results for PEST simulation. It can also speed up your final analysis if the optimization is finished!

If you have noticed, this method is also cross platform ready and it support parallel computing/calibration.

Let me know if you have any question.

