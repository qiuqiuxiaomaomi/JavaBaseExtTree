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
	  
	  我们知道java.util.HashMap不是线程安全的，因此如果在使用迭代器的过程中有其他线程修改了map，那么将抛出
	  ConcurrentModificationException，这就是所谓fail-fast策略。

          这一策略在源码中的实现是通过modCount域，modCount顾名思义就是修改次数，对HashMap内容的修改都将增加这个值，
	  那么在迭代器初始化过程中会将这个值赋给迭代器的expectedModCount。

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
  
      HttpServletResponse.sendRedirect与RequestDispatcher.forward方法都可以实现获取相应URL资源。
 
      sendRedirect实现请求重定向，forward实现的是请求转发。 
      在web服务器内部的处理机制也是不一样的。
 
      1. 跳转方式 
         运用forward方法只能重定向到同一个Web应用程序中的一个资源。而sendRedirect方法可以让你
         重定向到任何URL。  

         表单form的action= "/uu ";sendRedirect( "/uu ");表示相对于服务器根路径。
         如http://localhost:8080/Test应用（则提交至http://localhost:8080/uu）;  
         Forward代码中的 "/uu "则代表相对与WEB应用的路径。如http://localhost:8080/Test应用
        （则提交至http://localhost:8080/Test/uu）;
 
      2. forward重定向后，浏览器url地址不变，sendRedirect转发后，浏览器url地址变为目的url
         地址。
         forward()无法重定向至有frame的jsp文件,可以重定向至有frame的html文件, 同时forward()
         无法在后面带参数传递,
         比如servlet?name=frank,这样不行,可以程序内通过response.setAttribute( "name
         ",name)来传至下一个页面. 
 
      3. 使用forward重定向的过程，是浏览器先向目的Servlet发送一次Request请求，然后在服务器端
         由Servlet再将请求发送到目的url，再由服务器端Servlet返回Response到浏览器端。浏览器和
         服务器一次请求响应。
 
         使用sendRedirect转发的过程，浏览器先向目的Servlet发送一次请求，Servlet看到
         sendRedirect将目的url返回到浏览器，浏览器再去请求目的url,目的url再返回response到
         浏览器。浏览器和服务器两次请求响应。
 
      4. forward方法的调用者与被调用者之间共享Request和Response
         sendRedirect方法由于两次浏览器服务器请求，所以有两个Request和Response。
 
         如果使用request.setAttribute传递一些属性就需要用forward，如果想要跳转到别的应用的
         资源，就需要用sendRedirect。
 
      5.无论是forward方法还是sendRedirect方法调用前面都不能有PrintWriter输出到客户端。
        forward方法报错： Java.lang.IllegalStateException: Cannot forward after
        response has been committed
 
        sendRedirect报错：java.lang.IllegalStateException
        at org.apache.catalina.connector.ResponseFacade.sendRedirect(ResponseFacade.java:435)
</pre>

![](https://i.imgur.com/UVpvSln.png)

<pre>
Servlet的生命周期

      Servlet运行在Servlet容器中，其生命周期由容器来管理。Servlet的生命周期通过javax.servlet.Servlet
      接口中的init()、service()和destroy()方法来表示

      Servlet的生命周期包含了下面4个阶段：
         1.加载和实例化
         2.初始化
         3.请求处理
         4.服务终止

      Web服务器在与客户端交互时Servlet的工作过程是:
         1.在客户端对web服务器发出请求
         2.web服务器接收到请求后将其发送给Servlet
         3.Servlet容器为此产生一个实例对象并调用ServletAPI中相应的方法来对客户端HTTP请求进行处理,
           然后将处理的响应结果返回给WEB服务器.
         4.web服务器将从Servlet实例对象中收到的响应结构发送回客户端.
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
什么是布隆过滤器，其实现原理是？ False positive指的是？
  
      False Positive：把合法的判断成非法的，译为“误报”。
      False Negative：把非法的判断成合法，译为“漏报”。
</pre>

![](https://i.imgur.com/ZE30Btw.png)

<pre>
如何解决缓存单机热点问题 

   背景：
       电商场景促销活动的会场页由于经常集中在某个时间点进行“秒杀”促销，这些页面的QPS（服务器每秒可以
       处理的请求量）往往特别高，数据库通常无法直接支撑如此高QPS的请求，常见的解决方案是让大部分相同
       信息的请求都尽可能地压在缓存（cache）上来缓解数据库（DB）的压力，从而尽可能地去满足高并发访问
       的诉求（如图2-1所示）。

       在一次业务促销过程中，运营给一大批用户集中推送了一条消息：10点钟准时抢购一批远低于市场价而且数
       量有限的促销活动商品。由于确实物美价廉，用户收到消息之后10点钟准时进入手机客户端的会场页进行疯
       抢。几分钟内很多用户进入会场页，最终导致页面异常，服务器疯狂报警。报警信息显示很多关于缓存的异常，
       由于缓存拿不到数据转而会转向数据库去查询数据，这样数据库更加难以支撑，整个业务集群处于雪崩状态
      （如图2-2所示）。

       高并发下主备缓存的数据一致性
</pre>

<pre>
如何实现一个Hashtable？你的设计如何考虑Hash冲突？如何优化？
</pre>

<pre>
列举一个常用的Redis客户端的并发模型

      并发访问
          Redis为单进程单线程模式，采用队列模式将并发访问变为串行访问。Redis本身没有锁的概念，Redis对
          于多个客户端连接并不存在竞争，但是在Jedis客户端对Redis进行并发访问时会发生连接超时、数据转换
          错误、阻塞、客户端关闭连接等问题，这些问题均是由于客户端连接混乱造成。对此有2种解决方法：

              1.客户端角度，为保证每个客户端间正常有序与Redis进行通信，对连接进行池化，同时对客户端读
                写Redis操作采用内部锁synchronized。

              2.服务器角度，利用setnx实现锁。如某客户端要获得一个名字list的锁，客户端使用下面的命令进
                行获取：

				Setnx lock.list  current time + lock timeout
				
				 如返回1，则该客户端获得锁，把lock. list的键值设置为时间值表示该键已被锁定，该客户端
                 最后可以通过DEL lock.list来释放该锁。
				
				 如返回0，表明该锁已被其他客户端取得，等对方完成或等待锁超时。
</pre>

###TCP报头格式

![](https://i.imgur.com/ayXMOA2.png)

###TCP建立三次连接

![](https://i.imgur.com/9PrLp1l.png)

###TCP连接释放
![](https://i.imgur.com/FdYEm2P.png)

<pre>
tcp协议（建连过程，慢启动，滑动窗口，七层模型）

    （1）源端口和目的端口：与UDP类似，TCP的分用是通过端口实现的。
    （2）序号：TCP是面向字节流的，在TCP连接中传送的字节流的每一个字节都是有顺序的，整个要传送的字节流的
        起始序号必须要在连接建立时设置。首部中的序号字段值表示本报文段的数据的第一个字节的序号。该字段也
        称为“报文段序号”。
    （3）确认号：是期望收到对方下一个报文段的第一个数据字节的序号。
    （4）4位首部长度：它指出TCP报文段的数据起始处距离TCP报文段起始处有多远，因此也称为“数据偏移”。由于4
        位二进制数最大能表示十进制数字是15，因此数据偏移最大值是60，则选项长度最大为40字节。
    （5）保留：占6位，为今后使用，目前置为0
    （6）设置位：
        紧急URG：
           当URG=1时，表明紧急指针有效，它告诉系统此报文段中有紧急数据，应尽快传送，而不需要按原
           来的顺序排列等待。发送方会将紧急数据插入到本报文段最前面，在紧急数据之后的仍是普通数据。这是需
           要与首部紧急指针(Urgent Point)配合使用。
        确认ACK：
           仅当ACK=1时确认字段有效，建立连接后所有传输的报文段必须将ACK置为1。
        推送PSH：PSH=1时表示，该报文段希望到达对端时，将这个报文以及缓存区之间缓存尚未交付的数据一并
           交给进程。
        复位RST：当RST=1时表明，TCP链接出现严重差错，必须释放连接，然后再重新建立连接。当其为 1 的时
                候也可以用来拒绝一个非法的报文段或拒绝打开一个连接，也称为重建位或重置位。
        同步SYN：连接建立时用来同步序号，SYN=1表示这是一个连接请求或接受报文。SYN=1,ACK=0时表明这是一
                个连接请求报文，SYN=1,ACK=1表示同意与对方建立连接。
        终止FIN：用来释放一个连接。FIN=1表示数据已经发送完，要求释放连接。
    （7）窗口：指发送本报文段一方的接收窗口，告诉对方：从本报文段首部中的确认序号算起，接收方目前允许对
             方发送的数据量。窗口值经常动态变化着。
    （8）检验和：检验和字段检验的范围包括首部和数据两部分。和UDP一样，在计算检验和时，要在TCP报文段的前
             面加上12字节的伪首部。
    （9）紧急指针：仅在URG=1时才有意义，它指出本报文段中的紧急数据的字节数。紧急指针指出了紧急数据的末尾
             在报文段中的位置。

	TCP拆除连接（四次挥手）：
	     数据传输完成后，Client和Server都处于ESTABLISHED状态，通信的双方都可以进行释放连接的动作。
	     TCP连接释放的过程比较复杂，下来我们一条一条分析：
	        1）Client主动发送释放连接的请求，并停止发送数据。Client将连接释放报文段的首部的FIN置为1，
              其序号为u，它等于前面已传送过的数据的最后一个字节的序号加1。此时Client进入FIN-WAIT-1（
              终止等待1）状态。
	        2）Server接收到Client的释放请求后发出确认，确认号是u+1，而确认报文段自己的序号是v，等于
              Server前面已经传送过的数据的最后一个字节的序号加1。接着Server进入CLOSE-WAIT（关闭等待）
              状态，并且TCP会通知高层应用程序，此时Client到Server的连接已经关闭，但Server到Client的
              连接仍然存在，因此此时的TCP连接处于半关闭状态。Server仍然有可能会给Client发送数据，
              Client也要接收。
	        3）Client收到来自对方的确认后，进入FIN-WAIT-2（终止等待2）状态，等待Server释放连接。
	        5）Server发送完数据后发送释放报文段，其应用程序就通知TCP释放连接。Server发送的报文段中必须
               将FIN置为1。由于在半关闭状态Server可能也发送了数据，因此假定此时Server的序号为w，除此
               之外，Server也必须重复上次发送的确认号u+1。发送完后Server进入LAST-ACK（最后确认）状态，
               等待Client确认。
	        6）Client收到释放报文段后发送确认报文段。此时Client并没有释放掉连接，而是进入TIME-WAIT（
              时间等待）状态，等过了2MSL时间后才进入到CLOSED状态。
</pre>

![](https://i.imgur.com/vS6Rvfp.png)

<pre>
Socket交互的基本流程？
</pre>

<pre>
Rest和Http什么关系？大家都说Rest很轻量，你对Rest风格如何理解？

      REST和RESTFUL是什么
	   REST ( REpresentational State Transfer )，State Transfer 为 "状态传输" 或 "状态转移 "，
       Representational 中文有人翻译为"表征"、"具象"，合起来就是 "表征状态传输" 或 "具象状态传输" 
       或 "表述性状态转移"。

	   REST是一种架构风格，REST 指的是一组架构约束条件和原则。满足这些约束条件和原则的应用程序或设计就
       是 RESTful。其核心是面向资源，REST专门针对网络应用设计和开发方式，以降低开发的复杂性，提高系统的
       可伸缩性。

	   REST提出设计概念和准则为：
	   1.网络上的所有事物都可以被抽象为资源(resource)
	   2.每一个资源都有唯一的资源标识(resource identifier)，对资源的操作不会改变这些标识
	   3.所有的操作都是无状态的

	   REST简化开发，其架构遵循CRUD原则，该原则告诉我们对于资源(包括网络资源)只需要四种行为：创建，获
       取，更新和删除就可以完成相关的操作和处理。您可以通过统一资源标识符（Universal 
       Resource Identifier，URI）来识别和定位资源，并且针对这些资源而执行的操作是通过 HTTP 规范定义
       的。其核心操作只有GET,PUT,POST,DELETE。

	   由于REST强制所有的操作都必须是stateless的，这就没有上下文的约束，如果做分布式，集群都不需要考
       虑上下文和会话保持的问题。极大的提高系统的可伸缩性。
</pre>

<pre>
如何从一张表中查出name字段不包含“XYZ”的所有行？ 
</pre>

<pre>
如何优化数据库性能
      1）索引
      2）分库分表
      3）批量操作
      5）分页算法
      6) 升级硬盘SSD
      7) 业务优化
      8) 主从部署） 
</pre>

<pre>
mybatis如何实现批量提交？
</pre>

<pre>
如何查看Java应用的线程信息？

      jstack -l pid
</pre>

<pre>
Thread dump文件如何分析（Runnable，锁，代码栈，操作系统线程ID关联）
</pre>

<pre>
 Java服务端问题排查（OOM，CPU高，Load高，类冲突） 
</pre>

<pre>
发现磁盘空间不够，如何快速找出占用空间最大的文件？

      使用find命令找到大于指定大小的文件
      [root@localhost data]# find / -type f -size +10G

      du : 计算出单个文件或者文件夹的磁盘空间占用.
      sort : 对文件行或者标准输出行记录排序后输出.
      head : 输出文件内容的前面部分.

      # du -a /var | sort -n -r | head -n 10
</pre>

<pre>
/etc/hosts文件什么做用？

    Hosts - The static table lookup for host name（主机名查询静态表）

　　 hosts文件是Linux系统中一个负责IP地址与域名快速解析的文件，以ASCII格式保存在“/etc”目录下，
	文件名为“hosts”（不同的linux版本，这个配置文件也可能不同。比如Debian的对应文件是/etc/hostname）。
	hosts文件包含了IP地址和主机名之间的映射，还包括主机名的别名。在没有域名服务器的情况下，
	系统上的所有网络程序都通过查询该文件来解析对应于某个主机名的IP地址，否则就需要使用DNS服务程序来解决。
	通常可以将常用的域名和IP地址映射加入到hosts文件中，实现快速方便的访问。
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

     上下文切换（有时也称做进程切换或任务切换）是指 CPU 从一个进程或线程切换到另一个进程或线程。 进程（
     有时候也称做任务）是指一个程序运行的实例。在 Linux 系统中，线程就是能并行运行并且与他们的父进程（
     创建他们的进程）共享同一地址空间（一段内存区域）和其他资源的轻量级的进程。

     上下文切换可以认为是内核（操作系统的核心）在 CPU 上对于进程（包括线程）进行以下的活动：
         1）挂起一个进程，将这个进程在 CPU 中的状态（上下文）存储于内存中的某处
         2）在内存中检索下一个进程的上下文并将其在 CPU的寄存器中恢复，
         3）跳转到程序计数器所指向的位置（即跳转到进程被中断时的代码行），以恢复该进程。

     上下文切换的消耗
         上下文切换通常是计算密集型的。也就是说，它需要相当可观的处理器时间，在每秒几十上百次的切换中，
         每次切换都需要纳秒量级的时间。所以，上下文切换对系统来说意味着消耗大量的 CPU 时间，事实上，可
         能是操作系统中时间消耗最大的操作。

         Linux相比与其他操作系统（包括其他类 Unix 系统）有很多的优点，其中有一项就是，其上下文切换和
         模式切换的时间消耗非常少
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

     （1）final为关键字；

     （2）finalize()为方法；

     （3）finally为为区块标志，用于try语句中；

      作用：

        （1）final为用于标识常量的关键字，final标识的关键字存储在常量池

        （2）finalize()方法在Object中进行了定义，用于在对象“消失”时，由JVM进行调用用于对对象进行垃
            圾回收，类似于C++中的析构函数；用户自定义时，用于释放对象占用的资源（比如进行I/0操作）；

        （3）finally{}用于标识代码块，与try{}进行配合，不论try中的代码执行完或没有执行完（这里指有
            异常），该代码块之中的程序必定会进行；
</pre>

<pre>
Java有自己的内存回收机制，但为什么还存在内存泄露的问题呢？ 

      内存对象明明已经不需要的时候，还仍然保留着这块内存和它的访问方式（引用）。
</pre>

<pre>
什么是java序列化，如何实现java序列化?(写一个实例)？
</pre>

<pre>
NIO模型，select/epoll的区别，多路复用的原理

      epoll IO多路复用模型实现机制
            由于epoll的实现机制与select/poll机制完全不同，上面所说的 select的缺点在epoll上不复存在。

            设想一下如下场景：有100万个客户端同时与一个服务器进程保持着TCP连接。而每一时刻，通常只有几
            百上千个TCP连接是活跃的(事实上大部分场景都是这种情况)。如何实现这样的高并发？

            在select/poll时代，服务器进程每次都把这100万个连接告诉操作系统(从用户态复制句柄数据结构到
            内核态)，让操作系统内核去查询这些套接字上是否有事件发生，轮询完后，再将句柄数据复制到用户态，
            让服务器应用程序轮询处理已发生的网络事件，这一过程资源消耗较大，因此，select/poll一般只能处
            理几千的并发连接。

            
            epoll的设计和实现与select完全不同。epoll通过在Linux内核中申请一个简易的文件系统(文件系统
            一般用什么数据结构实现？B+树)。把原先的select/poll调用分成了3个部分：

            1）调用epoll_create()建立一个epoll对象(在epoll文件系统中为这个句柄对象分配资源)

            2）调用epoll_ctl向epoll对象中添加这100万个连接的套接字

            3）调用epoll_wait收集发生的事件的连接

            如此一来，要实现上面说是的场景，只需要在进程启动时建立一个epoll对象，然后在需要的时候向这
            个epoll对象中添加或者删除连接。同时，epoll_wait的效率也非常高，因为调用epoll_wait时，并
            没有一股脑的向操作系统复制这100万个连接的句柄数据，内核也不需要去遍历全部的连接。
</pre>

<pre>
NIO是什么？适用于何种场景？

      IO                NIO
      面向流            面向缓冲
      阻塞IO            非阻塞IO
      无                选择器

      面向流与面向缓冲
          Java NIO和IO之间第一个最大的区别是，IO是面向流的，NIO是面向缓冲区的。 Java IO面向流意味着
          每次从流中读一个或多个字节，直至读取所有字节，它们没有被缓存在任何地方。此外，它不能前后移动
          流中的数据。如果需要前后移动从流中读取的数据，需要先将它缓存到一个缓冲区。 Java NIO的缓冲导
          向方法略有不同。数据读取到一个它稍后处理的缓冲区，需要时可在缓冲区中前后移动。这就增加了处理
          过程中的灵活性。但是，还需要检查是否该缓冲区中包含所有您需要处理的数据。而且，需确保当更多的
          数据读入缓冲区时，不要覆盖缓冲区里尚未处理的数据。

      阻塞与非阻塞IO
          Java IO的各种流是阻塞的。这意味着，当一个线程调用read() 或 write()时，该线程被阻塞，直到
          有一些数据被读取，或数据完全写入。该线程在此期间不能再干任何事情了。 Java NIO的非阻塞模式，
          使一个线程从某通道发送请求读取数据，但是它仅能得到目前可用的数据，如果目前没有数据可用时，就
          什么都不会获取。而不是保持线程阻塞，所以直至数据变的可以读取之前，该线程可以继续做其他的事情。
          非阻塞写也是如此。一个线程请求写入一些数据到某通道，但不需要等待它完全写入，这个线程同时可以
          去做别的事情。 线程通常将非阻塞IO的空闲时间用于在其它通道上执行IO操作，所以一个单独的线程现
          在可以管理多个输入和输出通道（channel）。

      选择器（Selectors）
          Java NIO的选择器允许一个单独的线程来监视多个输入通道，你可以注册多个通道使用一个选择器，然
          后使用一个单独的线程来“选择”通道：这些通道里已经有可以处理的输入，或者选择已准备写入的通道。
          这种选择机制，使得一个单独的线程很容易来管理多个通道。
</pre>

<pre>
常用的集合类有哪些？比如List如何排序？
ArrayList和LinkedList内部的实现大致是怎样的？他们之间的区别和优缺点？
</pre>

<pre>
接口与抽象类的区别？

      1、抽象类和接口都不能直接实例化，如果要实例化，抽象类变量必须指向实现所有抽象方法的子类对象，接
        口变量必须指向实现所有接口方法的类对象。

      2、抽象类要被子类继承，接口要被类实现。

      3、接口只能做方法申明，抽象类中可以做方法申明，也可以做方法实现

      4、接口里定义的变量只能是公共的静态的常量，抽象类中的变量是普通变量。

      5、抽象类里的抽象方法必须全部被子类所实现，如果子类不能全部实现父类抽象方法，那么该子类只能是抽
        象类。同样，一个实现接口的时候，如不能全部实现接口方法，那么该类也只能为抽象类。

      6、抽象方法只能申明，不能实现，接口是设计的结果 ，抽象类是重构的结果

      7、抽象类里可以没有抽象方法

      8、如果一个类里有抽象方法，那么这个类只能是抽象类

      9、抽象方法要被实现，所以不能是静态的，也不能是私有的。

      10、接口可继承接口，并可多继承接口，但类只能单根继承。
</pre>

<pre>
 说一下几种常见的排序算法和分别的复杂度。 

　　· 用Java写一个冒泡排序算法 

　　· 描述一下链式存储结构。 

　　· 如何遍历一棵二叉树？ 

　　· 倒排一个LinkedList。 

　　· 用Java写一个递归遍历目录下面的所有文件。
</pre>

![](https://i.imgur.com/NPHpBci.png)

<pre>
自动装箱与拆箱

      由上可知Java中的基本数据类型有八种分别是：int（4字节） byte（1字节） short（2字节） long（8字节）
      float （4字节） double（8字节） char（2字节） boolean（1byte）基本数据类型不是对象，不能使用对
      象的方法。将基本数据类型转换为对象就是自动装箱的过程。
</pre>

<pre>
hashCode和equals方法的关系

      如果是你自己定义的一个类，比较自定义类用equals和==是一样的，都是比较句柄地址，因为自定义的类是
      继承于object，而object中的equals就是用==来实现的，你可以看源码。

      那为什么我们用的String等等类型equals是比较实际内容呢，是因为String等常用类已经重写了object中
      的equals方法，让equals来比较实际内容。

      背景：
          hashCode()方法和equal()方法的作用其实一样，在Java里都是用来对比两个对象是否相等一致，那
          么equal()既然已经能实现对比的功能了，为什么还要hashCode()呢？

          因为重写的equal（）里一般比较的比较全面比较复杂，这样效率就比较低，而利用hashCode()进行对
          比，则只要生成一个hash值进行比较就可以了，效率很高，那么hashCode()既然效率这么高为什么还
          要equal()呢？

          因为hashCode()并不是完全可靠，有时候不同的对象他们生成的hashcode也会一样（生成hash值得公
          式可能存在的问题），所以hashCode()只能说是大部分时候可靠，并不是绝对可靠，所以我们可以得出：
              1.equal()相等的两个对象他们的hashCode()肯定相等，也就是用equal()对比是绝对可靠的。
              2.hashCode()相等的两个对象他们的equal()不一定相等，也就是hashCode()不是绝对可靠的。

          所有对于需要大量并且快速的对比的话如果都用equal()去做显然效率太低，所以解决方式是，每当需要对
          比的时候，首先用hashCode()去对比，如果hashCode()不一样，则表示这两个对象肯定不相等（也就是
          不必再用equal()去再对比了）,如果hashCode()相同，此时再对比他们的equal()，如果equal()也
          相同，则表示这两个对象是真的相同了，这样既能大大提高了效率也保证了对比的绝对正确性！
</pre>

<pre>
String和StringBuffer、StringBuilder的区别：

      String为字符串常量，而StringBuilder和StringBuffer均为字符串变量，即String对象一旦创建之后该
      对象是不可更改的，但后两者的对象是变量，是可以更改的。

      而StringBuilder和StringBuffer的对象是变量，对变量进行操作就是直接对该对象进行更改，而不进行创
      建和回收的操作，所以速度要比String快很多

      在线程安全上，StringBuilder是线程不安全的，而StringBuffer是线程安全的

      如果一个StringBuffer对象在字符串缓冲区被多个线程使用时，StringBuffer中很多方法可以带有
      synchronized关键字，所以可以保证线程是安全的，但StringBuilder的方法则没有该关键字，所以不能保
      证线程安全，有可能会出现一些错误的操作。所以如果要进行的操作是多线程的，那么就要使用StringBuffer，
      但是在单线程的情况下，还是建议使用速度比较快的StringBuilder。
</pre>

<pre>
面向对象和面向过程的区别

      面向过程就是分析出解决问题所需要的步骤，然后用函数把这些步骤一步一步实现，使用的时候一个一个依次
      调用就可以了；面向对象是把构成问题事务分解成各个对象，建立对象的目的不是为了完成一个步骤，而是为
      了描叙某个事物在整个解决问题的步骤中的行为。

      面向对象是以功能来划分问题

      面向过程：
          优点：性能比面向对象高，因为类调用时需要实例化，开销比较大，比较消耗资源;比如单片机、嵌入式开
               发、 Linux/Unix等一般采用面向过程开发，性能是最重要的因素。 
          缺点：没有面向对象易维护、易复用、易扩展

      面向对象：
          优点：易维护、易复用、易扩展，由于面向对象有封装、继承、多态性的特性，可以设计出低耦合的系统，
                使系统 更加灵活、更加易于维护 
          缺点：性能比面向过程低
</pre>

![](https://i.imgur.com/CkWqKkK.jpg)

<pre>
嵌套for循环的优化准则：

      1）外小内大原则
      2）提取与循环无关的表达式
      3）消除循环终止判断的方法调用
      5）循环的异常捕获
         大家都知道，捕获异常是很耗资源的，所以不要讲try catch放到循环内部，优化后同样有好几个数量级的
         提升
</pre>

<pre>
@Retention(RetentionPolicy.RUNTIME)
@Target(value = {ElementType.METHOD, ElementType.TYPE})
@Documented
public @interface Authority {
}

      Retention注解
			Retention(保留)注解说明,这种类型的注解会被保留到那个阶段. 有三个值: 
			1.RetentionPolicy.SOURCE —— 这种类型的Annotations只在源代码级别保留,编译时就会被忽略 
			2.RetentionPolicy.CLASS —— 这种类型的Annotations编译时被保留,在class文件中存在,但JVM
                                       将会忽略 
			3.RetentionPolicy.RUNTIME —— 这种类型的Annotations将被JVM保留,所以他们能在运行时被JVM
                                       或其他使用反射机制的代码所读取和使用.

            下面示例中, @Retention(RetentionPolicy.RUNTIME)注解表明 Test_Retention注解将会由虚拟
            机保留,以便它可以在运行时通过反射读取.

       Documented 注解

            Documented 注解表明这个注解应该被 javadoc工具记录. 默认情况下,javadoc是不包括注解的. 但如
            果声明注解时指定了 @Documented,则它会被 javadoc 之类的工具处理, 所以注解类型信息也会被包括
            在生成的文档中.

       Target注解

            @Target说明了Annotation所修饰的对象范围：Annotation可被用于 packages、types（类、接口、枚
            举、Annotation类型）、类型成员（方法、构造方法、成员变量、枚举值）、方法参数和本地变量（如循环变
            量、catch参数）。在Annotation类型的声明中使用了target可更加明晰其修饰的目标。
 
            作用：用于描述注解的使用范围（即：被描述的注解可以用在什么地方） 
            取值(ElementType)有：

                 1.CONSTRUCTOR:用于描述构造器 
                 2.FIELD:用于描述域 
                 3.LOCAL_VARIABLE:用于描述局部变量 
                 4.METHOD:用于描述方法 
                 5.PACKAGE:用于描述包 
                 6.PARAMETER:用于描述参数 
                 7.TYPE:用于描述类、接口(包括注解类型) 或enum声明

        Inherited 注解

             这是一个稍微复杂的注解类型. 它指明被注解的类会自动继承. 更具体地说,如果定义注解时使用了 
             @Inherited 标记,然后用定义的注解来标注另一个父类, 父类又有一个子类(subclass),则父类的所
             有属性将被继承到它的子类中.
</pre>

![](https://i.imgur.com/VESJqh3.png)

<pre>
Spring aop vs aspectJ

      AspectJ是静态代理的增强，所谓的静态代理就是AOP框架会在编译阶段生成AOP代理类，因此也称为编译时增强

      使用Spring AOP与AspectJ的静态代理不同，Spring AOP使用的动态代理，所谓的动态代理就是说AOP框架不会
      去修改字节码，而是在内存中临时为方法生成一个AOP对象，这个AOP对象包含了目标对象的全部方法，并且在特定
      的切点做了增强处理，并回调原对象的方法
</pre>

<pre>
Error、Exception区别

    Error类和Exception类的父类都是throwable类，他们的区别是：

       1)Error类一般是指与虚拟机相关的问题，如系统崩溃，虚拟机错误，内存空间不足，方法调用栈溢等。对于这
         类错误的导致的应用程序中断，仅靠程序本身无法恢复和和预防，遇到这样的错误，建议让程序终止。

       2)Exception类表示程序可以处理的异常，可以捕获且可能恢复。遇到这类异常，应该尽可能处理异常，使程序
         恢复运行，而不应该随意终止异常。
</pre>

<pre>
8.Java中如何实现代理机制(JDK、CGLIB)

JDK动态代理：代理类和目标类实现了共同的接口，用到InvocationHandler接口。

CGLIB动态代理：代理类是目标类的子类，用到MethodInterceptor接口。
</pre>

<pre>
12.Java中的NIO，BIO，AIO分别是什么

BIO:同步并阻塞，服务器实现模式为一个连接一个线程，即客户端有连接请求时服务器端就需要启动一个线程进行处理，
如果这个连接不做任何事情会造成不必要的线程开销，当然可以通过线程池机制改善。BIO方式适用于连接数目比较小且固
定的架构，这种方式对服务器资源要求比较高，并发局限于应用中，JDK1.4以前的唯一选择，但程序直观简单易理解。

NIO:同步非阻塞，服务器实现模式为一个请求一个线程，即客户端发送的连接请求都会注册到多路复用器上，多路复用器
轮询到连接有I/O请求时才启动一个线程进行处理。NIO方式适用于连接数目多且连接比较短（轻操作）的架构，比如聊天
服务器，并发局限于应用中，编程比较复杂，JDK1.4开始支持。

AIO:异步非阻塞，服务器实现模式为一个有效请求一个线程，客户端的I/O请求都是由OS先完成了再通知服务器应用去启
动线程进行处理.AIO方式使用于连接数目多且连接比较长（重操作）的架构，比如相册服务器，充分调用OS参与并发操
作，编程比较复杂，JDK7开始支持。
</pre>

<pre>
17.出现OOM如何解决

一. 可通过命令定期抓取heap dump或者启动参数OOM时自动抓取heap dump文件。

二. 通过对比多个heap dump，以及heap dump的内容，分析代码找出内存占用最多的地方。

三. 分析占用的内存对象，是否是因为错误导致的内存未及时释放，或者数据过多导致的内存溢出。
</pre>

<pre>
Servlet的生命周期
     主要分三个阶段：初始化——调用init()方法，响应客户请求阶段——调用service()方法，终止阶段——调用
     destroy方法。工作原理：客户发送一个请求，servlet调用service方法对请求进行响应，即对请求方式进行匹
     配，选择调用doGet、doPost方法等，然后进入对于的方法中调用逻辑层的方法，实现对客户的响应。自定义的
     servlet必须首先servlet接口。

     具体生命周期包括：装载Servlet、服务器创建Servlet实例、服务器调用Servlet的init()方法、客户请求到达服
     务器、服务器创建请求对象、服务创建相应对象、服务器激活Servlet的service方法，请求对象和响应对象作为
     service()方法的参数、service()方法获得关于请求对象的信息，处理请求，访问其他资源，获得需要的信息、
     service()方法可能激活其他方法以处理请求，如doGet()，doPost()
</pre>

<pre>
十、Statement与PreparedStatement的区别,什么是SQL注入，如何防止SQL注入

     使用PreparedStatement可以提升代码的可读性和可维护性，可以尽最大可能提高性能。因为Statement每次执行
     一个SQL命令都会对其编译，但PreparedStatement则只编译一次。PreparedStatement就类似于流水线生产。另
     一方面PreparedStatement可以极大提高安全性：它对传递过来的参数进行了强制参数类型转换，确保插入或查询
     数据时，与底层数据库格式匹配。

     SQL注入：就是通过将sql命令插入到web表单递交或输入域名或页面请求的查询字符串，最终达到欺骗服务器执行
     恶意SQL命令。如sql命令：select id from test where name='1' or 1=1; drop table test,但用
     PreparedStatement就可以避免这种问题。
</pre>

<pre>
十四、反射讲一讲，主要是概念,都在哪需要反射机制，反射的性能，如何优化
能够分析类能力的程序称为反射。反射机制可以用来：在运行中分析类的能力，在运行中查看对象，如编写一个toString
方法供所有类使用。实现通用的数据操作代码。利用Method对象，这个对象很像C++的指针。

反射性能优化方法主要为设置不用做安全检查。
</pre>

<pre>
十九、Tomcat的session处理，如果让你实现一个tomcatserver，如何实现session机制
当一个session开始时，Servlet容器会创建一个HttpSession对象，在某些情况下把这些HttpSession对象从内存中转
移到文件系统中或数据库中。需要访问的时候将它们载入到内存中。这样的好处就是节省内存，当web服务器产生故障时，
还可以从文件系统或数据库中恢复Session的数据。管理session有两个类：1）StandardManager，这是一个默认的类，
当tomcat启动或重载时将会session对象保存到指定文件中。2）PersistentManager，管理方式更加灵活，具有容错能
力，可以及时把Session备份到Session Store中，可以控制内存中Session的数量。
</pre>


<pre>
Object的通用方法

通用方法有equals(), finalize(), toString(), 其他native方法有hashcode(), 
registerNatives(), getClass(), clone(), notify(), notifyAll(), wait()等。
</pre>

<pre>
Collection有哪些类

      Set, 
         HashSet, 
         TreeSet,
      List, 
         ArrayList, 
         LinkedList, 
         Vector,
         Arrays,
      SortedSet, 
      Map,
         SortedMap,   
      Collections,  
      AbstractCollection
</pre>

<pre>
jdbc的操作过程

      加载数据库驱动包、
      连接数据库、
      使用sql语句操作数据库、
      关闭数据库连接
</pre>

<pre>
介绍threadlocal

      可以叫做线程本地变量或线程本地存储。ThreadLocal为变量在每个线程中都创建了一个副本，每个线程都可以访
      问自己内部的副本变量。但可能这样做会导致内存占用较大。

      ThreadLocal类的几个方法：
            get() 用来获取ThreadLocal在当前线程中保存的变量副本，
            set()用来设置当前线程中变量的副本，
            remove()用来一冲当前线程中的变量副本，
            initialValue()一般用来在使用时进行重写，是一个延迟加载方法。

      应用场景：
          最常见的ThreadLocal使用场景是用来解决数据库连接、Session管理等。
</pre>

<pre>
线程之间的通信:

      主要包括互斥锁、条件变量、读写锁和线程信号灯。

          互斥锁：
                以排他方式防止数据被并发修改，互斥锁两个状态0和1，具体为申请锁，占用锁以防止数据被修改，
              此时默认为阻塞等等，最后释放锁。

          条件变量通信机制：
                原理：条件变量出现是，可以弥补互斥锁的缺陷，有些问题仅仅依靠互斥锁无法解决，但条件变量
              不能单独使用，必须配合互斥锁一起实现对象资源的互斥访问。

          读写锁：
                在对数据读写时，往往读占据主要部分，基本原则是如果其他线程读数据，则允许其他线程执行读
              操作，但不允许写操作，如果有其他线程申请写操作，则其他线程不能申请读操作和写操作。

          线程信号：
                线程拥有与信号相关的私有数据---线程信号掩码，线程可以向别的线程发送信号，每个线程可以设置
              自己的阻塞集合，所有线程中，同一信号任何线程对该线程的处理相同。
</pre>

<pre>
Jdk的并发工具包介绍

      Map并发包：
               其实现为ConcurrentHashMap，它实现了ConcurrentMap接口，put方法为根据计算出的hash值去
          获取segment对象，找到segment对象后调用该对象的put方法完成操作。segment中的put方法则是先加锁，
          然后判断数组大小，判断是否需要扩充，得到key所要存放的位置。

      List并发包：
               在高并发环境中使用CopyOnWriteArrayList代替ArrayList，添加元素是利用数组的copy功能和
          加锁机制，并发情况下，CopyOnWriteArrayList比ArrayList略快了一些。

      Set并发包
               CopyOnWriteSet和CopyOnWriteList底层实现差不多，只是会在添加元素时进行唯一性判断，如果
          对象数组中已经含有重复的元素，则不进行增加处理。

      Queue并发
               ArrayBlockingQueue，底层为数组，并对关键的方法入队，出队操作添加了锁机制。

      Atomic系列类
               比如AtomicInteger类，通过使用计数器操作时，一般为了避免线程安全问题，在方法上加锁操作，
          有了并发包就可以直接使用。
</pre>

<pre>
垃圾回收算法使用的产品、场景

      标记-清除算法：标记阶段，确定所有要回收的对象，并标记，清除阶段则将需要回收的对象清除。

      复制算法：把内存分为大小相等的两块，每次使用其中的一块，当垃圾回收时，把存活的对象复制到另一块上，
               然后把这块内存整个清理掉。两块内存比是8：1

      标记整理算法：把存活的对象往内存的一端移动，然后直接回收边界以外的内存。标记-整理算法提高了内存的利
                  用率，并且它适合在收集对象存活时间较长的老年代。

      分代回收算法：根据对象的存活时间把内存分为新生代和老年代，根据各代对象的存活特点，每代采用不同的GC
                  算法。新生代用标记-复制算法，老年代用标记-整理算法。
</pre>

<pre>
HashMap冲突解决方案：

      1）链表法
         链表法就是将相同hash值的对象组织成一个链表放在hash值对应的槽位
  
      2）开放定址法
         开放地址法是通过一个探测算法，当某个槽位已经被占据的情况下继续查找下一个可以使用的槽位

      java.util.HashMap采用的链表法的方式，链表是单向链表

      其中loadFactor加载因子是表示Hsah表中元素的填满的程度.

      若:加载因子越大,填满的元素越多,好处是,空间利用率高了,但:冲突的机会加大了.链表长度会越来越长,查找效率降低。

      反之,加载因子越小,填满的元素越少,好处是:冲突的机会减小了,但:空间浪费多了.表中的数据将过于稀疏（很
      多空间还没用，就开始扩容了）

      冲突的机会越大,则查找的成本越高.

      因此,必须在 "冲突的机会"与"空间利用率"之间寻找一种平衡与折衷. 这种平衡与折衷本质上是数据结构中有
      名的"时-空"矛盾的平衡与折衷.

　　  如果机器内存足够，并且想要提高查询速度的话可以将加载因子设置小一点；相反如果机器内存紧张，并且对查询
     速度没有什么要求的话可以将加载因子设置大一点。不过一般我们都不用去设置它，让它取默认值0.75就好了。
</pre>

<pre>
LockSupport

     LockSupport是JDK中比较底层的类，用来创建锁和其他同步工具类的基本线程阻塞原语。Java锁和同步器框架的
     核心AQS就是通过调用LockSupport.park(), LockSupport.unpark()实现线程的阻塞和唤醒的。

     LockSupport很类似于二元信号量(只有1个许可证可供使用)，如果这个许可还没有被占用，当前线程获取许可并
     继续执行；如果许可已经被占用，当前线程阻塞，等待获取许可。

     LockSupport是不可重入的，如果一个线程连续2次调用LockSupport.park()，那么该线程一定会一直阻塞下去。

     这说明线程如果因为调用park而阻塞的话，能够响应中断请求(中断状态被设置成true)，但是不会抛出
     InterruptedException
</pre>

<pre>
     红黑树：平衡二叉树，通过对任何一条从根到叶子的简单路径上各个节点的颜色进行约束，确保没有一条路径会比
     其他路径长2倍，因而是近似平衡的。所以相对于严格要求平衡的AVL树来说，它的旋转保持平衡次数较少。用于搜
     索时，插入删除次数多的情况下我们就用红黑树来取代AVL。

      B树，B+树：它们特点是一样的，是多路查找树，一般用于数据库中做索引，因为它们分支多层数少，因为磁盘
      IO是非常耗时的，而像大量数据存储在磁盘中所以我们要有效的减少磁盘IO次数避免磁盘频繁的查找。
      B+树是B树的变种树，有n棵子树的节点中含有n个关键字，每个关键字不保存数据，只用来索引，数据都保存在
      叶子节点。是为文件系统而生的。

      B+树相对B树磁盘读写代价更低：因为B+树非叶子结点只存储键值，单个节点占空间小，索引块能够存储更多的节点，从磁盘读索引时所需的索引块更少，所以索引查找时I/O次数较B-Tree索引少，效率更高。而且B+Tree在叶子节点存放的记录以链表的形式链接，范围查找或遍历效率更高。Mysql InnoDB用的就是B+Tree索引。

红黑树应用比较广泛：

·    1) 广泛用在C++的STL中。map和set都是用红黑树实现的。
·    2) 著名的linux进程调度Completely Fair Scheduler,用红黑树管理进程控制块。
·    3) epoll在内核中的实现，用红黑树管理事件块
·    5) nginx中，用红黑树管理timer等
·    6) Java的TreeMap实现
</pre>

###B+树 VS B树

![](https://i.imgur.com/mpznr5v.png)

<pre>
（1）不同的是，Ｂ＋树中间节点没有卫星数据（索引元素所指向的数据记录），只有索引，而Ｂ树每个结点中的每个
    关键字都有卫星数据；这就意味着同样的大小的磁盘页可以容纳更多节点元素，在相同的数据量下，Ｂ＋树更加
    “矮胖”，IO操作更少。
 (2) 其次，因为卫星数据的不同，导致查询过程也不同；Ｂ树的查找只需找到匹配元素即可，最好情况下查找到根节
     点，最坏情况下查找到叶子结点，所说性能很不稳定，而Ｂ＋树每次必须查找到叶子结点，性能稳定。
（3）在范围查询方面，B+树的优势更加明显 
　　B树的范围查找需要不断依赖中序遍历。首先二分查找到范围下限，在不断通过中序遍历，知道查找到范围的上限即
   可。整个过程比较耗时。 

　　而B+树的范围查找则简单了许多。首先通过二分查找，找到范围下限，然后同过叶子结点的链表顺序遍历，直至找到
   上限即可，整个过程简单许多，效率也比较高。 
</pre>

<pre>
为什么 MongoDB 使用B-树

     MongoDB 是一种 nosql，也存储在磁盘上，被设计用在 数据模型简单，性能要求高的场合。性能要求高，看看
     B/B+树的区别第一点：

     1) B+树内节点不存储数据，所有 data 存储在叶节点导致查询时间复杂度固定为 log n。而B-树查询时间复杂
        度不固定，与 key 在树中的位置有关，最好为O(1)

        我们说过，尽可能少的磁盘 IO 是提高性能的有效手段。MongoDB 是聚合型数据库，而 B-树恰好 key 和
        data 域聚合在一起。

     2) 为什么 Mysql 使用B+树
        Mysql 是一种关系型数据库，区间访问是常见的一种情况，而 B-树并不支持区间访问（可参见上图），而B+
        树由于数据全部存储在叶子节点，并且通过指针串在一起，这样就很容易的进行区间遍历甚至全部遍历。

        见B/B+树的区别第二点：

        B+树叶节点两两相连可大大增加区间访问性，可使用在范围查询等，而B-树每个节点 key 和 data 在一起，
        则无法区间查找。

     3) 其次B+树的查询效率更加稳定，数据全部存储在叶子节点，查询时间复杂度固定为 O(log n)。

     最后第三点：

        B+树更适合外部存储。由于内节点无 data 域，每个节点能索引的范围更大更精确
</pre>

###MyIsam

![](https://i.imgur.com/Q4KxyVO.png)

<pre>
InnoDB VS MyIsam
      MyIsam:

          主键索引：
                 MyISAM引擎使用B+Tree作为索引结构，叶节点的data域存放的是数据记录的地址

                 同样也是一颗B+Tree，data域保存数据记录的地址。因此，MyISAM中索引检索的算法为首先按照
                 B+Tree搜索算法搜索索引，如果指定的Key存在，则取出其data域的值，然后以data域的值为
                 地址，读取相应数据记录。

          辅助索引:
                 在MyISAM中，主索引和辅助索引（Secondary key）在结构上没有任何区别，只是主索引要求
                 key是唯一的，而辅助索引的key可以重复

          同样也是一颗B+Tree，data域保存数据记录的地址。因此，MyISAM中索引检索的算法为首先按照B+Tree
          搜索算法搜索索引，如果指定的Key存在，则取出其data域的值，然后以data域的值为地址，读取相应数
          据记录。

          MyISAM的索引方式也叫做“非聚集”的，之所以这么称呼是为了与InnoDB的聚集索引区分。

      InnoDB:
           
          然InnoDB也使用B+Tree作为索引结构，但具体实现方式却与MyISAM截然不同

          主键索引:
                 MyISAM索引文件和数据文件是分离的，索引文件仅保存数据记录的地址。而在InnoDB中，表数据文件本身就是按B+Tree组织的一个索引结构，这棵树的叶节点data域保存了完整的数据记录。这个
                 索引的key是数据表的主键，因此InnoDB表数据文件本身就是主索引。

                 (图inndb主键索引）是InnoDB主索引（同时也是数据文件）的示意图，可以看到叶节点包含了完
                 整的数据记录。这种索引叫做聚集索引。因为InnoDB的数据文件本身要按主键聚集，所以InnoDB要
                 求表必须有主键（MyISAM可以没有），如果没有显式指定，则MySQL系统会自动选择一个可以唯一
                 标识数据记录的列作为主键，如果不存在这种列，则MySQL自动为InnoDB表生成一个隐含字段作为
                 主键，这个字段长度为6个字节，类型为长整形。

                 InnoDB 表是基于聚簇索引建立的。因此InnoDB 的索引能提供一种非常快速的主键查找性能。不
                 过，它的辅助索引（Secondary Index， 也就是非主键索引）也会包含主键列，所以，如果主键
                 定义的比较大，其他索引也将很大。如果想在表上定义 、很多索引，则争取尽量把主键定义得小一
                 些。InnoDB 不会压缩索引。

       InnoDB索引和MyISAM索引的区别：

           一是主索引的区别，InnoDB的数据文件本身就是索引文件。而MyISAM的索引和数据是分开的。

           二是辅助索引的区别：InnoDB的辅助索引data域存储相应记录主键的值而不是地址。而MyISAM的辅助索
           引和主索引没有多大区别。
</pre>

![](https://i.imgur.com/utrFnwk.png)

<pre>
分布式缓存：

     Redis
     Memcached
     CouchBase
     JGroup + Evcache
     Gemfire(12306购票网站)
     Ignite
     Hazelcast
</pre>

<pre>
          对于频繁抛出的异常，JDK为了性能会做一个优化，在JIT重新编译后抛出没有堆栈的异常，在使用server
      模式的时候，这个优化是开启的。

          一个解决办法是暂时禁用这个优化，强制要求每次都要抛出有堆栈的异常。幸好JDK提供了选项来关闭这个优
      化，配置JVM参数:
                   -XX:-OmitStackTraceInFastThrow 就可以禁止这个优化（注意选项中的减号，加号是启用）

      -Xmx512m -XX:CompileThreshold=10000 设置堆最大为512M，设置当一个方法被调用1万次的时候就被JIT编译

      总结下本文找bug经历想表达的几点想法：
         （1）正确地打印错误日志
         （2）在server模式下，最好都设置-XX:-OmitStackTraceInFastThrow
         （3）使用类或者方法的时候，最好能详细阅读下javadoc，很多问题都能找到答案
         （4）使用SimpleDateFormat的时候要注意线程安全性，要么每次new，要么做同步，两者的性能有差距，
              但是这个差距很难成为你的性能瓶颈
</pre>

<pre>
     实时队列采用双队列模式，生产者将行为记录写入Queue1，worker服务从Queue1消费新鲜数据，如果异常则写入
     Queue2（主要保存异常数据），RetryWorker会监听Queue2，消费异常数据，如果还未处理成功按照一定的策略
     等待或者将异常数据再写入Queue2，如果数据发生积压可以调整worker的消费游标，从最新数据重新开始消费，保
     证了最新data得到处理，中间未处理的一段则可以启动backupWorker指定起止游标在消费完指定区间的数据后，
     backupWorker会自动停止。

     DB降级开关后，可直接写入redis（storm），同时将数据写入一份到Retry队列，在开启DB降级开关后消费Retry
     队列中的数据，从而把数据写入到mysql中，达到最终一致性。MYSQL切分为分片为2的N次方，例如原来分为两个库
     d0和d1均放在s0服务器上，s0同时有备机s1，扩容只要几步骤：确保s0到s1服务器同步顺利，没有明显延迟；s0
     暂时关闭读写权限；确保s1已经完全同步到s0更新；s1开放读写权限；d1的dns由s0切换到s1；s0开放读写权限。
</pre>

<pre>
DB的特性和隔离级别

4大特性：原子性，一致性，分离性，持久性

隔离级别：

读提交：写事务禁止读

读未提交：写事务允许读

可重复读：写事务禁止读事务，读禁止写

序列化：全部禁止

详细说明：读提交1个事务开始写则全部禁止其他事务访问该行。读未提交1个事务开始写则不允许其他事务同时写，但可以
读。可重复读 读事务会禁止写事务，写事物则禁止其他任何事务。序列化性能最低，全部禁止，串行执行。 MYSQL默认的
是可重复读。
</pre>

<pre>
多线程同步锁

A，RentrantLock，可重入的互斥锁，可中断可限时，公平锁，必须在finally释放锁，而synchronize由JVM释放。
可重入但是要重复退出，普通的lock()不能响应中断，lock.lockInterruptbly()可响应中断，可以限时tryLock()，
超时返回false，不会永久等待构成死锁。

B，Condition条件变量，signal唤醒其中1个在等待的线程，signalall唤醒所有在等待的线程await()等待并释放锁，
与lock结合使用。

C，semaphore信号量，多个线程比（额度=10）进入临界区，其他则阻塞在临界区外。

D，ReadWriteLock，读读不互斥，读写互斥，写写互斥。

E，CountDownLantch倒数计时器，countdown()和await()

F，CyCliBarrier

G，LockSupport，方法park和unpark
</pre>

<pre>
说一下内存泄露

A，HashMap,vector等容易（静态集合类）， 和应用程序生命周期一样，所引用的所有对象Object也不能释放。

B，当集合类里面的对象属性被修改后，再调用remove()不起作用，hashcode值发生了改变

C，其对象add监听器，但是往往释放对象时忘记去删除这些监听器

D，各种连接记得关闭

E，内部类的引用

F，调用其他模块，对象作用参数

G，单例模式，持有外部对象引用无法收回。
</pre>

<pre>
如何将数据分布在redis第几个库？

答：redis 本身支持16个数据库，通过 数据库id 设置，默认为0。
   例如jedis客户端设置。一：JedisPool(org.apache.commons.pool.impl.GenericObjectPool.Config 
   poolConfig, String host, int port, int timeout, String password, int database);
   第一种通过指定构造函数database字段选择库，不设置则默认0库。二：jedis.select(index);调用jedis的
   select方法指定。
</pre>