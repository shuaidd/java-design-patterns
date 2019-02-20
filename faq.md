---
layout: page
title: FAQ
permalink: /faq/
icon: fa-question
page-index: 5
---

### Q1: What is the difference between State and Strategy patterns? {#Q1}
### 状态模式和策略模式之间有什么区别


While the implementation is similar they solve different problems. The State
pattern deals with what state an object is in - it encapsulates state-dependent
behavior.
The Strategy pattern deals with how an object performs a certain task - it
encapsulates an algorithm.

虽然这两种设计模式实现非常类似，但是他们解决了不同的问题，状态模式处理对象所处的状态，封装了依赖于状态的行为，
策略模式处理对象如何执行特定的任务，它封装的是算法



### Q2: What is the difference between Strategy and Template Method patterns? {#Q2}
### 策略模式和模板方法模式的区别

In Template Method the algorithm is chosen at compile time via inheritance.
With Strategy pattern the algorithm is chosen at runtime via composition.

在模板方法中，算法是在编译时通过继承选择的。使用策略模式，算法在运行时通过组合选择。

### Q3: What is the difference between Proxy and Decorator patterns? {#Q3}
### 代理模式和装饰模式有什么区别

The difference is the intent of the patterns. While Proxy controls access to
the object Decorator is used to add responsibilities to the object.

不同之处在于模式的意图。 代理模式控制对象访问权限，装饰模式用于向对象添加职责。



### Q4: What is the difference between Chain of Responsibility and Intercepting Filter patterns? {#Q4}
### 责任链和拦截过滤器模式之间有什么区别？

While the implementations look similar there are differences. The Chain of
Responsibility forms a chain of request processors and the processors are then
executed one by one until the correct processor is found. In Intercepting
Filter the chain is constructed from filters and the whole chain is always
executed.

虽然实现看起来相似但存在差异。 责任链形成了一系列请求处理器，然后是处理器逐个执行，直到找到正确的处理器。 在拦截
过滤链由过滤器构成，整个链条始终如一执行。



### Q5: What is the difference between Visitor and Double Dispatch patterns? {#Q5}
### 访问者模式 和 双分派模式之间的区别

The Visitor pattern is a means of adding a new operation to existing classes.
Double dispatch is a means of dispatching function calls with respect to two
polymorphic types, rather than a single polymorphic type, which is what
languages like C++ and Java _do not_ support directly.

访问者模式是向现有类添加新操作的一种方法。双分派是一种相对于两个调度函数调用的方法
多态类型，而不是单一的多态类型

### Q6: What are the differences between Flyweight and Object Pool patterns? {#Q6}
### 享元模式和对象池模式的区别

They differ in the way they are used.

Pooled objects can simultaneously be used by a single "client" only. For that,
a pooled object must be checked out from the pool, then it can be used by a
client, and then the client must return the object back to the pool. Multiple
instances of identical objects may exist, up to the maximal capacity of the
pool.

In contrast, a Flyweight object is singleton, and it can be used simultaneously
by multiple clients.

As for concurrent access, pooled objects can be mutable and they usually don't
need to be thread safe, as typically, only one thread is going to use a
specific instance at the same time. Flyweight must either be immutable (the
best option), or implement thread safety.

As for performance and scalability, pools can become bottlenecks, if all the
pooled objects are in use and more clients need them, threads will become
blocked waiting for available object from the pool. This is not the case with
Flyweight.

池化对象同时只能被一个客户端使用，为了达到这个目的，一个池化对象必须从对象池获取，客户端使用完必须要再返还给对象池
，池中可能存在多个相同对象实例，直到达到池的最大容量
相比之下，一个享元对象必须是单例的，他可以同时被多个客户端使用

对于并发访问，池化对象可以使是可变的，通常他们是不需要线程安全的，通常同时只有一个线程在使用其中的一个实例，而享元
模式必须是不可变的（最好的选择），或者实现线程安全

至于性能和可伸缩性，池可能成为瓶颈，如果所有的池化对象正在使用中，并且更多客户端需要它们，线程将
等待池中的可用对象

### Q7: What are the differences between FluentInterface and Builder patterns? {#Q7}
### FluentInterface模式和构造者模式的区别

Fluent interfaces are sometimes confused with the Builder pattern, because they share method chaining and a fluent usage.
 However, fluent interfaces are not primarily used to create shared (mutable) objects, 
 but to configure complex objects without having to respecify the target object on every property change. 
 
流式接口通常和构造者模式混淆，因为他们共享方法链和流式的用法，流式接口主要不是用于创建共享对象，而是配置负载对象而不必在每次属性变更时重新指定对象

### Q8: What is the difference between java.io.Serialization and Memento pattern? {#Q8}
### 序列化和备忘录模式的区别

Memento is typically used to implement rollback/save-point support. 
Example we might want to mark the state of an object at a point in time, 
do some work and then decide to rollback to the previous state. 

On the other hand serialization may be used as a tool to save the state of an object into byte[] and preserving the contents in memory or disk.
 When someone invokes the memento to revert object's previous state then we can deserialize the information stored and recreate previous state. 

So Memento is a pattern and serialization is a tool that can be used to implement this pattern.
 Other ways to implement the pattern can be to clone the contents of the object and keep track of those clones.

备忘录通常被用来实现回滚和保存点操作，比如我们可能想标记一个对象在某个时间点的状态，执行一些操作之后再决定回滚到之前的状态
另一方面是一种保存对象到字节数组，内存，磁盘的工具，当需要恢复之前对象的状态时，可以反序列化之前保存的信息，并重新创建对象
因此备忘录是一种模式，而序列化是实现这种模式的一个工具，实现这个模式的其他方法也可以是克隆这个对象的内容，并保存这些克隆的信息