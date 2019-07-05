---
layout: post
title: 'Integrated groundwater and surface water modeling: the appropriate way to
  prepare the best DEM'
date: 2016-01-25 20:46:00.000000000 -08:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- Arc Hydro
- ArcMap
- DEM
- SAGA
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
permalink: "/2016/01/25/integrated-groundwater-and-surface-water-modeling-the-appropriate-way-to-prepare-the-best-dem/"
---
One the most important inputs for groundwater and surface water hydrology modeling is the [Digital Elevation Model](https://en.wikipedia.org/wiki/Digital_elevation_model) (DEM).

Though DEM can be obtained through many approaches, the final DEM varies significantly. Therefore, DEM&nbsp;can&nbsp;seldom &nbsp;be directly used in most modeling work. Instead, we often need to adjust the DEM so that it can meet the requirements of the hydrology modeling.

The adjustment, however, often involves series of operations. These operations can be carried out using different&nbsp;approaches&nbsp;in different orders. The result could be quite different. The important part is that most of them are unusable. So the question is, what is most promising way to prepare the DEM?

Here I have provided an example work flow, which may be suitable for most tasks. Then I will explain in details the purpose of this step and what tools we can make use of. In the end I will discuss why it should be done in this order.

1. Download the DEM datasets of the same format for the study area;
2. [Mosaic](http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html#//001700000097000000)these DEM datasets into one raster file;
3. [Resample](http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html#//00170000009t000000)the DEM if necessary;
4. [Project](http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html#//00170000007m000000)the DEM into required projection;
5. [Clip](http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html#//00170000009n000000)the DEM using &nbsp;a&nbsp;rectangle, whose&nbsp;spatial extent must cover the whole study area;&nbsp;
6. Download the stream datasets of the study area;
7. Process the stream datasets similar to DEM;
8. Burn the flow line into the DEM;
9. [Fill](http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html#//009z00000050000000.htm)the depression within the DEM;
10. Correct the DEM in flow line.

Explanations:
1. DEM datasets can be downloaded from [USGS NED](http://nationalmap.gov/elevation.html) in various formats and resolutions. Make sure the DEM datasets covers the spatial extent of the study area;
2. Depending on the spatial extent of the study area, it usually contains more than one DEM data file. Therefore, it is necessary to mosaic them into one file. This is because most GIS operations such as re-sample are sensitive to edge effects.&nbsp;
3. The resample operation could bring the DEM into desired spatial resolution. It is common to re-sample from high resolution to low resolution;
4. The DEM file is probably not in the desired projection under the study area.&nbsp;
5. Computational demand is something we try to avoid if possible. Therefore it is best to extract the DEM out from the larger file. However, we must keep the valuable information. So we can clip the DEM using a large rectangle.&nbsp;
6. Stream data are necessary to assist the [DEM reconditioning](http://www.ce.utexas.edu/prof/maidment/gishydro/ferdi/research/agree/agree.html);
7. The stream data also needs to prepared into the same spatial extent and projection;
8. Adjust the DEM so surface water can always flow into the streams. However, we don't want to change the DEM so much because the groundwater system also interacts with the stream.
9. Surface depression causes a lot of troubles for surface runoff. For most surface hydrology, they can be removed through the fill operation.
10. There might be still flaws within the DEM along the flow line, so we need to correct them separately.

Most of the GIS operations can be carried out within ArcGIS. However, other tools such as [ArcHydro](http://resources.arcgis.com/en/communities/hydro/01vn0000000s000000.htm), [SAGA](http://www.saga-gis.org/)are also very powerful.&nbsp;

Next, for most cases, these operations must be carried out in the above order. Step 3 and 4 can change order without too many differences. For DEM reconditioning, it is usually good practice to follow steps 8, 9 and 10 exactly. You will find that depressions still exist if you fill them in the first place since burn can change DEM. There is currently no tools can consider stream and depression at the same time. Double check the DEM afterwards is encouraged.

