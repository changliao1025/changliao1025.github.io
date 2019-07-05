---
layout: post
title: 'Spatial datasets operations: When the sky is failing'
date: 2016-09-13 20:53:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- ArcMap
- ArcObject
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
permalink: "/2016/09/13/spatial-datasets-operations-when-the-sky-is-failing/"
---
Not all raster can be re-projected to another projection, at least some tools don't allow us to.

For example, the AMSR-E/Aqua L3 Global Snow Water Equivalent EASE-Grids cannot be directly re-projected to UTM-6N within ENVI 5.1.  
[https://nsidc.org/data/docs/daac/ae\_swe\_ease-grids.gd.html](https://nsidc.org/data/docs/daac/ae_swe_ease-grids.gd.html)  
Please refer this website for projection information.

[![]({{ site.baseurl }}/assets/b7858-01.png?w=300)](https://changliao.files.wordpress.com/2016/09/b7858-01.png)

[![]({{ site.baseurl }}/assets/9e78e-02.png?w=300)](https://changliao.files.wordpress.com/2016/09/9e78e-02.png)

&nbsp;Fortunately, ArcMap can do a better job in this scenario.  
You can use the project tool just like any other operations.

In order to re-project lot of data using ArcObject, I have updated a ArcTool, which is basically a batch mode data operation toolkit. For this task, the screenshot is as follow:

[![]({{ site.baseurl }}/assets/b6d8e-03.png?w=300)](https://changliao.files.wordpress.com/2016/09/b6d8e-03.png)

Below is the result:

[![]({{ site.baseurl }}/assets/0f589-04.png?w=300)](https://changliao.files.wordpress.com/2016/09/0f589-04.png)

Beneath the hook is the GP tool, some sample scripts are as follow:

///================================================

public static object ProjectRaster(string sFileIn, string sFileOut, string sNewProject, double dCellSize)

&nbsp; &nbsp; &nbsp; &nbsp; {

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ESRI.ArcGIS.Geoprocessor.Geoprocessor gp = new ESRI.ArcGIS.Geoprocessor.Geoprocessor();

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ///========================================

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ///disable the pyramid&nbsp;

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ///========================================

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; gp.ResetEnvironments(); &nbsp; &nbsp; &nbsp;

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; gp.SetEnvironmentValue("Pyramid", "NONE"); &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; gp.OverwriteOutput = true;

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ///=================================

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ProjectRaster pProjectRaster = new ProjectRaster(sFileIn, sFileOut, sNewProject);

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; pProjectRaster.cell\_size = dCellSize;

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ///pProjectRaster.resampling\_type = "BILINEAR";

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; pProjectRaster.resampling\_type = "NEAREST";

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; return gp.Execute(pProjectRaster, null);

&nbsp; &nbsp; &nbsp; &nbsp; }

///=================================================

Remember that sometimes the environment setting can be messy, so you can always setup them explicitly following (even though the ESRI document itself is a mess):

[http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html?TopicName=Pyramid#/Pyramid/001w0000001w000000/](http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html?TopicName=Pyramid#/Pyramid/001w0000001w000000/)

One may ask, why would you re-project such a raster to the other projection which is not supported in ENVI?

There are other methods, maybe better ones to achieve this task. And this is just a demonstration of how to make use of the GP tool in ArcObject when ENVI/IDL fails.
