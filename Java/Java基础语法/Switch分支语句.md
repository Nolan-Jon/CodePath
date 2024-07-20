### switch语句结构：
```java
switch(a){
    case 1:
        System.out.println("1");
        break;
    case 2:
        System.out.println("2");
    default:
        System.out.println("default");
        break;
}
```
### switch细节：

- **switch**中，表达式的数据类型要和`case`后的常量类型一致，或者是可以自动转换的。
   - 必须是表达式的值可以转换成`case`后面常量的值，**反过来不可以**。
- **switch**中，表达式的返回值必须是以下类型：`byte、short、int、char、enum、String`
- `case`后面的值必须是常量，而不能是变量。
- `default`语句是可选的，当没有匹配项时，执行`default`语句。
- `break`语句用来在执行完一个`case`语句后跳出**switch**语句块，如果没有`break`，程序会顺序执行到**switch**结尾。

