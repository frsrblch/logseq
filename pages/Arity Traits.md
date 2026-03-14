- ```
  pub trait Unary<T> {
      type Output;
      fn op(value: T) -> Self::Output;
  }
  
  pub trait Binary<T, U> {
  	type Output;
      fn op(lhs: T, rhs: U) -> Self::Output;
  }
  ```
- Multivectors: `std`, scalars: `std`
	- Current approach
	- Requires `Scalar<T>` to implement binary ops
- Multivectors: `arity`, scalars: `std`
	- Allows simple trait bounds on scalar types
	- Does not require `Scalar<T>`
		- This simple wrapper type results in clunky syntax and requires a lot of mindless trait implementation
	- Allows `foo(bar, baz)` syntax
- Multivectors: `arity`, scalars: `arity`
	- Verbose `where` clause due to `Add: Binary<T, U, Output = V>` that can't be part of a supertrait like `geo_traits::Numbers<U>`
	- Calling `mul(lhs.x, rhs.y)` causes infinite recursion without specifying type parameters
- Multivectors: `std`, scalars: `arity`
	- Does not require `Scalar<T>`
	- Verbose `where` clause due to `Add: Binary<T, U, Output = V>` that can't be part of a supertrait like `geo_traits::Numbers<U>`