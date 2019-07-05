---
layout: post
title: 'IDL programming: How to design a simple program'
date: 2016-09-17 15:43:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
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
permalink: "/2016/09/17/idl-programming-how-to-design-a-simple-program/"
---
For scientists and engineers, our scripts/programs are usually very straightforward and simple. Even some of us are modelers, our models should be complex but the source code are still manageable.  
However, the re-usability of these simple programs are still necessary because a lot of our work must be done over and over again. For example, we need to plot/map some data in various scenarios. And we wants the plot/map program can be used for various types of inputs.

Specially, for IDL programming, there are a few common blocks that should be considered in a program.

1. Compiler option; this step is usually just for compiling setup, you can also specify it the start-up file.
2. Error control; some of the most important error information;
3. Global variable; this step should be used to define the global variable, such as the extension of a file.
4. Keyword check;
5. Local variable; this step should be project variable, such as data range.
6. Workspace; workspace usually refer to the directory all operations will be performance on.
7. Main: do the actual job.
8. Post; this is used to finish the program;&nbsp;
9. Cleanup; mainly for memory cleanup, (optional)

Another important tip is that do NOT try to finish everything within one program, especially for computationally intensive jobs.

I will provide an example soon.

