---
layout: post
title: 'Ecosystem development: from process-oriented to object-oriented system'
date: 2017-07-14 14:52:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- C++
- Object-Oriented Programming
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
permalink: "/2017/07/14/ecosystem-development-from-process-oriented-to-object-oriented-system/"
---
One of my recent projects is to develop a three-dimensional coupled water and carbon cycle ecosystem model. After finished the first version of the system, I wasn't quite satisfied with the system architecture, partly due to the complexity of the system dependency.

In fact, I have spent great amount of time trying to design the system to be well-structured. Using class in C++11, I have defined many classes to controls different types of algorithms and processes.&nbsp;

The interesting part of the story started to unveil when I started to write/revise the manuscript. When I tried to explain the conceptual model, I realized that even though the current system has use object-oriented programming (OOP) approach through class, most components within the system are not actually using the OOP concept at all. In a word, the system still acts like a process-oriented program.

Taking a review of several other Earth system models (e.g., Community Land Model), I realized that unfortunately most of current models fall into this catalog, process-oriented instead of object-oriented system.&nbsp;

Process-oriented system usually focuses on "action" instead of "object". For example, we focus on "photosynthesis" process but not the entry where it actually takes place. As this traditional approach is more intuitive to us, it usually causes problems in program development such as low reusability due to dependency.

Another problem arises in my own research is that process-oriented approach cannot handle interactions between processes/objects very well, at least not as intuitive as they are supposed to be. In lots of times, we are looking into the relationship between different species, or more generally, types of objects or individuals. In this scenario, an object-oriented approach will significantly improve the readability and efficiency in model development. And usually it may simply help us to understand some scientific questions.

In fact, in many fields (e.g., Artificial Intelligence) object-oriented approach is been widely used. In climate change, we are also using similar concepts such as "feedbacks" and "butterfly effects". However, we have not yet truly treat our Earth system as individual objects so far.

