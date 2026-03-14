- # Chapter 1: Geometric Algebra
	- ## 1-3. Frames and Matrices
		- Notation:
			- Exterior product
				- $A_n = a_1 \wedge ... \wedge a_n = (A^n)^{-1}$
				- $A^n = a^n \wedge ... \wedge a^1 = A_n^{-1}$
			- Remove one element from an exterior product
				- $A_n \setminus a_k = (-1)^{k-1} (a_1 \wedge ... \wedge \overset{\vee}{a_k} \wedge ... \wedge a_n)$
			- Replace one element with another in an exterior product
				- $A_n \setminus a_k \cup b = (a_1 \wedge ... \wedge a_{k-1} \wedge b \wedge a_{k+1} \wedge ... \wedge a_n)$
		- A frame $a_1$ .. $a_n$ can be orthogonalized to a set of $n$ vectors $c_k$ by:
			- $A_0 = 1$,   $A_1 = a_1$,   ...,   $A_n = a_1 \wedge ... \wedge a_n$
			- $c_k = \widetilde {A}_{k-1} A_k$
				- Dual by $A_k$ of the psuedoscalar $A_{k-1} of the vector space spanned by the preceing $k-1$ vectors
		- Reciprocal frames:
			- $a^k = (A_n \setminus a_k) A_n^{-1}$
		- Ex. Given a basis:
			- $B_n = e_1 \wedge (e_1 + e_2) \wedge (e_1 + e_2 + e_3) = e_{123}$
			- |1|2|3|
			  |$b_1 = e_1$|$b_2 = e_1 + e_2$ | $b_3= e_1 + e_2 + e_3$|
			  |$c_1 = 1 a_1 = a_1$|$c_2 = e_1 e_{12} = e_2$|$c_3 = e_{21} e_{123} = e_3$|
			  |$B_n \setminus b_1 = e_{13} + e_{23}$|$B_n \setminus b_2 = -e_{12} - e_{13}$|$B_n \setminus b_3 = e_{12}$|
			  |$b^1 = e_1 - e_2$|$b^2=e_2-e_3$|$b^3=e_3$|
			  |$b_1 \cdot b^1 = 1$|$b_2 \cdot b^2 = 1$|$b_3 \cdot b^3 = 1$|
			- Given $a$ in basis $e_i$, change to basis $b_i$
				- $a = 2 e_1 + 3 e_2 + 5 e_3 = \beta^i b_i$
				- $\beta^1 = (a \wedge b_2 \wedge b_3) / B_3 = -1$
				- $\beta^2 = (b_1 \wedge a \wedge b_3) / B_3 = -2$
				- $\beta^3 = (b_1 \wedge b_2 \wedge a) / B_3 = 5$
				- $a = -1 b_1 - 2 b_2 + 5 b_3$
		- Projection of $r$-vector $B_r$ into $\mathcal{G}(A_n)$:
			- $P_{A_n}(B_r) = (B_r \cdot A_n) A_n^{-1}$
		- To solve a vector equation of the form: $\displaystyle a = \beta^i b_i$
			- $\beta^k = (B_n \setminus b_k \cup a) B_n^{-1}$
		- To solve $n$ linear scalar equations in $n$ unknowns: $\alpha^j = b_k^j \beta^k$ for $j,k = 1, ... , n$
			- Use the convention that summation over repeated pairs of upper and lower indices
			- $a=\alpha^j a_j$,   $b_k = b_k^j a_j$
			- $\alpha^j = a^j \cdot a$,   $b_k^j = a^j \cdot b_k$
			- $\displaystyle\beta^k = \frac{(B_n \setminus b_k \cup a) \cdot A^n}{B_n \cdot A^n}$
		- Example: Invert a matrix
		  :LOGBOOK:
		  CLOCK: [2022-11-12 Sat 13:01:22]--[2022-11-12 Sat 13:01:23] =>  00:00:01
		  CLOCK: [2022-11-12 Sat 13:01:24]--[2022-11-12 Sat 13:01:24] =>  00:00:00
		  CLOCK: [2022-11-12 Sat 13:01:30]--[2022-11-12 Sat 13:01:31] =>  00:00:01
		  :END:
			- $[\alpha^j]=[b_k^j][\beta^k]$
			- $$
			  B
			  =
			  \left[\begin{array}{ccc}
			  1 & -1 & 2\\
			  1 & 2 & 1\\
			  1 & 0 & -1
			  \end{array}\right]
			  $$
			- $adj(b_j^i) = B_n \setminus b_i \cup a_j \cdot A^n$
			- $B \text{adj}(B) = \det(B) I$
			-
			- $$B^{-1} = \frac{1}{\det(B)} \text{adj}(B) = \frac{1}{\det(B)} \left[\begin{array}{ccc}
			  adj(b_1^1) & adj(b_2^1) & adj(b_3^1)\\
			  adj(b_1^2) & adj(b_2^2) & adj(b_3^2)\\
			  adj(b_1^3) & adj(b_2^3) & adj(b_3^3)\\
			  \end{array}\right]$$
			- $$
			  B^{-1}
			  =-\frac{1}{8}
			  \left[\begin{array}{ccc}
			  -2 & -1 & -5\\
			  2 & -3 & 1\\
			  -2 & -1 & 3
			  \end{array}\right]
			  $$
- # Chapter 2: Differentiation
	- ## 2-1. Differentiation by Vectors
		- Let $F(\tau)$ be a multivector-valued function on an $n$-dimensional vector space $\mathcal A_n$
		- $\partial_\tau F(\tau) = \partial F / \partial \tau$
		- For vector $a$ in $\mathcal A_n$, the derivative of $F$ in the direction of $a$, or the $a$-derivative of $F$ at $x$ is given by 
		  $$\displaystyle a \cdot \partial F(x) = \frac{\partial F(x + \tau a)}{\partial \tau} = \underset {\tau\rightarrow 0} \lim \frac{F(x+\tau a) - F(x)}{\tau}$$
		- If $F$ is defined and continuously differentiable at $x$, then $a\cdot \partial F(x)$ is a linear function of a
		  $$\underline F(x, a) = F_a(x) = a \cdot \partial F(x)$$
		  $$\underline F = \underline F(a) = F_a = a \cdot \partial F$$
			- This is the first differential or simply the differential of $F$
			- $\partial_x = \partial_i e_i$ has the properties of a vector
			- $a \cdot \partial_x$ is the $a$-derivative operator
		- $\partial_x$ has the properties:
			- $I \wedge \partial_x = 0$
			- $I \partial_x = I \cdot \partial_x$
		- Project into basis ${a^k}$:     $\displaystyle\partial_x = P(\partial_x) = \underset k \sum a^k a_k \cdot \partial_x$
		- $\underline F(a) = a \cdot \partial F = \frac 1 2 (a \partial F + \dot \partial a \dot F)$
		- $a \cdot \partial_x = P(a) \cdot \partial_x$
			- The directional derivative defines the differential $\underline F (b)$ for all vectors $b$ and not just elements of $\mathcal G^I (I)$
		- $a \cdot \partial$ preserves grades:    $a \cdot \partial \langle F \rangle_r = \langle a \cdot \partial F \rangle_r$
		- Linearity:
			- $\underline F(a + b) = \underline F(a) + \underline F(b)$
			- $\underline F (\lambda a) = \lambda \underline F(a)$
			- $a \cdot \partial (F + G) = a\cdot \partial F + a\cdot \partial G$
			- $\underline{F+G} = \underline F + \underline G$
		- Product rule:
			- $a \cdot \partial (F G) = (a\cdot \partial F) G + F (a\cdot \partial G)$
			- $\underline{FG} = \underline F G + F \underline G$
		- Chain rule:
			- Given $F(x) = G(f(x))$
			- $a \cdot \partial F = a \cdot \partial_x G(f(x)) = \underline f(a) \cdot \partial G$
			- $\underline F(x, a) = \underline G(f(x), \underline f(x, a))$
			- $\underline F(a) = \underline G(\underline f(a))$
			- The differential of a composite function is the composite of differentials
		- Second derivative:
			- $F_{ab} (x) = b \cdot \dot \partial a \cdot \partial \dot F(x)$
			- $F_{ab} = b \cdot \dot \partial a \cdot \partial \dot F$
			- Integrability condition: $F_{ab} = F_{ba}$
		- Differential of the identity function, $F(x) = x$
			- $a \cdot \partial_x x = P(a) = \partial_x(x \cdot a)$
			- For base vectors $a_k$:     $a_k \cdot \partial x = P(a_k) = a_k$
			- $\partial_x (x \cdot a) = \underset k \sum a^k a_k \cdot \partial_x(c \cdot a) = \underset k \sum a^k a_k \cdot a =  P(a)$
			- $\partial_x = P(\partial_x) = \partial_a a \cdot \partial_x$
			- $\partial_x F(x) = \partial_a a \cdot \partial_x F(x) = \partial_a \underline F(x, a)$
			- $\partial F = \underline{\partial F}$
			- Differential ($\partial_a F$) is grade preserving, derivative ($\partial_x F$) is not
		- $\partial F = \partial \cdot F + \partial \wedge F$
			- If $F = \phi(x)$ is scalar-valued then $\partial \cdot \phi = 0$ and $\partial\phi = \partial\wedge\phi$
				- This is the gradient of $\phi$
			- Divergence of F:    $\partial \cdot F$
			- Curl of F:    $\partial \wedge F$
		- $\partial(F + G) = \partial F + \partial G$
		- $\partial(FG) = \underline \partial \underline F G + \underline\partial F \underline G$
			- $\displaystyle\dot \partial F \dot G = \partial_y(F(x)G(y)) |_{y=x}$
			- $\partial$ only differentiates quantities to its right, thus $F \partial G = F \dot \partial \dot G$
				- If otherwise, indicate with dots $\dot F \dot \partial \dot G = \dot F \dot \partial G + F \dot \partial \dot G$
		- Adjoint of a function:
			- The differential, $\underline f(a)$ of a vector-valued function $x' = f(x)$ is a vector-valued linear function of its differential argument $a$
			- The adjoint of $f$:    $\overline f(a') = \underline \partial \underline f \cdot a' = \partial f \cdot a'$
				- $\overline f(x, a') = \partial_a \underline f(x, a) \cdot a' = \partial_x f(x) \cdot a'$
			- Let $P$ be the projection into the range of $f$ and $P'$ be a projection into the range of $\underline f$
				- $P \overline f P'(a') = \overline f (a')$
				- $P' \underline f P(a) = \underline f(a)$
		- Chain rule for the derivative:   If $F(x) = G(f(x))$ then:   $\partial_x F(x) = \overline f(\partial_{x'})G(x')$
			- The change of variables from $x$ to $x' = f(x)$ induces the adjoint linear transformation of the derivative $\partial_{x'}$ to    $\partial_x = \overline f (\partial_{x'})$
		- If we differentiate the funtion $F = F(x)$ twice:
			- $\partial_x^2 = F(x) = \partial_b \partial_a F_{ab} = (\partial_b \cdot \partial_a + \partial_b \wedge \partial_a) F_{ab}$
			- By the integrability condition, we have:
				- $\partial_x \wedge \partial_x F(x) = 0$
				- The Laplacian: $\partial_x^2 = \partial_x \cdot \partial_x$
		- Derivatives of elementary functions where $\partial = \partial_x$
			- $\partial_x |x|^2 = \partial_x x^2 = 2 P(x) = 2x$  (product rule)
			- $\partial_x \wedge x = 0$  (integrability condition)
			- $\partial_x x = \partial_x \cdot x = n$
			- $\partial_x |x|^k = k|x|^{k-2} x$
			- $\displaystyle \partial_x \left(\frac{x}{|x|^k}\right) = \frac{n-k}{|x|^k}$
			- $\partial_x \log |x| = \frac{x}{x^2} = x^{-1}$
			- If $A=P(A)=\langle A\rangle_r$
				- $\dot \partial_x (\dot x \cdot A) = (A \cdot \partial_x) x = rA$
					- Compare to projection:     $A^{-1} A \cdot \partial x = P_A(\partial)x = \partial P_A(x) = r$
					- And consider the pseudoscalar:     $I^{-1} I \cdot \partial x = P_I(\partial)x = \partial P_I(x) = n$
				- $\dot \partial_x (\dot x \wedge A) = (A \wedge \partial_x) x = (n-r)A$
					- Project $A^*$:    $A^{-1} A \wedge \partial x = (IA)^{-1} (IA) \cdot \partial x = P_{IA}(\partial)x = \partial P_{IA}(x) = n-r$
				- $\displaystyle\dot \partial_x A \dot x = \underset k \sum a^k A a_k = (-1)^r(n-2r)A$
		- The algebraic properties of vectors apply to the derivative
			- $b \cdot (c \wedge a) = (b \cdot c) a - c (a \cdot b)$
			- $b \cdot (\partial \wedge a) = b \cdot \partial a - \dot \partial \dot a \cdot b$
			- $\partial(a \cdot b) = (a \cdot \partial) b + (b \cdot \partial) a - a \cdot (\partial \wedge b) - b \cdot (\partial \wedge a)$
			- Lie bracket:
				- $[a, b] = \partial \cdot (a \wedge b) - b (\partial \cdot a) + a (\partial \cdot b)$
				- where $[a, b] = a \cdot \partial b - b \cdot \partial a$
			- Jacobi identity:      $a \cdot (b \wedge c) + b \cdot (c \wedge a) + c \cdot (a \wedge b) = 0$
				- $a \cdot (\partial \wedge b) = \dot b \cdot (\dot \partial \wedge a) + \dot\partial \cdot (a \wedge \dot b)$
				                     $= (a \wedge \partial) \cdot b + a \cdot \partial b - a \partial \cdot b$
				- $\partial \cdot (a \wedge b) = \dot a (\dot \partial \wedge \dot b) - \dot b \cdot (\dot \partial \wedge \dot a)$
				                     $= (b \wedge \partial) \cdot a + a \cdot (\partial \wedge b) - (a \wedge \partial) \cdot b - b\cdot (\partial \wedge a)$
	- ## 2-2. Multivector Derivatives, Differentials, and Adjoints
		- Let $F = F(X)$ be a function defined on $\mathcal G(I)$ with unit pseudoscalar $I = \langle I \rangle_n$
		- Let $P(A) = (A \cdot I) \cdot \tilde I$ be the projection of a given multivector A into $\mathcal G(I)$
		- The $A$-derivative of $F$ at $X$ is defined by:          $A * \partial_X F(X) = \partial_\tau F(X + \tau P(A)) | _{\tau = 0}$
			- Where $*$ is the scalar product, such that $A*B = \langle AB \rangle$
		- $\underline F = \underline F(A) = \underline F(X, A) = F_A(X) = A * \partial F$
		- Properties:
			- $\underline F(A) = \underline F(P(A))$
			- $A * \partial \langle F \rangle_r = \langle A * \partial F \rangle_r = \langle \underline F(A) \rangle_r$
			- $\underline F(A+B) = \underline F(A) + \underline F(B)$
			- $\underline F(\lambda A) = \lambda \underline F(A)$     if $\lambda = \langle \lambda \rangle$
			- $A * \partial (F + G) = A * \partial F + A * \partial G$
			- $A * \partial (FG) = (A * \partial F) G + F(A * \partial G)$
		- If $X' = f(X)$ is a function defined on $\mathcal G(I)$ with values in $\mathcal G(I')$ where $I' = \langle I' \rangle_n$ then differentiation of the composite function is given by the chain rule
			- $A * \partial F = A * \partial_X G(f(X)) = \underline f(A) * \partial G$
			- Or, equivalently:    $\underline F(A) = \underline G(\underline f(A))$
		- The second differential of $F = F(X)$ defined by:
			- $F_{AB} = F_{AB}(X) = B * \dot \partial A * \partial \dot F$
		- Satisfies the integrability condition:     $F_{AB}(X) = F_{BA}(X)$
		- The derivative $\partial = \partial_X$ with respect to a variable $X$ in $\mathcal G(I)$ has the algebraic properties of a multivector in $\mathcal G(I) where ${a_J}$ is a basis for $\mathcal G(I)$$
			- $\partial X = P(\partial_X) = \underset J \sum a^J a_J * \partial_X$
			- $\displaystyle\partial_X = \underset r \sum \partial_{\langle X \rangle_r}$
		- The derivative wrt a variable $X_{\bar r} = \langle X \rangle_r$ in $\mathcal G^r(I)$
			- $\displaystyle\partial_{\langle X \rangle_r} = \langle \partial_X \rangle_r = \underset J \sum \langle a^J \rangle_r \langle a_J \rangle_r * \partial_X$   is
			- $\displaystyle\partial = \underset r \sum \partial_{\bar r}$
			- $\displaystyle A*\partial = \underset r \sum A_{\bar r} * \partial = \underset r \sum A * \partial_{\bar r} = \underset r \sum A_{\bar r} * \partial_{\bar r}$
		- The derivative can be obtained from the differential by
			- $\partial_X = \partial_A A * \partial_X$
			- $\partial F = \partial_X F(X) = \partial_A \underline F(X, A) = \underline \partial \underline F$
		- The adjoint of $F = F(X)$:
			- $\overline F = \overline F(A') = \underline {\partial F} *A' = \partial F * A'$
			- $B * \overline F(A) = \underline F(B) * A$
		- p55
-