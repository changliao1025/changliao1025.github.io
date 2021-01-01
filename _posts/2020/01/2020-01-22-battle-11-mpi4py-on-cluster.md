---
layout: post
title: 'Battle 11: Mpi4py on cluster'
date: '2020-01-22T17:57:00.000-08:00'
author: Chang Liao
tags:
- mpi4py
- Python
- HPC
- MPI
modified_time: '2020-04-03T09:22:36.299-07:00'
blogger_id: tag:blogger.com,1999:blog-3189999653395802666.post-3359843679142732252
blogger_orig_url: https://codedoesnotlie.blogspot.com/2020/01/battle-11-mpi4py-on-cluster.html
---

One of my Python scripts is taking too long to run, which exceeds the short 
queue. 
<div>I decided to use MPI, and mpi4py seems to be a good choice.<div>But there 
are many issue when I first used it.<div> 
<div>After many attempts, I found at least one way to use it.<div> 
<div>Some ideas are from here: 
[https://researchcomputing.princeton.edu/mpi4py](https://researchcomputing.princeton.edu/mpi4py)<div> 
<div>1. ssh into the cluster 
1. load anaconda into system 
1. create a conda environment for this task mpienv 
1. activate the environment 
1. load compiler, I used gcc 
1. load openmpi 
1. export MPICC="$(which mpicc)" 
1. pip install mpi4py,  you should not use conde-forge channel because it will 
install mpi again. 
1. test with python -c "import mpi4py" 
<div>So earlier I had issues and there are several lessons:<div>1. You should 
load before installing mpi4py 
1. Because we need to use system mpi, we need to load mpi after activate the 
cnvironment. 
<div> 
<div>Good luck! 