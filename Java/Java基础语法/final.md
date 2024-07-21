# final类：
- 当**不希望类被继承**时，需要使用`final`关键字修饰类。
- `final`破坏了**继承关系**，本质上是将类中的方法锁定，防止任何继承类修改方法的含义。
- 如果一个类是**final类**，那么不需要将其中的方法声明成**final方法**，因为无法被继承的类一定不支持重写。
- **包装器**与**String类**都是**final类**，因此这些类不能够被继承。
```java
public final class Test{
    //类
}
```
# final方法：

- 在不破坏继承关系的前提下，不希望父类的某个方法被子类**重写**，需要使用`final`关键字修饰方法。
```java
public final class Test{
    public final void func(){
        //方法体
    }
}
```
# final属性：

- 不希望类中属性的值被修改。
```java
public final class Test{
    private final double PI = 3.1415926;
}
```
# final局部变量：

- 需要在**定义局部变量的时候给定初始值，之后不能修改**。
```java
public final class Test{
    public static void main(String[] args){
        final double PI = 3.1415;
    }
}
```
# final的使用细节：

1. `final`修饰的**属性**或**局部变量**叫“**常量**”，一般用**XX_XX_XX**命名。
2. `final`修饰的**局部变量**需要在**定义时**赋初始值。
3. `final`修饰的**普通属性**需要在如下位置赋初始值：
   1. 定义属性时。
   2. 构造器中。
   3. 普通代码块中。
      1. 不能在静态代码块中赋初始值！！！
4. `final`修饰的**静态属性**需要在如下位置赋初始值：
   1. 定义属性时。
   2. 静态代码块中。
5. `final`不能修饰构造器。
# final和static搭配：
## static final属性：

- 用`static`关键字修饰**final属性**时，编译器会做底层优化，**_避免加载类_**。
   - 如果一个属性是**final类型**，最好将其定义为**static final类型**。
```java
public class Tools {
    public static final double PI = 3.14;
    static {
        System.out.println("Tools类的静态代码块");
    }
    public static final void print(String str) {
        System.out.println(str);
    }
}
```
```java
public class Test {
    public static void main(String[] args) {
        System.out.println(Tools.PI);
    }
}
```

- **打印结果**：
   - ![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1721564451593-a8e2343c-0b45-4f09-8f81-95976bad1688.png#averageHue=%23202124&clientId=u097e6bb0-a27b-4&from=paste&height=83&id=ucc3d966a&originHeight=165&originWidth=737&originalType=binary&ratio=2&rotation=0&showTitle=false&size=8349&status=done&style=none&taskId=u6c1a6978-f0a1-4e83-b1c0-9b8abdac18f&title=&width=368.5)
   - 由于没有执行静态代码块，因此`Tools`类没有加载。
- **注意**：
   - `static final`修饰的属性必须在**定义时赋初始值**，这样才不会加载类。
   - 如果在静态代码块中赋初始值，JVM依旧会加载类。
## static final方法：

- 编译器没有对**static final方法**进行优化，调用**static final方法**会加载类。
```java
public class Tools {
    public static final double PI = 3.14;
    static {
        System.out.println("Tools类的静态代码块");
    }
    public static final void print(String str) {
        System.out.println(str);
    }
}
```
```java
public class Test {
    public static void main(String[] args) {
        Tools.print("Hello World");
    }
}
```

- **打印结果**：
   - ![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1721564746831-7656af83-b9c3-4de1-ad61-fe5f4211dec6.png#averageHue=%23202125&clientId=u097e6bb0-a27b-4&from=paste&height=116&id=u9f4f46cb&originHeight=231&originWidth=755&originalType=binary&ratio=2&rotation=0&showTitle=false&size=16227&status=done&style=none&taskId=u1d03e4d6-901f-4a00-aebd-b182fbdb910&title=&width=377.5)
