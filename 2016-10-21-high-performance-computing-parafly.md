---
layout: post
title: 'High Performance Computing: ParaFly'
date: 2016-10-21 18:20:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- HPC
- IDL
- OpenMP
- ParaFly
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
permalink: "/2016/10/21/high-performance-computing-parafly/"
---
In my recent posts I shared some first hand experience of parallel computing using OpenMP.  
While OpenMP is supported by many programming languages, there are still a few does not. So here I am sharing another approach to create a parallel computing job.

The utility I will use is called "ParaFly". There are some information you can read [here](http://parafly.sourceforge.net/).  
Basically, ParaFly can be used to run a list of command simultaneously. This approach will be particularly useful for some types of jobs in which tasks are independent with each other (such as for loop) but take a long time to run.

In my case, I was using the IDL library to process a huge amount to spatial datasets. I will use this job as an example to show how it is done.

Organically, I have to call a routine:  
PRO project48, extension\_file = ef, \$  
&nbsp; &nbsp; filename\_mapinfo, \$  
&nbsp; &nbsp; missing\_value, \$  
&nbsp; &nbsp; o\_pixel\_size, \$  
&nbsp; &nbsp; prefix\_in, $  
&nbsp; &nbsp; prefix\_out = po, \$  
&nbsp; &nbsp; workspace\_in, \$  
&nbsp; &nbsp; workspace\_out, \$  
&nbsp; &nbsp; year\_end, \$  
&nbsp; &nbsp; year\_start

to re-project a list of raster image files from 1980 to 2015.  
IDL is known for [inefficient](http://www.idlcoyote.com/tips/forloops2.html)in for loop just like MATLAB.

And it is not easy to parallel IDL on a Linux HPC. You can use C/C++ to call IDL with OpenMP enabled if possible, but then you have to write some additional program to do the work. You can also use GDAL library to write a projection function then you can use OpenMP freely, but that certainly requires some efforts.

However, with ParaFly, we can do the work within a few minutes if you are lucky.  
First, we need to add an additional routine to call the above routine, but this new routine should accept one parameter, which is time(year), because all the other will remain the same.  
Such as:  
;- &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;   
PRO project48\_tmax, year  
&nbsp;COMPILE\_OPT IDL2  
&nbsp; year\_start = year  
&nbsp; year\_end = year  
&nbsp; ;;some other lines are remove here  
&nbsp; project48, extension\_file = file\_extension, $  
&nbsp; &nbsp; filename\_mapinfo, $  
&nbsp; &nbsp; missing\_value, $  
&nbsp; &nbsp; o\_pixel\_size, $  
&nbsp; &nbsp; prefix\_in, $  
&nbsp; &nbsp; workspace\_in, $  
&nbsp; &nbsp; workspace\_out, $  
&nbsp; &nbsp; year\_end,$  
&nbsp; &nbsp; year\_start  
&nbsp; PRINT, 'Finished!'  
END

Then the routine is wrapped and ready for ParaFly.

You may want to write another wrapper to generate the ParaFly file, such as:  
PRO prepare\_parafly\_files &nbsp; &nbsp; &nbsp;   
&nbsp; COMPILE\_OPT IDL2  
&nbsp; year\_start = 1980 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;   
&nbsp; year\_end = 2015  
&nbsp; ;;some other lines are remove here  
&nbsp; FOR year = year\_start, year\_end, 1 DO BEGIN   
&nbsp; &nbsp; &nbsp;year\_str = STRING(year, format = '(i04)') &nbsp; &nbsp;   
&nbsp; &nbsp; &nbsp;str = 'idl -e '+ '"' +'project48\_tmax, ' $ &nbsp;   
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;+ year\_str + '"' &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;   
&nbsp; &nbsp; &nbsp;PRINTF, lun, str &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;   
&nbsp; ENDFOR &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;   
&nbsp; FREE\_LUN, lun &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;   
END

Then work should be done.  
Theoretically, you can request the whole node with all cores in one job, and then gain speed the number of core faster. For example, if I request 10 cores, then the program will improve to 10 time faster.

