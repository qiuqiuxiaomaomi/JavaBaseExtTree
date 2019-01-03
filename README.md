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

<pre>
嵌套for循环的优化准则：

      1）外小内大原则
      2）提取与循环无关的表达式
      3）消除循环终止判断的方法调用
      5）循环的异常捕获
         大家都知道，捕获异常是很耗资源的，所以不要讲try catch放到循环内部，优化后同样有好几个数量级的
         提升
</pre>
