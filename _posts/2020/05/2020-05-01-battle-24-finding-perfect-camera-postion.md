---
layout: post
title: 'Battle 24: Finding the perfect camera postion'
date: '2020-05-01T11:34:00.001-07:00'
author: Chang Liao
tags:
- Python
- VTK
- PyVista
- Visualization
- 3D
- Camera
modified_time: '2020-05-01T14:44:48.885-07:00'
blogger_id: tag:blogger.com,1999:blog-3189999653395802666.post-3094225625198397874
blogger_orig_url: https://codedoesnotlie.blogspot.com/2020/05/battle-24-finding-perfect-camera-postion.html
---

The question is how we can find a perfect camera position when plotting a 3D 
VTK object. 

The definition of camera position is nicely illustrated by this post: 

[https://stackoverflow.com/questions/30690348/make-camera-lookdirection-look-front-face/30691275#30691275](https://stackoverflow.com/questions/30690348/make-camera-lookdirection-look-front-face/30691275#30691275) 

So the question for us, how do we define it for a general dataset. 