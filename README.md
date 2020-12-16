# JourneyToWest

learn java together

这是zq的JAVA学习之路，网上的经验贴很多，建议集思广益，选择适合自己的。



# 1、JAVA基础语法

[菜鸟教程](https://www.runoob.com/java/java-tutorial.html)

# 2、算法课

[Coursera算法课](https://www.coursera.org/learn/algorithms-part1)

虽然是算法课，但是因为是JAVA语言实现的，所以在学习算法的过程中，可以同时学习JAVA语言，前提是你有一定的JAVA基础，但是不需要太多基础，一点点就ok。在学这门课之前，我基本上只了解JAVA的基础知识；但是在上完这门课之后，我的JAVA水平也有了相应的提高，比如对private\public修饰的方法有了更清晰的认识，对new()有个更清晰的认识，如何调用其它类，创建私有类，等等。因为在学习的过程中，会遇到一些自己之前不清楚的知识点，然后会去查资料，然后就懂了，这样就有提升。

关于对这门课程的学习，建议先浏览pdf，了解大概要讲什么，再观看视频。视频的质量很不错，可以根据实际情况选择倍速播放。只看pdf似乎是无法学会的。为了理解，可以选择中文字幕；为了学习相关英文术语，可以选择英文字幕。

在观看完视频之后，一定要完成最后的大作业（不是测验）。大作业是对整章内容的提升，它不是课程内容的简单重复，你必须有自己的思考，才能完成这份大作业。提前预警，debug是很痛苦的，课程需要80分才能通过，加油！



# 3、多线程（学习中...）

[微信读书：实战Java高并发程序设计（第2版）](https://weread.qq.com/web/reader/2b0326d0718487522b0092ekc81322c012c81e728d9d180)

可以一边看一边在书上笔记，一边写写例子。

私人笔记：

## 第一章

**并发（concurrency）、并行（parrallelism）**。并发：多任务交替执行，可能是串行，对于外部观察者来说是同时进行的；并行一定是“同时执行”。

如果只有一个CPU，不可能是真实并行的；一次只能执行一条指令。

**原子性（Atomicity）**：一个操作是不可中断的。

**可见性（Visibility）**：一个线程修改了共享变量的值，其余的线程能否知道。

**有序性（Ordering）**：指令重排，可以保证串行语义一致，但是没有义务保证多线程的语义一致。

## 第二章 Java并行基础

**进程**：系统进行资源分配和调度的基本单位，是程序的实体。

**线程**：轻量级进程，是程序执行的最小单位。使用多线程而不是多进程，是因为线程之间的切换和调度的成本远远小于进程。

```java
public enum State{
    NEW,
    RUNNABLE,
    BLOCKED,
    WAITING,
    TIMED_WAITING,
    TERMINATED;
}
```

![](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1608106325853.png)

启动线程要用start()方法，不是run()方法，run()是在当前线程下串行执行。

终止线程不要用stop()，可以自己定义一个方法退出循环。

中断线程：Thread.interrupt()  Thread.isInterrupted()  Thread.interrupted()，Thread.sleep()会被中断而抛出异常，此时它会清楚中断标记，因此需要在异常处理中再次设置中断标记位。

等待（wait）和通知（notify），wait()方法会释放目标对象的锁，但是sleep()不会释放任何资源。

不推荐suspend和resume，可以利用wait和notify从应用层面实现suspend和resume



**volatile**：对保证操作的原子性有很大帮助，但是不能代替锁，因为它无法保证复合操作的原子性，比如i++

**守护线程（Daemon）**：当用户线程退出时，应用里只有守护线程时，Java虚拟机就会退出。

**线程优先级**：

```java
public final static int MIN_PRIORITY=1;
public final static int NORM_PRIORITY=5;
public final static int MAX_PRIORITY=10;
```

**synchronized**：指定枷锁对象、直接作用于实例方法、直接作用于静态方法

# 第三章 JDK并发包



































