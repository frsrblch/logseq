- Taken from Geometric Algebra for Physicists
- Elementary principles
	- $\bold v = \dot {\bold x} = \frac {d \bold  x} {dt}$
	- $\bold p = m \bold v$
	- $\dot {\bold p} = \bold f$
	- $\bold f = m \bold a$
	- $\bold a = \ddot {\bold x} = \frac{d^2 \bold x}{dt^2}$
	- $W_{12} = \displaystyle\int_{t_1}^{t_2} \bold f \cdot \bold v dt = \displaystyle\int_1^2 \bold f \cdot d \bold s$
	  $W_{12} = m \displaystyle\int_{t_1}^{t_2} \bold a \cdot \bold v dt = \frac m 2 \displaystyle\int_{t_1}^{t_2} \frac d {dt} v^2 dt$
	  $T = \frac 1 2 m v^2$
	- For conservative forces: $\bold f = - \nabla V$
		- $W_{12} = - \displaystyle\int_1^2 d\bold s\cdot \nabla V = V_1 - V_2$
		- $E = T + V$
- Angular momentum
	- $L = \bold x \wedge \bold p$
	- $\dot L = \dot {\bold x} \wedge \bold p + \bold x \wedge \dot {\bold p}$
	      $= \bold v \wedge (m \bold v) + \bold x \wedge (m \bold a)$
	      $= 0+\bold x \wedge \bold f$
	      $= N$
	- $N$ defines torque about the origin
	- $\bold x = r \hat {\bold x}$
	- $\dot {\bold x} = \dot r \hat{\bold x} + r \dot{\hat{\bold x}}$
	- $L = m \bold x \wedge (\dot r \hat{\bold x} + r \dot{\hat{\bold x}})$
	      $= mr \hat{\bold x} \wedge (\dot r \hat{\bold x} + r \dot{\hat{\bold x}})$
	      $= mr^2 \hat{\bold x} \wedge \dot{\hat{x}}$
	- Since $\hat{\bold x}^2 = 1$, we must have $0 = \frac{d}{dt}\hat{\bold x}^2 = 2 \hat{\bold x}\cdot\dot{\hat{\bold x}}$ and therefore
		- $L = mr^2 \hat{\bold x}\dot{\hat{\bold x}} = -mr^2 \dot{\hat{\bold x}} \hat{\bold x}$
- Systems of particles
	- $\displaystyle{\underset j \sum \bold f_{ij} + \bold f_i^e = \dot{\bold p_i}}$
		- $\bold f_i^e$ are external forces
	- $\bold f_{ij} = -\bold f_{ji}$
	- Center of mass: $\bold X = \displaystyle{\frac 1 M} \underset i \sum m_i \bold x_i$ where $M = \underset i \sum m_i$
	- $\displaystyle{\bold P = \underset i \sum {\bold p}_i = M \frac {d \bold X}{dt}}$
	- $L = \displaystyle{\underset i \sum \bold x_i \wedge \bold p_i}$
	- $\displaystyle{\dot L = \underset i \sum \bold x_i \wedge \dot{\bold p}_i} = \underset i \sum \bold x_i \wedge \bold f_i^e + \underset{i,j} \sum \bold x_i \wedge \bold f_{ji}$
	- $\displaystyle{\dot L = \frac {dL}{dt} = N^e}$ (total external torque)
	- Position relative to center of mass: $\bold x_i = \bold x_i' + \bold X$ such that $\displaystyle{\underset i \sum m_i \bold x_i'} = 0$
	- Velocity relative to velocity of center of mass: $\bold v_i = \bold v_i' + \dot{\bold X}$
	- Total angular momentum:
	  $\displaystyle{L = \underset i \sum \left( \bold X \wedge m_i \dot{\bold X} + \bold x_i' \wedge m_i \bold v_i' + m_i \bold x_i' \wedge \dot{\bold X} + \bold X \wedge m_i \bold v_i' \right) }$
	      $\displaystyle{= \bold X \wedge \bold P + \underset i \sum \bold x_i' \wedge \bold p_i' + 0 + 0}$
		- Then simply choose the origin such that the center of mass is at rest
	- Total kinetic energy:
	  $\displaystyle{T = \underset i \sum \frac 1 2 m_i \bold v_i^2 = \frac 1 2 M \dot{\bold X}^2 + \frac 1 2 \underset i \sum m_i {\bold v_i'}^2}$
- Two-body central force interactions
	- $m_1 \ddot{\bold x}_1 = \bold f$
	- $m_2 \ddot{\bold x}_2 = -\bold f$
	- $\bold x = \bold x_1 - \bold x_2$
	- $m_1 m_2 \ddot{\bold x} = (m_1 + m_2) \bold f$
	- Reduced mass: $\displaystyle\frac 1 \mu = \frac 1 {m_1} + \frac 1 {m_2}$
	- $\mu \ddot{\bold x} = \bold f$
	- $\bold f = f \hat{\bold x}$
	- In terms of center of mass $\bold X$ and relative vector $\bold x$:
		- $m_1 \bold x_1 = m_1 \bold X + \mu \bold x$
		- $m_2 \bold x_2 = m_2 \bold X - \mu \bold x$
	- Total angular momentum: $L_t = m_1 \bold x_1 \wedge \dot{\bold x}_1 + m_2 \bold x_2 \wedge \dot{\bold x}_2 = M \bold X \wedge \dot{\bold X} + \mu \bold x \wedge \dot{\bold x}$
		- $L = \mu \bold x \wedge \dot{\bold x}$
		- $\displaystyle T = \frac 1 2 \mu \dot{\bold x}^2 = \frac 12 \mu (\dot r \hat{\bold x} + r \dot{\hat{\bold x}})^2 = \frac 1 2 \mu \dot r^2 + \frac 1 2 \mu r^2 \dot{\hat{\bold x}}^2$
		- $L^2 = - \mu^2 r^4 \hat{\bold x} \dot{\hat{\bold x}} \dot{\hat{\bold x}} \hat{\bold x} = - \mu^2 r^4 \dot{\hat{\bold x}}^2$
		- $l = |L| = \mu r^2 |\dot{\hat{\bold x}}|$
-