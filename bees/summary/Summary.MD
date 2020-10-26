##### 读写分离原则

##### Copy-On-Write

CopyOnWrite容器即写时复制的容器。通俗的理解是当我们往一个容器添加元素的时候，不直接往当前容器添加，而是先将当前容器进行Copy，复制出一个新的容器，然后新的容器里添加元素，添加完元素之后，再将原容器的引用指向新的容器。这样做的好处是我们可以对CopyOnWrite容器进行并发的读，而不需要加锁，因为当前容器不会添加任何元素。所以CopyOnWrite容器也是一种读写分离的思想，读和写不同的容器。

##### 并发问题

各种并发容器，比如 ConcurrentHashMap、CopyOnWriteArrayList。
各种线程安全队列（Queue/Deque），如 ArrayBlockingQueue、SynchronousQueue。
各种有序容器的线程安全版本等。