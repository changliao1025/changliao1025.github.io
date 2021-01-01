---
layout: post
title: 'Battle 30: Naming system'
date: '2020-06-30T12:28:00.001-07:00'
author: Chang Liao
tags:
- ELM
modified_time: '2020-06-30T12:28:18.776-07:00'
blogger_id: tag:blogger.com,1999:blog-3189999653395802666.post-3259267161008689176
blogger_orig_url: https://codedoesnotlie.blogspot.com/2020/06/battle-30-naming-system.html
---

A typicl ELM history file variable has the following structure:<div><span 
style="background-color: white; color: #f97583; font-family: -apple-system, 
system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira 
Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; 
font-size: 14px;"> 
<span style="background-color: white; color: #f97583; font-family: 
-apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, 
&quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, 
sans-serif; font-size: 14px;">if<span style="background-color: white; color: 
#172b4d; font-family: -apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, 
Oxygen, Ubuntu, &quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica 
Neue&quot;, sans-serif; font-size: 14px;"> (use_cn) <span 
style="background-color: white; color: #f97583; font-family: -apple-system, 
system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira 
Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; 
font-size: 14px;">then<br style="background-color: white; color: #172b4d; 
font-family: -apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, 
Ubuntu, &quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica 
Neue&quot;, sans-serif; font-size: 14px;" /><span style="background-color: 
white; color: #172b4d; font-family: -apple-system, system-ui, &quot;Segoe 
UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira Sans&quot;, &quot;Droid 
Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; font-size: 14px;"><span>   
 this<span style="background-color: white; color: #f97583; font-family: 
-apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, 
&quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, 
sans-serif; font-size: 14px;">%<span style="background-color: white; color: 
#172b4d; font-family: -apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, 
Oxygen, Ubuntu, &quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica 
Neue&quot;, sans-serif; font-size: 14px;">qflx_evap_tot(begp:endp) <span 
style="background-color: white; color: #f97583; font-family: -apple-system, 
system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira 
Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; 
font-size: 14px;">=<span style="background-color: white; color: #172b4d; 
font-family: -apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, 
Ubuntu, &quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica 
Neue&quot;, sans-serif; font-size: 14px;"> spval<br style="background-color: 
white; color: #172b4d; font-family: -apple-system, system-ui, &quot;Segoe 
UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira Sans&quot;, &quot;Droid 
Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; font-size: 14px;" /><span 
style="background-color: white; color: #f97583; font-family: -apple-system, 
system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira 
Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; 
font-size: 14px;"><span>    <span> call<span style="background-color: white; 
color: #172b4d; font-family: -apple-system, system-ui, &quot;Segoe UI&quot;, 
Roboto, Oxygen, Ubuntu, &quot;Fira Sans&quot;, &quot;Droid Sans&quot;, 
&quot;Helvetica Neue&quot;, sans-serif; font-size: 14px;"> <span 
style="background-color: white; color: #b392f0; font-family: -apple-system, 
system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira 
Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; 
font-size: 14px;">hist_addfld1d<span style="background-color: white; color: 
#172b4d; font-family: -apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, 
Oxygen, Ubuntu, &quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica 
Neue&quot;, sans-serif; font-size: 14px;"> (<span style="background-color: 
white; color: #ffab70; font-family: -apple-system, system-ui, &quot;Segoe 
UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira Sans&quot;, &quot;Droid 
Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; font-size: 
14px;">fname<span style="background-color: white; color: #f97583; font-family: 
-apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, 
&quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, 
sans-serif; font-size: 14px;">=<span style="background-color: white; color: 
#9ecbff; font-family: -apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, 
Oxygen, Ubuntu, &quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica 
Neue&quot;, sans-serif; font-size: 14px;">'QFLX_EVAP_TOT'<span 
style="background-color: white; color: #172b4d; font-family: -apple-system, 
system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira 
Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; 
font-size: 14px;">,<span style="background-color: white; color: #ffab70; 
font-family: -apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, 
Ubuntu, &quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica 
Neue&quot;, sans-serif; font-size: 14px;"> units<span style="background-color: 
white; color: #f97583; font-family: -apple-system, system-ui, &quot;Segoe 
UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira Sans&quot;, &quot;Droid 
Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; font-size: 14px;">=<span 
style="background-color: white; color: #9ecbff; font-family: -apple-system, 
system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira 
Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; 
font-size: 14px;">'mm H2O/s'<span style="background-color: white; color: 
#172b4d; font-family: -apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, 
Oxygen, Ubuntu, &quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica 
Neue&quot;, sans-serif; font-size: 14px;">, &amp;<br style="background-color: 
white; color: #172b4d; font-family: -apple-system, system-ui, &quot;Segoe 
UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira Sans&quot;, &quot;Droid 
Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; font-size: 14px;" /><span 
style="background-color: white; color: #ffab70; font-family: -apple-system, 
system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira 
Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; 
font-size: 14px;"><span>    <span>    avgflag<span style="background-color: 
white; color: #f97583; font-family: -apple-system, system-ui, &quot;Segoe 
UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira Sans&quot;, &quot;Droid 
Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; font-size: 14px;">=<span 
style="background-color: white; color: #9ecbff; font-family: -apple-system, 
system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira 
Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; 
font-size: 14px;">'A'<span style="background-color: white; color: #172b4d; 
font-family: -apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, 
Ubuntu, &quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica 
Neue&quot;, sans-serif; font-size: 14px;">,<span style="background-color: 
white; color: #ffab70; font-family: -apple-system, system-ui, &quot;Segoe 
UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira Sans&quot;, &quot;Droid 
Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; font-size: 14px;"> 
long_name<span style="background-color: white; color: #f97583; font-family: 
-apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, 
&quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, 
sans-serif; font-size: 14px;">=<span style="background-color: white; color: 
#9ecbff; font-family: -apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, 
Oxygen, Ubuntu, &quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica 
Neue&quot;, sans-serif; font-size: 14px;">'qflx_evap_soi + qflx_evap_can + 
qflx_tran_veg'<span style="background-color: white; color: #172b4d; 
font-family: -apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, 
Ubuntu, &quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica 
Neue&quot;, sans-serif; font-size: 14px;">, &amp;<br style="background-color: 
white; color: #172b4d; font-family: -apple-system, system-ui, &quot;Segoe 
UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira Sans&quot;, &quot;Droid 
Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; font-size: 14px;" /><span 
style="background-color: white; color: #ffab70; font-family: -apple-system, 
system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira 
Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; 
font-size: 14px;"><span>    <span>    ptr_patch<span style="background-color: 
white; color: #f97583; font-family: -apple-system, system-ui, &quot;Segoe 
UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira Sans&quot;, &quot;Droid 
Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; font-size: 14px;">=<span 
style="background-color: white; color: #172b4d; font-family: -apple-system, 
system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira 
Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; 
font-size: 14px;">this<span style="background-color: white; color: #f97583; 
font-family: -apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, 
Ubuntu, &quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica 
Neue&quot;, sans-serif; font-size: 14px;">%<span style="background-color: 
white; color: #172b4d; font-family: -apple-system, system-ui, &quot;Segoe 
UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira Sans&quot;, &quot;Droid 
Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; font-size: 
14px;">qflx_evap_tot,<span style="background-color: white; color: #ffab70; 
font-family: -apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, 
Ubuntu, &quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica 
Neue&quot;, sans-serif; font-size: 14px;"> default<span 
style="background-color: white; color: #f97583; font-family: -apple-system, 
system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira 
Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; 
font-size: 14px;">=<span style="background-color: white; color: #9ecbff; 
font-family: -apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, 
Ubuntu, &quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica 
Neue&quot;, sans-serif; font-size: 14px;">'inactive'<span 
style="background-color: white; color: #172b4d; font-family: -apple-system, 
system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira 
Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; 
font-size: 14px;">,<span style="background-color: white; color: #ffab70; 
font-family: -apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, 
Ubuntu, &quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica 
Neue&quot;, sans-serif; font-size: 14px;"> c2l_scale_type<span 
style="background-color: white; color: #f97583; font-family: -apple-system, 
system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira 
Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; 
font-size: 14px;">=<span style="background-color: white; color: #9ecbff; 
font-family: -apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, 
Ubuntu, &quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica 
Neue&quot;, sans-serif; font-size: 14px;">'urbanf'<span 
style="background-color: white; color: #172b4d; font-family: -apple-system, 
system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira 
Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; 
font-size: 14px;">)<br style="background-color: white; color: #172b4d; 
font-family: -apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, 
Ubuntu, &quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica 
Neue&quot;, sans-serif; font-size: 14px;" /><span style="background-color: 
white; color: #f97583; font-family: -apple-system, system-ui, &quot;Segoe 
UI&quot;, Roboto, Oxygen, Ubuntu, &quot;Fira Sans&quot;, &quot;Droid 
Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; font-size: 14px;">end 
if<div><span style="background-color: white; color: #f97583; font-family: 
-apple-system, system-ui, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, 
&quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, 
sans-serif; font-size: 14px;"> 
The question is: for a single variable, how do we control it in the 
post-process?<div> 
<div>A Netcdf file only have a unique field name, so it is natural to use the 
field name for post-process.<div> 