# cheney-and-mark-sweep
## compare cheney's algorithm and Mark-compact algorithm and demonstration which is  better and why? And the comparison between mark-sweep and cheney's algorithm with pseudo code for implementing cheney's algorithm, C++ code 
## mark and compact
In computer science, a mark-compact algorithm is a type of garbage collection algorithm used to reclaim unreachable memory. Mark-compact algorithms can be regarded as a combination of the mark-sweep algorithm and Cheney's copying algorithm.This address the fragmentation caused by mark-sweep, which leads to significantly more efficient future allocations via the use of a “bump” allocator (similar to how a stack works), but adds on extra time and processing while GC is running because of the extra iteration(s).

## mark and sweep
the earliest and most basic garbage collection algorithm is Mark-Sweep garbage collection - or a copy collector , and most modern algorithms are a variant on it. Mark-Sweep is a “stop-the world” collector, which means that at some point when the program requests memory and none is available, the program is stopped and a full garbage collection is performed to free up space.
## cheney's copy algorithm
Cheney’s Algorithm is a subset of garbage collectors known as copying collectors. In copying collectors, reachable objects are relocated from one address to another during a collection. Available memory is divided into two equal-size regions called the from-space and the to-space.

# my point of view
Cheney’s algorithm is better than Mark- sweep algorithm
## complexity
For most practical applications involving a lisp-like language Cheney’s Copy Collector surpasses a traditional Mark-Sweep GC in terms of speed and worst-case space performance.

## allocation timing
Cheney’s algorithm has a key advantage over non-copying techniques for allocation timing because it does not require the use of a complete allocator, with freeing and coalescing. Because the entire heap is copied over and freed all at once, it simply needs to use a “bump pointer” for allocation: the algorithm simply tracks the end of the allocated heap and increments this pointer with each new allocation. As a result, Cheney’s algorithm works faster than Mark-Sweep by a factor of four for allocation. 

## concluding statements
Since a Mark-Sweep collector traverses the heap by following pointers to referenced objects starting at the roots, it is necessary for a Mark-Sweep collector to traverse the heap multiple times in order to mark and sweep objects to be freed. In contrast, a Copy collector copies objects reachable from a root note from the from-space in memory to the to-space as the nodes are traversed with Cheney’s bread-first search. As we have stated in this paper, both garbage collectors can be utilized effectively in different environments, or for different languages.

