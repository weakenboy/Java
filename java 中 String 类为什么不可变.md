# java中String类为什么不可变？

> 不可变对象，顾名思义就是创建后的对象不可以改变，典型的例子有java中的String类型。

字符串池

字符串池是方法区中的一部分特殊存储。当一个字符串被被创建的时候，首先会去这个字符串池中查找，如果找到，直接返回对该字符串的引用。

缓存Hashcode

Java中经常会用到字符串的哈希码（hashcode）。例如，在HashMap中，字符串的不可变能保证其hashcode永远保持一致，这样就可以避免一些不必要的麻烦。这也就意味着每次在使用一个字符串的hashcode的时候不用重新计算一次，这样更加高效。

安全性

String被广泛的使用在其他Java类中充当参数。比如网络连接、打开文件等操作。如果字符串可变，那么类似操作可能导致安全问题。

不可变对象天生就是线程安全的

因为不可变对象不能被改变，所以他们可以自由地在多个线程之间共享。不需要任何同步处理。

总之，String被设计成不可变的主要目的是为了安全和高效。所以，使String是一个不可变类是一个很好的设计。