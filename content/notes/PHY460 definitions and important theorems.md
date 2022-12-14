---
title: "PHY460 definitions"
tags:
- "PHY460"
---
## 1-Dimensional definitions and Theorems
### Generalization/reduction of order
- reduction to a system of first-order differential equations $$\frac{d}{dt} \vec{x} = \vec{f}(\vec{x})$$ enables plotting in phase space
- usually depends on a substitution of $y = \dot{x}$ and solving for y
### Existence & Uniqueness
- $\dot{x} = v(x)$ has a _unique_ solution around an initial condition $(t_0, x_0)$ provided the functions are smooth in the service of the _Lipschitz condition_ 
### Lipschitz Condition $[L]$
-  $\forall x, y \in (a, b), |v(x) - v(y)| < k |x-y|$ 
- this implies that $v(x)$ is continuous and a finite derivative exists almost anywhere $$ \frac{|v(x)-v(y)|}{|x-y|}<k, \ k\text{ being a finite number} $$
- this effectively means that solutions reach a fixed point in finite time
### Bifurcation
- quantitative change in behaviour
	- creation or destruction of fixed points
	- change in stability of fixed points
### Saddle-node bifurcation
- has the normal form $\dot{x} = r + x^2$
	- when $r>0$, no fixed points
	- when $r=0$, 1 fixed point (semi-stable)
	- when $r < 0$, 2 fixed points (1 stable, 1 unstable)
- fixed points appear and disappear
### Transcritical Bifurcation
- normal form: $\dot{x} = rx-x^2$
- one fixed point is maintained, but undergoes a change in stability. Another fixed point merges with the other (at $r=0$), and re-emerges out the other side, with the two fixed points having swapped stability
### Subcritical pitchfork bifurcation
- normal form: $\dot{x} = rx + x^3 - x^5$ 
- one unstable fixed point becomes one stable and 2 unstable fixed points (mathematically)
- physical systems have the $x^5$ higher order stabilizing term to avoid loss of generality, adding another two stable fixed points above and below the unstable ones, which can be jumped to exhibiting hysteresis
### Hysteresis
- Hysteresis is when, in a case of a subcritical pitchfork bifurcation, a particle leaves the origin after it is stable to either the positive or negative branch. If the control parameter is adjusted such that the origin regains stability, for some range of the parameter, it stays on its new branch until that branch loses stablity itself.
### Supercritical Pitchfork bifurcation
- normal form: $\dot{x} = rx-x^3$
- a stable fixed point splits into an unstable fixed point and two stable fixed points
- describes second order (gradual) phase transitions
### Nondimensionalization
- This is the substitution $t=T\tau$ where $\tau$ is the dimensionless time and $T$ is the characteristic timescale
- the nondimensionalized system makes relationships easier to notice, since it reduces the number of parameters we need to be concerned with, and can identify those individual parameters later
## 2-Dimensional Definitions and Theorems
### 2-dimensional system
- system of differential equations $$\begin{cases}
  \dot{x} &= f(x,y) \\
  \dot{y} & = g(x,y)
  \end{cases}$$
### phase plane
- the plane made by $(x,y)$
### Nullcline
- where $\dot{x}=0$ or $\dot{y} = 0$ 
- includes nullclines, which are lines where one variable has time progression and the other doesn't
### Fixed points
- a point where $(\dot{x}, \dot{y}) = (0,0)$
- i.e. there is no time progression
### Phase Portrait
- graph of the overall trajectories in phase space (not all trajectories, just the qualitatively demonstrative ones)
### Closed Orbit
- a trajectory that circulates around a fixed point and back on itself
- for any initial point on the trajectory $\vec{x}_0$, for some time $t$, the trajectory will return to $\vec{x}_0$ 
### Liapunov Stable
- all trajectories sufficiently close to a fixed point $\dot{\vec{x}}$ remain sufficiently close for all time
### Linear Stability analysis of a fixed point in 2-Dimensions
- Found by finding the eigenvalues of the Jacobian matrix at the fixed point $$A = \begin{pmatrix}
  \frac{\partial \dot{x}}{\partial x} && \frac{\partial \dot{x}}{\partial y} \\
  \frac{\partial \dot{y}}{\partial x} && \frac{\partial \dot{y}}{\partial y}
  \end{pmatrix}$$
	- Once you have found this matrix, plug in $(x^\*, y^\*)$ and find the eigenvalues
- these eigenvalues can be found by taking the trace $\tau$ and determinant $\Delta$ of $A$ $$\begin{split} 
  \tau &= a + b \\
  \Delta & = ad-bc
  \end{split}$$ and plugging these values into the quadratic equation$$\lambda_{1,2} = \frac{\tau \pm \sqrt{\tau^2 - 4\Delta}}{2}$$
- There are a few cases that these fixed points can have based on their eigenvalues. When the eigenvalues are purely real and distinct ($\lambda_1 \neq \lambda_2$, $\tau^2 - 4 \Delta > 0$) we have
	- if $\lambda_1, \lambda_2 > 0$ **stable node**
	- if $\lambda_1, \lambda_2 < 0$ **unstable node**
- if the eigenvalues are of opposite sign, the fixed point is a saddle
	In all of these cases, the trajectories become parallel with the eigendirection (span of eigenvector) of greatest norm. When the eigenvalues are complex ($\tau^2 - 4 \Delta < 0$) 
	- if the eigenvalues are complex but not purely imaginary ($\tau \neq 0$) the fixed point is a **spiral** with stability found by analyzing the sign of the real componant
		- if the eigenvalues are purely imaginary ($\tau = 0$) the fixed point is a **centre**, with a family of closed obits around it (these orbits are never attractors or repellers, each trajectory stays isolated in its original closed orbit)
- If $\lambda_1 = \lambda_2$ there is only one eigenvalue, and there are new cases
	- if there are still 2 eigenvectors, every vector is an eigenvector with the same eigenvalue and the fixed point is a **star**, stable if $\lambda < 0$, unstable if $\lambda > 0$ 
		- if there is only one eigenvector, the fixed point is a **degerate node** and all trajectories become parallel with this single eigendirection
## Borderline cases for linear stability analysis-referring to nonlinear terms
- For the borderline cases (centres, stars, nodes, i.e. when there are not two eigenvalues of distinct magnitude), the conclusions of linear stability analysis can turn out to be wrong when considering nonlinear terms
	- For stars and nodes, stability does not change, but for centres it can
		- this can be resolved by tranforming into polar coordinates and seeing if the radius is increasing or decreasing monotonically with time. If this is true, the point is a spiral
### Conservative systems
- Systems for which there is a conserved quantity
- based on the conservation of energy
- A conservative system has a conserved quantity (a function $E(\vec{x})$) that is constant on trajectories, but not constant on any open set
- this implies that the system cannot have any attracting points
- conservative systems have a way of asserting that a nonlinear centre is truly a centre. 
	- if a system has a conserved quantity, and stability analysis says its a centre, than it is a centre even when considering nonlinear terms
	- if the fixed point $\vec{x}^\*$ is a local miniumun of $E$ then all trajectories sufficiently close to $\vec{x}^\*$ are closed
### Homoclinic Orbits
- trjectories that begin and end at the same fixed point
- take infinite time to leave, and to return
### Reversible systems
- have time-reversal symmetry
	- the dynamics look the same if time runs forwards or backwards 
- more specifically, a reversible system is any 2nd order system that is invariant under $t \rightarrow -t$ and $y \rightarrow -y$ 
	- For example, any system where $$\begin{cases}
	  \dot{x} &= f(x,y) \\
	  \dot{y} & = g(x,y)
	  \end{cases}$$ where $f$ is odd and $g$ is even (i.e. $f(x, -y) = -f(x,y)$ and $g(x, -y) = g(x,y)$
- reversable systems are different from conservative systems, but showing that a system is reversible is enough to show that a nonlinear centre exists
- effectively, reversability is being symmetric across the $x$-axis
### Heteroclinic trajectory or Saddle Connection
- a trajectory directly between two saddle points
- more common in reversible or conservative systems
- also takes infinite time to arrive and leave
### Index of a curve
- The index of a curve is $I_o = \frac{1}{2 \pi} [\varphi]_C$ 
	- $[\phi]_C$ is the sum of the differences between the angles relative to the horizontal of any vector that passes through a simply connected closed curve on a continuously differentiable vector field $\dot{\vec{x}} = \vec{f}vec{x})$ that passes through no fixed points (call this angle $\varphi$)
	- the index is always an integer value, since $[\varphi]_C$ must rotate back to itself
- Properties of the Index of a Curve
	- If $C$ can be continuously deformed into $C'$ (i.e. deformed without crossing any fixed points) then $I_C = I'_C$ 
		- this is because any continuous integer function must be constant
	- If $C$ contains no fixed points, then $I_C = 0$
		- this is because any difference must return to the same point without fully rotating.
	- If we reverse all arrows in $f$ by reversing time $t \rightarrow -t$ then the index is unchanged
		- This is because reversing time is equivalent to the translation $\varphi \rightarrow \varphi + \pi$ and we are taking the sum of differences, which is unchanged by such a transformation
	- If $C$ is a trajectory of the system, then $I_c = +1$
		- this is because the flow follows the path of $C$ if $C$ is a trajectory
	- If we subdivide $C = C_1 + C_2$, then its index is the sum of the indicies of the curves $I_C = I_{C_1} + I_{C_2}$ 
		- this is because the overlapping sections of the curves are equal and opposite, and thus cancel out.
### Index of a point
- the index of a curve that includes only one fixed point $\vec{x}^*$ 
	- if $\vec{x}^*$ is a stable or unstable node, or a spiral, or a centre, $I_C = +1$
	- if $\vec{x}^*$ is a saddle, $I_C = -1$
### Index of a curve enclosing $n$ fixed points
- If $C$ ncloses $n$ fixed points $x_1^\*, x_2^\*, ... , x_n^\*$, then $I_C = I_1 + I_2 + ... + I_n$ 
	- this is because any arbitrarily small curves around non-fixed points have $I_C = 0$, meaning only the curves enclosing fixed points constribute. Then by the additive property, we take the sum.
### Limit Cycle
- A limit cycle is an isolated closed trajectory
- neighbouring trajectories spiral into or out of limit cycles
- If a system has a limit cycle, it settles into a self-sustained oscillations for large $t$
### Gradient systems
- A gradient system is a system that can be written as $\dot{\vec{x}} = - \nabla V$ Where $V(\vec{x})$ is a continuous single valued scaler function
- limit cycles are impossible on gradient systems
### Liapunov Functions
- A Liapunov function is a continuously differentiable, real valued function $V(\vec{x})$ where
	- $V(\vec{x})>0$ for all $\vec{x} \neq \dot{\vec{x}}$, and $V(\vec{x}^\*) = 0$ (positively definate)
	- $\dot{V} < 0$ for all $\vec{x} \neq \vec{x}^*$ (all trajectories flow toward $\vec{x}^\*$) 
- If a liapunov function is found for a fixed point, it must be globally asymptotically stable for all initial conditions $\vec{x}(t) \rightarrow \vec{x}^*$ and thus the system must have no closed orbits 
- requires divine inspiration to find Liapunov functions
### Dulac's Criterion
- Dulac's criterion is a theorem for ruling out closed orbits using green theorem, and is as follows
	- Let $\dot{\vec{x}} = \vec{f}(\vec{x})$ be a continuously differentiable vector field on a simply connected subset of the plane $R$
	- If there exists a continuously differentiable, real valued function $g(\vec{x})$ such that $\nabla \cdot g(\vec{x})$has one definate sign throughout $R$, then there are no closed orbits through $R$
- requires divine inspiration to find $\vec{g}$ 
	- sometimes $g = 1, \frac{1}{x^a y^b}, e^{ay}$ work
### Poincaré-Bendixson theorem
- Allows us to verify that closed limit cycles exist, as well as that chaos cannot exist on the phase plane.
- Consider the following conditions
	- $\dot{\vec{x}} = \vec{f}(\vec{x})$ be a continuously differentiable vector field on a subset of the plane $R$ 
	- $R$ is closed and bounded
	- $R$ contains no fixed points
	- There exists some trajectory $C$ that is confined to $R$ for all time (i.e. starts in $C$ and never leaves)
- If all of these criteria are met, $C$ is either a closed orbit or it spirals into a closed orbit as $t \rightarrow \infty$ 
- Since this trajectory cannot pass over itself in 2D, it must settle into a closed orbit
	- this implies there is no chaos in the phase plane
- Does not apply in 3-D since trajectories can wander around and settle into a strange attractor
### Bifurcations in 2-D
- A bifurcation is a change in the structure of the phase portrait
	- a change in the number and location of fixed points, closed orbits, or saddle connections as the control parameters change
### Saddle Bifurcation
- Prototype: $$\begin{cases}
  \dot{x} &= \mu - x^3 \\
  \dot{y} & = -y
  \end{cases}$$ if we take $\mu > 0$, we can see that there is a sable node at $(\sqrt{\mu}, 0)$ and a saddle at $(-\sqrt{\mu}, 0)$ As $\mu$ is decreased, these fixed points merge at $\mu = 0$ and then vanish for $\mu < 0$
### Transcritical & pitchfork bifurcations
- act similarly to their 1-D counterparts, just with $\dot{y}= -y$ added
### Hopf Bifurcations
- Hopf Bifurcations are bifurcations where a stable fixed point with two complex-conjugate eigenvalues loses its stability by simultaneously having the real componants of their eigenvalues go from being negative to being positive.
- (important and subtle) For this to happen, the eigenvalues must have nonzero real componants, and thus can only be spirals and not centres 
- Hopf Bifurcations can be **supercritical**, **subcritical**, or **degenerate**
### Supercritical Hopf Bifurcation
- A supercritical Hopf bifurcaiton is a bifurcation that takes a fixed point that is a stable spiral and turns it into an unstable spiral being orbited by a small, nearly elliptical limit cycle
- can occur in any dimension $n \geq 2$ 
- prototype: $$\begin{cases}
  \dot{r} & = \mu r -r^3 \\
  \dot{\theta} &= \omega+br^2
  \end{cases}$$
	- for $\mu<0$ the origin is a stable spiral with a direction depending on $\omega$. 
	- for $\mu = 0$ the origin is a weak stable spiral (linear stability analysis would call it a centre)
	- for $\mu > 0$ the origin is an unstable spiral with a stable circular limit cycle at $r = \sqrt{\mu}$ 
- There are some attributes that are _generically_ true
	- the limit cycle grows continuosly from the origin an increases proportional to $\sqrt{\mu - \mu_c}$ for $\mu$ close to $\mu_c$ 
	- the frequency of oscillation is approximately $\omega = \text{Im}(\lambda)$ evaluated at $\mu=\mu_c$
		- this is exact at the limit cycle and correct within $O(\mu-\mu_c)$
		- this means the period is $T = \frac{2 \pi}{\text{Im}(\lambda)} + O(\mu-\mu_c)$
### Subcritical Hopf Bifurcation
- A subcritical Hopf Bifurcation is where an unstable spiral surrounded by a stable limit cycle becomes an unstable limit limit cycle surrounded by a larger stable limit cycle, both of which surround a stable spiral. A trajectory will jump like in a subcritical pitchfork bifurcation, and will exhibit hysteresis
- prototype: $$\begin{cases}
  \dot{r} & = \mu r -r^3-r^5 \\
  \dot{\theta} &= \omega+br^2
  \end{cases}$$
	- if $\mu < 0$ there is a stable spiral at the origin surrounded by an small unstable limit cycle, surrounded by a larger stable limit cycle
	- if $\mu = 0$ the unstable limit cycle has shrunk in radius and merged with the origin, turning it into an unsable spiral
	- if $\mu > 0$ the origin is an unstable spiral and the only stable attractor is the larger limit cycle
- This system exhibits **hysteresis** in that when $\mu$ is increased over 0, the particles that go to it will not return to the origin even if the origin regains stability
### Degenerate Hopf Bifurcation
- A degenerate Hopf Bifurcation is a Hopf Bifurcation where a stable spiral transitions into a family of concentric closed orbits, and then into an unstable limit cycle
	- consider the damped pendulum $\ddot{x} + \mu \dot{x} + \sin x = 0$ 
		- if $\mu >0$ the origin is a stable spiral
		- if $\mu = 0$ the origin is a centre surrounded by a family of closed orbits (making this not quite a true Hopf Bifurcation)
		- if $\mu < 0$ the origin is an unstable spiral
- Degenerate Hopf Bifurcations typically happen when a nonconservative system suddenly becomes conservative at $\mu_c$. In this case, the origin becomes a nonlinear centre rather than the weak spiral required by a Hopf Bifurcation
### Infinite Period Bifurcations
### Homoclinic Bifurcations
### Pointcaré maps
### Lorenz System
### Chaos
