Fundamental tool of concurrency control
Obtain lock before accessing item
	What if conflicting lock is locked? 
		Shared lock: conflicts with exclusive locks
		Exclusive lock: conflicts with all other kinds of locks
	Concurrency control manager maintains lock table