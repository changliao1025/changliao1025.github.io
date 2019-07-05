---
layout: post
title: 'Parameter estimation: data format in model I/O'
date: 2015-10-27 17:28:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- IDL
- MODFLOW
- PEST
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
permalink: "/2015/10/27/parameter-estimation-data-format-in-model-i-o/"
---
Parameter estimation, also referred as model calibration, usually involves with model simulations with different sets of data and parameters.

A common practice is to replace the parameter within model inputs with different values and calculate the minimum objective function, which is used in [PEST](http://www.pesthomepage.org/).

Most of the time, parameter estimation can be very computational. Therefore, a better data format can reduce I/O burden and improve the efficiency.

A typical example is as follows:

To calibrate the groundwater modeling such as MODFLOW, a few template files much be prepared for PEST package. Since PEST requires that all ASCII file must NOT exceed 2000 in width. This means that all the template files must be written with care.  
For simulations with large spatial domains, the input files are usually large as well. And it is very important to keep the data format well designed that the accuracy and efficiency could be compromised.

On the other hand, PEST also reads the output from model simulation. It is also important to design an efficient format for the instruction file.

Further analysis of these types of data requires other scripts for I/O, especially when encountered with binary data.

So, the general guidelines would as follows:

1. Use special characters (white space) to separate individual data values whenever possible for inputs;
2. Use fixed format for model output;
3. Use exponent scientific format when values are large or small;
4. Avoid unnecessary space when possible;
5. Use advanced format such as binary if possible.

I will provide a real-life format example for MODFLOW simulation later.

Comments are welcome.
