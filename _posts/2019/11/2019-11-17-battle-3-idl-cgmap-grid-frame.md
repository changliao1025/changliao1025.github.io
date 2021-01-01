---
layout: post
title: 'Battle 3: IDL cgmap grid frame'
date: '2019-11-17T22:35:00.001-08:00'
author: Chang Liao
tags:
- QGIS
- IDLCoyote
- IDL
- Python
- GIS
- ArcGIS
modified_time: '2019-11-17T22:36:19.506-08:00'
thumbnail: https://1.bp.blogspot.com/-2pxooJ55bRc/XdI7ifW1vEI/AAAAAAAA5hA/gkwWF7YR8McYkdojD_mBewbynVwyl8MwwCLcBGAsYHQ/s72-c/dem.jpg
blogger_id: tag:blogger.com,1999:blog-3189999653395802666.post-5621882378293482355
blogger_orig_url: https://codedoesnotlie.blogspot.com/2019/11/battle-3-idl-cgmap-grid-frame.html
---

IDL is so far my go-to programming language in terms of map visualization. 

Recently, I picked up an old function I wrote years ago to use it in my 
current projects, but there was some issue with the 
[cgmap_grid](http://www.idlcoyote.com/idldoc/maps/cgmap_grid.html) map input: 

<style type="text/css">p.p1 {margin: 0.0px 0.0px 0.0px 0.0px; font: 11.0px 
Monaco; color: #408080} span.s1 {color: #000000} </style> 
<div class="p1">map = OBJ_NEW('cgMap', 'UTM', ELLIPSOID = 'GRS 1980', Zone = 
6, $<div class="p1"><span class="s1"><span class="Apple-converted-space">     
Position = position_map, XRANGE = XRANGE, yrange = yrange) 

Basically, when I first developed this function, I didn't use a generalized 
map structure. 
So the question how should I define a map structure for any raster file. 

I found a solution fast: 
[cggeomap](http://www.idlcoyote.com/idldoc/cg/cggeomap.html) 
<div class="p1">pMapCoord = <span 
class="s1">cgGeoMap(sFilename_geotiff,$<style type="text/css">p.p1 {margin: 
0.0px 0.0px 0.0px 0.0px; font: 11.0px Monaco} span.s1 {color: #00c0c0} 
</style> 
<div class="p1"><span class="Apple-converted-space">    geotiff = pGeotag)<div 
class="p1"> 
The source code is pretty simple and easy. However, it missed the position and 
ranges. So I tried to add them back and tested it.<div>I noticed that the grid 
does not has labels! Initially I thought maybe the increment is too large, so 
I set it to 0.01. It gave an error.<div> 
<div>At this point, as a developer, I started to debug. I followed the 
function inside and checked the boundary. What surprised me was that the range 
is -180 to 180! But my data is only a small watershed!<div class="p1"><span 
style="color: black; font-family: &quot;times&quot;; font-size: small;"> 
<div class="p1"><span style="color: #00c0c0;">cgGeoMap offers a keyword to 
display the data directly, so I gave a try. It works fine with the label. So 
what is the problem? 
<div> 
<div>I noticed the map structure changed within 
[cgmap_grid](http://www.idlcoyote.com/idldoc/maps/cgmap_grid.html), but I am 
not sure how. I was convinced that the boundary was wrong.<div> 
<div>At last, I suddenly realized that why don't I check the original code as 
I have modified a lot. I followed inside again and the boundary was -180 to 
180!<div>So it was not about the boundary.<div> 
<div>I got back to the <span style="color: #00c0c0; font-family: 
&quot;monaco&quot;; font-size: 11px;">cgGeoMap, and tested a few more 
increment and it worked.<div>So what is needed is:<div><style 
type="text/css">p.p1 {margin: 0.0px 0.0px 0.0px 0.0px; font: 11.0px Monaco} 
</style> 
<div class="p1">pMapCoord -&gt; SetProperty, Position=position_map<div>Below 
is the result converted from eps:<div class="separator" style="clear: both; 
text-align: center;">[<img border="0" data-original-height="1200" 
data-original-width="1500" height="512" 
src="https://1.bp.blogspot.com/-2pxooJ55bRc/XdI7ifW1vEI/AAAAAAAA5hA/gkwWF7YR8McYkdojD_mBewbynVwyl8MwwCLcBGAsYHQ/s640/dem.jpg" 
width="640" 
/>](https://1.bp.blogspot.com/-2pxooJ55bRc/XdI7ifW1vEI/AAAAAAAA5hA/gkwWF7YR8McYkdojD_mBewbynVwyl8MwwCLcBGAsYHQ/s1600/dem.jpg)<div> 
<div>Why I bother to use IDL instead of other tools like Python, 
ArcMap?<div>First, I don't have access to Windows often, and working with GUI 
is always a pain.<div>Second, Python does not have good package to support all 
map projection labels.<div> 