- Mean anomaly:
	- Anomaly offset: $$M_0$$
	- Orbital period: $$p_o$$
	- Time index: $$t$$
	  $$M = \tau t / p_o + M_0$$
- Eccentric anomaly  $$E$$, solved using Newton-Raphson method:
	- Eccentricity: $$e$$
	- Initial:
	  $$E_0 = \frac{M + e \sin M}{(1 - \sin(M + e) + \sin M)} $$
	- Iterative:
	  $$E_n = \frac{E_{n-1} - e  \sin E_{n-1} - M}{1 - e \cos E_{n-1}}$$
- True anomaly:
	- Anomaly:
	  $$A = \cos^{-1} {\frac{\cos E - e}{1-e-\cos E}}$$
	- True anomaly:
	  \begin{equation}
	  T = \begin{cases}
	         \tau - A & \text{for} E \mod \tau \in [\pi, \tau) \\
	         A & \text{for} E \mod \tau \in [0, \pi) \\
	       \end{cases}
	  \end{equation}
- Gravitational sphere of influence:
	-
	  $$r_{SOI} \approx a *\left(\frac{m}{M}\right)^{2/5}$$
- Roche limit sets the minimum orbital distance of natural satellites, below which they are ripped apart by tidal forces