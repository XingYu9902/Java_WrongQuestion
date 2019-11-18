1.String属于引用类型

> `×`  在Java中，数组和String字符串都不是基本数据类型，**它们被当作类来处理**，是引用数据类型。

2.3.14是float型

> `×` Java中浮点型常量默认为double型，如果要声明一个float型，需在后面加f或F (这个居然也选错...)

3.声明数组时可以直接指定数组的大小

>`×` Java语言声明数组时不能指定其长度

4.java程序编译的结果（class文件）中包含的是实际机器的CPU指令

>`×` JVM负责将class文件翻译成特定平台的机器指令，并不在class文件中包含

5.有如下类定义：
```Java
  public class Rectangle {
  public int width = 3;
  public int height = 4;
  public int area() {
          return width * height;
  }
  }
  则如下代码输出结果为：
  Rectangle rectangle;
  rectangle.height = 5;
  System.out.println(rectangle.area());
  ```
  
  >编译错误，因为rectangle没有初始化，程序不能运行 (一点要细心...)
  
  6.执行如下代码片段后，i和n的值分别为：
  ```Java
  int i = 10;
  int n =( i++) % 5;
  ```
  >结果为i=11,n=0 ； 解析：i++，i会增加一，但是整个表达式返回的值是i的旧值。与之对应的是++i，i也会增加一，整个表达式返回的是i的新值。
  
  7.对于Java1.7及之后版本，如下不能用于switch的类型是：
  
  >double类型。 (凭感觉选对了，实际很好想到.. 因为浮点数不精确)
  
  8.下列关于main方法的描述中，错误的是？
  
  `A` main方法是Java程序的入口
  
  `B`main方式的格式为public static void main(String[] args){}
  
  `C`B选项中所描述格式中形参args不能更改，如果将args改为arguments则不能通过编译
  
  `D`main方法可以被重载
  
  >正确答案为：C ； 形参名字可以随意更改，形参类型不可以更改，必须是String[]；
  
  >读完题目想都没想就选了D选项，关于main方法的重载我会单独放在一个md中解释。
  
  >[main方法重载](https://github.com/XingYu9902/Java_WrongQuestion/blob/master/overloadMain.md)
  
  9.Given the uncompleted code of a class:
  
  ```Java
  class Person {

    String name, department;

    int age;

    public Person(String n){ name = n; }

    public Person(String n, int a){ name = n; age = a; }

    public Person(String n, String d, int a) {

        // doing the same as two arguments version of constructor 

        // including assignment name=n,age=a

        department = d;

   }

}
```
Which expression can be added at the "doing the same as..." part of the constructor?（可以在构造函数中添加哪个表达式来实现"dong the same as..."的内容)

  `A` Person(n,a);
  
  `B` this(Person(n,a));
  
  `C` this(n,a);
  
  `D` this(name,age);
  
  >正确答案：C ；可以使用this来调用`同类`中的构造函数，在第三个构造方法中添加C选项即可完成所要求的内容。
  
  10.Given the following class 
  
  ```Java
  class MyNumber

{

   private int num = 5;

   public MyNumber(int num) { this.num = num; }

   public int getNum() { return num; }

   public void setNum(int num) { this.num = num; }

}

   What is output after the executation of following code? 

   MyNumber obj1 = new MyNumber();

   MyNumber obj2 = new MyNumber(10);

   obj2 = obj1;

   obj2.setNum(20);

   System.out.println(obj1.getNum() + “,” + obj2.getNum());
   ```
   
>正确答案 ：编译错误 ； 如果一个类中定义了构造方法，编译器便不会自动添加默认的无参构造方法，而代码中obj1对象调用了无参构造方法，编译出错。

11. Given the following class:
```Java
class Mixer {

    Mixer() { }

    Mixer(Mixer m) { m1 = m; }

    Mixer m1;


    public static void main(String[] args) {

        Mixer m2 = new Mixer();

        Mixer m3 = new Mixer(m2);  m3.go();

        Mixer m4 = m3.m1;  m4.go();

        Mixer m5 = m2.m1;  m5.go();

    }

    

    void go() { System.out.print("hi "); }

}
```
What is the result

  `A` Compilation fails
  
  `B` hi hi hi
  
  `C` hi hi, followed by an exception
  
  `D` hi, followed by an exception
  
  >正确答案：C ； m3.m1本质上是m2的，因此m4是真实存在的。而m2.m1没有赋值过，所以m5是null，因此无法调用m5.go(), 运行错误。
