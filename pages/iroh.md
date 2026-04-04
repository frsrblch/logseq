- ecosystem
	- `iroh`: endpoints, connections, relays, etc
	- `iroh-blobs`:
	- `iroh-gossip`: message dissemination
	- `iroh-docs`:
- `iroh-lighthouse`
	- Design 1: tasks communicating through channels
		- Pros: each task has one function
		- Cons: wiring it up is a bit of a pain
		- {{renderer excalidraw, excalidraw-2026-03-14-11-36-10}}
	- Design 2: supervisor monitoring a list of tasks
		- ```
		  enum Task {
		      AnnounceDht(JoinHandle<()>),
		      GetPeers(JoinHandle<Vec<IpAddr>>),
		  }
		  ```
-