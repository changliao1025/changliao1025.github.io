---
layout: post
title: Publication graphic generation workflow
date: 2019-06-28 23:29:22.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- Figure
- IDL
- Inkscape
- PS
- Publication
- Python
meta:
  _publicize_job_id: '32296873354'
  timeline_notification: '1561764566'
author:
  login: changliao
  email: changliao1025@outlook.com
  display_name: Chang Liao
  first_name: ''
  last_name: ''
permalink: "/2019/06/28/publication-graphic-generation-workflow/"
---
<!-- wp:paragraph -->

Preparing graphics for journal publication is an important step before we submit the manuscript. And sometimes this process is not as smooth as we expected. There are several problems we often encounter:

<!-- /wp:paragraph -->

<!-- wp:list -->

- We generally generate more than enough figures and in the end, we only need a few;
- We also use different format for different purposes. For example, we use jpg/png for debugging. And we use svg/postscript for high quality production. A conversion is usually required.
- Journals usually prefer 600dpi high resolution figures. So postscript format might be the best option.
- Indexing is important for final upload.
- Subplot makes it even complicated.
- We use more than one tools as well. I use IDL/Python for plotting, but I also use GIMP/Snagit/Inkscape for some processes. Keep the process consistent is not easy.

<!-- /wp:list -->

<!-- wp:paragraph -->

So maybe we need a clear road map so we won't get lost easily. Here are my plans:

<!-- /wp:paragraph -->

<!-- wp:list -->

- Produce postscript/svg when possible using DrawIO/Python/IDL;
- If we need subplot, produce them simultaneously;
- Avoid using GIMP/Inkscape unless in the final step;
- Better file system management.

<!-- /wp:list -->

<!-- wp:paragraph -->

I might provide an example later.

<!-- /wp:paragraph -->

