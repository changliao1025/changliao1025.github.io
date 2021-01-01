---
layout: post
title: 'Battle 25: VTK visualization'
date: '2020-05-07T09:34:00.001-07:00'
author: Chang Liao
tags:
- E3SM
- VTK
- Visualization
- 3D
modified_time: '2020-05-07T10:08:26.519-07:00'
thumbnail: https://1.bp.blogspot.com/-QgAynVphoAQ/XrRAa8OtU-I/AAAAAAAA9dc/4PJQeAQNbV8HQjt6IXEidEVYG1nRsAYSwCK4BGAsYHg/s72-c/row-major-3D.png
blogger_id: tag:blogger.com,1999:blog-3189999653395802666.post-7404369665452647672
blogger_orig_url: https://codedoesnotlie.blogspot.com/2020/05/battle-25-vtk-visualization.html
---

In my recent posts, I discussed how to generate 3D plots using MayaVi and 
PyVista, both of them works but not as great as I expected.<div><ul 
style="text-align: left;">1. MayaVi has issue with rendering using OpenCL 
1. PyVista does not expose enough APIs to control the plot 
<div>So these are great tools to start with, but later on I decided to switch 
back to raw VTK.<div>I used another package called PyeVTK 
([https://github.com/paulo-herrera/PyEVTK](https://github.com/paulo-herrera/PyEVTK)), 
it basically help you to export data into the VTK format.<div> 
<div>As we know, VTK supports the legacy (text-based) and new (xml-based) 
format.<div>In earlier days, I already developed two models to export data to 
the legacy format. <div>One of them is in my Git: 
[https://github.com/changliao1025/modelview](https://github.com/changliao1025/modelview)<div> 
<div>This time I decided to use the package which uses XML.<div>It is 
straightforward to follow the example. You need to be careful with the data 
section still because of the memory alignment with 3D datasets.<div 
class="separator" style="clear: both; text-align: center;">[<img border="0" 
data-original-height="390" data-original-width="799" 
src="https://1.bp.blogspot.com/-QgAynVphoAQ/XrRAa8OtU-I/AAAAAAAA9dc/4PJQeAQNbV8HQjt6IXEidEVYG1nRsAYSwCK4BGAsYHg/s320/row-major-3D.png" 
width="320" 
/>](https://1.bp.blogspot.com/-QgAynVphoAQ/XrRAa8OtU-I/AAAAAAAA9dc/4PJQeAQNbV8HQjt6IXEidEVYG1nRsAYSwCK4BGAsYHg/row-major-3D.png)<div> 
<div>After that, I was able to produce some results:<div class="separator" 
style="clear: both; text-align: center;">[<img border="0" 
data-original-height="574" data-original-width="718" 
src="https://1.bp.blogspot.com/-V29eHga4sDQ/XrQ38UQKQMI/AAAAAAAA9c8/gGFQw-WLdMYb-zUhorVxHuDbo6Sj_UFiwCK4BGAsYHg/s320/artifact.png" 
width="320" 
/>](https://1.bp.blogspot.com/-V29eHga4sDQ/XrQ38UQKQMI/AAAAAAAA9c8/gGFQw-WLdMYb-zUhorVxHuDbo6Sj_UFiwCK4BGAsYHg/artifact.png)<div> 
<div> 
<div> 
<div>However, there is some issue with Visit or ParaView, if the mesh cell are 
too close, there might be an artifact with the rendering. So I increased the 
distance slightly and the new results look great.<div> 
<div style="text-align: center;"><img border="0" data-original-height="940" 
data-original-width="1064" 
src="https://1.bp.blogspot.com/-ACiegQ6sH9w/XrQ3gUU8snI/AAAAAAAA9co/4TcX0dWkk_QvPx_km-IPyBA_vozlPqMmQCK4BGAsYHg/s320/wtd_vtk.png" 
width="320" /><div style="text-align: left;">With that, the python package I 
developed for E3SM can fully support VTK now.<div style="text-align: center;"> 