- Bulk and Weight
	- `Bulk` + `Weight` = `Whole`
	- `Whole` - `Whole` = `Zero`
- Type set for `PGA<T>`
	- 1. `Zero`
	  2. `T` (scalar)
	  3. `Antiscalar<T>`
	  4. `Point<T, Pt: Through>`
	  5. `Line<T, Ln: Through>`
	  6. `Plane<T, Pl: Through>`
	  7. `Scalars<T, Sc: Through>` (magnitude?)
	  8. `Motor<T, Sc: Through, Ln: Through>`
	  9. `Flector<T, Pt: Through, Pl: Through>`
- Products
	- `*Product<Rhs>` - `Scalar-`, `Vector-`, `Bivector-`, `Trivector-`
	- Lhs = `Scalars` (4)
		- Rhs = `Scalars`
			- `Scalar`
		- Rhs = `Point`
			- `Vector`
		- Rhs = `Line`
			- `Bivector`
		- Rhs = `Plane`
			- `Trivector`
	- Lhs = `Point` (8)
		- Rhs = `Scalars`
			- `Vector`
			- `Trivector`
		- Rhs = `Point`
			- `Scalar`
			- `Bivector`
		- Rhs = `Line`
			- `Vector`
			- `Trivector`
		- Rhs = `Plane`
			- `Scalar`
			- `Bivector`
	- Lhs = `Line` (7)
		- Rhs = `Scalars`
			- `Bivector`
		- Rhs = `Point`
			- `Vector`
			- `Trivector`
		- Rhs = `Line`
			- `Scalar`
			- `Bivector`
		- Rhs = `Plane`
			- `Vector`
			- `Trivector`
	- Lhs = `Plane` (8)
		- Rhs = `Scalars`
			- `Vector`
			- `Trivector`
		- Rhs = `Point`
			- `Scalar`
			- `Bivector`
		- Rhs = `Line`
			- `Vector`
			- `Trivector`
		- Rhs = `Plane`
			- `Scalar`
			- `Bivector`
- Binary Ops
	- 1. Wedge
	  2. Dot
	  3. Antiwedge
	  4. Antidot
	  5. Geometric Product
	  6. Geometric Antiproduct
	  7. Commutators?
- Unary Ops
	- 1. Right Complement
	  2. Left Complement
	  3. Reverse
	  4. Antireverse
- Conformal Geometric Algebra: $$\mathbb{R}^{n+1, 1}$$
	- R3 dims: $$e_1, e_2, e_3$$
	- Null cone bases:
		- $$e \cdot e = 1$$
		- $$\bar e \cdot \bar e = -1$$
	- Origin: $$n = \frac{1}{2} (e + \bar e) = \bold o$$
		- $$n \cdot n = 0$$
	- Infinity: $$\bar n = \bar e - e = \bold \infty$$
		- $$\bar n \cdot \bar n = 0$$
		- $$n \cdot \bar n = -1$$
		- $$n \wedge \bar n = \frac{1}{2} (e + \bar e) \wedge (\bar e - e) = \frac{1}{2} ( e \bar e - \bar e e) = e \bar e$$
	- Pseudoscalar: $$I_3 = e_{123}$$
	- Point: $$\bold p_x = \bold o + \bold x + \frac{1}{2} x^2 \bold \infty$$
	- Point pair:
		- $$\bold p_x \wedge \bold p_y = \bold x \wedge \bold y + (\bold x - \bold y) \wedge \bold o + \frac{1}{2} (y^2 \bold x - x^2 \bold y) \wedge \bold \infty + \frac{1}{2} (y^2 - x^2) \bold o \wedge \bold \infty$$
-
	-