
### Java中static的特点

1、 static在java中到底代表什么，为何要用它？

2、 static在java中怎么用？

3、 static 有那些特点和使用的“局限”？

4、当成员变量被静态修饰后，和非静态成员变量的区别？

 

1、 static在java中到底代表什么，为何要用它？

      static――静态――“指定位置“
      首先，我们来看看java的内存：java把内存分为栈内存和堆内存，栈内存用来存放一些基本类型的变量和数组及对象的引用变量，而堆内存主要是来放置对象的。
      用 static的修饰的变量和方法，实际上是指定了这些变量和方法在内存中的“固定位置”－static storage。既然要有“固定位置”那么他们的 “大小”似乎就是固定的了，有了固定位置和固定大小的特征了，在栈中或堆中开辟空间那就是非常的方便了。如果静态的变量或方法在不出其作用域的情况下，其引用句柄是不会发生改变的。
      我们常看到：static变量有点类似于C中的全局变量的概念；静态表示的是内存的共享，就是它的每一个 实例都指向同一个内存地址。把static拿来，就是告诉JVM它是静态的，它的引用（含间接引用）都是指向同一个位置，在那个地方，你把它改了，它就不会变成原样，你把它清理了，它就不会回来了。

      注：java的主类中main()方法本身就是一个static的，所以main方法的执行就是在没有产生新的实例的情况。

 

2、 static在java中怎么用？

 

static是一个修饰符，用于修饰成员（成员变量和成员函数）。
当成员被静态修饰后，就多了一个调用方式，除了可以被对象调用外，还可以直接被类名调用：类名.静态成员。
 
3、 static 有那些特点和使用的“局限”？
（一）特点
	静态成员随着类的加载而加载；
	静态成员优先于对象存在；
	静态成员被所有对象所共享；
	静态成员多了一个中调用方式，可以被类名直接调用。
（二）利弊
	利：
	对对象的共享数据进行单独空间的存储，节省空间，没有必要每一个对象中都存储一份；
	可以直接被类名调用。
	弊：
	生命周期过长；
	访问出现局限性，只能访问静态。
（三）注意事项
	静态方法只能访问静态成员, 非静态方法既可以访问静态又可以访问非静态；
	静态方法中不可以定义this，super关键字；（因为this代表是对象，而静态存在时，有可能没有对象，且静态优先于对象存在。所以静态方法运行时，this是没有任何对象代表的。 简单说，先进内存的数据不可以访问后进内存的数据，可是后进内存数据可以访问先进内存的数据）
	主函数是静态的
 
4、当成员变量被静态修饰后，和非静态成员变量的区别？
	静态变量也称为类变量，也就是直接可以被类名调用的变，这个变量是所属于类的；
	        非静态变量称为成员变量，或者实例变量，是被对象调用的，是所属具体对象的。
	静态变量随着类的加载而加载，也意味着随着类的消失而消失，生命周期最长； 
	        实例变量，随着对象的创建而加载，随着对象的消失而消失，按照对象的生命周期而存在。
	静态变量存储在方法区的静态区中；
	        实例变量存在于对象所属的堆内存中。
	静态变量数据，被所有对象所共享；
	        实例变量是对象中的特有数据。