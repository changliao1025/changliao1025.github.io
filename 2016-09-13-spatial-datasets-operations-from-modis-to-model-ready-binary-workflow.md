---
layout: post
title: 'Spatial datasets operations: From MODIS to model ready binary workflow'
date: 2016-09-13 14:44:00.000000000 -07:00
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
permalink: "/2016/09/13/spatial-datasets-operations-from-modis-to-model-ready-binary-workflow/"
---
I have written a couple of articles regarding the potential issues during raster operations. Here I have put down some typical workflow for these operations.  
For study area smaller than one MODIS granule, following these steps:

The common method that will work for you:

1. Convert one HDF file to GeoTIFF using ArcMap, save this file as A.tif.
2. Convert all HDF files to GeoTIFF using IDL and A.tif, call routine "hdf2tiff". In this step, you should set all unwanted pixel to missing value, such as -9999.
3. Project one GeoTIFF A.tif to B.dat using ArcMap;
4. Project all GeoTIFF to ENVI files using B.dat, call routine "project48";
5. Define the missing value for all the ENVI files from step 4,&nbsp;call routine&nbsp;"define\_envi\_missing\_value";
6. Prepare the shapefile mask for the study area, C.shp using Arcmap, C should has the same projection as the target projection;
7. Extract all ENVI files using the C.shp shapefile , call routine "extract50".

_(Updated January 15 2017).&nbsp;_

_Since in some cases it is impossible to re-project a raster from one projection to another using common projection method, which mean the above step 4 is going to fail unless you use rigorous&nbsp;projection method.&nbsp;__At the same time, rigorous method takes a long time to run. Therefore, we recommend an extraction before projection ([more details](https://github.com/changliao1025/eslib/issues/2)). And the new steps are:_

1. Convert one HDF file to GeoTIFF using ArcMap, save this file as A.tif.
2. Convert all HDF files to GeoTIFF using IDL and A.tif, call routine "hdf2tiff". In this step, you should set all unwanted pixel to missing value, such as -9999.
3. Prepare a rectangle shapefile B.shp which covers your study domain using ArcMap. B.shp has the same spatial reference with A.tif;
4. Extract all the GeoTIFF&nbsp;files using the rectangle shapefile B.shp.
5. Define the missing value for all the ENVI files from step 4;
6. Extract the A.tif using B.shp and save it as C.dat;
7. Project C.dat to D.dat with the target spatial reference using ArcMap;
8. Project all ENVI files from step 4 using D.dat, call routine "project48";
9. Prepare the shapefile mask for the study area, E.shp, E should has the same projection as the target projection;
10. Extract all ENVI files from step 8 using the E.shp shapefile.

Good luck.

