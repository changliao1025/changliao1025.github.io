---
layout: post
title: 'Scientific writing: high quality scalable vector graphics'
date: 2017-01-18 03:20:00.000000000 -08:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- Google
- Postscript
- SVG
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
permalink: "/2017/01/18/scientific-writing-high-quality-scalable-vector-graphics/"
---
I recently found a new way to prepare publication-ready high quality vector graphic using Google Drive.  
Here is the result:

[googleapps domain="docs" dir="spreadsheets/d/16NjXTNqRbB2yb0M1Z69c2TlSDEzFEr4e9OILvXNIlnk/pubchart" query="oid=1955051236&format=interactive" width="662" height="410" /]

Here are steps you can follow:

1. Prepare a Google sheets within Google Drive;
2. Insert chart from the menu;
3. Define whatever color or label you like;
4. Use development tool within Google Chrome to find the SVG tag in the html script;
5. Open your text editor and paste the SVG html tag into it;
6. Make up the SVG header, remember to define the SVG version.
7. Save the text file as a SVG file.
8. You may want to convert the SVG file to a [Postscript](https://en.wikipedia.org/wiki/PostScript) (PS) file so you can convert it to any 600dpi raster figure.

The essential idea behind this is that [Google Chart API](https://developers.google.com/chart/) uses [SVG](https://en.wikipedia.org/wiki/Scalable_Vector_Graphics) and we are basically calling Google Chart API to produce chart without actually writing any script!

The above figure is Copy right protected&nbsp;
