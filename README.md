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

<pre>
字符编码：
      1、常用的字符编码
      2、如何解决中文乱码问题

      java中的字符编码方式
      https://www.cnblogs.com/liujinhong/p/5995946.html
</pre>

<pre>
算法

     1、排序都有哪几种方法？

     2、会写常用的排序算法，如快排，归并等。

     3、各种排序算法的时间复杂度和稳定性5、和广度优先搜索

     6、最小生成树

     7、常见Hash算法，哈希的原理和代价

     8、全排列、贪心算法、KMP算法、hash算法

     9、一致性Hash算法
</pre>

<pre>
Tomcat的session处理，如果让你实现一个tomcatserver，如何实现session机制

      sessionid是一个会话的key，浏览器第一次访问服务器会在服务器端生成一个session，有一个
      sessionid与它对应。tomcat生成的sessionid叫做jsessionid.

      session在访问tomcat服务器HttpRequestRequest的getSession()的时候创建，tomcat
      的ManagerBase类提供了创建sessionid的方法: 随机数 + 时间 + jvmid.

      存储在服务器的内存中，tomcat的StandardManager类将session存储在内存中，也可以持\久
      化到file，数据库，memcache，redis等。客户端只保存sessionid到cookie中，而不会保
      存session，session销毁只能通过invalidate或超时，关掉浏览器并不会关闭session。

      那么Session在何时创建呢？当然还是在服务器端程序运行的过程中创建的，不同语言实现的应
      用程序有不同创建Session的方法，而在Java中是通过调用HttpServletRequest的getSession
      方法（使用true作为参数）创建的。在创建了Session的同时，服务器会为该Session生成唯一
      的Session id，而这个Session id在随后的请求中会被用来重新获得已经创建的Session；
      在Session被创建之后，就可以调用Session相关的方法往Session中增加内容了，而这些内容
      只会保存在服务器中，发到客户端的只有Session id；当客户端再次发送请求的时候，会将这
      个Session id带上，服务器接受到请求之后就会依据Session id找到相应的Session，从而再
      次使用之。

      ManagerBase是所有session管理工具类的基类，它是一个抽象类，所有具体实现session管理
      功能的类都要继承这个类，该类有一个受保护的方法，该方法就是创建sessionId值的方法：
     （tomcat的session的id值生成的机制是一个随机数加时间加上jvm的id值，jvm的id值会根据
      服务器的硬件信息计算得来，因此不同jvm的id值都是唯一的），StandardManager类是tomcat
      容器里默认的session管理实现类，它会将session的信息存储到web容器所在服务器的内存里。
      PersistentManagerBase也是继承ManagerBase类，它是所有持久化存储session信息的基类，
      PersistentManager继承了PersistentManagerBase，但是这个类只是多了一个静态变量和一个
      getName方法，目前看来意义不大，对于持久化存储session，tomcat还提供了StoreBase的抽象
      类，它是所有持久化存储session的基类，另外tomcat还给出了文件存储FileStore和数据存储
      JDBCStore两个实现。
</pre>

<pre>
反射讲一讲，主要是概念,都在哪需要反射机制，反射的性能，如何优化

    反射使用的领域
       1）Java编码时知道类和对象的具体信息，此时直接对类和对象进行操作即可，无需反射
       2）如果编码时不知道类或者对象的具体信息，此时应该使用反射来实现

       具体：
           1）比如类的名称放在XML文件中，属性和属性值放在XML文件中，需要在运行时读取XML文件，
              动态获取类的信息
           2）在编译时根本无法知道该对象或类可能属于哪些类，程序只依靠运行时信息来发现该对象和
              类的真实信息

       反射技术优缺点
           优点：
              1）反射提高了Java程序的灵活性和扩展性，降低耦合性，提高自适应能力。它允许程序创
                 建和控制任何类的对象，无需提高硬编码目标类
              2）反射是其他一些常用语言，如C、C++、Fortran或者Pascal等不具备的
              3）Java反射技术应用领域很广，如软件测试、JavaBean等
              5）许多流行的开源框架例如Struts、Hibernate、Spring在实现过程中都采用了该技术
           缺点：
              1）性能问题：使用反射基本上是一种解释操作，用于字段和方法接入时要远慢于直接代码。
                因此Java反射机制只要应用在对；灵活性和扩展性要求很高的系统框架上，普通程序不
                建议使用
              2）使用反射会模糊程序内部逻辑：程序员希望在代码中看到程序的逻辑，反射等绕过了源
                 代码的技术，因而会带来维护问题。反射代码比相应的直接代码更复杂
</pre>

<pre>
sendRedirect, foward区别
</pre>

<pre>
Servlet的生命周期
</pre>

<pre>
JDK源码里面都有些什么让你印象深刻的设计模式使用，举例看看？ 
</pre>

<pre>
你能列举一个使用了Visitor/Decorator模式的开源项目/库吗？
</pre>

<pre>
你在设计一个工厂的包的时候会遵循哪些原则？
</pre>

<pre>
你能举例几个常见的设计模式
</pre>

<pre>
map/reduce过程，如何用map/reduce实现两个数据源的联合统计 
</pre>

<pre>
什么是布隆过滤器，其实现原理是？ False positive指的是？
</pre>

<pre>
如何解决缓存单机热点问题 
</pre>

<pre>
如何实现一个Hashtable？你的设计如何考虑Hash冲突？如何优化？
</pre>

<pre>
列举一个常用的Redis客户端的并发模型
</pre>

<pre>
tcp协议（建连过程，慢启动，滑动窗口，七层模型）
</pre>

<pre>
Socket交互的基本流程？
</pre>

<pre>
Rest和Http什么关系？大家都说Rest很轻量，你对Rest风格如何理解？
</pre>

<pre>
TCP建立 断开连接的过程
</pre>

<pre>
如何从一张表中查出name字段不包含“XYZ”的所有行？ 
</pre>

<pre>
如何优化数据库性能（索引、分库分表、批量操作、分页算法、升级硬盘SSD、业务优化、主从部署） 
</pre>

<pre>
mybatis如何实现批量提交？
</pre>

<pre>
如何查看Java应用的线程信息？
</pre>

<pre>
Thread dump文件如何分析（Runnable，锁，代码栈，操作系统线程ID关联）
</pre>

<pre>
 Java服务端问题排查（OOM，CPU高，Load高，类冲突） 
</pre>

<pre>
发现磁盘空间不够，如何快速找出占用空间最大的文件？
</pre>

<pre>
/etc/hosts文件什么做用？
</pre>

<pre>
Linux Load过高的可能性有哪些？
</pre>

<pre>
怎么看一个Java线程的资源耗用？
</pre>

<pre>
Linux 硬链接和软链接的区别？
</pre>

<pre>
上下文切换是什么含义
</pre>

<pre>
Java里面的Threadlocal是怎样实现的？
</pre>

<pre>
如何创建线程？如何保证线程安全？
</pre>

<pre>
Java程序是否会内存溢出，内存泄露情况发生？举几个例子。
</pre>

<pre>
如何查看JVM的内存使用情况？
</pre>

<pre>
如何用Java分配一段连续的1G的内存空间？需要注意些什么？ 
</pre>

<pre>
final/finally/finalize的区别？
</pre>

<pre>
Java有自己的内存回收机制，但为什么还存在内存泄露的问题呢？ 
</pre>

<pre>
什么是java序列化，如何实现java序列化?(写一个实例)？
</pre>

<pre>
NIO模型，select/epoll的区别，多路复用的原理
</pre>

<pre>
NIO是什么？适用于何种场景？
</pre>

<pre>
常用的集合类有哪些？比如List如何排序？
ArrayList和LinkedList内部的实现大致是怎样的？他们之间的区别和优缺点？
</pre>

<pre>
接口与抽象类的区别？
</pre>

<pre>
 说一下几种常见的排序算法和分别的复杂度。 

　　· 用Java写一个冒泡排序算法 

　　· 描述一下链式存储结构。 

　　· 如何遍历一棵二叉树？ 

　　· 倒排一个LinkedList。 

　　· 用Java写一个递归遍历目录下面的所有文件。
</pre>

<pre>
自动装箱与拆箱
</pre>

<pre>
hashCode和equals方法的关系
</pre>

<pre>
String和StringBuffer、StringBuilder的区别
</pre>

<pre>
面向对象和面向过程的区别
</pre>