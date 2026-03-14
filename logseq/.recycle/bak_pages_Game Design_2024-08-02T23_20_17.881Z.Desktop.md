- Crate overview
	- `camera`
	- `clifford`
		- TODO reconfigure for conformal-style bases: $n_0 \cdot n_{\inf} = -1$,     $n_0 \wedge n_{\inf} = e_{-}e_{+}$
	- `num-dual`
		- TODO consider inverted structure:
			- `Vector<f64 + ε f64>` -> `Vector<f64> + ε Vector<f64>`
	- `curves`
		- TODO [Hermite splines](https://en.wikipedia.org/wiki/Cubic_Hermite_spline)
		- TODO shaping function for quintics
	- `orbital_mechanics2`
		- TODO deorbiting lookup tables
			- Deorbit state at time: acceleration, time
			- Deorbit time to reach distance (and state at that point): acceleration, distance
		- TODO intraorbit pathing
		  :LOGBOOK:
		  CLOCK: [2024-04-11 Thu 00:25:46]--[2024-04-11 Thu 00:25:46] =>  00:00:00
		  CLOCK: [2024-04-11 Thu 00:25:46]
		  :END:
			- model as angle between departure vector and orbit plane as a function of time and use newton's method to solve for the alignment time
			- compare phase with departure trajectory and state to determine delay before departure burn
		- TODO think about how to navigate through multi-star systems
	- `stellar_mechanics2`
		- TODO planet generation
			-
		- TODO `enum GalaxyShape { UniformSpherical, Elliptical }`
			- sample `GalaxyShape` to get ``
	- `planetary_dynamics2`
		- TODO so much to do here
	- `procedural_generation` - all good
	- `simplex` (noise)
		- TODO investigate progress
	- `simplex_interpolation` - all good
- Hermite splines for motion paths where control points are position and velocity
- Different AI difficulty settings are programmed the same, they just have different amounts of noise added to the derivative of the strategy layer when they're making decisions.
- Consider game state as a differentiable system, where input parameters can be repeatedly tested and averaged to calculate derivatives
	- Implications for training AI systems, and tweaking game balance
- Star Systems
  collapsed:: true
	- Tree-based data structure allows multi-star systems
	- Minimap-style system diagram using log-distances
	  collapsed:: true
		- Scaled distance, $s(d) = b \log(d)^{a}$, with $a$ and $b$ such that $s(1 \text{AU}) = 1$
			- $a=10$ seems to scale things nicely
	- Log-Normal distribution for star distance between max(star_radius) * 6 to, say, 1000 AU
	- Planet orbits unstable above $p_{planet} > 0.25 p_{star}$
- Stars
  collapsed:: true
	- [Luminous efficacy function](https://en.wikipedia.org/wiki/Luminous_efficiency_function)
		- Create lookup table from graph
	- [Black-body Radiation](https://en.wikipedia.org/wiki/Black-body_radiation)
		- Create function: `f(wavelength) -> W/um`
	- Create lookup table for K -> lum. eff.
		- Available sources don't go high enough
- Navigation
  collapsed:: true
	- Deorbiting:
		- TODO Align orbit plane with target vector
		  :LOGBOOK:
		  CLOCK: [2024-01-05 Fri 00:58:19]--[2024-01-05 Fri 00:58:19] =>  00:00:00
		  CLOCK: [2024-01-05 Fri 00:58:19]
		  :END:
		- DONE Determine acceleration to leave along target vector ([sheet](https://docs.google.com/spreadsheets/d/1wYxL_gRClJZcl0zHZMtvMYsbyELvo03cQ8MDMB-TopU/edit#gid=0))
		- Burn to midpoint, brake to destination
- Planets
	- Procedural Generation
		- Generate initial masses using a log-normal distribution
		- Scale planets by the following factors:
			- Frost line: smooth transition to simulate the accretion of ices (water, methane, ammonia)
			- Density gradient: there is more material nearer to the star, but each star will have a different gradient
				- A large, spread-out protoplanetary disc, or a small, dense one
				- \[ \rho(r) = \rho_0 \left( \frac{r}{r_0} \right)^{-p} \exp\left(-\left(\frac{r}{r_c}\right)^{q-p}\right) \]
				  where:
					- \( \rho(r) \) is the density at a distance \( r \) from the star.
					- \( \rho_0 \) is the density at a reference distance \( r_0 \) from the star.
					- \( p \) is the power-law exponent.
					- \( r_c \) is the characteristic radius beyond which the exponential taper begins to significantly affect the density distribution.
					- \( q \) is another exponent that determines the sharpness of the taper.
			- Protoplanetary disc: higher material density nearer to the star, more area to sweep farther from the star, with a lower accretive efficiency farther from the star.
	- Atmosphere
		- ${T_e}^4=\frac{S_o (1-A)} {4 \sigma \epsilon (1-f)}$
			- $f=1-\frac{S_o (1-A)} {4 \sigma \epsilon {T_e}^4}$
		- $f(g)=\frac{2}{1+e^{-g}}-1$
			- $f(0) = 0$, $f(\infty)=1$
			- $(f+1) (1+e^{-g})=2$
			- $e^{-g}=\frac{2}{(f+1)}-1$
			- $g = -\ln {(\frac{2}{(f+1)}-1)}$
		- $g(atmosphere) = ...$
	- Orbit
	- Surface
		- Triangulation: building a graph from vertex nodes
			- [half-edge data structures](https://jerryyin.info/geometry-processing-algorithms/half-edge/)
			- [delaunay triangulation](https://ianthehenry.com/posts/delaunay/)
		- Area of a triangle on a sphere:
			- Spherical excess:    $E = \theta_A + \theta_B + \theta_C - \pi$
			- Area of triangle:    $A = r^2 E$
		- Mapping spherical coordinates to barycentric coordinates, $r+s+t=1$
			- This is an approximation that works better for small triangles
			- $A_{sph} = \{\theta_A, \phi_A\}$
			- $F(r, s, t) = r A_{sph} + s B_{sph} + t C_{sph}$
		- Dunavant quadrature rules for triangular domains
			- $\displaystyle\int_A f(r, s, t)dA = A {\sum_{i=1}^{ng}} w_i f(r_i, s_i, t_i)$
		- 3D noise map
			- References
				- Texture and Modeling: A Procedural Approach (book)
					- Ridged multifractal
					- Look for papers published by the authors for more detail and further developments
				- [Terrain synthesis using noise](https://trepo.tuni.fi/handle/10024/101043) (paper)
				- Terrain Synthesis By-Example (paper)
				- Parametrically controlled terrain generation (paper)
				- A Survey of Procedural Methods for Terrain Modelling (paper)
			- `noise` crate with `SuperSimplex`
			- simplex noise elevation
				- TODO multiply successive octaves by current value to flatten low-lying areas
			- humidity:
				- based on prevailing winds, based on Coriolis effect
				- sample surroundings for water, measuring farther upwind than downwind
				- high elevations between water and position diminish humidity
			- temperature factors:
				- angle between orbital plane and angular momentum bivectors
				- stellar radiation
				- rotation speed (longer days mean larger amplitude)
			- Alternative: tessellated icosahedron with OpenSimplex
			- Generate noise functions for the various planetary attributes
				- Best for immutable properties
				- Create $n^3$ grid,
				- $PRNG(\text{planet seed},\text{attribute seed}, n) = PRNG(\text{planet seed} \land \text{attribute seed} \land n)$
			- Power functions affect distribution
				- $f(x) = x$ gives uniform distribution, $A = \frac 1 2$
				- $f(x) = x^{19}$ is zero nearly everywhere, $A = \frac 1 {20}$
		- Sphere tiling
		- Location-based division
			- Octree partition
			- Tessellated
				- Icosahedron?
					- Allow positioning and movement on subfaces
					- Intersection of 3 golden rectangles ($$1$$ by $$\frac{1+ \sqrt 5} 2$$)
				- Tetrahedron
- Cities
  collapsed:: true
	- Population
	- Demographics?
	- Culture
		- Model using large integers, where the values mutate periodically
		- Mutations spread via lines of communication and migration
		- Cultures can be compared to see how many bits they share
		- Similar cultures have better relations
	- Lon/Lat positions
- Hyperspace
  collapsed:: true
	- Attributes:
		- Consider as a hyperspatial 5th dimension
		- Deeper have higher local lightspeeds
		- Mass has lower specific inertia
			- Acceleration multiplied for non-inertial hyper-spatial engines
				- Ineffective in realspace compared to conventional engines, but powerful in hyperspace
			- Conventional thrust unaffected
		- Gravitational gradient limits depth
			- Hyper-limit around stars and planets
			- Shallow bands accessible in interplanetary space
			- Deeper bands accessible at distance from the star
		- Without active hyperdrive, matter returns to real-space, accelerating toward realspace like a cork in water
			- Collision with realspace is a bad thing
			- More powerful drives capable of maintaining greater hyperspatial displacement and faster translations into and out of hyperspace
		- Turbulence increases with depth?
			- 4D noise scaled according to depth
	- Forms:
		- Translation: moving objects entirely out of realspace
		- Tunneling: fold a region of realspace into hyperspace
			- Broadcast antenna: FTL communications through deep hyperspace bands
			- Hyper beacon: Navigational aid
			- Hyper-spatial scanners: FTL detection of hyper footprints
			- Inertial dampening: allow greater safe acceleration
		- Projection: create a hyper-spatial gradient across a region of space
			- Deflectors: fold glancing blows out of real-space, effectively presenting a smaller target
			- Armor hardening?
			- Hyper-spatial sails?
- Combining `physics_types` and `clifford`
  collapsed:: true
	- Strongly-typed units allow for type-safe unit conversion:
		- `pub struct Mass<T, U>(pub T)`
		- `pub struct Distance<T, U>(pub ga_3d::Vector<T>)`
		- `pub struct Distance<T, U>(pub pga_3d::Bivector<T>)`
		- `pub struct Transformation<T, U>(pub Motor<T, Unit>)`
			- ```
			  impl<T: Number, U: LengthUnit> Exp for Distance<T, U> {
			      type Output = Transformation<T, U>;
			      fn exp(self) -> Self::Output {
			      	let neg_half = Scalar::new(T::from_f64(0.5));
			          Transformation::new(
			              self.0.mul(neg_half).exp()
			          )
			      }
			  }
			  ```
	- Without specialization, we can't have concrete impls that overlap with blanket impls
		- This is solved by using a closed algebra of types, and not having operations on generic types (`T`)
	- `clifford` + `physics_types` -> `geometric_physics`
		- Include `cgmath` conversions
		- Basic types:
			- `Mass`, `Time`, `Length`, `Temperature`
		- Derived types:
			- `Duration` =  $\Delta$ `Time`
			- `Area` = `Length`$^2$
			- `Volume` = `Length`$^3$
			- `Density` = `Mass` / `Volume`
			- `Pressure` = `Force` / `Area`
			- `Energy` = `Force` * `Distance`
			- `MassRate` = $\Delta$ `Mass` / `Duration`
		- Vectorizable types
			- e.g.:
				- ```
				  pub struct Velocity3<T>(clifford::ga_3d::Vector<T>);
				  
				  impl<T> Velocity<T> {
				  	pub fn norm(self) -> Velocity<T> {
				      	Velocity(self.0.norm())
				      }
				  }
				  ```
			- `Distance` = $\Delta$ `Position`
			- `Velocity` = `Distance` / `Duration`
			- `Acceleration` = `Velocity` / `Duration`
			- `Force` = `Mass` * `Acceleration`
			- `Momentum` = `Mass` * `Velocity`
			- `Impulse` = $\Delta$ `Momentum`
			- `ImpulseRate` = `Impulse` / `Duration`
		- Bivectorizable types
			- `AngularMomentum` = `Distance` $\wedge$ `Momentum`
			- `AngularImpulse` = $\Delta$ `AngularMomentum`
	- This still feels like a misadventure in bike-shedding
- Random noise
	- [OpenSimplex noise](https://www.shadertoy.com/view/ttdGR8)
	- Stochastic process, brownian motion
		- https://en.wikipedia.org/wiki/Wiener_process#Brownian_scaling
- Data model
	- CRUD - Create, Read, Update, Delete
	- Commands: Delete, Create,
	- Systems: Update, Read, and issue Commands
		- Update: each data component can only be updated by one system
		- No cyclic dependencies: if updating `DataA` requires reading `DataB`, updating `DataB` cannot depend on reading `DataA`
	- System Scheduling
		- Systems have a definitive order, given by a system index
		- System sets describe a set of systems that do not have conflicting borrows
		- System sets are built so they can be run in parallel without overlapping mutable borrows
- Tech Stack
	- ![image.png](../assets/image_1695447838801_0.png)
	- [Fontello](https://fontello.com/) - icons as fonts
	-