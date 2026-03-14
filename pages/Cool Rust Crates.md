- [`castaway`](https://docs.rs/castaway/) - specialization through type casting and matching
- [`paste`](https://docs.rs/paste/) - string manipulation of idents
- [`ref-cast`](https://docs.rs/ref_cast/) - cast `&T` to `&Wrapped(T)`
- `par` - session types for structured concurrency
- https://github.com/mickvangelderen/prevent_drop
	- compile time errors for dropped values
- `iroh` - QUIC networking (successor to TCP)
- `crabtime` - more powerful than `macro_rules!`, simpler than `proc-macro`
	- ```
	  eval! {
	  	let dims = 2..=3;
	      for dim in dims 2..=4 {
	      	let ident = format!("Vector{dim}");
	          
	          let fields = 'x'..='z'
	          	.take(dim)
	              .fold(String::new(), |mut output, x| {
	              	use std::io::Write;
	              	writeln!(&mut output, "pub {x}: f32,").unwrap();
	                  output
	              });
	              
	          output! {
	          	pub struct {{ident}} {
	              	{{fields}}
	              }
	          }
	      }	
	  }
	  ```
- `cargo-mobile2` - Android/iOS development
- `winit` - window and event loop
- `tao` - `winit` fork that uses `Gtk` on Linux
-