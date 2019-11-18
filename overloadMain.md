### 关于main方法重载问题

由于main函数的重要性，一致认为main函数是不能重载的，但是经过学习发现，main函数也是可以重载的，但是起决定作用的还是带String[]参数的那个main方法。

下面是测试main方法重载的源码：

```Java
public class Test {
    public static void main(String[] args) {
        System.out.println("测试main方法重载");
        main();
        main(0);
        main(0,1);
    }
    public static void main(){
        System.out.println("第一个main重载方法");
    }

    public static void main(int x){
        System.out.println("第二个main重载方法");
    }
    public static void main(int x,int y){
        System.out.println("第三个main重载方法");
    }
}
```

运行结果：

>测试main函数重载

>第一个main重载方法

>第二个main重载方法

>第三个main重载方法

>运行结果说明main方法是可以重载的
