---
title: "PHY460 definitions"
tags:
- "PHY460"
---
# Overview
## The importance of being nonlinear
### phase space
- the space where the axes are the parameters of a system of differential equations
- we are interested in drawing trajectories when given a system
### trajectory
- a curve drawn by the solutions (say $(x_1, x_2)$) to system (say $(\dot{x}_1, \dot{x}_2)$) in phase space.
- the curves are the show the dynamics of the system
### $n$-dimentional system or $n$th-order system
- a system is $n$-dimensional when it has the coordinates $x_1, x_2, ... , x_n$ and thus has an $n$-dimensional phase space
- this $n$ determines the dimension of the phase space, and thus also the drawing
### nonautonomous system
- A nonautonomous system is a system that is explicitly time dependent
- makes our equations partial differential equations
# 1-D Flows
## Flows on the line
### one-dimensional or first order system
- systems where $n=1$, expressed in the form of $\dot{x} = f(x)$ where $f(x)$ cannot explicitly depend on $t$
- archetypical system
### flow
- if $\dot{x} >0$ the flow is to the right
- if $\dot{x} < 0$ the flow is to the left
- allows us to characterize the behavior of a system
### fixed points
- occur when $\dot{x} = 0$ 
### stable fixed points
- occur when $\ddot{x} > 0$
- AKA *attractors* or *sinks* 
- with a perturbation to the left, the system gets pushed back to the right, with a perturbation to the left, there is a push back to the left
- all flows end at a stable fixed point or diverges to infinity

### unstable fixed points
- occur when $\ddot{x} < 0$ 
- AKA *repellers* or *sources*
- any perturbation away from an unstable fixed point sends it to the nearest stable fixed point or out to infinity
- all flows end at a stable fixed point or diverges to infinity.

## Fixed Points and Stability
### phase point
- we take an arbitrary initial condition $x(t_0) = x_0$
- this point is the phase point
- we follow the flow from this point on a *phase portrait* to see how the particle behaves as $t \rightarrow \infty$
### trajectory
- the plot of the evolution of the *phase point* as $t \rightarrow \infty$ on the *phase portrait*
- shows what stable point the *phase point* converges towards, or whether it diverges.
### phase portrait
- plot of $(t, x(t))$
- shows all the qualitatively different trajectories of the system
### equilibrium
- represented by fixed points
- if $x=x^*$ then $x= x^*$ for all time
- A stable equilibrium are geometrically represented by stable fixed points
## Population Growth
### Logistic equation 
- take $N=$ current population, $r=$ growth rate, $K =$ Carrying Capacity  $\dot{N} = rN \left( 1 - \frac{N}{K} \right)$ And $N = N_0 e^{rt}$
- models population growth
- displays fractal bifurcation behavior
### Carrying Capacity ($K$)
- if  $N < K$ the population keeps growing with the growth rate $r$
- if  $N>K$ the population starts decreasing.
## Linear Stability analysis
### Linearization about $x^*$ 
- $\dot{\eta} \approx \eta f'(x)$ where $\eta = \frac{d}{dt}(x-x^*) = \dot{x}$ 
- any perturbation $\eta(t)$ grows exponentially if $f'(x)>0$ and decays if $f'(x)<0$
- if $f'(x) = 0$ the test is inconclusive, as this is the higher order terms of the Taylor series are not negligible 
- this allows us to determine the stability of fixed points algebraically
### characteristic time scale
- $\tau=\frac{1}{|f'(x^*)|}$ 
- $\tau$ is the time required for $x(t)$ to vary dignificantly in the neighborhood of $x^*$ 
## Existence and uniqueness
### Existence and Uniqueness theorem
- we have the initial value problem $$\dot{x} = f(x), \ x(o) = x_0$$ If $f(x)$ and $f'(x)$ are continuous on an open interval $R$ of the $x$-axis, and that $x_0 \in R$. Then the initial value problem has a solution $x(t)$ on some time interval $(-\tau, \tau)$ about $t=0$ and this solution is unique.
- when the solution is not unique, we cannot use the geometric approach to analyzing the behavior of a particle. This is because the particle could move any of the possible ways
## Impossibility of Oscillations
### monotonicity
- $\dot{x} \geq 0$ is always true or $\dot{x}\leq 0$ is always true
- when approaching an equilibrium solution, the particle can never overshoot the mark, and damped osciallations can never happen
### Over Damped Limit
- for a mechanical system, say a spring that is in a highly viscous fluid, when preturbed, it will not oscillate, rather it will be pulled to an equilibrium point
- this approach to an equilibrium point follows monotonicity
## Potentials
### Potential $V(x)$
- defined as $$\dot{x} =f(x) = - \frac{dV}{dx}$$
- $V(t)$ decreases along trajectories, and the system always moves towards a lower potential
### equilibrium point
- occur when $\frac{dV}{dx} = 0$ and thus where $V(x)$ remains constant
- the local minima of $V(x)$ correspond to stable fixed points
- the local maxima of $V(x)$ correspond to unstable fixed points
### Double-well potential or Bistable potential
- a potential with two local minima of $V(x)$
- a system with 2 stable equilibria
## Solving Equations on the Computer
### Euler's Method
- numerical integration scheme which follows $$ x_{n+1} = x_n + f(x_n)\Delta t $$
- must start with some initial condition $x = x_0$ at $t=t_0$ and with a known $f(x)$
### Error
- $$ E = |x(t_n)-x_n| $$
- this is the error in a single timestep.
### Stepsize $\Delta t$
-  the amount of time between each step in a numerical integration
- smaller $\Delta t$ means a smaller error
### Fourth-order Runge-Kutta method
- thought of as the best compormise between minimizing error as well as compute time
- First, four numbers are calculated $$ \begin{split} k_1 & = f(x_n) \Delta t \\ k_2 & = f(x_n + \frac{1}{2} k_1) \Delta t \\ k_3 & = f(x_n + \frac{1}{2} k_2) \Delta t \\ k_4 & = f(x_n +k_3) \Delta t \end{split}$$ and then $x_{n+1}$ is given by $$ x_{n+1} = x_n + \frac{1}{6}(k_1 + 2k_2 + 2k_3 + k_4) $$
### Round-off Error
- the error inherent to computer calculations, also called *floating point error*
### Slope Field
- when solving systems numerically, the first thing we do is plot a slope field on the $(t, x)$ plane. 
- for each point on the plane, $dx/dt$ at that point is computed, and thus makes a field of slopes
- Once we have ethe slope field, we can draw our trajectories from any initial condition, as governed by our slope field.
# Bifurcations
## Introduction to Bifurcations
### Bifucations
- changes in position or stability of fixed points
- qualitative changes in dynamics
### Bifurcation Points
- values of the control parameter $r$ where a bifucation occurs
- acts as a sort of critical point
## Saddle-Node Bifurcations
### Saddle-Node Bifurcation
- Bifurcation where fixed points are created and destroyed
- prototypically $\dot{x} = r + x^2$
- if $r>0$  there are no fixed points
- if $r = 0$ there is one semi-stable fixed point
- if $r<0$ there is one stable fixed point and one semi-stable fixed point
### Bifurcation Diagram
- plot of $(r, x)$ which shows for what values of $r$ there are bifurcations
- plotted in parameter space
- the shape of the plot on a bifurcation diagram allows for the classification of a bifurcaiton
### Bifurcation curve
- the plot on a bifurcation diagram is a bifurcation curve, representing the chagne in qualitative behavior in the parameter space
### Normal Forms
- protypical forms of a kind of bifurcation
- representative of all examples of that bifurcation
## Transcritical Bifurcation
### Transcritical bifurcation
- has the normal form $\dot{x} = rx - x^2$
- one fixed point always remains, but its stability changes, or rather, undergoes an exchange of stabilities
### Exchange of Stabilities
- for when there are two fixed points, and they swap stability after a bifurcation
- usually goes from ($x_1^*$ stable, $x_0^*$ unstable) $\rightarrow$ ($x_0^*$ semistable) $\rightarrow$ ($x_0^*$ stable, $x_2^*$ unstable)
## Pitchform Bifurcation
### Symmetry
- bitchfork bifurcations are found in problems that demonstrate a symmetry
- fixed points appear in symmetrical pairs
- if a pillar is to buckle under a certain load, it is as likely to buckle left as to buckle right, and thus has a symmetry
### Supercritical Pitchform Bifurcation
- Normal form $\dot{x} = rx -x^3$ 
- for $r \leq 0$ there is only one stable point at $x^* = 0$
- for $r>0$ there are 3 fixed points
	- one unstable fixed point at $x^*=0$ 
	- two stable fixed points at $x^* = \pm \sqrt{r}$ 
### Critical Slowing Down
- in a supercritical fixed point, when $r=0$ the clope of the $(\dot{x}, x)$ graph is 0 at the fixed point $x^*=0$ 
- this means the solution no longer decays exponentially fast, resulting in a critical slowing down
### Subcritical pitchfork Bifurcation
- Normal form $\dot{x} = rx - x^3$ 
- for $r \leq 0$ there is only one unstable fixed point at $x^* = 0$
- for $r>0$ there are 3 stationary points
	- one stable fixed point at $x^*=0$ 
	- two un stable points at $x^* = \pm \sqrt{r}$ 
- the actual canonical system of a subcritical pitchfork is $\dot{x} = rx+x^3-x^5$
### Symmetry Broken Solutions
- the solution has less symmetry than the governing equation
- this points at a fundamental change in dynamics
### Characteristic Time Scale
- RETURN TO, YOU DO NOT UNDERSTAND THIS
### Cusp point
- when there are two control parameters, $r, \ h$ 
- occurs when two bifrucation curves meet tangentially on a stability diagram
- this means two parameters must be tuned
### Stability Diagram
- show changes of behavior in parameter space
### Cusp Catastrophe
- RETURN TO, YOU DO NOT UNDERSTAND THIS
# Linear Systems
## Definitions and Examples
### Two Dimensional Linear System
- has the form $$\begin{split} \dot{x} & = ax + by \\ \dot{y} & = cx + dy\end{split}$$
- can be rewrittten in the form of  $\dot{\vec{x}} = A \vec{x}$ where $A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$ and $\vec{x} = \begin{pmatrix} x  \\ y \end{pmatrix}$ 
- linear means that if $\vec{x}_1$ and $\vec{x}_2$ are solutions, then any linear combination of these $c_1 \vec{x}_1 + c_2 \vec{x}_2$ 
- the solutions to these DE's are trajectories in the phase space
### Simple harmonic Oscillator
- has form $m\ddot{x} + kx = 0$
- 