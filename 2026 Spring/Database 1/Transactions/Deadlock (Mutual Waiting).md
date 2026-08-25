Where a lock is implemented but both are waiting for the other to unlock
	Does not release until transaction is complete, but how do you progress if both are locked
		A lot of systems will try to detect it
		Another thing that you could do is put a timer (timeout) if deadlock happens. Not the best solution, timeout interval is hard to determine.
		If we do use locks, we should set different timeout timers, as time interval may have to increase for rollback issues