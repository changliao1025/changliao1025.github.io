---
layout: post
title: 'Integrated groundwater and surface water modeling: restore the stream index
  relationship'
date: 2015-10-07 16:06:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- Arc Hydro
- ArcMap
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
permalink: "/2015/10/07/integrated-groundwater-and-surface-water-modeling-restore-the-stream-index-relationship/"
---
Numerical hydrology models usually require the stream index to be built prior to the actual simulation.  
It is also good practice to keep them in order so it is much easier to analyse the results.

Here I have provided an examples how it could be done using some scripts and [ArcMap](http://www.esri.com/software/arcgis).  
After the drainage line is defined from watershed delineation process such as using [Arc Hydro tool](http://resources.arcgis.com/en/communities/hydro/01vn0000000s000000.htm).  
The resulting attribute table will be like this:

[![]({{ site.baseurl }}/assets/40b19-drainageline.png?w=296)](https://changliao.files.wordpress.com/2015/10/40b19-drainageline.png)

First, it is good practice to make a copy of the file. Then we need to "[Delete](http://help.arcgis.com/EN/arcgisdesktop/10.0/help/index.html#//00170000004n000000)" unwanted fields and only keep the HydroID, GridID and NextdownID fields.

Then export the attribute table into a text file and run the IDL routine "restore\_drainageline\_spatial\_relationship", which will produce a new index for each stream segment.

You can copy the created text file content into the Microsoft Excel for next step.

Then edit the drainage shapefile feature and replace the HydroID and NextdownID fields using the just copied indices in the Excel.

After this, the spatial relationship is restored but not sorted in the attribute table. We can use the "[Sort](http://help.arcgis.com/EN/arcgisdesktop/10.0/help/index.html#//001700000057000000)" tool is sort them using HydroID field.&nbsp;

[![]({{ site.baseurl }}/assets/d7525-field_sort.png?w=300)](https://changliao.files.wordpress.com/2015/10/d7525-field_sort.png)

The final attribute table will be like this:

[![]({{ site.baseurl }}/assets/55b7a-sort_table.png?w=223)](https://changliao.files.wordpress.com/2015/10/55b7a-sort_table.png)

Well done! This attribute table is ready for other operations.

Please leave a comment if you have questions!  
Thank you!

