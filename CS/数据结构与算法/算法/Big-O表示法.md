## 时间复杂度：
时间复杂度反应算法**运行时间**随数据量变大的**增长趋势**。
### 常见的时间复杂度类型：
![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1721096414697-1ee5c378-a2f1-4a53-8cab-c1eb149050ad.png#averageHue=%23fefefe&clientId=ude79912b-83fe-4&from=paste&height=89&id=u523521eb&originHeight=177&originWidth=1383&originalType=binary&ratio=2&rotation=0&showTitle=false&size=38618&status=done&style=none&taskId=ub89eef2e-0dbc-4f56-bafb-280843b7391&title=&width=691.5)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1721096443272-49494130-dd00-46c7-9c92-1697ff4dad13.png#averageHue=%23fdfbfb&clientId=ude79912b-83fe-4&from=paste&height=627&id=u15fd78cf&originHeight=1253&originWidth=2469&originalType=binary&ratio=2&rotation=0&showTitle=false&size=234953&status=done&style=none&taskId=ue5463b62-f574-44dc-a09f-2958d35e20f&title=&width=1234.5)
### 时间复杂度为O(1)的代码：
![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1720784635366-60b98a02-86dc-43bf-8f57-e7eeffc6cceb.png#averageHue=%23fbfbfb&clientId=ub86d870b-5e1f-4&from=paste&height=446&id=u118a516f&originHeight=891&originWidth=869&originalType=binary&ratio=2&rotation=0&showTitle=false&size=29188&status=done&style=none&taskId=ufe994a34-7dd9-463e-a72e-2aa4d57e5b0&title=&width=434.5)

- **常数阶**的操作数量与输入数据大小n无关，即不随着n的变化而变化。
### 时间复杂度为O(logN)的代码：
![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1720784622389-64d15f8b-772b-4414-93ca-a6167966e5a4.png#averageHue=%23fafafa&clientId=ub86d870b-5e1f-4&from=paste&height=441&id=u2cf69db9&originHeight=881&originWidth=884&originalType=binary&ratio=2&rotation=0&showTitle=false&size=26893&status=done&style=none&taskId=u2bb3843d-afbc-4d98-96a7-4e3419e4de2&title=&width=442)

- 要理解这段代码的时间复杂度为什么是`O(logN)`，我们需要一些简单的数学知识：**指数与对数的转换**
   - 我们假设：while循环执行k次，也就意味着`i = i  * 2k`，由于n无穷大，所以我们可以近似认为`i = 2k`,当代码执行完毕时`i = n`，即`2k = n`
   - 指数与对数的转换公式：![](https://cdn.nlark.com/yuque/__latex/a2424af30426fe9167bde1d0f451bc62.svg#card=math&code=a%5Eb%20%3D%20N%20%20%3C%E2%80%94%E2%80%94%3E%20log_aN%20%3D%20b%0A&id=psUg4)
   - 因此：`k = log2n`，我们可以忽略底数2，认为时间复杂度为logn
- 从更高层次理解：
   - `i++`表示i的变化是**线性**的，因此最终的时间复杂度也是**线性**的。
   - `i = i * 2`表示i的变化是**指数**的，因此最终的时间复杂度是**对数**的。
### 时间复杂度为O(nlogN)的代码：
![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1720787037463-1da7eafe-4a57-4ac6-994c-3699f7da4975.png#averageHue=%23f9f9f9&clientId=u5d5769c6-358d-4&from=paste&height=445&id=u87b44b6d&originHeight=889&originWidth=897&originalType=binary&ratio=2&rotation=0&showTitle=false&size=37298&status=done&style=none&taskId=uffbac8e5-c9f6-4090-8072-f47c1b3516f&title=&width=448.5)

- **线性对数阶**常出现在**嵌套循环**中，两层的时间复杂度分别为**O(logN)**和**O(n)**。
- **主流排序算法**的时间复杂度通常为**O(nlogN)**：快速排序、归并排序、堆排序。
### 时间复杂度为O(n2)的代码：
![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1720840653902-248ae407-1824-486b-99b5-764caea9b968.png#averageHue=%23fafafa&clientId=ue59025ab-e869-4&from=paste&height=427&id=ub7f4aed6&originHeight=853&originWidth=893&originalType=binary&ratio=2&rotation=0&showTitle=false&size=31256&status=done&style=none&taskId=uabcaa755-2ae1-4956-a232-5f074412be2&title=&width=446.5)

- 两个时间复杂度都为n的嵌套循环。
### 时间复杂度为O(nm)的代码：
![](https://cdn.nlark.com/yuque/0/2024/jpeg/35940756/1720840856544-a21614ea-a873-434c-b00c-ae450f827fff.jpeg)

- 一个时间复杂度为n的循环嵌套一个时间复杂度为m的循环。
## 空间复杂度：
空间复杂度反应算法**内存空间**随数据量变大的**增长趋势**。

- 算法在运行过程中使用的**内存空间**主要包括以下几种：
   - **输入空间**：用于存储算法的输入数据。
   - **输出空间**：用于存储算法的输出数据。
   - **暂存空间**：用于存储算法在运行过程中的变量、对象、函数上下文等数据。暂存空间又可以划分为以下三个部分：
      - **暂存数据**：用于保存算法运行过程中的各种常量、变量、对象等。
      - **栈帧空间**：用于保存调用函数的上下文数据。系统在每次调用函数时都会在栈顶部创建一个栈帧，函数返回后，栈帧空间释放。
      - **指令空间**：用于保存编译后的程序指令，通常忽略不计。
- 在分析一段程序的空间复杂度时，我们通常统计以下部分：
   - ![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1721098516206-4182854e-4b84-42b1-b419-c71763ea76c5.png#averageHue=%23fcfcfc&clientId=ude79912b-83fe-4&from=paste&height=315&id=u10c6d08b&originHeight=629&originWidth=1287&originalType=binary&ratio=2&rotation=0&showTitle=false&size=70952&status=done&style=none&taskId=u943d6837-4e18-4afd-b82b-cb3b7be2f8b&title=&width=643.5)
### 空间复杂度为O(1)的代码：
![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1720842161135-cca8df75-fd83-4108-ae54-7e404c107247.png#averageHue=%23fcfcfc&clientId=ue59025ab-e869-4&from=paste&height=440&id=u27a640f0&originHeight=879&originWidth=901&originalType=binary&ratio=2&rotation=0&showTitle=false&size=22190&status=done&style=none&taskId=u5a88b984-30af-4a09-a10f-9433ada3736&title=&width=450.5)

- 单个变量/对象的分配，我们认为空间复杂度为1。
### 空间复杂度为O(n)的代码：
![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1720842425058-7e78d3c0-f9f1-4ea9-a681-ba226a71b0bb.png#averageHue=%23fbfbfb&clientId=ue59025ab-e869-4&from=paste&height=436&id=uf68a68c6&originHeight=871&originWidth=897&originalType=binary&ratio=2&rotation=0&showTitle=false&size=31064&status=done&style=none&taskId=uf97d6dbf-72be-47ae-af66-7b6da321c0a&title=&width=448.5)

- **一维数组**占据的空间复杂度是n。
### 空间复杂度为O(n2)的代码：

- 分配的内存是二维数组。
