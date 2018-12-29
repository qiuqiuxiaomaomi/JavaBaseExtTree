# JavaBaseExtTree
Java架构师基础


<pre>
Json的优缺点
      优点：
          1）数据格式比较简单，易于读写，格式都是压缩的，占用带宽小
          2）易于解析，客户端Javascript可以简单的通过eval_r()进行json数据的读取
          3）支持多种语言，便于服务器端解析
          5）因为json格式能直接为服务器端代码使用，大大简化了服务器端和客户端的代码开发量，
             且完成任务不变，并且易于维护。

      缺点：
          1）没有xml格式这么推广的深入人心和广泛使用，没有xml那么通用性
          2）json格式目前在web service中推广还属于初级阶段。
</pre>

<pre>
XML解析

    XML是一种通用的数据交换格式,它的平台无关性、语言无关性、系统无关性、给数据集成与交互带来
    了极大的方便。XML在不同的语言环境中解析方式都是一样的,只不过实现的语法不同而已。

　　XML的解析方式分为四种：
        1、DOM解析；
        2、SAX解析；
        3、JDOM解析；
        4、DOM4J解析。
   其中前两种属于基础方法，是官方提供的平台无关的解析方式；后两种属于扩展方法，它们是在基础
   的方法上扩展出来的，只适用于java平台。
</pre>

<pre>
java的反射可以绕过访问权限，访问到类的私有方法和成员。

    可能这点会引起安全性的讨论。反射的使用帮助解决很多复杂的问题，其运行时的类型检查，动态
    调用，代理的实现等，反射为我们写程序带来了很大的灵活性，很多功能都是基于反射。利用反射还
    可以访问内部类、匿名内部类的私有属性。
</pre>

![](https://i.imgur.com/Ma5EAs3.png)

![](https://i.imgur.com/FDZfEW3.png)

<pre>
svn VS git

      SVN（Subversion）是集中式管理的版本控制器;
      Git是分布式管理的版本控制器！
      这是两者之间最核心的区别。

      SVN只有一个单一的集中管理的服务器，保存所有文件的修订版本，而协同工作的人们都通过客户
      端连到这台服务器，取出最新的文件或者提交更新。

      Git每一个终端都是一个仓库，客户端并不只提取最新版本的文件快照，而是把原始的代码仓库完
      整地镜像下来。每一次的提取操作，实际上都是一次对代码仓库的完整备份
</pre>

![](https://i.imgur.com/7oW10uM.png)

<pre>
HashMap和Hashtable区别，原理

      Hashtable 继承自 Dictiionary 而 HashMap继承自AbstractMap.

      HashMap和Hashtable的区别
          HashMap是Hashtable的轻量级实现（非线程安全的实现），他们都完成了Map接口。主要
          的区别有：线程安全性，同步(synchronization)，以及速度。

          1.Hashtable继承自Dictionary类，而HashMap是Java1.2引进的Map interface的一个实现。

          2.HashMap允许将null作为一个entry的key或者value，而Hashtable不允许。

          3.HashMap是非synchronized，而Hashtable是synchronized，这意味着Hashtable是
          线程安全的，多个线程可以共享一个Hashtable；而如果没有正确的同步的话，多个线程是
          不能共享HashMap的。Java 5提供了ConcurrentHashMap，它是HashTable的替代，
          比HashTable的扩展性更好。（在多个线程访问Hashtable时，不需要自己为它的方法实现
          同步，而HashMap 就必须为之提供外同步(Collections.synchronizedMap)）

          4.另一个区别是HashMap的迭代器(Iterator)是fail-fast迭代器，而Hashtable的
          enumerator迭代器不是fail-fast的。所以当有其它线程改变了HashMap的结构（增加或
          者移除元素），将会抛出ConcurrentModificationException，但迭代器本身的remove()
          方法移除元素则不会抛出ConcurrentModificationException异常。但这并不是一个一定
          发生的行为，要看JVM。这条同样也是Enumeration和Iterator的区别。fail-fast机制如
          果不理解原理，可以查看这篇文章：http://www.cnblogs.com/alexlo/archive/2013/03/14/2959233.html

          5.由于HashMap非线程安全，在只有一个线程访问的情况下，效率要高于HashTable。

          6.HashMap把Hashtable的contains方法去掉了，改成containsvalue和containsKey。
           因为contains方法容易让人引起误解。 

          7.Hashtable中hash数组默认大小是11，增加的方式是 old*2+1。HashMap中hash数组的
            默认大小是16，而且一定是2的指数。

          8..两者通过hash值散列到hash表的算法不一样：
             HashTbale是古老的除留余数法，直接使用hashcode
             int hash = key.hashCode();  
             int index = (hash & 0x7FFFFFFF) % tab.length; 
             而后者是强制容量为2的幂，重新根据hashcode计算hash值，在使用hash 位与 （hash
             表长度 – 1），也等价取膜，但更加高效，取得的位置更加分散，偶数，奇数保证了都
             会分散到。前者就不能保证
</pre>