---
layout: post
title: 'Battle 22: scatter plot with kde using matplotlib'
date: '2020-04-16T10:47:00.002-07:00'
author: Chang Liao
tags:
- Scatterplot
- Python
- KDE
- SNS
- Matplotlib
modified_time: '2020-04-16T10:47:59.467-07:00'
thumbnail: https://1.bp.blogspot.com/-WiPcJwr78Ww/XpiYIoQOpHI/AAAAAAAA8uo/5FhDkcjmWYcrGg9bCvQ1yUmOpKjwxh1QQCLcBGAsYHQ/s72-c/sur_slp-zwt_scatterplot.png
blogger_id: tag:blogger.com,1999:blog-3189999653395802666.post-9002670781130601180
blogger_orig_url: https://codedoesnotlie.blogspot.com/2020/04/battle-22-scatter-plot-with-kde-using.html
---


<div class="separator" style="clear: both; text-align: left;">How to produce a 
scatter alike plot using Matplotlib without using SNS or other packages?<div 
class="separator" style="clear: both; text-align: center;">[<img border="0" 
data-original-height="1543" data-original-width="1600" height="385" 
src="https://1.bp.blogspot.com/-WiPcJwr78Ww/XpiYIoQOpHI/AAAAAAAA8uo/5FhDkcjmWYcrGg9bCvQ1yUmOpKjwxh1QQCLcBGAsYHQ/s400/sur_slp-zwt_scatterplot.png" 
width="400" 
/>](https://1.bp.blogspot.com/-WiPcJwr78Ww/XpiYIoQOpHI/AAAAAAAA8uo/5FhDkcjmWYcrGg9bCvQ1yUmOpKjwxh1QQCLcBGAsYHQ/s1600/sur_slp-zwt_scatterplot.png)<div 
class="separator" style="clear: both; text-align: left;">Here are several 
issues we need to consider and corresponding solutions (later):<div 
class="separator" style="clear: both; text-align: left;">1. Setup the axes 
(there are 3 ax object here) positions; 
1. Control the tick range and label; 
1. Fix the overlap at intersection origin; 
1. Choose a good color map for density plot; 
1. Choose the counter alike density plot; 
1. Setup KDE plot with shade; 
1. Hide KDE plot tick label; 
1. Set up KDE plot grid; 
1. Set up KDE plot tick intervals; 
1. Set up a vertical KDE plot; 
1. Compatibility between density plot and KDE plot tick intervals. 
<div>This plot is inspired by sns.jointplot and python-graph-gallery.com.<div> 
<div>Thank you. 
<span id="goog_399399436"><span id="goog_399399437"> 