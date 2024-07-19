### Java基础介绍：
#### Java程序的执行过程：
![](https://cdn.nlark.com/yuque/0/2024/jpeg/35940756/1720246036222-64c85616-9427-4d08-b146-d5d101f26c62.jpeg)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1720278740570-28eb9d36-6553-41dd-8240-198f7b02f162.png#averageHue=%23101010&clientId=u5f581578-8032-4&from=paste&height=613&id=ue550ddb8&originHeight=613&originWidth=1101&originalType=binary&ratio=1&rotation=0&showTitle=false&size=24096&status=done&style=none&taskId=ueaf070f3-98ad-4e9e-9241-6f948fc0950&title=&width=1101)

- `Hello.java`是**源文件**，`javac`工具对其进行**编译**操作，生成**字节码文件**`Hello.class`
   - 注意，如果有中文，在使用**终端**进行编译的时候，需要将`Hello.java`的编码格式换成**GBK**。
- `java Hello`表示运行`Hello`这个类
#### JDK与JRE：

- JDK的全称是Java Development Kit，即Java开发工具包，JDK是提供给Java开发人员使用的，其中包含了**Java开发工具集**，也包括了**JRE**。
- JRE的全称是Java Runtime Enviroment，即Java运行环境，`JRE = JVM + Java核心类库`，如果想要运行一个开发好的Java程序，只需要JRE。
- `JDK = JRE + Java的开发工具`(如：javac、java、javadoc、javap)。
#### Java核心类库版本：

- Java EE，Java Enterprise Edition，即Java企业版，多用于企业级开发，从Java5.0之后改名为Java EE。
- Java SE，Java Standard Edition，即Java标准版，多用于个人开发者，从Java5.0之后改名为Java SE。
- Java ME，Java Micro Edition，即Java微型版，主要用于移动设备、嵌入式设备上的Java程序开发，从Java5.0之后改名为Java ME。
- 一般情况下，不严格区分**Java核心类库**和**JDK**：
   - **Java SE 8**是长期支持版本，通常来讲我们认为这是**JDK版本**，当然也可以认为是**Java核心类库版本**。
   - **Java SE 11**也是长期支持版本。
#### JDK 8.0安装包：
[JDK 8.0 For Windows](https://www.oracle.com/cn/java/technologies/downloads/#java8-windows)
**Oracle账号**：~~1031964705@qq.com~~
**Oracle密码**：~~Jiang18231452021@~~
#### JDK 8.0安装/配置：
**安装**：
![注意安装路径](https://cdn.nlark.com/yuque/0/2024/png/35940756/1720249176516-015741de-f3b9-455b-b1f5-625f1fa2b2a3.png#averageHue=%23eae9e8&clientId=u5f581578-8032-4&from=paste&height=373&id=uc0c946c5&originHeight=373&originWidth=491&originalType=binary&ratio=1&rotation=0&showTitle=true&size=21090&status=done&style=none&taskId=uad9b07f2-a40d-46be-929b-5f997284a3d&title=%E6%B3%A8%E6%84%8F%E5%AE%89%E8%A3%85%E8%B7%AF%E5%BE%84&width=491 "注意安装路径")
![公共JRE安装路径](https://cdn.nlark.com/yuque/0/2024/png/35940756/1720249367611-e3e2ebc9-549b-48df-a1e7-42feed3d17a7.png#averageHue=%23f5f4f0&clientId=u5f581578-8032-4&from=paste&height=271&id=u05260b04&originHeight=380&originWidth=697&originalType=binary&ratio=1&rotation=0&showTitle=true&size=16987&status=done&style=none&taskId=u8dfb3d52-875f-4918-97f7-182844f3ebe&title=%E5%85%AC%E5%85%B1JRE%E5%AE%89%E8%A3%85%E8%B7%AF%E5%BE%84&width=497 "公共JRE安装路径")
![安装成功](https://cdn.nlark.com/yuque/0/2024/png/35940756/1720249423731-667c0b3e-3a5a-40dc-9db9-01cafd1821f8.png#averageHue=%23f7f7f6&clientId=u5f581578-8032-4&from=paste&height=374&id=u082bcc4b&originHeight=374&originWidth=494&originalType=binary&ratio=1&rotation=0&showTitle=true&size=16001&status=done&style=none&taskId=ud665bbc4-e646-4dcc-abd4-9be5dd24499&title=%E5%AE%89%E8%A3%85%E6%88%90%E5%8A%9F&width=494 "安装成功")
**配置**：
![添加JDK的环境变量](https://cdn.nlark.com/yuque/0/2024/png/35940756/1720249924892-ac0e29ec-c774-4291-a7fc-aed35fa717c7.png#averageHue=%23f0eeed&clientId=u5f581578-8032-4&from=paste&height=558&id=udb98c9dc&originHeight=558&originWidth=519&originalType=binary&ratio=1&rotation=0&showTitle=true&size=42893&status=done&style=none&taskId=u440ca2d7-5039-41dc-9151-c424866be5d&title=%E6%B7%BB%E5%8A%A0JDK%E7%9A%84%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F&width=519 "添加JDK的环境变量")
![检测JDK版本](https://cdn.nlark.com/yuque/0/2024/png/35940756/1720250081882-e100c260-e9e3-494c-b2b3-397667dab21d.png#averageHue=%23101010&clientId=u5f581578-8032-4&from=paste&height=570&id=u5d92fc7b&originHeight=570&originWidth=1102&originalType=binary&ratio=1&rotation=0&showTitle=true&size=27490&status=done&style=none&taskId=uc1a39f0d-e592-4411-8d7a-c830cb80bc2&title=%E6%A3%80%E6%B5%8BJDK%E7%89%88%E6%9C%AC&width=1102 "检测JDK版本")

### Java开发细节：
#### 源文件与类的关系：

- **一个源文件**中最多有**一个public类**，其他类的个数不限。
- 源文件进行编译后，每一个类都会对应一个`.class`文件。
- 如果源文件中包含一个public类，那么文件名必须和该类名相同。
- 非public类中可以拥有**主方法**，可以运行非public类中的主方法。
#### Java基本数据类型：
Java提供了8种基本数据类型，每种数据类型的大小不随环境而改变。

- **byte**：8位有符号数，范围-128 ~ 127
- **short**：16位有符号数，范围-32768 ~ 32767
- **int**：32位有符号数，Java的整形常量默认是int类型
- **long**：64位有符号数，后缀为L
- **float**：32位单精度浮点数，后缀为f
- **double**：64位双精度浮点数，后缀d，Java的浮点型常量默认是double类型
- **boolean**：1位，只取true或false
- **char**：16位单一的Unicode字符，用单引号赋值，范围\u0000 ~ \uffff(0 ~ 65535)

**浮点数相关细节**：

- `float num = 1.1f`，如果不加后缀f，则会发生转换错误，Java不支持将double类型自动转换为float类型。
- 通常情况下，应该使用**double**，因为他比**float**更精确。
- 不要对浮点数进行直接的大小判断。应该以两个数的差值的绝对值在某个精度内进行判断。

**布尔类型相关细节**：

- 在Java中，不可以将**0**或**非0**赋值给`boolean`类型，只能对其赋值**true**或**false**。
#### Java类的组织形式：
![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1721111147744-0d589e35-ff0d-4528-9193-5143c9a881f6.png#averageHue=%23fdfdfd&clientId=u4d98c6dd-6144-4&from=paste&height=414&id=uac11395c&originHeight=827&originWidth=845&originalType=binary&ratio=2&rotation=0&showTitle=false&size=45348&status=done&style=none&taskId=u894af75d-6705-48e2-81ca-898166b7458&title=&width=422.5)
**Java在线API手册**：[https://www.matools.com/api/java8](https://www.matools.com/api/java8)
#### Java自动类型转换：
**两条转换路径(精度小的类型自动转换成精度大的类型)**：

- `char` ——> `int` ——> `long` ——> `float` ——> `double`
- `byte` ——> `short` ——> `int` ——> `long` ——> `float` ——> `double`

**转换细节**：

- 有多种类型的数据混合运算的时候，系统将所有数据转换成精度最大的那种数据类型，再进行计算。
- 将精度大的数据类型转换成精度小的数据类型时会报错，Java不支持这样操作。
- 虽然整数常量默认是`int`类型，但对`byte`或`short`类型赋值时，只要整数值不超过`byte`或`short`的表示范围，那么该整数常量是`byte`或`short`类型。
- `boolean`类型不参与自动类型转换。
- (byte、short)和char之间不能够自动转换。
- `byte`、`short`和`char`之间可以计算，在计算时转换成`int`类型，因此计算后的结果最少要保存在`int`类型里。
```java
byte m = 10;
byte n = 11;
//byte temp = m + n; 错误
int temp = m + n;//正确
```
#### Java强制类型转换：

- Java中可以通过强制类型转换将精度大的数据类型转换为精度小的数据类型，需要加强制类型转换符`()`，可能会造成溢出。
#### 取模的本质：

- `a % b = a - a / b * b`
#### 后置递增和前置递增的本质：
```java
int i = 1;
i = i++;
```

- `i = i++`的执行过程：**先赋值再递增**
   - `temp = i;`//此时i = 1
   - `i = i + 1;`//此时i = 2
   - `i = temp;`//此时i = 1
```java
int i = 1;
i = ++i;
```

- `i = ++i`的执行过程：**先递增再赋值**
   - `i = i + 1;`//此时i = 2
   - `temp = i;`//此时i = 2
   - `i = temp;`//此时i = 2
#### 关系运算符的返回值：

- 关系运算符的返回值是`boolean`类型，要么为**true**，要么为**false**，**关系表达式**只能赋值`给boolean`类型。
#### Java中的逻辑运算符和按位运算符：

- 逻辑运算符：`&&`、`||`、`!`
- 按位运算符：`&`、`|`、`^`
- 逻辑运算符执行逻辑运算，逻辑运算的表达式结果为`boolean`类型。
- 按位运算符执行按位运算，按位运算的表达式的结果遵循四则运算的原则。
- **按位与、按位或和按位异或**也可以做逻辑运算(即**用在逻辑表达式之间**)，此时表达式的结果是`boolean`类型(即可以将结果赋值给`boolean`类型的变量)，与逻辑运算符的区别：

**按位与**：
```java
byte a = 1;
byte b = 2;
int c = a & b;
System.out.println(c);
//0000 0001 & 0000 0010 = 0000 0000 
```
```java
int a = 5;
int b = 10;
if (a < 4 & b++ < 11){
    
}
System.out.println(b);
//逻辑表达式中a < 4不成立，但依旧会执行b++ < 11这条语句
//这也是与逻辑与不同的地方，逻辑与在判断出第一个表达式错误之后就会得出结果
//最后b的值为11
```
**按位或**：
```java
byte a = 1;
byte b = 2 ;
int c = a | b;
System.out.println(c);
//0000 0001 | 0000 0010 = 0000 0011
```
```java
int a = 5;
int b = 10;
if (a < 10 | b++ < 11){

}
System.out.println(b);
//逻辑表达式中a < 10已经成立，但依旧会执行b++ < 11这条语句
//这也是与逻辑或不同的地方，逻辑或在判断出第一个表达式正确之后就会得出结果
//最后b的值为11
```
**按位异或**：
```java
byte a = 1;
byte b = 3;
int c = a ^ b;
System.out.println(c);
//0000 0001 ^ 0000 0011 = 0000 0010
```
```java
byte a = 1;
byte b = 3;
boolean c = (a > 0) ^ (a < 2);  //true ^ true = false
boolean d = (b > 4) ^ (b < 2);  //false ^ false = false
boolean e = (a > 2) ^ (b > 2);  //false ^ true = true
System.out.println(c);
System.out.println(d);
System.out.println(e);
```
#### Java中标识符的命名规则：

- 标识符由**26个英文字母**、**0 ~ 9数字**、**_**和**$**组成。
- 数字不能做标识符的开头。
- 标识符中**可以包含**关键字和保留字。
- 标识符严格区分大小写。
- 标识符长度**无限制**。
- 标识符**不能包含**空格。
#### Java中标识符的命名规范：

- [Java开发手册(黄山版).pdf](https://www.yuque.com/attachments/yuque/0/2024/pdf/35940756/1720586073519-f01b36a2-c3d6-448d-8913-cac0a2c50465.pdf?_lake_card=%7B%22src%22%3A%22https%3A%2F%2Fwww.yuque.com%2Fattachments%2Fyuque%2F0%2F2024%2Fpdf%2F35940756%2F1720586073519-f01b36a2-c3d6-448d-8913-cac0a2c50465.pdf%22%2C%22name%22%3A%22Java%E5%BC%80%E5%8F%91%E6%89%8B%E5%86%8C(%E9%BB%84%E5%B1%B1%E7%89%88).pdf%22%2C%22size%22%3A1496687%2C%22ext%22%3A%22pdf%22%2C%22source%22%3A%22%22%2C%22status%22%3A%22done%22%2C%22download%22%3Atrue%2C%22taskId%22%3A%22u17d5d53b-30ad-4799-9a5e-06bc4402da1%22%2C%22taskType%22%3A%22upload%22%2C%22type%22%3A%22application%2Fpdf%22%2C%22__spacing%22%3A%22both%22%2C%22mode%22%3A%22title%22%2C%22id%22%3A%22ubfec14da%22%2C%22margin%22%3A%7B%22top%22%3Atrue%2C%22bottom%22%3Atrue%7D%2C%22card%22%3A%22file%22%7D)
