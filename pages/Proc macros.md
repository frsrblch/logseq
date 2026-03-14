- Nine Rules for Creating Proc Macros
	- [Article](https://towardsdatascience.com/nine-rules-for-creating-procedural-macros-in-rust-595aa476a7ff)
	- [Video](https://www.youtube.com/watch?v=DMLBBZBlKis)
	- 1. Split project into 3 crates:
		- Top level project, which exports the macro
		- "Derive" project, which converts `proc_macro::TokenStream` to `proc_macro2::TokenStream` and calls the core project, and converts the returned value to from`pm2::TS` to `pm::TS`
		- Core project, which contains the logic of expanding the macro
			- Works only with `proc_macro2::TokenStream`
		- Three crates form a `[workspace]`, which allows commands to be run across all members, share an output directory
	- 2. Convert freely between `TokenStream`, `String`, syntax tree (`syn` types), and literal code
		- | To | From | Method |
		  | string of code | literal code | std::stringify!() |
		  | string of code | syntax tree | quote!(\#syntax_tree).to_string() |
		  | string of code | TokenStream | .to_string() |
		  | string of syntax | literal code | format!("{:?}",parse2::<SynType>(quote! {...}).expect(...) |
		  | string of syntax | syntax tree | format!("{:?}"),…), format!("{:\#?}"),…) |
		  | string of tokens | literal code | format!("{:?}",quote! {...}) |
		  | string of tokens | TokenStream | format!("{:?}"),…), format!("{:#?}"),…) |
		  | syn::Error | TokenStream | .to_compile_error() [see Rule \#7] |
		  | syntax tree | literal code | parse_quote!(…) |
		  | syntax tree | proc_macro::TokenStream | parse_macro_input!(…), parse |
		  | syntax tree | string of code | parse_str(…) |
		  | syntax tree | TokenStream | parse2::<SynType>(…), etc |
		  | TokenStream | literal code | quote!(…) |
		  | TokenStream | string of code | parse_str(…) |
		  | TokenStream | syntrax tree | quote!(\#syntax_tree) or .to_token_stream(), |
		  | TokenStream | TokenStream | .into(), ::from(...) [see Rule \#1] |
	- 3. Create debuggable unit tests (in the core crate)
	- 4. Understand Rust syntax trees
		- Use [AST Explorer](https://astexplorer.net/) and `syn` documentation to understand syntax trees
	- 5. Construct syntax trees with `parse_quote!` and Rust's `Struct { ..remaining_fields }` syntax
		- This is a lot slower than the `quote!` macro
	- 6. Recursively manipulate syntax trees (`syn::Fold`)
	- 7. Use `proc_macro_error` to return ergonomic and testable errors
	- 8. Test integration including UI with`trybuild`
		- test the macro on real code
-