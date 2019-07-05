---
layout: post
title: 'High performance computing: how to run IDL program on a cluster'
date: 2015-10-30 00:42:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- HPC
- IDL
- PBS
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
permalink: "/2015/10/30/high-performance-computing-how-to-run-idl-program-on-a-cluster/"
---
One of the advantages of IDL is that it could be deployed on Linux system, to say a HPC (High Performance Computer). Fortunately my research group have this computational resource to advance my research.

So the question is how to run IDL programs on HPC?  
Basically of course you can use X-Windows and IDLDE like what you did in Windows system.  
But that is NOT what I am about to cover in this discussion.

Before I start, you properly could refer to [this page](http://www.umbc.edu/hpcf/hpc-archived/Running%20IDL%20on%20HPC.html) first.  
Some core idea is as follow:

#!/bin/bash  
: The above line tells Linux to use the shell /bin/bash to execute  
: this script. That must be the first line in the script.  
: You must have no lines beginning with # before these  
: PBS lines other than the /bin/bash line:  
#PBS -N 'hello\_parallel'  
#PBS -o 'qsub.out'  
#PBS -e 'qsub.err'  
#PBS -W umask=007  
#PBS -q low\_priority  
#PBS -l nodes=1:ppn=4  
#PBS -m bea

: Change the current working directory to the directory from which you ran qsub:  
cd $PBS\_O\_WORKDIR  
: Run IDL and tell it to execute the "main" procedure:  
idl -e main  
Above is an example to submit an IDL job into the query using PBS.  
For more info about PBS, go to  
[http://en.wikipedia.org/wiki/Portable\_Batch\_System](http://en.wikipedia.org/wiki/Portable_Batch_System)  
An explicit example of PBS script could be found at:  
[http://www.rcac.purdue.edu/userinfo/resources/rossmann/userguide.cfm#run](http://www.rcac.purdue.edu/userinfo/resources/rossmann/userguide.cfm#run)  
Also, the readers are supposed to have obtained some basic Linux skills.

Several features of HPC are flexible data storage capacity. When I was conducting my job, I usually do not want to place massive data with my program code. And I also benefit a lot from third party library including the [NASA IDL Library](http://idlastro.gsfc.nasa.gov/). So I want to automatically import those libraries when I submit my IDL job as well.

Here is what I did:  
Firstly, add a single line into the bash profile, which define the IDL\_STARTUP environment   
For different type of shell, the file you want to add the above line might be different, but the principle is the same.  
Then, go to the path you specified and create you startup file. A simple example of mine is as follow:

[![]({{ site.baseurl }}/assets/9ef57-startup.jpg?w=300)](https://changliao.files.wordpress.com/2015/10/9ef57-startup.jpg)

The most important line within this startup file is the !PATH variable, which include the path where I put all my third party library.  
Some mistakes you want to avoid is the absolute path and relative path issue. You can't be too sure those library are really included even you see the 'IDL is awesome' comes out when IDL is launched! One simple to examine is to start the IDLDE to see whether any of the library routines is highlighted when used.

A common error still remains that IDL can not find the routine even you thought it is right there!  
The solution is that try to load the routing into IDL and compile it. If the compile gets passed, mostly you will be able to call it now.

For some reason some library are written for years. So as new IDL is releases, some may not work and need some updates if necessary. And that is why you can't call them now but they still work yesterday!

After these steps, you will be able to call any routine from IDL, as long as the library is placed under the path.  
One more aspect needs to be considered is that IDL may not have the authority to access or write data across different directory, even you can see the result when debugging. The most reliable way is to operate on directory under corresponding HPC.  
Thanks for the help from [Michael Galloy](https://plus.google.com/u/0/114075308258338504407/posts) and ENVI/IDL support team.

