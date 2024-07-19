### Scanner类介绍：
- Scanner类创建的对象是一个简单的**文本扫描器**，简单来讲就是：获取数据源(输入流、用户、文件等)的输入，对输入文本进行扫描。
- 想要更清晰的了解Scanner的工作过程，我们需要了解一下Java中的“**令牌**”：
   - 令牌即tokens，是由编译器识别的程序的**最小元素**，Java中的令牌包括标识符、关键字、运算符、文字和分隔符。
- 在Scanner中，默认分隔符是**空格**，也可以调用`useDelimiter`方法自定义分隔符。
- 分隔符将字符串划分为令牌，随后可以调用各种`next`方法将得到的**令牌**转换成不同类型的值。
### 引入及创建类的对象：
```java
import java.util.Scanner;
public class Input{
    public static void main(String[] args){
        Scanner input = new Scanner(System.in);
    }
}
```
### 相关方法解析：
#### 构造方法：

- 构造从指定**文件**扫描的对象：
   - `Scanner input = new Scanner(File source);`
- 构造从指定**输入流**扫描的对象：
   - `Scanner input = new Scanner(InputStream source);`
- 构造从指定**字符串**扫描的对象：
   - `Scanner input = new Scanner(String source);`
#### next及其原始类协同方法：

- **next**：
   - 查找并返回该**文本扫描器**的下一个完整令牌，返回类型是`String`。
- **nextByte**：
   - 将下一个**令牌**扫描成`Byte`类型并返回。
- **nextShort**：
   - 将下一个**令牌**扫描成`Short`类型并返回。
- **nextInt**：
   - 将下一个**令牌**扫描成`int`类型并返回。
- **nextLong**：
   - 将下一个**令牌**扫描成`long`类型并返回。
- **nextFloat**：
   - 将下一个**令牌**扫描成`float`类型并返回。
- **nextDouble**：
   - 将下一个**令牌**扫描成`double`类型并返回。
- **nextLine**：
   - 返回**一整行**数据，返回类型是`String`。
#### hasNext及其原始类协同方法：

- **hasNext**：
   - 如果该**文本扫描器**扫描出一个**完整令牌**，则返回**true**。
