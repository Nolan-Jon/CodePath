# Arrays类的概念：
- `Arrays`类包含了用于**操作数组**的各种方法，适用于各种**基本数据类型数组**和**对象数组**。
   - 此类的所有方法，在数组引用为`null`时，都会抛出`NullPointerException`异常。
- `Arrays`类的签名：`public class Arrays extends Object`
   - `Arrays`类可以被其他类继承，但不建议这样做。
- `Arrays`类中的方法(不包括继承于`Object`的方法)均为**静态方法**，因此不需要创建`Arrays`对象就可以使用。
   - `Arrays`类中只有**默认无参构造器**。
- `Arrays`类自身没有属性。
# 数组的排序：
## 基本数据类型的排序：

- 

## 基于Object的排序：

- 

## 基于泛型的排序：

- 需要实现`Comparator`接口，通常在`sort`中采用**匿名内部类实参**。
# Arrays类的使用：

- [Arrays类的Java API](https://docs.oracle.com/javase/8/docs/api/)
