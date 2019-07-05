---
layout: post
title: 'Numerical simulation: ode/pde solver and spin-up'
date: 2017-09-01 06:08:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- CLM
- MODFLOW
- ODE
- Optimization
- PDE
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
permalink: "/2017/09/01/numerical-simulation-ode-pde-solver-and-spin-up/"
---
For Earth Science model development, I inevitably have to deal with ODE and PDE equations. I also have come across some discussion related to this topic, i.e.,

[https://www.researchgate.net/post/What\_does\_one\_mean\_by\_Model\_Spin\_Up\_Time](https://www.researchgate.net/post/What_does_one_mean_by_Model_Spin_Up_Time)

In an attempt to answer this question, as well as redefine the problem I am dealing with, I decided to organize some materials to illustrate our current state on this topic.

Models are essentially equations. In Earth Science, these equations are usually ODE or PDE. So I want to discuss this from a mathematical perspective.

Ideally, we want to solve these ODE/PDE with initial condition (IC) and boundary condition (BC) using various numerical methods.  
[https://en.wikipedia.org/wiki/Initial\_value\_problem](https://en.wikipedia.org/wiki/Initial_value_problem)  
[https://en.wikipedia.org/wiki/Boundary\_value\_problem](https://en.wikipedia.org/wiki/Boundary_value_problem)

Because of the nature of geology, everything is similar to its neighbors. So we can construct a system of equations which may have multiple equation for each single grid cell. Now we have an array of equations with the same number of knowns and unknowns. We can solve them simultaneously using numerical&nbsp;methods. In this case, we are not using “spin-up” at all. In fact, lots of models do not use spin-up to reach steady state, e.g., three-dimensional groundwater model MODFLOW.

For example, let's imagine a single cube and corresponding model in space as below:

[![]({{ site.baseurl }}/assets/db2ff-cube.png?w=300)](https://changliao.files.wordpress.com/2017/09/db2ff-cube.png)

\begin{equation}  
\frac{ \partial Q }{ \partial t } = f(Q) + f(w) + ... + Source - Sink  
\end{equation}  
where $Q$ is unknown system state variable, i.e., storage;  
$f(Q)$ is storage related process;  
$f(w)$ is other processes;  
$Source$ is source;  
and $Sink$ is sink.

In most cases, the $f(Q)$ depends on local gradient, which means that:  
\begin{equation}  
f(Q) = f(Q\_{i,j}, Q\_{i-1,j}, ...)  
\end{equation}

With certain boundary condition (BC), we can write an array of equations:

\begin{equation} \label{equ:matrix}  
\begin{bmatrix}  
&nbsp; &nbsp; &nbsp; \frac{ \partial Q\_{0,0} }{ \partial t }&nbsp; \\[0.3em]  
&nbsp; &nbsp; &nbsp; \frac{ \partial Q\_{1,0} }{ \partial t }&nbsp; \\[0.3em]  
&nbsp; &nbsp; &nbsp; \frac{ \partial Q\_{2,0} }{ \partial t }&nbsp; \\[0.3em]  
&nbsp; &nbsp; &nbsp; \frac{ \partial Q\_{i,j} }{ \partial t }  
&nbsp; &nbsp; &nbsp;\end{bmatrix} =  
&nbsp; &nbsp; &nbsp;\begin{bmatrix}  
&nbsp; &nbsp; &nbsp; &nbsp;f(Q\_{0,0}) + f(w\_{0,0}) + ... + Source\_{0,0} - Sink\_{0,0} \\[0.3em]  
&nbsp; &nbsp; &nbsp; &nbsp;f(Q\_{1,0}) + f(w\_{1,0}) + ... + Source\_{1,0} - Sink\_{1,0} \\[0.3em]  
&nbsp; &nbsp; &nbsp; &nbsp;f(Q\_{2,0}) + f(w\_{2,0}) + ... + Source\_{2,0} - Sink\_{2,0} \\[0.3em]  
&nbsp; &nbsp; &nbsp; &nbsp;f(Q\_{i,j}) + f(w\_{i,j}) + ... + Source\_{i,j} - Sink\_{i,j}  
&nbsp; &nbsp; &nbsp;\end{bmatrix}  
\end{equation}

In some simple scenarios, we can solve the equations above directly. For example, when $Q\_{i,j}$ is the only unknown, the total unknowns and number of equations are the same.

However, as our models grow more complicated, e.g., CESM. Our ODE and PDE are getting more complex when all the terms on the right hand side are more complicated. Existing numerical methods may not suit for the equation solving any more. So instead of solving the equation directly, we let the system to evolve through time naturally. And this process is often called “spin-up”. In this scenario, we can use spin-up to approximate $Q\_{i,j}$ with initial condition (IC).

Regardless of the initial condition, the system will gradually converge to "steady state". For example, regardless how much water is stored in the tank initially, the water will reach the same level after certain time when inflow equals outflow.

[![]({{ site.baseurl }}/assets/82cb4-water_tank.png?w=300)](https://changliao.files.wordpress.com/2017/09/82cb4-water_tank.png)

You can easily setup much complicated scenarios similar to:

[![]({{ site.baseurl }}/assets/0e9c6-ode-pde.png?w=300)](https://changliao.files.wordpress.com/2017/09/0e9c6-ode-pde.png)

When you have multiple pools and flux terms, the system may become very sensitive to certain parameters.

Besides, if you take a close look at most numerical methods, they usually use iteration/time step to reach solution. Therefore, they are actually very similar to spin-up but with different time steps.

The criteria which is used to determine whether the system is in "steady state" is also critical. More often we expect a state variable does not change significantly with time, then we say this system is in "steady state". However, any threshold has a limit, needless to say that seldom a system is in absolute steady state.

Because of the complexity of the system, a spin-up can be trapped inside a local valley/hilltop similar to:

[![]({{ site.baseurl }}/assets/52005-global.png?w=300)](https://changliao.files.wordpress.com/2017/09/52005-global.png)

In this case, our "criteria" must be carefully defined, but that is out of the scope of this discussion.

Getting back the equation, even though we may list as many as equations in the matrix, there are no more than 27 equations associated with each cube in a 3D space because there are only 26 neighbors for each cube. As a result, after we estimated the system state variable using spin-up, we no longer need to solve a matrix of equations anymore and we can directly calculate all terms just like spin-up process.

So here comes the question: when do we still need numerical methods to solve ODE/PDE equations?

I believe a side by side comparison will make it easier to understand the fundamental idea behind different approaches.

Let's start with the classical heat equation:

[https://en.wikipedia.org/wiki/Heat\_equation](https://en.wikipedia.org/wiki/Heat_equation)

There is also a very nice program online to demonstrate the equation:  
[http://people.sc.fsu.edu/~jburkardt/cpp\_src/fd1d\_heat\_explicit/fd1d\_heat\_explicit.html](http://people.sc.fsu.edu/~jburkardt/cpp_src/fd1d_heat_explicit/fd1d_heat_explicit.html)  
If you compare the formula with above discussion, then we should realize that this method is very similar to "spin-up".

But as the title implies, this is an explicit method, specifically, an explicit finite difference method, which is widely used in numerical simulation.

[https://en.wikipedia.org/wiki/Finite\_difference\_method](https://en.wikipedia.org/wiki/Finite_difference_method)

"In mathematics, finite-difference methods (FDM) are numerical methods for solving differential equations by approximating them with difference equations, in which finite differences approximate the derivatives. FDMs are thus discretization methods. Today, FDMs are the dominant approach to numerical solutions of partial differential equations"

However, how we approximate the derivatives determines the accuracy of the method and explicit apparently has least accuracy compared with implicit and other methods.

In general, "the implicit scheme is always numerically stable and convergent but usually more numerically intensive than the explicit method as it requires solving a system of numerical equations on each time step.", that is why we seldom use implicit methods on large modeling system such as CESM.

To summarize, "spin-up" is an explicit Euler forward finite difference method and most linear/nonlinear matrix solvers are implicit finite difference methods.  
You can find the advantage and disadvantage of both methods easily.

