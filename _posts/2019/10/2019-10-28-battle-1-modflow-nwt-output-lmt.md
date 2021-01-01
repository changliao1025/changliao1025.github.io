---
layout: post
title: 'Battle 1: MODFLOW-NWT output LMT'
date: '2019-10-28T22:53:00.001-07:00'
author: Chang Liao
tags:
- Fortran
- MODFLOW
- MT3D
modified_time: '2019-10-29T12:09:13.248-07:00'
blogger_id: tag:blogger.com,1999:blog-3189999653395802666.post-2516559152926366080
blogger_orig_url: https://codedoesnotlie.blogspot.com/2019/10/battle-1-modflow-nwt-output-lmt.html
---

While I was trying to run the MT3D, I received an error: 
<span style="color: red;">Error Reading Flow-Transport Link File Possibly 
Caused by: 
 1. Incompatible Styles of Unformatted Files Used by MODFLOW and MT3D-USGS, 
ensure usage 
 of FREE in MT3D-USGS name file matches LMT; 
 2. Unformatted Flow-Transport Link File Saved by Version 1 of LinkMT3D 
    Package Which Is No Longer Supported by MT3D-USGS. 
<div><span style="color: red;"> 
<div>Based on some initial 
investigations:<div>https://water.usgs.gov/nrp/gwsoftware/ModelMuse/Help/index.html?lmt6.htm"**Unformatted** 
– the flow-transport link file is saved as an unformatted (binary) file, 
compatible with all versions of MT3D and MT3DMS." 
<div> 
<div>So I have to convert the input to unformatted.<div><div>However, doing so 
will yield another error.<div>This error is basically caused by the undefined 
variable "FORM" in the source code file lmt8_nwt.f:<div><div style="color: 
#d4d4d4; font-family: Menlo, Monaco, &quot;Courier New&quot;, monospace; 
font-size: 12px; white-space: pre;"><span style="color: 
#c586c0;">IF(ILMTFMT<span style="color: #569cd6;">.EQ.<span style="color: 
#b5cea8;">0) <span style="color: #c586c0;">THEN<div style="font-family: Menlo, 
Monaco, &quot;Courier New&quot;, monospace; font-size: 12px; white-space: 
pre;"><span style="color: #d4d4d4;"><span style="color: #b5cea8;">          
<span style="color: #c586c0;">OPEN(IUMT3D,<span style="color: 
#9cdcfe;">FILE=FNAME,<span style="color: #9cdcfe;">FORM=<span style="color: 
red;">**FORM**<span style="color: #d4d4d4;">,<span style="color: 
#9cdcfe;">ACCESS<span style="color: #d4d4d4;">=ACCESS,<div style="color: 
#d4d4d4; font-family: Menlo, Monaco, &quot;Courier New&quot;, monospace; 
font-size: 12px; white-space: pre;"><span style="color: #569cd6;">     
&amp;<span style="color: #9cdcfe;">      ACTION=ACTION(<span style="color: 
#b5cea8;">2),<span style="color: #9cdcfe;">STATUS=<span style="color: 
#ce9178;">'REPLACE')<div style="color: #d4d4d4; font-family: Menlo, Monaco, 
&quot;Courier New&quot;, monospace; font-size: 12px; white-space: pre;"><span 
style="color: #b5cea8;">        <span style="color: 
#c586c0;">ELSEIF(ILMTFMT<span style="color: #569cd6;">.EQ.<span style="color: 
#b5cea8;">1) <span style="color: #c586c0;">THEN<div style="color: #d4d4d4; 
font-family: Menlo, Monaco, &quot;Courier New&quot;, monospace; font-size: 
12px; white-space: pre;"><span style="color: #b5cea8;">          <span 
style="color: #c586c0;">OPEN(IUMT3D,<span style="color: 
#9cdcfe;">FILE=FNAME,<span style="color: #9cdcfe;">FORM=<span style="color: 
#ce9178;">'FORMATTED',<span style="color: #9cdcfe;">ACTION=ACTION(<span 
style="color: #b5cea8;">2),<div style="color: #d4d4d4; font-family: Menlo, 
Monaco, &quot;Courier New&quot;, monospace; font-size: 12px; white-space: 
pre;"><span style="color: #569cd6;">     &amp;<span style="color: #9cdcfe;">   
   STATUS=<span style="color: #ce9178;">'REPLACE',<span style="color: 
#9cdcfe;">DELIM=<span style="color: #ce9178;">'APOSTROPHE')<div style="color: 
#d4d4d4; font-family: Menlo, Monaco, &quot;Courier New&quot;, monospace; 
font-size: 12px; white-space: pre;"><span style="color: #c586c0;">ENDIF<span 
style="color: black; font-family: &quot;times&quot;; font-size: small; 
white-space: normal;"> Another quick investigation: 
<div>https://docs.oracle.com/cd/E19957-01/805-4939/6j4m0vnaf/index.html<div>We 
can replaced the FORM to "UNFORMATTED".<div> 
<div>Rebuild the program and the simulation is running again!<div> 
<div>Later on it turned out I need to set the LMT to free format in MT3D and 
MODFLOW should still use FORMATTED. 