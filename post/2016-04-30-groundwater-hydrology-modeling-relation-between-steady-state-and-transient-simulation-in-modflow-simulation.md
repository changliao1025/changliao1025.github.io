---
layout: post
title: 'Groundwater hydrology modeling: relation between steady state and transient
  simulation in MODFLOW simulation'
date: 2016-04-30 00:15:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- Groundwater
- MODFLOW
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
permalink: "/2016/04/30/groundwater-hydrology-modeling-relation-between-steady-state-and-transient-simulation-in-modflow-simulation/"
---
Standard groundwater modeling usually uses the three-dimensional Richard's equation to describe the groundwater flow. Solution to the Richard equation usually requires numerical methods such as finite-difference equation used in USGS MODFLOW.  
To solute the array of equations within MODFLOW, an initial head is required regardless of steady state (SS) or transient (TR) simulation.  
As the MODFLOW manual states that in a steady state simulation, the storage terms are ignored since storage of each grid cell is constant with time.  
One of the common problems to run the MODFLOW is &nbsp;that we don't have the initial head data for the simulation. Therefore it is usually suggested that a SS simulation could be run at first to provide the head for the TR simulation. This is because SS is independent with initial head, but TR isn't.  
However, whether placing the SS simulation ahead of TR simulations is doubtful in many practices! Here are the explanations:  
First, the SS flow equation should only be simulated when the system is in equilibrium state.By definition, the steady state flow equation means for each grid cell, the flow and storage don't change with time. In most natural scenarios, these requirements are rarely met. However, the hydrologic system may be very close to equilibrium under certain circumstances. For instance, during winter time, the water flow is ignorable if most hydrologic processes are impaired due to the snow cover and frozen ground.

Second. even if the hydrologic system is close to equilibrium, inappropriate settings for the SS simulation will produce unrealistic results. In order to achieve the steady state for each grid cell, numerical method solver will redistribute the water within the hydrologic system through the head redistribution. After the SS simulation, head distribution may be rather different compared with reality. Several aspects may account for the discrepancy: 1) source/sink terms including pumping, infiltration are not accurate enough; 2) boundary condition is not accurate or missing; 3) model structure, layer settings have flaws which can't match up the reality.

Essentially, the head distribution at any given stress period is sufficient enough to start a simulation. However, approach to establish the head distribution remains the challenge. For cases started with SS, dedicated considerations of the above aspects may provide reliable results. Or else, reasonable assumption of initial head may yield even better results for TR simulation.

On the other side, model calibration could provide an approach to further reduce the uncertainty in initial head distribution even though these related variable are not best described as parameters.
