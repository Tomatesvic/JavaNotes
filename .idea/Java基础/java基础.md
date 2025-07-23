# java基础

基本类型

byte(1) 、short(2)、int(4)、long(8)、char(2)、float(4)、double(8)、boolean(1)

对象创建过程：类加载->声明类型引用->堆内存分配->属性0值初始化->对象头设置->属性显示初始化->构造方法初始化

JVM：编辑-> 加载-> 验证-> 准备-> 解析-> 使用 ->销毁

接口：没有构造方法、没有继承关系、没有对象实例化、pubilc ststic final修饰成员变量，支持多继承
抽象类：抽象方法、抽象类不能实例化、抽象类可以有构造方法、抽象类可以有静态方法、抽象类可以有静态变量、抽象类可以有实例变量、抽象类可以有实例方法

Aop常用注解：@Aspect、@Before、@After、@AfterReturning、@AfterThrowing、@Around

StringBuilder：单线程、效率高 
StringBuffer：线程安全

创建对象的方式： new一个对象、对象克隆、对象序列化、反射、动态代理

集合：
ArraryList：底层是数组，实现了List接口，允许null元素
LinkedList：底层是链表，实现了Deque接口，允许null元素
HashSet和HashMap：底层是HashTable，java8以后是数组+链表+红黑树
HashMap：是根据哈希值快速定位，顺链表查找，大于8转红黑树
TreeSet和TreeMap：底层是红黑树
LinkedHash和LinkedHashMap:是LinkList的增强HashMap

Volatile：禁止指令重排序，不能保证原子性，保证可见性、有序性；
Atomic：保证原子性、可见性、有序性；
Synchrorized：可以保证可见性、原子性、有序性、无法禁止指令重排；

并发的原则：线程的原子性、可见性、有序性
事务特点：ACID 即 原子性、一致性、隔离性、持久性

创建线程的方式：
1. 继承Thread类
2. 实现Runable、Callable
3. new Thread

线程池：
1. 创建线程池：new ThreadPoolExecutor();
2. 参数分别是 核心线程数、最大线程数、存活时间、时间单位、等待队列、线程工厂、拒绝策略
等待队列：new LinkedBlockingQueue<>(3);
线程工厂：ExecutorsDefaultThreadFactory.getDefaultThreadFactory();
拒绝策略：new ThreadPoolExecutor.AbortPolicy();
AbortPolicy：抛出RejectedExecutionException异常
DiscardPolicy：直接丢弃任务 不会抛出异常
DiscardOldestPolicy：丢弃队列中最老的任务
CallerRunsPolicy：调用者所在的线程执行
使用：executorService.execute(runnable);
关闭：executorService.shutdown();

ReentrantLock 可重入锁：并发竞争下，Synchronized性能好，因为ReentrantLock有同步消除偏向锁
分布式锁：锁的粒度越细，越容易产生死锁，一般用Zookeeper，或者用Redis，setnx命令

锁的分类：乐观锁/悲观锁、公平锁/非公平锁、可重入锁/不可重入锁
锁的实现：synchronized、ReentrantLock、ReadWriteLock
synchronized：悲观锁、可重入锁、互斥锁、独占锁
ReentrantLock：悲观锁、可重入锁、公平锁、独占锁
ReadWriteLock：悲观锁、可重入锁、公平锁、读锁、写锁
