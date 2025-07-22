# java基础

基本类型

byte(1) 、short(2)、int(4)、long(8)、char(2)、float(4)、double(8)、boolean(1)

对象创建过程：类加载->声明类型引用->堆内存分配->属性0值初始化->对象头设置->属性显示初始化->构造方法初始化

JVM：编辑-> 加载-> 验证-> 准备-> 解析-> 使用 ->销毁

StringBuilder：单线程、效率高 StringBuffer：线程安全