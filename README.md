# MPSC_Queue
MPSC_Queue is based on single linked list. Producers have the queue allocate a msg object, set msg content and push it back to the queue; Consumer pops all msgs from the queue at a time, process them and give the objects back to the queue for later allocation from producers. So neither producer nor consumer need to allocate memory themselves and no memory copy is required in any of the operations.

There're two versions of implementation: 
## MPSCQueue(mpsc_queue.h)
MPSCQueue is for single process usage, it allows for configurating a pre-allocated msg size and max allocated msg size at run time.

## SHMMPSCQueue(shm_mpsc_queue.h)
SHMMPSCQueue can reside in shared memory, thus suitable for IPC, and the msg size is fixed at compile time.

# Example
[test](https://github.com/MengRao/MPSC_Queue/tree/master/test) provides a simple test program and a full fledged async logging implementation(based on [muduo](https://github.com/chenshuo/muduo)), for both versions.
