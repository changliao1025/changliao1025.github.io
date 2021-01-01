---
layout: post
title: 'Battle 4: setting the right size for map plot '
date: '2019-12-19T11:49:00.000-08:00'
author: Chang Liao
tags:
- Mapping
- IDL
- Plotting
modified_time: '2019-12-19T13:42:07.368-08:00'
thumbnail: https://1.bp.blogspot.com/-ENVgaC09eP0/XefyGjQPPjI/AAAAAAAA5wE/9ld635BzLcg0GCTXpoIMZy_uARNNkDnpACLcBGAsYHQ/s72-c/dem.jpg
blogger_id: tag:blogger.com,1999:blog-3189999653395802666.post-5806970622190074727
blogger_orig_url: https://codedoesnotlie.blogspot.com/2019/12/battle-4-setting-right-size-for-map-plot.html
---

<div>How to control the size of text so they look pleasantly for readers?<div> 
<div>Here is a solution for map object:<div> 
charsize = cgdefcharsize() 
<div> 
main title: charsize  * 1.0 
cgmap_grid: charsize  * 0.7 
<div>longitude: charsize  * 0.6<div>latitude: charsize  * 0.6<div>colorbar 
title: charsize  * 0.7<div>colorbar label: charsize  * 0.8<div> 
<div>To illustrate:<div class="separator" style="clear: both; text-align: 
center;">[<img border="0" data-original-height="1600" 
data-original-width="1581" height="640" 
src="https://1.bp.blogspot.com/-ENVgaC09eP0/XefyGjQPPjI/AAAAAAAA5wE/9ld635BzLcg0GCTXpoIMZy_uARNNkDnpACLcBGAsYHQ/s640/dem.jpg" 
width="632" 
/>](https://1.bp.blogspot.com/-ENVgaC09eP0/XefyGjQPPjI/AAAAAAAA5wE/9ld635BzLcg0GCTXpoIMZy_uARNNkDnpACLcBGAsYHQ/s1600/dem.jpg)<div 
class="separator" style="clear: both; text-align: left;">Later I will provide 
other examples for other type of plots. <div> 