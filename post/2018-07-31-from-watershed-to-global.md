---
layout: post
title: From watershed to global
date: 2018-07-31 17:59:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- ECOGlobe
- GDAL
- GPU
- Hadoop
- HDF
- MPI
- NetCDF
- OpenMP
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
permalink: "/2018/07/31/from-watershed-to-global/"
---
Ever since I finished my 3D ecosystem simulation using the ECO3D model, I started to think about applying this model to a larger spatial domain such as global.

While there are several technical difficulties in doing so, there are also different combinations of solutions to resolve these issues. In this post I will list out major issues we will address:

- First, on a global scale, we need much more massive input data preparation. What's more, some traditional algorithm/method may not even work. For example, the watershed lineation process on global scale will not be used anymore. Instead, another river routing algorithm or dataset should be used.
- File I/O will becomes an issue. Global scale simulation will use parallel computing, which mean the file I/O must support parallel reading/writing. Whether file system will be ideal or other options remains unclear. For example, can we use database or Hadoop?
- Parallel computing with/without MPI/OpenMP. I am not sure of other options but running billion of instances on HPC requires parallel computing for sure. Maybe Hadoop or GPU could help.
- Global grid system must be updated. Can we have a uniform grid scheme for simulation? With spatial relationship established, interactions among grids can be easier considered.
- File storage. If data are not stored in database alike data server. A better storage approach will be used.

Because the ECO3D is finally released, my next research focus will be applying it to a large spatial domain. The following steps should be taken in sequence:

1. Add MPI capability to the ECO3D model. Currently it only uses OpenMP for a watershed scale. On a global scale, MPI is an inevitable path;
2. Develop the DGGS for the spatial discretization scheme;
3. Design a better storage system for file I/O.
4. Develop a GDAL-based raster/vector dataset tool, this tool will be used to speed up all geospatial dataset operations.

I am also looking forward to working with collaborators.

