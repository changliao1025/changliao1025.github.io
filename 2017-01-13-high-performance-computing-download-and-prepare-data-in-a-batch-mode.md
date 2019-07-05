---
layout: post
title: 'High Performance Computing: Download and prepare data in a batch mode'
date: 2017-01-13 21:15:00.000000000 -08:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- HPC
- Linux
- Wget
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
permalink: "/2017/01/13/high-performance-computing-download-and-prepare-data-in-a-batch-mode/"
---
Over the time, I need to manipulate a lot of data on a Linux cluster. Some of these manipulations actually read/write data, whereas some are essentially file system operations, such as downloading the files.  
Here I present a list of similar operations suitable for HPC using pbs job approach whenever possible.  
I do not attempt to include all possible methods but only the ones that I find useful and easy to prepare in seconds.  
**Download**  
The most efficient way to download MODIS alike data using HPC.  
wget -r --no-parent -R "index.html\*" --retr-symlinks -A "\*.nc" ftp-url  
wget -r --no-parent -R "index.html\*" -A "MOD17A2.A2000\*.hdf" -A "MOD17A2.A2000\*.xml" http-url  
wget -r --no-parent -R "index.html\*" -A "MOD17\*.hdf" -A "MOD17\*.xml" http-url  
You can basically setup filter for file type, year and granule id.  
  
A live example:  
///==========================================================  
#!/bin/bash &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp;  
#PBS -l nodes=1:ppn=1 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp;  
#PBS -l naccesspolicy=singleuser &nbsp; &nbsp; &nbsp;&nbsp;  
#PBS -l walltime=40:00:00 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp;  
#PBS -M your email address  
#PBS -m ae &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp;  
#PBS -N download &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp;  
#PBS -q standby &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp;  
cd $PBS\_O\_WORKDIR  
wget -r --no-parent &nbsp;-R "index.html\*" &nbsp; --retr-symlinks &nbsp;-A "\*.tar" ftp://somwhere  
///==========================================================  
  
**Compress and extract&nbsp;**  
Examples:  
///==========================================================  
#!/bin/bash &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  
#use this script to extract tar files under the sub directory &nbsp; &nbsp;&nbsp;  
for dir in `find -mindepth 1 -maxdepth 1 -type d`  
do  
&nbsp; &nbsp; cd $dir  
&nbsp; &nbsp; echo $dir  
&nbsp; &nbsp; tar xf \*.tar ./  
&nbsp; &nbsp; cd ..  
done  
///==========================================================  
#!/bin/bash  
# Pass the name of the file to unpack on the command line $1  
for file in \*.gz  
do  
&nbsp; &nbsp; gunzip -d "$file"  
done  
///==========================================================  
  
**Search**  
grep -rnw '/path/to/somewhere/' -e "pattern"  
find . -maxdepth 1 -name "\*string\*" -print  
**Comiple**  
make &\> results.txt  
  
**Count** &nbsp;  
find . -name '\*.cpp' | xargs wc -l  
  
**Debug**  
qsub -I -lnodes=1:ppn=20 -lwalltime=04:00:00 -q boss &nbsp;-X  
  
  
Simply organize these above bash script and replace with commands, most file system related&nbsp;tasks can be resolved. I will add more related scripts later.  
  

  

