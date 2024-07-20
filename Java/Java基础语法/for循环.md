### for循环的基本语法：
```java
for (循环变量初始化;循环条件;循环变量迭代){
    statement;
}
```
### 使用for循环构建死循环：
```java
for (;;){
    //这是一个死循环
}
```
### for循环中的循环初始值：

- for循环中的循环初始值可以有**多条初始化语句**，但要求类型一样，中间用“,”隔开。
```java
for (int i = 0, j = 2; i < 10; i++){
    //初始化语句必须写成int i = 0, j = 2;
    //不能写成int i = 0, int j = 2;
}
```
### 嵌套循环：

- 嵌套循环建议一般使用两层，不超过三层，否则，代码的可读性很差。
### for each循环：

- **for each**循环可以用来依次处理**数组**或**元素集合**中的**“每个元素”**，不必考虑指定的**下标值**。
```java
for (var : collection){
    statement;
}
```

- **for each**循环定义一个变量**var**，用于暂存集合中的每一个元素，**var**的类型要与集合中的元素类型相同。
- **collection**是**数组**或实现**Iterable接口的类对象**。
```java
int[] a = {1,2,3,4,5,6,7,8,9};
for (int element : a){
    System.out.println(element);
}
```
### 空心金字塔：

- 请编写一个程序，可以接收一个整数，表示层数(totalLevel)，打印出空心金字塔。
- **化繁为简的思想**：
   - **第一步：打印半个金字塔**
```java
/*
*
**
***
****
*****
*/
//思路：层数和点数相同
int totalLevel = 5;
//i表示层数(1 ~ 5)，j表示点数
for (int i = 1; i <= totalLevel; i++){
    for (int j = 1; j <= i; j++){
        System.out.print("*");
    }
    System.out.println("");
}
```

      - ![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1720769817358-ef4445df-25ab-4631-88e8-6bd32564efa7.png#averageHue=%231f2023&clientId=ue3b067ea-34a5-4&from=paste&height=162&id=u245763db&originHeight=323&originWidth=959&originalType=binary&ratio=2&rotation=0&showTitle=false&size=11067&status=done&style=none&taskId=ua87c7b31-a628-4d08-9117-a4e30277a44&title=&width=479.5)
   - **第二步：打印整个全金字塔**
```java
/*
    *          totalLevel - 1个空格  +  1个* 
   ***         totalLevel - 2个空格  +  3个*
  *****        totalLevel - 3个空格  +  5个*
 *******       totalLevel - 4个空格  +  7个*
*********      totalLevel - 5个空格  +  9个*
*/
//i表示层数(1 ~ 5)，j表示点数/空格数
//空格数 = totalLevel - i
//点数 = i + i - 1
int totalLevel = 5;
for (int i = 1; i <= totalLevel; i++){
    for (int j = 1; j <= totalLevel - i; j++){
        System.out.print(" ");
    }
    for (int j = 1; j <= i + i - 1; j++){
        System.out.print("*");
    }
    System.out.println("");
}
```

      - ![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1720770629340-7d2b7831-591e-4c48-9eee-dfbc077436ca.png#averageHue=%231f2023&clientId=ue3b067ea-34a5-4&from=paste&height=154&id=u1215e169&originHeight=307&originWidth=999&originalType=binary&ratio=2&rotation=0&showTitle=false&size=11061&status=done&style=none&taskId=ufd340c33-3dda-4be6-90d9-724e9922af2&title=&width=499.5)
   - **第三步：打印空心金字塔**
```java
/*
     *
    * *
   *   *
  *     *
 *       *
***********
*/
//i表示层数,j表示带点数/空格数
//前置空格数 = totalLevel - i
//在打印点的时候要进行判断，即只打印第一个点和最后一个点
//最后一行的点要完整打印
int totalLevel = 5;
for (int i = 1; i <= totalLevel; i++){
    //打印前置空格
    for (int j = 1; j <= totalLevel - i; j++){
        System.out.print(" ");
    }
    //打印点和空格
    for (int j = 1; j <= i + i - 1; j++){
        if (j == 1 || j == i + i - 1 || i = totalLevel){
            System.out.print("*");
        }
        else {
            System.out.print(" ");
        }
    }
    System.out.println("");
}
```

      - ![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1720771590183-4a3dcac9-6e4c-4888-8791-7d33554d629b.png#averageHue=%231f2023&clientId=ue3b067ea-34a5-4&from=paste&height=155&id=ud6df496d&originHeight=309&originWidth=791&originalType=binary&ratio=2&rotation=0&showTitle=false&size=10735&status=done&style=none&taskId=u414257b6-c09f-4ec6-bcdf-e1ddf72a07e&title=&width=395.5)
### break在循环中的使用：

- 当循环的次数不确定时，我们可以在循环中创建**条件语句，**当满足某个条件的时候，触发`break`来**结束循环**。
   - `break`只能用来跳出**循环**和**switch语句**。
   - 当`break`用在循环语句中时，用来跳出**距离最近的循环体**。
### continue在循环中的使用：

- `continue`负责在循环体中结束本次循环，继续执行下一次循环。
   - `continue`出现在嵌套循环中时，作用于**距离最近的循环体**。
