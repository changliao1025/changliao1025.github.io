---
layout: post
title: Tips for ArcSWAT issue
date: 2019-02-28 19:53:00.000000000 -08:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- ArcGIS
- ArcSWAT
- SWAT
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
permalink: "/2019/02/28/tips-for-arcswat-issue/"
---
I have to use ArcSWAT to prepare some SWAT model simulation inputs. And the experience wasn't exactly good (maybe we need a different tool to do this the right way).

Below I listed a few issues I have encountered and potentially fixed:

- Failed to create raster dataset. This issue might be related to permission control on Windows.

Based on my experience, it is best to create the project under the root directory using the ArcSWAT interface. Do not create the directory outside using other method (WSL mkdir caused this error multiple times on my Windows 10).

[![]({{ site.baseurl }}/assets/baf57-watershed_error.png?w=300)](https://changliao.files.wordpress.com/2019/02/baf57-watershed_error.png)

- Object reference not set. This issue is often related to the above issue. If the DEM was successfully, you should not receive this error.

[![]({{ site.baseurl }}/assets/98d72-arcmaperror001.png?w=300)](https://changliao.files.wordpress.com/2019/02/98d72-arcmaperror001.png)

- SWAT check error: SWAT check version may not be compatiable with the latest SWAT version. For example, check this discussion: [https://groups.google.com/forum/#!topic/swatuser/aSsSeJVIrvU](https://groups.google.com/forum/#!topic/swatuser/aSsSeJVIrvU)

I will keep adding related issues until the project is finished.

