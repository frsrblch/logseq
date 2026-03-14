- [Learn Prolog Now](https://www.let.rug.nl/bos/lpn//lpnpage.php?pageid=online)
- https://www.scryer.pl/
	- SWI-Prolog does not support CLP over integers
- Import library:
	- ```
	  :- use_module(library(clpz)).
	  :- use_module(library(lists)).
	  
	  :- use_module(library(clpBNR)).
	  ```
	- `clpz`: constrained logic programming over intergers
	- `lists`: working with lists
	- `simplex`: solve linear programming problems
	- `cplBNR`: constrained logic programming over real numbers
		- approximates floating point numbers using ranges
		- https://ridgeworks.github.io/BNRProlog-Papers/
-
-
-
-