# 多线程 Multithread

## 使用多线程

Java提供了多种创建和管理线程的方式，主要有以下四种：

- 通过继承Thread类，重写run()方法，然后创建Thread类的对象并调用start()方法来启动线程。
- 通过实现Runnable接口，实现run()方法，然后创建Runnable接口的实现类的对象，并作为参数传递给Thread类的构造方法，再调用start()方法来启动线程。
- 通过实现Callable接口，实现call()方法，然后创建Callable接口的实现类的对象，并使用FutureTask类来包装，再作为参数传递给Thread类的构造方法，再调用start()方法来启动线程。这种方式可以获取线程的返回值。
- 通过使用ExecutorService接口，创建线程池，然后提交Runnable或Callable接口的实现类的对象，再使用Future接口来获取线程的返回值。这种方式可以简化线程的管理和调度。

## 线程池

管理线程的 数量、复用、生命周期、任务与线程解耦

### 工作方式

使用**阻塞队列**实现，队列为空，获取元素被阻塞，队列为满，添加元素被阻塞。阻塞队列存储外部提交过来的任务。

几个重要的参数：  
核心线程数 最大线程数  
工作队列类型  
拒绝策略  
线程回收 等待时间 单位

根据 系统负载和硬件资源 配置 核心线程数和最大线程数 ， 确保充分利用资源

工作队列类型：任务提交速度较快，用无界队列

考虑引入并行处理和异步处理

---

线程池是一种管理多个线程的技术，它可以提高程序的性能和资源利用率，避免频繁地创建和销毁线程。线程池的基本思想是：

- 预先创建一定数量的线程，放入一个线程队列中，这些线程称为核心线程。
- 当有新的任务提交时，如果核心线程都在忙，就将任务放入一个任务队列中，等待空闲的线程来执行。
- 如果任务队列也满了，就创建新的线程，直到达到线程池的最大容量，这些线程称为非核心线程。
- 如果非核心线程闲置了一定时间，就会被销毁，回收资源。
- 如果核心线程闲置了一定时间，根据配置的策略，可能会被保留或者销毁。

线程池的使用方法一般有以下几步：

- 创建一个线程池对象，指定核心线程数、最大线程数、非核心线程存活时间、任务队列的容量和拒绝策略等参数。
- 创建一个或多个 Runnable 或 Callable 接口的实现类对象，封装要执行的任务逻辑。
- 调用线程池对象的 execute() 或 submit() 方法，将任务对象提交给线程池。
- 调用线程池对象的 shutdown() 或 shutdownNow() 方法，关闭线程池，等待所有任务完成。

Java 提供了一个 Executors 类，用来创建和管理线程池。Executors 类提供了一些静态方法，可以根据不同的需求，创建不同类型的线程池，例如：

- newFixedThreadPool()：创建一个固定大小的线程池，核心线程数和最大线程数相等，任务队列无界，适合执行长期的任务。
- newCachedThreadPool()：创建一个可缓存的线程池，核心线程数为0，最大线程数无限大，非核心线程存活时间很短，任务队列同步，适合执行短期的任务。
- newSingleThreadExecutor()：创建一个单线程的线程池，核心线程数和最大线程数都为1，任务队列无界，适合执行顺序的任务。
- newScheduledThreadPool()：创建一个定时的线程池，核心线程数可指定，最大线程数无限大，任务队列延迟，适合执行定时或周期性的任务。

## ThreadPoolExecutor 类

管理和创建线程池

几个重要的参数：

- corePoolSize：线程池中的**核心线程数**，决定是否创建新的线程来处理任务
- maximumPoolSize：线程池中允许的**最大线程数**，超过这个数的线程会被回收
- keepAliveTime：**非核心**线程的**空闲存活时间**，超过这个时间的线程会被终止
- unit：空闲存活时间的**单位**，如秒、毫秒等
- workQueue：**任务队列**，用于存放已提交的任务，等待线程来执行
- threadFactory：线程工厂，用于**创建线程**
- handler：**拒绝策略**，当线程池和任务队列都满了时，如何**处理新来**的任务
