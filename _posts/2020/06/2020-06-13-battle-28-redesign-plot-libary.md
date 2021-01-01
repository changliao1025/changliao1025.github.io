---
layout: post
title: 'Battle 28: redesign the plot libary'
date: '2020-06-13T14:56:00.001-07:00'
author: Chang Liao
tags:
- Python
- Software
- Matplotlib
modified_time: '2020-06-13T14:56:39.059-07:00'
thumbnail: https://1.bp.blogspot.com/-WXogke5-J3k/XuQGJox3-eI/AAAAAAAADYA/Ln1EJIaMLOQ5jH6EQKF9XRhXDbgZt8vmACK4BGAsYHg/s72-c/tsplot.png
blogger_id: tag:blogger.com,1999:blog-3189999653395802666.post-6423765435967231520
blogger_orig_url: https://codedoesnotlie.blogspot.com/2020/06/battle-28-redesign-plot-libary.html
---


<div class="separator" style="clear: both; text-align: left;">I have developed 
a Python library for various projects. This library has many different 
features including the plotting functions. But I am not satisfied with the 
current strategy/structure of some components. For example, I somehow wrote a 
list of functions for a similar purpose.<div class="separator" style="clear: 
both; text-align: left;">Now it is time to re-organize some functions.<div 
class="separator" style="clear: both; text-align: left;"> 
<div class="separator" style="clear: both; text-align: center;">[<img 
border="0" data-original-height="423" data-original-width="435" 
src="https://1.bp.blogspot.com/-WXogke5-J3k/XuQGJox3-eI/AAAAAAAADYA/Ln1EJIaMLOQ5jH6EQKF9XRhXDbgZt8vmACK4BGAsYHg/s320/tsplot.png" 
width="320" 
/>](https://1.bp.blogspot.com/-WXogke5-J3k/XuQGJox3-eI/AAAAAAAADYA/Ln1EJIaMLOQ5jH6EQKF9XRhXDbgZt8vmACK4BGAsYHg/s435/tsplot.png)<div 
class="separator" style="clear: both; text-align: center;"> 
<div class="separator" style="clear: both; text-align: center;"> 
<div class="separator" style="clear: both; text-align: left;">So there are 
several principles I will consider in the redesign:<div class="separator" 
style="clear: both; text-align: left;"><ol style="text-align: left;">1. I will 
not specify the temporal resolution, and it can be daily, monthly, or even 
hourly. This will be completely decided by the input datatime information. But 
user can specify the format using an optional argument; 
1. There is no need to separate single and multiple data plot. 
1. The zoom feature can be an individual function for now. Later on we can 
merge it at an optional feature. 
1. 3D plot needs additional simplification. 
<div> 
<div> 
<div class="separator" style="clear: both; text-align: left;"> 