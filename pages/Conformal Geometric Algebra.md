- 5D geometric algebra of $$\mathbb R_{4,1}$$
  (Taken from the Appendix of Geometric Algebra in Practice)
- **Section 21.2.1** Representing Euclidean points in Minkowski space
	- Euclidean point: $$\bold x = x_1 e_1 + x_2 e_2 + x_3 e_3$$
	- Extends the homogeneous model: $$x = e_0 + \bold x$$
	- Adds two basis vectors: $$n_0$$ and $$n_\infty$$
		- Point at the origin: $$n_0$$
		- Point at infinity: $$n_\infty$$
	- Point representation: $$x = n_0 + \bold x + \frac 1 2 || \bold x || ^2 n_\infty$$
		- Unit-weight points: $$x \cdot n_\infty = -1$$
	- Caley table of 
	  |$$\cdot$$|$$n_0$$|$$\bold x$$|$$n_\infty$$|
	  |---:|:---:|:---:|:---:|
	  |$$n_0$$|0|0|-1|
	  |$$\bold x$$|0|$$x \cdot x$$|0|
	  |$$n_\infty$$|-1|0|0|
	- Alternative basis vectors:
		- Positive square:
		      $\sigma_+ = n_0 - \frac 1 2 n_\infty$ 
		      $\sigma_+^2 = +1$
		- Negative square:
		      $\sigma_- = n_0 + \frac 1 2 n_\infty$
		      $\sigma_-^2 = -1$
		- Or, conversely:
		      $n_0 = \frac 1 2 (\sigma_+ + \sigma_-)$
		      $n_\infty = \sigma_- - \sigma_+$
		- Because there are 4 basis vectors squaring to $$+1$$ and one squaring to $$-1$$, we donote this space as $$\mathbb R_{4, 1}$$
		- Dot product encodes the squared Euclidean distance
		  $x \cdot y = (n_0 + \bold x + \frac 1 2 || \bold x || ^2 n_\infty) \cdot (n_0 + \bold y + \frac 1 2 || \bold y || ^2 n_\infty)$
		           $=(0 + 0-\frac 1 2 ||\bold y||^2) + (0 + \bold x \cdot \bold y + 0) + (-\frac 1 2 || \bold x||^2 + 0 + 0)$
		           $=-\frac 1 2 (\bold x - \bold y)\cdot(\bold x - \bold y)$
		           $=-\frac 1 2 || \bold x - \bold y||^2$
		-
			- Since points have zero distance to themselves: $$x \cdot x = 0$$
		- The vectors in conformal space represent planes and spheres
		- Sphere with center $$C$$ and radius $$\rho$$ in Euclidean space
		  $$\sigma = \alpha(c - \frac 1 2 \rho^2 n_\infty)$$
			- Center $$c$$, radius $$\rho$$, and weight $$\alpha$$, through the equation $$x \cdot \sigma = 0$$
			- A point $$X$$ on such as sphere would satisfy $$||\bold x - \bold c||^2 = \rho^2$$, therefore  $$x \cdot c = -\frac 1 2 \rho^2$$
			- A point is just a sphere with zero radius
		- Plane is a [degenerate](https://en.wikipedia.org/wiki/Degeneracy_(mathematics)) case of a sphere with unit normal $$\bold n$$ and oriented distance from the origin $$\delta$$
		  $$\pi = \alpha(\bold n + \delta n_\infty)$$
			- Has no $$n_0$$ component and therefore satisfies  $$n_\infty \cdot \pi = 0$$
- **Section 21.2.2** Orthogonal Transformations as Multiple Reflections in a Sandwiching Representation
	- Suppose that we want to reflect Euclidean vector $$\bold x$$ in a plane through the origin with normal vector $$\bold a$$:
		- Awkward linear transformation:  $$\bold x \mapsto \bold x - 2(\bold x \cdot \bold a) \bold a / (\bold a \cdot \bold a)$$
		- Dot product is the symmetric part of the more fundamental geometric product: 
		  $$\bold a \cdot \bold x = \frac 1 2 (\bold{ax} + \bold{xa})$$
		- The geometric product is [bilinear](https://en.wikipedia.org/wiki/Bilinear_form) and associative, but not necessarily commutative
			- $||\bold x||^2 = \bold x \cdot \bold x = \bold{xx} = \bold x^2$
		- Vectors have a unique inverse such that  $$\bold {xx}^{-1}= \bold x^{-1} \bold x = 1 $$
		- $$\bold x^{-1} = \frac {\bold x}{\bold x^2}$$
		- Reflection in the hyperplane with normal $\bold a$$:   $$\bold x \mapsto-\bold{axa}^{-1}$$
		- Embedding this in CGA gives:   $$x \mapsto - \bold a x \bold a^{-1}$$
			- The point at the origin and at infinity are not affected by this transformation
	- Two rotations is a rotation, so given a second hyperplane $$\bold b$$ at the origin:   $$x \mapsto (\bold {ba}) x (\bold {ba})^{-1}$$
		- The intersection of $$\bold a$$ and $$\bold b$$ through the origin is the axis of rotation
		- These operators are called **versors** or, when unitized, **rotors**
		- They can be applied to other elements, such as lines and circles
- **Section 21.2.3** Constructing Elements by Anti-symmetry
	- Outer product is the anti-symmetric part of the geometric product
	  $$\bold x \wedge \bold a = \frac 1 2 (\bold{xa} - \bold{ax})$$
		- It follows that:
		      $\bold x \wedge \bold a = - \bold a \wedge \bold x$
		      $\bold x \wedge \bold x = 0$
	- For parallel vectors:
	      $\bold {xa} = \bold {ax}$
	- For orthogonal vectors:
	      $\bold {xa} = -\bold {ax}$
	      $\bold x \cdot \bold a = 0$
	- Can be extended to multiple terms:    $\bold a \wedge \bold b \wedge \bold c = \frac 1 2 (\bold {abc} - \bold {cba}) = \det([\bold {abc}])  \bold e_1 \wedge \bold e_2 \wedge \bold e_3$
	- In the conformal model, $$a \wedge b$$ represents an oriented point-pair
		- If $$x \wedge a \wedge b  = 0$$, $x$ is either $a$ or $b$
	- Oriented circle:  $a \wedge b \wedge c$
	- Oriented sphere:  $a \wedge b \wedge c \wedge d$
	- These are "flats" if one of the points is $n_\infty$
		- Flat point:  $a \wedge n_\infty$
		- Line:  $a \wedge b \wedge n_\infty$
		- Plane:  $a \wedge b \wedge c \wedge n_\infty$
- **Section 21.2.4** Dual Specification of Elements Permits Intersection
	- The orthogonality demand $x \cdot (c - \frac 1 2 \rho^2 n_\infty) = 0$ is equivalent to $x$ laying on a sphere with center $c$ and radius $\rho$
		- If $x$ is on $\sigma$, the Euclidean distance between them is zero?
	- Duality: complementation through division by the pseudoscalar
		- Division by pseudoscalar is multiplication by the inverse:
		- In 3D Euclidean space:
		      $\bold I_3 = \bold e_1 \wedge \bold e_2 \wedge \bold e_3 = \bold e_1 \bold e_2 \bold e_3 = \bold e_{123}$
		      $\bold I_3^{-1} = \bold e_3 \wedge \bold e_2 \wedge \bold e_1 = \bold e_3 \bold e_2 \bold e_1 = \bold e_{321} = -\bold I_3$
		      $\bold I_3 \bold I_3^{-1} = \bold I_3^{-1} \bold I_3 = 1$
		- In conformal space:  $I_{4,1}^{-1} = n_0 \wedge \bold I_3^{-1} \wedge n_\infty = -I_{4,1}$
	- Dualization:  $A^* = A I_n^{-1}$
		- Returns an element orthogonal to the input
	- Meet (intersection) of A and B:  $A \cap B$
		- $(A \cap B)^* = B^* \wedge A^*$
	- Extension of the inner product:  $(A \cdot B)^* = (A \wedge B^*)$
		- When arguments of the inner product are the same grade, the result coincides with the scalar product  $A * B = \langle AB \rangle_0 = \langle AB \rangle$  (no zero implies scalar)
	- Orthogonal projection of $X$ onto $B$:  $$X \mapsto (X \cdot B^{-1})\cdot B$$
		- E.g., projecting a line onto a sphere produces a great circle
	-