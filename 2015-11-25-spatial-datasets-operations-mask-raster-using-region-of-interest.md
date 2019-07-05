---
layout: post
title: 'Spatial datasets operations: mask raster using region of interest'
date: 2015-11-25 01:01:00.000000000 -08:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- ArcMap
- ENVI
- Extract
- IDL
- ROI
- Shapefile
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
permalink: "/2015/11/25/spatial-datasets-operations-mask-raster-using-region-of-interest/"
---
Climate change related studies usually involve spatial datasets extraction from a larger domain.  
In this article, I will briefly discuss some potential issues and solutions.

In the most common scenario, we need to extract a raster file using a polygon based shapefile. And I will focus as an example.

In a typical desktop application such as [ArcMap](https://desktop.arcgis.com/en/desktop/)or [ENVI](http://www.exelisvis.com/ProductsServices/ENVIProducts/ENVI.aspx), this is usually done with a tool called [clip](http://resources.arcgis.com/en/help/main/10.1/index.html#//00170000009n000000)or [extract](http://resources.arcgis.com/EN/HELP/MAIN/10.1/index.html#//009z0000002n000000)using mask or [ROI](https://www.exelisvis.com/docs/regionofinteresttool.html).

Before any analysis can be done, it is the best practice to project all datasets into the same projection.

If you are lucky enough, you may find that the polygon you will use actually matches up with the raster grid perfectly. But it rarely happens unless you created the shapefile using "[fishnet](http://resources.arcgis.com/EN/HELP/MAIN/10.1/index.html#//00170000002q000000)" or other approaches.

What if luck is not with you? The algorithm within these tool usually will make the best estimate of the value based on the location. The nearest re-sample, but not limited to, will be used to calculate the value. But what about the output location of the new data. Since the output will also be a raster with the same resolution, it the best solution that the output raster can match up with input raster perfectly.

Another issue is the efficiency because we usually have more than one raster need to be extracted from. Apparently this could be done using programming. Since ArcGIS doesn't support quite well on Linux, it is very naturally we use IDL/ENVI to achieve the task. In ENVI, the concept of ROI is used to extract raster. However there is another issue, ROI and the input raster have a one to one relation, which means that you can't use one single ROI to extract all the raster. The good news is that we can dynamically create ROI from shapefile using APIs.

There are some articles online stating that you can open a shapefile directly and store it as the FID, which can be used as the mask. It is NOT going to work. Instead, you need to create a shapefile object and retrieve all the boundary locations, then you can get all the values needed.The last step will be save the data with spatial reference.

Some incomplete demo code using IDL is listed here:

1. _&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;_ &nbsp; &nbsp;;;Read shapefile
2. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;oshp = OBJ\_NEW('IDLffshape', shapefile\_in)
3. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;oshp -\> GetProperty, n\_entities = n\_ent, Attribute\_info = attr\_info, $
4. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; n\_attributes = n\_attr, Entity\_type = ent\_type
5. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;roi\_shp = LONARR(n\_ent)
6. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;FOR ishp = 0, n\_ent - 1 DO BEGIN
7. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; entitie = oshp -\> GetEntity(ishp)
8. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ;;Check polygon
9. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; IF entitie.SHAPE\_TYPE EQ 5 THEN BEGIN
10. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;record = \*(entitie.VERTICES)
11. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;;;Convert coordinates
12. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;ENVI\_CONVERT\_FILE\_COORDINATES, fid\_in, xmap, ymap, record[0, \*], record[1, \*]
13. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;;;Create ROI
14. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;roi\_shp[ishp] = ENVI\_CREATE\_ROI(ns = ns\_in, nl = nl\_in)
15. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;ENVI\_DEFINE\_ROI, roi\_shp[ishp], /polygon, xpts = REFORM(xmap), ypts = REFORM(ymap)
16. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;IF ishp EQ 0 THEN BEGIN
17. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ;;nearest sampling is used
18. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; xmin = ROUND(MIN(xMap))
19. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; yMin = ROUND(MIN(yMap))
20. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;ENDIF ELSE BEGIN
21. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ;;there should be only one polygon in most cases
22. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; RETURN
23. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;ENDELSE
24. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ENDIF
25. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; oshp -\> DestroyEntity, entitie
26. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;ENDFOR
27. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;;;apply the mask
28. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;ENVI\_MASK\_DOIT, AND\_OR = 1, /IN\_MEMORY, ROI\_IDS = roi\_shp, $
29. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;ns = ns\_in, nl = nl\_in, /inside, $
30. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;r\_fid = fid\_mask
31. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;;;define the output raster array
32. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;dims\_mask = [-1, xMin, (xMin + ncol - 1), yMin, (ymin + nrow - 1)]
33. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;m\_pos = [0]
34. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;;;subset the input raster and save it within the memory
35. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;filename\_out = year\_out + !slash + prefix\_out + year\_str + day\_str + envi\_extension
36. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;ENVI\_MASK\_APPLY\_DOIT, FID = fid\_in, POS = pos, DIMS = dims\_mask, $
37. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;M\_FID = fid\_mask, M\_POS = m\_pos, VALUE = missing\_value, /in\_memory, $
38. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;R\_FID = fid\_out
39. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;ENVI\_FILE\_QUERY, fid\_out, ns = ns\_out, nl = nl\_out, nb = nb\_out, bname = bname\_out, dims = dims\_out
40. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;data = ENVI\_GET\_DATA(fid = fid\_out, dims = dims\_out, pos = pos)
41. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;;;output with pre-defined spatial reference
42. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;ENVI\_WRITE\_ENVI\_FILE, FLOAT(data), map\_info = map\_info, out\_name = filename\_out, $
43. &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;nb = nb\_out, ns = ncol, nl = nrow, OUT\_DT = 4

Feel free to try it out and give me feedback.

