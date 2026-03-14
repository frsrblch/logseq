- Orbital parameters -> state vectors, State vectors -> orbital parameters
	- https://space.stackexchange.com/questions/19322/converting-orbital-elements-to-cartesian-state-vectors
- [Keplerian Parameters](https://en.wikipedia.org/wiki/Orbital_elements#Keplerian):
	- Reference direction: ♈︎
	- Reference plane
	- Eccentricity (scalar): $e$
	- Semimajor Axis: $a$
	- Orbital plane:
		- Inclination: $i$
		- Longitude of the ascending node: $\Omega$
	- Argument of periapsis: $\omega$
	- Mean anomaly: $M$
	- True anomaly offset: $\nu_0$
- GA Parameters:
	- Orbital plane (unit bivector): $\hat B$
	- Eccentricity vector (unit vector on $\hat B$): $\hat e$
		- $\hat {\bold{e}} = \hat {\bold{r}}$ when $\nu = 0$
	- $\mu = GM$
	- $p = a(1 - e^2)$
	- $\displaystyle r = \frac{p}{1+e \cos \nu}$
	- $\hat {\bold x} = \cos \nu e_x + \sin \nu e_y$
	- $h = \sqrt{\mu p}$
	- $\bold x = r \hat{\bold x} = r (\cos \nu e_x + \sin \nu e_y)$
	- $\displaystyle\dot {\bold x} = \frac{he}{rp} \sin \nu \bold x + \frac{h}{r}(-\sin \nu e_x + \cos \nu e_y) = \frac{he}{rp} \sin \nu \bold x + \frac{h}{r}\dot{\hat {\bold{x}}}$
		- $\displaystyle = \frac{he}{p} \sin \nu \hat{\bold x} + \frac{h}{r}\dot{\hat{\bold{x}}}$
	- $\displaystyle M = \exp \left(-\frac \nu 2 \hat B\right)$
	- $\hat {\bold{x}} = M \hat e M^{-1}$
- ![image.png](../assets/image_1666553556203_0.png)
- Orbital period: $T$
- Eccentricity scalar: $\epsilon$
- Mean anomaly: $\displaystyle M = \frac{\tau t}{T}$
- First-order approximation: $\phi = M + \epsilon \sin M$
- Second-order approximation: 
      $\phi = M + \epsilon \sin (M + \epsilon \sin M)$
      $\phi = M + \epsilon \sin M \cos (\epsilon \sin M) + \epsilon \cos M \sin (\epsilon \sin M)$
- If $\epsilon$ is small:
      $\displaystyle \phi = M + \epsilon \sin M + \frac{\epsilon^2}{2} \sin 2M$
- $\displaystyle\cos \theta = \frac{\cos \phi - \epsilon}{1 - \epsilon\cos\phi}$
- $\displaystyle\tan \frac{\theta}{2} = \left( \frac{1 + \epsilon}{1-\epsilon}\right)^{\frac 1 2}\tan{\frac{\phi}{2}}$
- $\bold a = a e_x$, $\bold b = b e_y$
- $r = a(1 - \epsilon \cos \phi)$
- $\hat{\bold{r}} = \hat{\bold{\epsilon}} e^{i \theta}$
- $h$, specific angular momentum:
	- $h = \sqrt {\mu a(1 - \epsilon^2)}$
- Calculate orbital parameters from pos-vel state
	- Angular momentum: $h = r \wedge v$
	- Semi-major axis:
	  collapsed:: true
	  \begin{equation}
	  a = \frac{-Gm}{2\left(\frac{1}{r}\right)^2 - \frac{v^2}{Gm}}=\frac{-\mu}{\frac{2}{r^2} - \frac{v^2}{\mu}}
	  \end{equation}
		- Eccentricity, e:
		  \begin{equation}
		  e = \sqrt{1 - \frac{b^2}{a^2}}
		  \end{equation}
	- The eccentricity of an orbit can be calculated from the position and velocity of the orbiting body using the following equation:
	- \begin{equation}
	  e = \sqrt{1 + \frac{2 E h^2}{G^2 m^2}}
	  \end{equation}
	- where $E$ is the specific orbital energy, $h$ is the specific angular momentum, $G$ is the gravitational constant, and $m$ is the mass of the central body.
	- The specific orbital energy, $E$, can be calculated from the position and velocity vectors of the orbiting body using the following equation:
	  \begin{equation}
	  E = \frac{v^2}{2} - \frac{G m}{r}
	  \end{equation}
	- where $v$ is the magnitude of the velocity vector, $r$ is the distance between the orbiting body and the central body, $G$ is the gravitational constant, and $m$ is the mass of the central body.
	- The specific angular momentum, $h$, can be calculated from the position and velocity vectors of the orbiting body using the following equation:
	- \begin{equation}
	  h = r \times v
	  \end{equation}
	- where $\times$ denotes the cross product of the position and velocity vectors.
	- Once the eccentricity is calculated, it can be used to determine other orbital parameters, such as the semi
	- The eccentricity of an orbit can be calculated from the position and velocity of the orbiting body using the following steps:
	- Calculate the specific angular momentum vector, $\textbf{h}$:
	  \begin{equation}
	  \textbf{h} = \textbf{r} \times \textbf{v}
	  \end{equation}
	  
	  where $\textbf{r}$ is the position vector of the orbiting body, and $\textbf{v}$ is its velocity vector.
	- Calculate the specific energy, $E$:
	  \begin{equation}
	  E = \frac{v^2}{2} - \frac{GM}{r}
	  \end{equation}
	  
	  where $v$ is the velocity of the orbiting body, $r$ is its distance from the central body, $G$ is the gravitational constant, and $M$ is the mass of the central body.
	- Calculate the semi-major axis, $a$:
	  \begin{equation}
	  a = -\frac{GM}{2E}
	  \end{equation}
	- Calculate the magnitude of the eccentricity vector, $e$:
	  \begin{equation}
	  e = \sqrt{1 - \frac{h^2}{GMa}}
	  \end{equation}
	  
	  where $h$ is the magnitude of the specific angular momentum vector.
	  
	  The above equations assume that the central body is a point mass, and that the orbit is Keplerian (i.e., there are no perturbations from other bodies or from non-gravitational forces). The eccentricity of the orbit describes the shape of the orbit, with values ranging from 0 (for a circular orbit) to 1 (for a parabolic orbit).
	- The direction of the eccentricity vector can be calculated from the position and velocity of an orbiting body using the following steps:
	- Calculate the specific angular momentum vector, $\textbf{h}$:
	  \begin{equation}
	  \textbf{h} = \textbf{r} \times \textbf{v}
	  \end{equation}
	  
	  where $\textbf{r}$ is the position vector of the orbiting body, and $\textbf{v}$ is its velocity vector.
	- Calculate the unit vector in the direction of the specific angular momentum, $\textbf{n}$:
	  \begin{equation}
	  \textbf{n} = \frac{\textbf{h}}{|\textbf{h}|}
	  \end{equation}
	- Calculate the unit vector in the direction of the position vector, $\textbf{r}$:
	  \begin{equation}
	  \textbf{u}_r = \frac{\textbf{r}}{|\textbf{r}|}
	  \end{equation}
	- Calculate the unit vector in the direction of the velocity vector, $\textbf{u}_v$:
	  \begin{equation}
	  \textbf{u}_v = \frac{\textbf{v}}{|\textbf{v}|}
	  \end{equation}
	- Calculate the eccentricity vector, $\textbf{e}$:
	  \begin{equation}
	  \textbf{e} = \frac{\textbf{u}_v \times \textbf{n}}{|\textbf{u}_v \times \textbf{n}|}
	  \end{equation}
	  
	  where $\times$ denotes the cross product.
	  
	  The eccentricity vector points from the center of the ellipse towards the point of closest approach, or periapsis. If the orbit is circular, the eccentricity vector is zero. If the orbit is elliptical, the eccentricity vector points in the direction of the periapsis, which is the point of closest approach to the central body. If the orbit is hyperbolic, the eccentricity vector points in the direction of the asymptote.
	- If B is calculated from r, won't theta always be zero?
	  collapsed:: true
		- You are correct that if the bivector $\mathbf{B} = \mathbf{r} \wedge \mathbf{v}$ is calculated from the position vector $\mathbf{r}$, then the angle $\theta$ between $\mathbf{r}$ and the plane of $\mathbf{B}$ will be zero. This is because the position vector is already in the plane of $\mathbf{B}$, so no rotation is necessary to align it with the plane.
		  In this case, the rotor $R$ simplifies to the identity rotor, and the reflection matrix $M$ becomes the projection matrix onto the plane of $\mathbf{B}$:
		  \begin{equation}
		  M = \frac{1}{|\mathbf{B}|^2}(\mathbf{B}\mathbf{B} - \mathbf{I}) = \frac{1}{|\mathbf{B}|^2}(\mathbf{r} \wedge \mathbf{v})(\mathbf{r} \wedge \mathbf{v})^\dagger
		  \end{equation}
		- where $(\mathbf{r} \wedge \mathbf{v})^\dagger$ is the dual of the bivector $\mathbf{r} \wedge \mathbf{v}$.
		  The eccentricity vector can then be computed as:
		  \begin{equation}
		  \mathbf{e} = M \mathbf{r} = \frac{\mathbf{r}(\mathbf{r} \cdot \mathbf{v})^2}{|\mathbf{B}|^2} - \frac{\mathbf{v}(\mathbf{r} \cdot \mathbf{v})}{|\mathbf{B}|^2}
		  \end{equation}
		- This expression reduces to the familiar formula for the eccentricity vector in terms of the position and velocity vectors, where the first term represents the radial component of the eccentricity vector, and the second term represents the tangential component.
	- What are the equations in LaTeX format for calculating the magnitude and direction of eccentricity from the position and velocity of an orbiting body?
	  collapsed:: true
		- The eccentricity of an orbiting body can be calculated from its position and velocity vectors using the following equations:
		- \begin{align}
		  \vec{r} &= x \hat{i} + y \hat{j} + z \hat{k}\end{align}
		- \begin{align}
		  \vec{v} &= v_x \hat{i} + v_y \hat{j} + v_z \hat{k}
		  \end{align}
		- where $\vec{r}$ is the position vector of the orbiting body, $\vec{v}$ is its velocity vector, $x$, $y$, and $z$ are the components of the position vector, and $v_x$, $v_y$, and $v_z$ are the components of the velocity vector.
		- The magnitude of eccentricity $e$ can be calculated as:
		  \begin{equation}
		  e = \sqrt{\left(\frac{v^2}{\mu} - \frac{1}{r}\right)^2\cos^2\theta + \left(\frac{v^2}{\mu} - \frac{1}{r}\right)^2\sin^2\theta}
		  \end{equation}
		- where $v$ is the speed of the orbiting body, $r$ is the magnitude of the position vector, $\mu$ is the standard gravitational parameter of the central body, and $\theta$ is the angle between the position vector and the velocity vector.
		- The direction of eccentricity can be calculated as:
		  \begin{equation}
		  \vec{e} = \frac{1}{\mu}\left[(v^2 - \frac{\mu}{r})\vec{r} - (\vec{r} \cdot \vec{v})\vec{v}\right]
		  \end{equation}
		- where $\vec{e}$ is the eccentricity vector.
		- The equation for the standard gravitational parameter $\mu$ is:
		- \begin{equation}
		  \mu = GM
		  \end{equation}
		- where $G$ is the gravitational constant and $M$ is the mass of the central body. The standard gravitational parameter is a fundamental parameter in celestial mechanics and is used to calculate the orbital dynamics of satellites, planets, and other celestial bodies. It has units of distance cubed per time squared ($\mathrm{m^3/s^2}$ or $\mathrm{km^3/s^2}$, for example).
	- Given the eccentricity vector $\vec{e}$ and the semi-major axis $a$ of an orbiting body, the position and velocity of the body at any point in its orbit can be calculated using the following equations:
	  \begin{align}
	  r &= \frac{a(1-e^2)}{1+e\cos{\theta}} \
	  \vec{r} &= r(\cos{\theta},\hat{i} + \sin{\theta},\hat{j}) \
	  v &= \sqrt{\mu\left(\frac{2}{r} - \frac{1}{a}\right)} \
	  \vec{v} &= \frac{\mu}{h} \vec{e} \times \vec{r}
	  \end{align}
	- where $r$ is the magnitude of the position vector, $\vec{r}$ is the position vector, $v$ is the magnitude of the velocity vector, $\vec{v}$ is the velocity vector, $\theta$ is the true anomaly (the angle between the periapsis and the position vector measured from the center of the orbit), $\mu$ is the standard gravitational parameter of the central body, and $h$ is the specific angular momentum, given by $h = r v \cos{\gamma}$, where $\gamma$ is the angle between the position and velocity vectors.
	- These equations assume a Keplerian orbit, meaning that the orbiting body is subject only to the gravitational force of the central body and no other external forces. They also assume that the orbit is elliptical and that the central body is at one of the foci of the ellipse.
	- The true anomaly $\theta$ is the angle between the periapsis (the closest point of the orbit to the central body) and the position vector of an orbiting body, measured from the center of the orbit. It can be calculated from the eccentric anomaly $E$ using the following equation:
	- \begin{equation}
	  \tan{\frac{\theta}{2}} = \sqrt{\frac{1+e}{1-e}} \tan{\frac{E}{2}}
	  \end{equation}
	- where $e$ is the eccentricity of the orbit. The eccentric anomaly $E$ is related to the mean anomaly $M$ by Kepler's equation:
	  \begin{equation}
	  M = E - e \sin{E}
	  \end{equation}
	- where $M$ is a measure of the position of the orbiting body in its orbit, with $M = 0$ at the periapsis and increasing with time. Kepler's equation cannot be solved analytically in general, so numerical methods such as Newton-Raphson iteration or the bisection method are typically used to find the value of $E$ that satisfies the equation for a given value of $M$. Once $E$ is known, the true anomaly can be calculated using the first equation.
	- Sure, here are the equations written in LaTeX:
	- Specific angular momentum vector:
	  
	  $${\bf h} = {\bf r} \times {\bf v}$$
	- Magnitude of specific angular momentum vector:
	  
	  $$h = \left|{\bf h}\right|$$
	- Specific energy:
	  
	  $$E = \frac{1}{2} \left|{\bf v}\right|^2 - \frac{G M}{\left|{\bf r}\right|}$$
	- Semi-major axis:
	  
	  $$a = -\frac{G M}{2E}$$
	- Eccentricity vector:
	  
	  $${\bf e} = \frac{1}{M}\left[\frac{{\bf v} \times {\bf h}}{G} - \frac{{\bf r}}{\left|{\bf r}\right|}\right]a - \frac{{\bf r}}{\left|{\bf r}\right|}$$
	  
	  where boldface letters denote vectors.
- The semi-major axis of an orbit is a fundamental parameter that describes the size and shape of the orbit. It is defined as half the length of the major axis of the ellipse that represents the orbit, and it is related to the specific energy of the orbit as follows:
  
  $$a = -\frac{G M}{2E}$$
  
  where  `a`  is the semi-major axis,  `G`  is the gravitational constant,  `M`  is the mass of the central body, and  `E`  is the specific energy of the orbit.
  
  To calculate the semi-major axis vector from the position and velocity vectors of a body, you can use the following steps:
- Calculate the magnitude of the position vector,  `r` , and the magnitude of the velocity vector,  `v` :
  
  $$r = \left|{\bf r}\right| \qquad v = \left|{\bf v}\right|$$
- Calculate the specific energy of the orbit,  `E` , using the formula:
  
  $$E = \frac{1}{2}v^2 - \frac{G M}{r}$$
- Calculate the semi-major axis,  `a` , using the formula:
  
  $$a = -\frac{G M}{2E}$$
- Calculate the semi-latus rectum, `p`, of the orbit, which is given by:
  
  $$p = \frac{h^2}{G M}$$
  
  where `h` is the magnitude of the specific angular momentum vector.
- Calculate the eccentricity, `e`, of the orbit, which is given by:
  
  $$e = \sqrt{1 + \frac{2 E h^2}{G^2 M^2}}$$
- Calculate the semi-minor axis,  `b` , of the orbit, which is given by:
  
  $$b = a \sqrt{1 - e^2}$$
- Finally, calculate the semi-major axis vector,  `a_vec` , as a unit vector in the direction of the position vector,  `r` , scaled by the semi-major axis length,  `a` , as follows:
  
  $${\bf a}_{\rm vec} = \frac{{\bf r}}{\left|{\bf r}\right|} a$$
  
  The semi-major axis vector points from the center of the ellipse to one of its foci, and it determines the size and shape of the orbit.
- Are 
  \begin{equation}
  \vec{e} = \frac{1}{\mu}\left[(v^2 - \frac{\mu}{r})\vec{r} - (\vec{r} \cdot \vec{v})\vec{v}\right]
  \end{equation}
  and 
  $${\bf e} = \frac{1}{M}\left[\frac{{\bf v} \times {\bf h}}{G} - \frac{{\bf r}}{\left|{\bf r}\right|}\right]a - \frac{{\bf r}}{\left|{\bf r}\right|}$$ equivalent?
	- No, the two equations are not equivalent.
	- The first equation relates to the specific angular momentum vector $\vec{h}$ and the specific mechanical energy $E$ of a particle in a central force field, where $\mu$ is the standard gravitational parameter, $v$ is the velocity of the particle, $r$ is the distance from the particle to the center of the force, and $\vec{r}$ is the position vector of the particle relative to the center of the force. The vector $\vec{e}$ in this equation represents the eccentricity vector of the particle's orbit.
	- On the other hand, the second equation appears to relate to the motion of a celestial body in a general relativistic context, where $M$ is the mass of the central body, $G$ is the gravitational constant, ${\bf v}$ is the velocity of the body, ${\bf h}$ is the specific angular momentum vector, and ${\bf r}$ is the position vector of the body relative to the central body. The vector ${\bf e}$ in this equation appears to represent the eccentricity vector of the body's orbit, and $a$ is likely the semimajor axis of the orbit.
	- These two equations have different forms and relate to different physical contexts, and therefore cannot be directly equated or considered equivalent.
- From the position and velocity of an orbiting body, calculate the true anomaly.
	- To calculate the true anomaly of an orbiting body, you can use the following formula:
	  
	  $$\tan\frac{\theta}{2}=\sqrt{\frac{1+e}{1-e}}\tan\frac{E}{2}$$
	  
	  where $\theta$ is the true anomaly, $e$ is the eccentricity of the orbit, and $E$ is the eccentric anomaly, which is related to the mean anomaly $M$ through Kepler's equation:
	  
	  $$M = E - e\sin E$$
	  
	  To calculate $E$, you can use the following iterative algorithm:
	- Set an initial value for $E_0 = M$.
	- For $i=1,2,3,...$, calculate:
	  $$E_i = M + e\sin E_{i-1}$$
	- Stop iterating when $|E_i-E_{i-1}|<\epsilon$, where $\epsilon$ is a small tolerance value.
	  
	  Once you have determined $E$, you can use the first equation to calculate $\theta$. Note that the sign of $\theta$ depends on the quadrant of the orbit that the body is currently in, so you may need to add or subtract $2\pi$ to ensure that $\theta$ is in the correct range.
- Orbital Position using #[[Simplex Interpolation]]
	- $Mx = x' = x + t \dot x$
	- $\displaystyle M = (x + t \dot x) / x$
	- $\displaystyle M = \frac{1}{|x|^2} (xx + t \dot x x)$
	- $\displaystyle M = 1 + \frac{t}{|x|^2} \dot x x$
	- $\displaystyle M = 1 + \frac{t}{|x|^2} \dot x \cdot x +  \frac{t}{|x|^2} \dot x \wedge x$
	- ...
- A New Approach to Differential Geometry Using Clifford's Geometric Algebra
	- D1:
	  $$r = \frac{b^2}{a (-e \cos θ + 1)}$$
	- D2:
	  $$r = \frac{(-e^2 + 1) a}{(-e \cos θ + 1)}$$
	- D3:
	  $$\sqrt{x + 1} = -\frac{1}{8} x^2 + \frac{1}{2} x + 1$$
	- D4:
	  $$(-x + 1)^{-1} = x + x^2 + 1$$
	  D5:
	  $$\sin (u + x) = \sin u - \frac{1}{2} x^2 \sin u + x \cos u$$
	  D6:
	  $$\cos (u + x) = \cos u - \frac{1}{2} x^2 \cos u - x \sin u$$
	- D7:
	  $$\frac{1}{2} r^2 \frac{dθ}{dt} = h$$
	- D9:
	  $$h = \frac{π a b}{T}$$
	- D10:
	  $$r = (-e^2 + 1) (e^2 \cos^2 θ + e \cos θ + 1) a$$
	- D11a:
	  $$(-e^2 + 1)^2 (e^2 \cos^2 θ + e \cos θ + 1)^2 \sqrt{e^2 + 1} \frac{dθ}{dt} = \frac{2 π \sqrt{e^2 + 1} b}{a T}$$
	- D1:
	  $$r = \frac{b^2}{a (-e \cos θ + 1)}$$
	- D2:
	  $$r = \frac{(-e^2 + 1) a}{(-e \cos θ + 1)}$$
	- D3:
	  $$\sqrt{x + 1} = -\frac{1}{8} x^2 + \frac{x}{2} + 1$$
	- D4:
	  $$(-x + 1)^{-1} = x + x^2 + 1$$
	  D5:
	  $$\sin (u + x) = \sin u - \frac{1}{2} x^2 \sin u + x \cos u$$
	  D6:
	  $$\cos (u + x) = \cos u - \frac{1}{2} x^2 \cos u - x \sin u$$
	- D7:
	  $$\displaystyle \frac{r^2 \frac{dθ}{dt}}{2} = h$$
	- D9:
	  $$h = \frac{π a b}{T}$$
	- D10:
	  $$r = (-e^2 + 1) (e^2 \cos^2 θ + e \cos θ + 1) a$$
	- D11a:
	  $$(-e^2 + 1)^2 (e^2 \cos^2 θ + e \cos θ + 1)^2 \sqrt{e^2 + 1} \frac{dθ}{dt} = \frac{2 π \sqrt{e^2 + 1} b}{a T}$$
	-