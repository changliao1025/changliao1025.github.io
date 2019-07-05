---
layout: post
title: 'Spatial datasets operations: From MODIS HDF to Binary file'
date: 2016-09-12 21:49:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- ArcMap
- ENVI
- IDL
- MODIS
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
permalink: "/2016/09/12/spatial-datasets-operations-from-modis-hdf-to-binary-file/"
---
MODIS products are widely used in Earth Science, here I present some typical demos and tryouts to deal with MODIS datasets.

All the MODIS products datasets are distributed in HDF format.

To get familiar with HDF, you can go to:

[https://en.wikipedia.org/wiki/Hierarchical\_Data\_Format](https://en.wikipedia.org/wiki/Hierarchical_Data_Format)

or&nbsp;

[https://www.hdfgroup.org/HDF5/](https://www.hdfgroup.org/HDF5/)

MODIS land surface products usually have a different map projection than most of our projects.

Here are some information of this projection:

[http://modis-land.gsfc.nasa.gov/MODLAND\_grid.html](http://modis-land.gsfc.nasa.gov/MODLAND_grid.html)

Therefore, a re-project is needed to convert HDF datasets to our projects.

There are quite a few tools available to operate on HDF files, but most of them are not efficient enough. You have to repeat the same set of operations. Therefore, using IDL or ArcObject based script/program is desirable.

The first step is to extract the datasets from HDF, and we also need to define the projection as exactly the same with HDF. Below is a very simple way to do so. You can use ArcMap to open one single HDF file and output the datasets as TIFF or other raster datasets formats.

[![]({{ site.baseurl }}/assets/009eb-sce_arcmap.png?w=300)](https://changliao.files.wordpress.com/2016/09/009eb-sce_arcmap.png)

Fig 1. Convert result from HDF to GeoTIFF in ArcMap 10.1.

Unfortunately, ENVI doesn't support all the MODIS product quite well so far. And the map projection cannot be read after the conversion using ArcMap, see below.

[![]({{ site.baseurl }}/assets/5e1d4-sce_envi.png?w=300)](https://changliao.files.wordpress.com/2016/09/5e1d4-sce_envi.png)

Fig 2. File viewing in ENVI 5.1 of the same file.

Even though ENVI can directly open this file, this does not mean we can open the file using ENVI/IDL  
;;===================================================  
&nbsp; IF FILE\_TEST(filename\_in) EQ 1 THEN BEGIN  
&nbsp; &nbsp; &nbsp; &nbsp; PRINT, filename\_in &nbsp; &nbsp;   
&nbsp; &nbsp; &nbsp; &nbsp; ENVI\_OPEN\_FILE, filename\_in, r\_fid = r\_fid  
&nbsp; &nbsp; &nbsp; &nbsp; IF r\_fid NE -1 THEN BEGIN  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ENVI\_FILE\_QUERY, r\_fid, dims = dims, nb = nb  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; pos = LINDGEN(nb)  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; filename\_out = year\_out + !slash + prefix\_out + year\_str + day\_str + extension\_envi  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ENVI\_CONVERT\_FILE\_MAP\_PROJECTION, background = missing\_value, $  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; dims = dims, $  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; fid = r\_fid, $  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; grid = [10, 10], $  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; o\_pixel\_size = o\_pixel\_size, o\_proj = map\_info, out\_name = filename\_out, $  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; pos = pos, $  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; resampling = 0, $  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; warp\_method = 0  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ENVI\_FILE\_MNG, id = r\_fid, /remove  
&nbsp; &nbsp; &nbsp; &nbsp; ENDIF ELSE BEGIN  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; PRINT, 'Cannot open the file!'  
&nbsp; &nbsp; &nbsp; &nbsp; ENDELSE  
&nbsp; &nbsp; &nbsp; ENDIF  
;;==================================================

For the same file, above script will print "Cannot open the file!"

A workaround method is using the GeoTIFF instead of native ENVI dat file.  
You can pass either the geotag using a filename or a struct in the ENVI/IDL script.  
After this, you will get a binary dat file with a header file which contains the map projection information.

The bottom line is that you can prepare individual files (for parameters) using ArcMap and run ENVI/IDL scripts on HPC. In this case, you gain both flexibility and efficiency.

