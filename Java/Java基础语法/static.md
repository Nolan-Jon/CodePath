# 静态类：
- 如果一个类要被声明为`static`，只有一种情况：**静态内部类**。
# 静态属性：
## 静态属性的概念：

- 将一个类中的**属性**定义为`static`，这个**静态属性属于这个类**。
- 无论创建多少个对象，只有一个静态属性，所有的对象共享这个静态属性。
- 即使没有创建对象，这个静态属性也存在。
## 静态属性的初始化：

- 静态属性不需要在构造器中进行初始化，应该在**定义类**的时候进行**显式初始化**。
## 静态属性的调用：

- 静态属性的值**可以被修改**。
- 静态变量的**访问权限**取和**访问范围**决于**访问修饰符**。
- 静态属性需要使用**类名+.**进行调用。
   - 在同一个类的方法中调用静态属性时，可以直接使用名称调用。
- 静态属性随着类的加载而创建，即使没有创建对象实例也可以访问静态属性。
- **静态属性的存储位置**：
   - 在JDK8之前，静态属性存储在**方法区**。
   - 在JDK8之后，静态属性存储在**堆**中，更确切来讲，存储在类对应的`Class`对象的尾部。
- **不要通过this或super关键字调用静态属性，请使用类名调用**！！！
## 静态属性的分类：
### 静态变量属性：

- 为了满足**封装**的思想，需要将访问修饰符设置为**private**，这意味着**静态变量属性**只能在**类中的方法**调用。
- 如果我们希望静态属性可以被修改，那么就定义静态变量属性，否则使用静态常量属性！！！
```java
//在同一个类中调用静态属性，可以直接使用名称调用
class Employee{
    private static String companyName = "CCNU-IOT";
    private String name;
    private int salary;

    public Employee(String name, int salary) {
        this.name = name;
        this.salary = salary;
    }
    public String EmployeeInfo(){
        return "Name: " + name + ", Salary: " + salary + " in " + companyName;
    }
}
```
```java
//调用静态属性时，不需要创建任何对象
public class ArraysTem {
    public static void main(String[] args) {
        System.out.println(Employee.name);
    }
}
class Employee{
    public static String name = "nolan";
    //这不满足封装的思想，我们通常不这样做
    //如果外界想调用name，我们可以使用静态常量属性
}
```
### 静态常量属性：

- 通常，我们将**静态常量属性**的**访问修饰符**设置为**public**，这依旧满足封装的思想，因为**final**修饰的对象不允许被修改。
```java
public class ArraysTem {
    public static void main(String[] args) {
        System.out.println(Employee.name);
    }
}
class Employee{
    public static final String name = "nolan";
    //static和final的位置可以互换
}
```
# 静态方法：
## 静态方法的概念：

- 将一个类中的**方法**定义为`static`，这个**静态方法属于这个类**。
- 静态方法不属于任何对象：
   - 静态方法没有**this**参数。
   - 静态方法**只能访问静态属性或静态方法**。
      - 普通方法可以访问**静态属性**和**静态方法。**
   - **注意：静态方法可以调用构造器！！！**
      - 很显然，构造器不是普通方法，构造器属于类，不属于对象。
- **如果我们希望不创建实例，也可以调用某个方法(即当做工具)，那么应该将该方法定义成static。**
## 静态方法的调用：

- 静态方法的调用：通过**类名+.**进行调用。
   - 虽然对象可以调用静态方法，但是不建议这样做，这种写法会造成混淆，误认为静态方法是普通成员方法。
   - 通常情况下，我们将静态方法的访问修饰符设置为`public`。
- **不要通过this或super关键字调用静态方法，请使用类名调用**！！！
```java
public class ArraysTem {
    public static void main(String[] args) {
        System.out.println(Employee.info());
    }
}
class Employee{
    public static String info(){
        return "Employee Info";
    }
}
```
