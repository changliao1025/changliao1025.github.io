---
layout: post
title: 'High Performance Computing: OpenMP and Anusplin'
date: 2016-10-04 18:53:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- Anusplin
- GCC
- HPC
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
permalink: "/2016/10/04/high-performance-computing-openmp-and-anusplin/"
---
This is a live example from the project I am working right now. Good luck if you are following!  
In order to speed my Anusplin program, I decided to use OpenMP. [Anusplin](http://fennerschool.anu.edu.au/research/products/anusplin-vrsn-44) is a package for climate data preparation.

My program was written in C++ as usual. C++ itself is fast, but Anusplin program takes a long time to run for approximately 50K+ simulations. Previously I set up some system pause (0.1second) between each run. Let's see what OpenMP can do.

There are many guide of OpenMP online.  
First you need to know what's the GCC version you get, such as  
///===========================================  
gcc -v  
Using built-in specs.  
COLLECT\_GCC=gcc  
COLLECT\_LTO\_WRAPPER=/apps/rhel6/gcc/5.2.0/libexec/gcc/x86\_64-unknown-linux-gnu/5.2.0/lto-wrapper  
Target: x86\_64-unknown-linux-gnu  
Configured with: /tmp/aai/gcc-5.2.0/configure --prefix=/apps/rhel6/gcc/5.2.0 --enable-languages=c,c++,fortran --enable-shared --enable-threads=posix --disable-checking --disable-multilib --with-system-zlib --enable-\_\_cxa\_atexit --disable-libunwind-exceptions --enable-java-awt=gtk --with-gmp=/apps/rhel6/gcc/5.2.0/gmp-6.1.0 --with-mpfr=/apps/rhel6/gcc/5.2.0/mpfr-3.1.3 --with-mpc=/apps/rhel6/gcc/5.2.0/mpc-1.0.3  
Thread model: posix  
gcc version 5.2.0 (GCC)&nbsp;  
///===========================================  
Usually the higher, the better, but you may need to double check.  
Then here is the OpenMP version support in different versions of GCC.  
[https://gcc.gnu.org/wiki/openmp](https://gcc.gnu.org/wiki/openmp)

Next, I will follow this [guide](http://bisqwit.iki.fi/story/howto/openmp/) if possible:  
First, I need to enable OpenMP compiler flag in my makefile as: (remember to backup the makefile if you want)  
**g++ tmp.cpp -fopenmp**

```

```

Then I added the simplest control to my for loop:

**#pragma omp parallel for**

  

Save the source code and re-compile.

My first error:

invalid exit from OpenMP structured block.

My second error:

undefined reference to `GOMP\_parallel\_start  
(You need to link with -fopenmp. Your makefile doesn't provide that flag on the linker step. Just add -fopenmp to your LDFLAGS)

After fixing these two errors within one minute, the re-compile was successful.

However, there is an error thrown out as:  
\*\*\* glibc detected \*\*\* ./anusplin\_openmp: double free or corruption (fasttop): 0x00002b8144000af0 \*\*\*

So after some research, I have set a few variables as private in the OpenMP and everything works now.

By the way, if you have troubles with memory issues brought out by OpenMP, you can try [Valgrind](http://valgrind.org/docs/manual/quick-start.html).

