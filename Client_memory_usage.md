That's not entirely true.

GPGNet reserves 180 mb of virtual memory for itself. You can check this
by activating the "commit size" column in the task manager. That's the
amount of virtual memory that is reserved for use by a process.

FAF only reserves only 80-90 mb, but use it immediatly in order to be as
responsive as possible.

While GPGNet will use huge amount of memory in certain conditions (try
to open the world map, or many windows - leader boards, vault, ...), the
memory used by FAF will stay very stable.

It's a memory versus performance issue : Even if GPGNet will use less
memory with a minimal use of features, it will be always slower than
FAF. And for the same amount of features, FAF will be faster and will
use less memory.