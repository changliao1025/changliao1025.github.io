---
layout: post
title: 'Battle 16: IDL tiff issue'
date: '2020-02-17T22:29:00.003-08:00'
author: Chang Liao
tags:
- GeoTiff
- IDL
modified_time: '2020-02-17T22:29:39.881-08:00'
blogger_id: tag:blogger.com,1999:blog-3189999653395802666.post-7102380262467013826
blogger_orig_url: https://codedoesnotlie.blogspot.com/2020/02/battle-16-idl-tiff-issue.html
---

ENVI function does not produce the GeoTiff by default. 
We need another function to convert it to GeoTiff. 
For example: 

<div style="line-height: 18px;"><div style="background-color: #1e1e1e; color: 
#d4d4d4; font-family: Menlo, Monaco, &quot;Courier New&quot;, monospace; 
font-size: 12px; white-space: pre;"><span style="color: 
#dcdcaa;">ENVI_MASK_APPLY_DOIT, /in_memory, DIMS = dims_mask, $<div 
style="background-color: #1e1e1e; color: #d4d4d4; font-family: Menlo, Monaco, 
&quot;Courier New&quot;, monospace; font-size: 12px; white-space: pre;">       
                          FID = fid_in, $<div style="background-color: 
#1e1e1e; color: #d4d4d4; font-family: Menlo, Monaco, &quot;Courier New&quot;, 
monospace; font-size: 12px; white-space: pre;">                                
 M_FID = fid_mask, M_POS = m_pos, $<div style="background-color: #1e1e1e; 
color: #d4d4d4; font-family: Menlo, Monaco, &quot;Courier New&quot;, 
monospace; font-size: 12px; white-space: pre;">                                
 POS = pos, $<div style="background-color: #1e1e1e; color: #d4d4d4; 
font-family: Menlo, Monaco, &quot;Courier New&quot;, monospace; font-size: 
12px; white-space: pre;">                                 R_FID = fid_out, 
$<div style="background-color: #1e1e1e; color: #d4d4d4; font-family: Menlo, 
Monaco, &quot;Courier New&quot;, monospace; font-size: 12px; white-space: 
pre;">                                 VALUE = missing_value 
<div style="background-color: #1e1e1e; color: #d4d4d4; font-family: Menlo, 
Monaco, &quot;Courier New&quot;, monospace; font-size: 12px; white-space: 
pre;"><span style="color: #dcdcaa;">ENVI_FILE_QUERY, fid_out, dims=dims<div 
style="background-color: #1e1e1e; color: #d4d4d4; font-family: Menlo, Monaco, 
&quot;Courier New&quot;, monospace; font-size: 12px; white-space: pre;"><span 
style="color: #dcdcaa;">ENVI_OUTPUT_TO_EXTERNAL_FORMAT, fid = fid_out 
,OUT_NAME = sFilename_out,$<div style="background-color: #1e1e1e; color: 
#d4d4d4; font-family: Menlo, Monaco, &quot;Courier New&quot;, monospace; 
font-size: 12px; white-space: pre;">              dims=dims<div 
style="background-color: #1e1e1e; color: #d4d4d4; font-family: Menlo, Monaco, 
&quot;Courier New&quot;, monospace; font-size: 12px; white-space: pre;"> 