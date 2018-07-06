# rixinsummertraining-dayi-
日新暑假封训日志（JAVA）的
第一次记录
1.java的文件是先编码然后先生成一个.class的字节码文件然后再有jvm去转化成执行文件所以可以在不同的平台（系统）上使用。这就是java的跨平台性。
2.jvm：虚拟机将.class加载并且运行
  jre：jvm+系统类库运行java代码所必须的最小环境
  jdk：jre+一些编译运行等功能是开发java所必须的最小环境（java开发包）
3.java严格区分大小写println输出后换行print输出后不换行
4.int的范围为21亿到-21亿如果超出则报错，而如果是（1+最大值）不会报错只会溢出（得不到正确的答案）所以要使用长整形long，但是一般默认赋值时如a=10000这个10000默认为整形如果
要他默认为长整形则a=10000L，记住如果默认为int的时候赋值大于范围的最大值或者小于范围的最小值则会报错。如a=2200000000报错，a=2200000000L则为正确。同样的道理浮点型默认为double如果要变成float
在后面加F或者f。
5.如果字符串要进行判断要用equals函数如：String x ；if（x=equals（exit））  在Java中必须要用equals才能进行字符串判断。而像int这种基本类型则用==。
6.Java中继承用extend
7.Java中super值的是当前对象的父类在Java中必须先写父类再写派生类派生类的构造函数必须用super调用父类的无参构造函数然后调用派生类自己的构造函数如果手动调用了父类（也是用super）
的构造函数则不会默认调用。如果在派生类的构造函数中有参则会显示编译错误必须用super手动调用。
8.向上造型只能用父类的东西如变量函数而不能用派生类
9.重写是运行期绑定所以看对象来绑定，重载是编译器绑定所以看参数的类型来绑定。
//
重写必须函数类型名字都一样只能参数不一样
而重载只要名字一样参数不一样
//
10.抽象设计规则：
1）将所有派生类所共有的属性和行为，抽象到超类
2）所有派生类的行为都一样，设计为普通方法
所有派生类的行为都不一样，设计为抽象方法抽象方法在子类种必须重写而普通方法不需要
11.抽象类不能被实例化比如student是抽象类则不能student a=new student 不能new student只能被继承使用。但是数组的对象可以。
12.抽象类的意义
1）封装类中所有的共同属性和行为
2）为派生类提供统一的类型——向上造型
3）抽象类包含抽象方法为所有派生类提供统一入口，派生类不一样，但入口一样。
13.内部类
形如class Aoo{
class Boo{}
}
1)该类只能服务于外部类不能被其他类调用
2）通常内部类在外部内内部声明内部类可以直接访问外部成员因为默认有个this指针。
14.匿名内部类：如abstrct class Aoo{}本来不能直接Aoo o1=new Aoo但是可以Aoo o1=new Aoo{}等于创建了一个Aoo的派生类并且同时声明该派生类的对象o1.
15.接口为只有部分类有公共属性和方法才定义接口接口中只要出现就一定是常量所以定义要同时初始化。
出现方法一定是抽象的所以不需要包括方法体。所以一定要重写。
！！！！接口也不能被实例化。
接口也可以向上造型。
16.强制类型转换（向上造型这一类的）有两个条件满足则转换成功不满足则失败：
1）引用所指的对象，就是该类型。
2）引用所指的对象，实现了该接口。
Aoo o1=new Boo();//向上造型（自动类型转换）
Boo o2=(Boo)o1;//符合条件1;
Inter1 o3=(Inter1)o1;//符合条件2
Coo o4=(Coo)o1;//类型转换异常
interface Inter1{
}
class Aoo{
}
class Boo extends Aoo implements Inter1
{
}
class Coo extends Aoo{}



可以通过instanceof 来判断是否该类型。
