---
layout: post
title: 'High Performance Computing: A library of utilities'
date: 2016-09-17 21:16:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- Cluster
- HPC
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
permalink: "/2016/09/17/high-performance-computing-a-library-of-utilities/"
---
<p>A brief look into all the advanced modules we can do on a typical HPC cluster.<br />I will gradually introduce what I have been using over the time to advance my research.</p>
<p>--------------------------- /opt/modules/modulefiles ---------------------------
  
&nbsp; &nbsp;abaqus/6.12-3  
&nbsp; &nbsp;abinit/7.6.4\_openmpi-1.8.1\_intel-14.0.2.144  
&nbsp; &nbsp;ampl/20100429  
&nbsp; &nbsp;anaconda/2.0.1-py26  
&nbsp; &nbsp;anaconda/2.0.1-py27 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;anaconda/2.0.1-py33  
&nbsp; &nbsp;anaconda/2.0.1-py34  
&nbsp; &nbsp;ansys/14.0  
&nbsp; &nbsp;ansys/14.5  
&nbsp; &nbsp;ansys/15.0  
&nbsp; &nbsp;ansys/16.2 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;ansysem/16.2  
&nbsp; &nbsp;ase/3.6.0.2515  
&nbsp; &nbsp;ase/3.8.1.3440  
&nbsp; &nbsp;ase/3.9.1.4567 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;atk/12.8.2  
&nbsp; &nbsp;atk/13.8.0 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;atk/2014.1  
&nbsp; &nbsp;atlas/3.11.30\_gcc-4.7.2 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;atlas/3.11.34\_gcc-4.7.2  
&nbsp; &nbsp;autodesk/2013  
&nbsp; &nbsp;autodesk/2015 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;bbftp/3.2.0  
&nbsp; &nbsp;bioinfo  
&nbsp; &nbsp;boost/1.49.0  
&nbsp; &nbsp;boost/1.53.0\_intel-13.1.1.163  
&nbsp; &nbsp;boost/1.55.0\_intel-14.0.2.144  
&nbsp; &nbsp;boost/1.57.0\_intel-15.0.1.133  
&nbsp; &nbsp;boost/1.58.0\_intel-15.0.2.164  
&nbsp; &nbsp;boost/1.58.0\_intel-15.0.3.187  
&nbsp; &nbsp;boost/1.60.0\_impi-5.1.2.150\_intel-16.0.1.150  
&nbsp; &nbsp;boost/1.60.0\_impi-5.1.3.181\_intel-16.0.2.181  
&nbsp; &nbsp;boost/1.60.0\_intel-16.0.1.150 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;cdat/5.2  
&nbsp; &nbsp;cdo/1.6.9  
&nbsp; &nbsp;cgal/4.4  
&nbsp; &nbsp;cgal/4.6.1 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;clcgwb/6.5.1  
&nbsp; &nbsp;cmake/2.8.11.2 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;cmake/3.1.1  
&nbsp; &nbsp;comsol/4.4  
&nbsp; &nbsp;comsol/5.1  
&nbsp; &nbsp;comsol/5.1.0.145  
&nbsp; &nbsp;comsol/5.2 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;cplex/12.1  
&nbsp; &nbsp;cplex/12.6.0.0 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;desmond/v4.5  
&nbsp; &nbsp;desmond/v31023  
&nbsp; &nbsp;desmond/v38017 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;devel/20150609  
&nbsp; &nbsp;dmtcp/2.0  
&nbsp; &nbsp;doxygen/1.8.7  
&nbsp; &nbsp;eclipse/4.2.1  
&nbsp; &nbsp;eclipse/4.4.2 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;eigen/3.1.3  
&nbsp; &nbsp;eman/1.9  
&nbsp; &nbsp;eman/2.07 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;envi/4.8 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;envi/5.0  
&nbsp; &nbsp;envi/5.3  
&nbsp; &nbsp;espresso/4.0.3\_impi-4.1.1.036\_intel-13.1.1.163  
&nbsp; &nbsp;espresso/4.3.2\_impi-4.1.1.036\_intel-13.1.1.163  
&nbsp; &nbsp;espresso/5.1\_impi-4.1.1.036\_intel-13.1.1.163  
&nbsp; &nbsp;espresso/5.2.1\_impi-5.0.3.048\_intel-15.0.3.187 &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;ferret/6.8.4.2  
&nbsp; &nbsp;ffmpeg/2.1.3  
&nbsp; &nbsp;fftw/2.1.5\_gcc-4.7.2\_openmpi-1.8.1  
&nbsp; &nbsp;fftw/2.1.5\_intel-15.0.3.187\_openmpi-1.8.1  
&nbsp; &nbsp;fftw/3.3.4\_gcc-4.7.2\_openmpi-1.8.1  
&nbsp; &nbsp;fftw/3.3.4\_impi-4.1.1.036  
&nbsp; &nbsp;fftw/3.3.4\_impi-5.0.3.048  
&nbsp; &nbsp;fftw/3.3.4\_impi-5.1.1.109  
&nbsp; &nbsp;fftw/3.3.4\_impi-5.1.2.150  
&nbsp; &nbsp;fftw/3.3.4\_intel-13.1.1.163\_openmpi-1.8.1 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;fftw/3.3.4\_intel-14.0.2.144\_openmpi-1.8.1  
&nbsp; &nbsp;fftw/3.3.4\_intel-15.0.1.133\_openmpi-1.8.1  
&nbsp; &nbsp;gamess/01.MAY.2013.R1  
&nbsp; &nbsp;gams/24.1.1  
&nbsp; &nbsp;gaussian03/E.01  
&nbsp; &nbsp;gaussian09/C.01  
&nbsp; &nbsp;gaussian09/D.01 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;gaussian09/E.01  
&nbsp; &nbsp;gaussview/5.0.8  
&nbsp; &nbsp;gcc/4.7.2 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;gcc/4.8.2  
&nbsp; &nbsp;gcc/4.9.2  
&nbsp; &nbsp;gcc/5.2.0  
&nbsp; &nbsp;gdal/1.10.0  
&nbsp; &nbsp;gdal/1.11.1\_gcc-4.7.2 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;gdb/7.5.1  
&nbsp; &nbsp;geos/3.4.2\_gcc-4.7.2  
&nbsp; &nbsp;git/1.8.5.1  
&nbsp; &nbsp;gmp/5.1.3  
&nbsp; &nbsp;gmt/5.1.1  
&nbsp; &nbsp;gnuplot/4.6.2  
&nbsp; &nbsp;gpaw/0.10.0.11364\_openmpi-1.8.1\_intel-13.1.1.163  
&nbsp; &nbsp;gpaw/0.11.0.13004\_impi-5.1.2.150\_intel-16.0.1.150 &nbsp; (D)  
&nbsp; &nbsp;grads/2.0.2  
&nbsp; &nbsp;grass/6.4.2  
&nbsp; &nbsp;gromacs/5.0  
&nbsp; &nbsp;gs/9.15  
&nbsp; &nbsp;gsl/1.6  
&nbsp; &nbsp;gsl/1.15 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;guile/1.8.7  
&nbsp; &nbsp;gurobi/6.5.0  
&nbsp; &nbsp;harminv/1.3.1  
&nbsp; &nbsp;hdf5/1.8.7\_gcc-4.7.2  
&nbsp; &nbsp;hdf5/1.8.7\_intel-13.1.1.163 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;hdf5/1.8.7\_intel-14.0.2.144  
&nbsp; &nbsp;hdf5/1.8.7\_intel-15.0.1.133  
&nbsp; &nbsp;hdf5/1.8.12\_impi-4.1.1.036  
&nbsp; &nbsp;hdf5/1.8.12\_intel-13.1.1.163  
&nbsp; &nbsp;hdf5/1.8.13\_gcc-4.7.2  
&nbsp; &nbsp;hdf5/1.8.13\_impi-5.0.3.048  
&nbsp; &nbsp;hdf5/1.8.13\_intel-15.0.1.133  
&nbsp; &nbsp;hdf5/1.8.16\_impi-5.0.3.048  
&nbsp; &nbsp;hdf5/1.8.16\_impi-5.1.2.150  
&nbsp; &nbsp;hdf5/1.8.16\_intel-15.0.3.187  
&nbsp; &nbsp;hdf5/1.8.16\_intel-16.0.1.150  
&nbsp; &nbsp;hpc/5.3.2  
&nbsp; &nbsp;hspice/2013.03  
&nbsp; &nbsp;hypre/2.9.0b\_impi-5.0.2.044\_intel-15.0.1.133  
&nbsp; &nbsp;hypre/2.10.0b\_impi-5.0.2.044\_intel-15.0.1.133  
&nbsp; &nbsp;hypre/2.10.0b\_impi-5.0.3.048\_intel-15.0.2.164  
&nbsp; &nbsp;hypre/2.11.0\_impi-5.0.3.048\_intel-15.0.2.164 &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;idl/8.2  
&nbsp; &nbsp;idl/8.4 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;imod/4.7.6  
&nbsp; &nbsp;impi/4.1.0.030  
&nbsp; &nbsp;impi/4.1.1.036  
&nbsp; &nbsp;impi/5.0.0.028  
&nbsp; &nbsp;impi/5.0.2.044  
&nbsp; &nbsp;impi/5.0.3.048 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;impi/5.1.1.109  
&nbsp; &nbsp;impi/5.1.2.150  
&nbsp; &nbsp;impi/5.1.3.181  
&nbsp; &nbsp;intel/12.0.084  
&nbsp; &nbsp;intel/13.0.1.117  
&nbsp; &nbsp;intel/13.1.1.163 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;intel/14.0.0.080  
&nbsp; &nbsp;intel/14.0.2.144  
&nbsp; &nbsp;intel/15.0.1.133  
&nbsp; &nbsp;intel/15.0.2.164  
&nbsp; &nbsp;intel/15.0.3.187  
&nbsp; &nbsp;intel/16.0.0.109  
&nbsp; &nbsp;intel/16.0.1.150  
&nbsp; &nbsp;intel/16.0.2.181  
&nbsp; &nbsp;jasper/1.900.1  
&nbsp; &nbsp;java/1.6.0\_45  
&nbsp; &nbsp;java/1.7.0\_21 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;lammps/1Feb14\_intel-14.0.2.144\_openmpi-1.8.1  
&nbsp; &nbsp;lammps/15Feb16\_impi-5.1.2.150  
&nbsp; &nbsp;lammps/15May15\_impi-5.0.2.044 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;libctl/3.2.1  
&nbsp; &nbsp;mathematica/9.0  
&nbsp; &nbsp;matlab/R2012a  
&nbsp; &nbsp;matlab/R2013a &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;matlab/R2014a  
&nbsp; &nbsp;matlab/R2014b  
&nbsp; &nbsp;matlab/R2015b  
&nbsp; &nbsp;meep/1.3\_impi-5.0.3.048 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;meep/1.3\_openmpi-1.8.1\_gcc-4.7.2  
&nbsp; &nbsp;molpro/2010.1.24  
&nbsp; &nbsp;molpro/2012.1.0 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;mono/3.12.1  
&nbsp; &nbsp;mopac/2012  
&nbsp; &nbsp;mpc/0.9  
&nbsp; &nbsp;mpfr/3.1.2  
&nbsp; &nbsp;namd/2.9-ibverbs  
&nbsp; &nbsp;namd/2.9-tcp &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;ncl/6.1.0 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;ncl/6.3.0  
&nbsp; &nbsp;nco/4.4.6\_intel-13.1.1.163  
&nbsp; &nbsp;ncview/2.1.2  
&nbsp; &nbsp;netcdf/3.6.3\_gcc-4.7.2  
&nbsp; &nbsp;netcdf/3.6.3\_intel-13.1.1.163  
&nbsp; &nbsp;netcdf/3.6.3\_intel-14.0.2.144  
&nbsp; &nbsp;netcdf/3.6.3\_intel-15.0.1.133  
&nbsp; &nbsp;netcdf/4.1.1\_gcc-4.7.2\_hdf5-1.8.7  
&nbsp; &nbsp;netcdf/4.1.1\_gcc-4.7.2  
&nbsp; &nbsp;netcdf/4.1.1\_intel-13.1.1.163\_hdf5-1.8.7  
&nbsp; &nbsp;netcdf/4.1.1\_intel-13.1.1.163 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;netcdf/4.1.1\_intel-14.0.2.144  
&nbsp; &nbsp;netcdf/4.1.1\_intel-15.0.1.133  
&nbsp; &nbsp;netcdf/4.3.2\_intel-13.1.1.163\_hdf5-1.8.12  
&nbsp; &nbsp;netcdf/4.3.2\_intel-13.1.1.163  
&nbsp; &nbsp;netcdf/4.3.3.1\_gcc-4.7.2\_hdf5-1.8.13  
&nbsp; &nbsp;netcdf/4.3.3.1\_intel-15.0.1.133\_hdf5-1.8.13  
&nbsp; &nbsp;ngspice/25  
&nbsp; &nbsp;nlopt/2.4.1  
&nbsp; &nbsp;nwchem/6.3-src.2013-05-28  
&nbsp; &nbsp;nwchem/6.5 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;octave/3.6.4  
&nbsp; &nbsp;openfoam/2.2.0  
&nbsp; &nbsp;openmpi/1.8.1\_gcc-4.7.2  
&nbsp; &nbsp;openmpi/1.8.1\_intel-13.1.1.163 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;openmpi/1.8.1\_intel-14.0.2.144  
&nbsp; &nbsp;openmpi/1.8.1\_intel-15.0.1.133  
&nbsp; &nbsp;openmpi/1.8.1\_intel-15.0.3.187  
&nbsp; &nbsp;openmpi/1.10.1\_gcc-5.2.0  
&nbsp; &nbsp;openmpi/1.10.1\_intel-16.0.1.150  
&nbsp; &nbsp;p4vasp/0.3.26  
&nbsp; &nbsp;papi/4.2.0  
&nbsp; &nbsp;parafly/r2013-01-21  
&nbsp; &nbsp;paraview/4.2  
&nbsp; &nbsp;pbs-spark-submit/1.5.1  
&nbsp; &nbsp;pending  
&nbsp; &nbsp;petsc/3.4.3\_impi-4.1.0.030\_intel-13.1.1.163\_feast  
&nbsp; &nbsp;petsc/3.4.3\_impi-4.1.0.030\_intel-13.1.1.163  
&nbsp; &nbsp;petsc/3.4.3\_impi-4.1.1.036\_intel-13.1.1.163  
&nbsp; &nbsp;petsc/3.4.4\_impi-4.1.1.036\_intel-14.0.2.144  
&nbsp; &nbsp;petsc/3.5.3\_impi-5.0.2.044\_intel-15.0.1.133  
&nbsp; &nbsp;petsc/3.5.3\_openmpi-1.8.1\_intel-15.0.1.133 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;pgi/11.8-0 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;pgi/12.10-0  
&nbsp; &nbsp;pgi/13.8-0  
&nbsp; &nbsp;pgi/14.7-0  
&nbsp; &nbsp;pgi/14.10-0  
&nbsp; &nbsp;pgi/15.1-0  
&nbsp; &nbsp;pgi/15.5-0  
&nbsp; &nbsp;pgi/15.7-0  
&nbsp; &nbsp;pgi/15.10-0  
&nbsp; &nbsp;pgi/16.1-0  
&nbsp; &nbsp;pgi/16.3-0  
&nbsp; &nbsp;pnetcdf/1.4.1\_impi-4.1.1.036  
&nbsp; &nbsp;poweracoustics/3.0b  
&nbsp; &nbsp;powerdelta/2.1b  
&nbsp; &nbsp;powerflow/5.0b  
&nbsp; &nbsp;powerflow/5.1b &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;proj/4.8.0  
&nbsp; &nbsp;protobuf/2.6.0  
&nbsp; &nbsp;python/anaconda &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;python/2.7.2  
&nbsp; &nbsp;python/2.7.5\_intel-13.1.1.163  
&nbsp; &nbsp;python/2.7.6\_intel-14.0.2.144  
&nbsp; &nbsp;python/2.7.8\_intel-15.0.1.133  
&nbsp; &nbsp;python/2.7.8\_intel-15.0.2.164  
&nbsp; &nbsp;python/2.7.8\_intel-15.0.3.187  
&nbsp; &nbsp;python/2.7.8\_intel-16.0.0.109  
&nbsp; &nbsp;python/2.7.8\_intel-16.0.1.150  
&nbsp; &nbsp;python/2.7.8\_intel-16.0.2.181  
&nbsp; &nbsp;python/3.4.1  
&nbsp; &nbsp;r/2.15.1  
&nbsp; &nbsp;r/3.1.0 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;r/3.2.2  
&nbsp; &nbsp;r/3.2.3  
&nbsp; &nbsp;rasmol/2.7.4.2  
&nbsp; &nbsp;retools/1.3  
&nbsp; &nbsp;root/5.34.18  
&nbsp; &nbsp;root/5.34.30 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;rstudio/0.98.1056  
&nbsp; &nbsp;sac/101.4  
&nbsp; &nbsp;sas/9.3  
&nbsp; &nbsp;sentaurus/2013.03  
&nbsp; &nbsp;sietraj/349\_2012-03-20  
&nbsp; &nbsp;spark/1.5.1  
&nbsp; &nbsp;sprng/2.0b  
&nbsp; &nbsp;swig/2.0.4  
&nbsp; &nbsp;tecplot/360-2013-R1 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)  
&nbsp; &nbsp;tecplot/360-2016-R2  
&nbsp; &nbsp;thermocalc/3.1  
&nbsp; &nbsp;tigervnc/1.2.0  
&nbsp; &nbsp;totalview/8.11.0-0  
&nbsp; &nbsp;totalview/8.12.0-0 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;totalview/8.15.0-15  
&nbsp; &nbsp;totalview/8.15.4-6  
&nbsp; &nbsp;use.own  
&nbsp; &nbsp;valgrind/3.8.1  
&nbsp; &nbsp;visit/2.6.3  
&nbsp; &nbsp;vmd/1.9.1  
&nbsp; &nbsp;vtk/6.0.0  
&nbsp; &nbsp;xalt/xalt  
&nbsp; &nbsp;xcrysden/1.5.53  
&nbsp; &nbsp;xmgrace/5.1.22  
&nbsp; &nbsp;xmgrace/5.1.23 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(D)  
&nbsp; &nbsp;xyce/6.1\_tri-11.6.1\_openmpi-1.8.1\_intel-13.1.1.163  
&nbsp; &nbsp;xyce/6.2\_tri-11.10.2\_openmpi-1.8.1\_intel-15.0.1.133  
&nbsp; &nbsp;xyce/6.2\_tri-11.10.2\_Serial\_intel-15.0.1.133  
&nbsp; &nbsp;xyce/6.4.0\_tri11\_openmpi\_intel14  
&nbsp; &nbsp;xyce/6.4.0\_tri11\_Serial\_intel14 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (D)

&nbsp; Where:  
&nbsp; &nbsp;(D): &nbsp;Default Module

Use "module spider" to find all possible modules.  
Use "module keyword key1 key2 ..." to search for all possible modules matching  
any of the "keys".
