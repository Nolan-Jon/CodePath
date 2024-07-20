# main方法的形式：
```java
public static void main(String[] args){
    
}
```
# main的调用与执行：

- **Java虚拟机**调用类的`main()`方法，为了获得`main()`的**访问权限**，需要将`main()`方法设置为`public`。
- 在调用过程中，不必创建`main()`方法所在类的对象，因此需要把`main()`方法设置为**静态方法(static)**。
- 在`main()`方法中，可以直接调用`main()`方法所在类的**静态方法**或**静态属性**。
   - 不能在`main()`方法中访问该类的**普通成员**和**普通方法**。
- `main()`方法接收`String[]`类型的参数，该数组中保存执行`java`命令时传递给**所运行的类**的参数。
   - ![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1721491444398-52a1d5a4-362f-4569-8182-78c58801d63e.png#averageHue=%23fbfbfb&clientId=ue1244460-e971-4&from=paste&height=286&id=u718126f6&originHeight=571&originWidth=799&originalType=binary&ratio=2&rotation=0&showTitle=false&size=39742&status=done&style=none&taskId=uc28b9ba3-3bc5-43b9-869c-d7d8765f01a&title=&width=399.5)
# main参数传递：

- **在IDEA中给main方法传递参数**：
   - ![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1721491892417-3bf75267-10ca-44a5-8996-58f4661c5188.png#averageHue=%2325272a&clientId=ue1244460-e971-4&from=paste&height=902&id=u6b4bbb87&originHeight=1803&originWidth=2771&originalType=binary&ratio=2&rotation=0&showTitle=false&size=253066&status=done&style=none&taskId=u063c7dea-dcbd-4479-a0a1-9724ac7419d&title=&width=1385.5)
   - ![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1721491866502-6e349529-a91c-4cfb-bbed-6e6e4c57d9dd.png#averageHue=%232a2c30&clientId=ue1244460-e971-4&from=paste&height=902&id=ue69fd585&originHeight=1803&originWidth=2771&originalType=binary&ratio=2&rotation=0&showTitle=false&size=358266&status=done&style=none&taskId=ub5d020f8-3ea1-47df-ae33-7d20defaa34&title=&width=1385.5)
   - ![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1721491919899-87ea883b-ab7d-4208-966b-16ca14671694.png#averageHue=%231f2023&clientId=ue1244460-e971-4&from=paste&height=160&id=u698e8d24&originHeight=319&originWidth=1007&originalType=binary&ratio=2&rotation=0&showTitle=false&size=13955&status=done&style=none&taskId=ub0b4cd5b-2c63-4b3e-a237-8e432bb122e&title=&width=503.5)
