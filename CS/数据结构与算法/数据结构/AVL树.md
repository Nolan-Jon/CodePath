# AVL树的概念：
- **二叉搜索树**具有优秀的时间复杂度，一个**完美的二叉搜索树**执行各种操作的时间复杂度是**O(logN)**。
- **二叉搜索树**执行多次**插入**或**删除**操作后，很大概率退化成**链表**，此时各种操作的时间复杂度退化成**O(n)**。
- **删除节点**：

![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1721985369974-c924d362-734f-4a1c-afd2-4b043ad5a8f0.png#averageHue=%23fbfbfb&clientId=u38deec09-8fed-4&from=paste&height=349&id=u6359c323&originHeight=697&originWidth=1333&originalType=binary&ratio=2&rotation=0&showTitle=false&size=109730&status=done&style=none&taskId=ua4d8747f-2816-42b7-bee2-a1a265e7195&title=&width=666.5)

   - 从**平衡二叉树**退化成链表。
- **插入节点**：

![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1721985396575-7b4cd5a3-a22c-4bd3-acc6-f0bf8b9c7deb.png#averageHue=%23fbfbfb&clientId=u38deec09-8fed-4&from=paste&height=346&id=u243e0816&originHeight=691&originWidth=1325&originalType=binary&ratio=2&rotation=0&showTitle=false&size=112516&status=done&style=none&taskId=u664a5da1-a099-448b-8721-382e41cebd0&title=&width=662.5)

   - 从**完美二叉树**退化成普通二叉树(也可以认为是链表)。
- **AVL树**能够确保在持续的**插入**和**删除**节点后**不退化**，从而使得各种操作的时间复杂度保持在**O(logN)**。
- 在需要**频繁增删查改**的环境中，**AVL树**能够始终保持高效的数据操作性能。
- **AVL树**既是**二叉搜索树**，也是**平衡二叉树**，要**时刻满足**这两种性质。
## AVL树的常见术语：

- **节点高度**：AVL树的相关操作需要获取节点高度，每个节点都要存储节点高度`height`。
```java
/* AVL 树节点类 */
class TreeNode {
    public int val;        // 节点值
    public int height;     // 节点高度
    public TreeNode left;  // 左子节点
    public TreeNode right; // 右子节点
    public TreeNode(int x) { val = x; }
}
```

   - **节点高度**是指从该节点到它最远叶节点的距离，即**经过边的数量**，叶节点的高度为0，空节点的高度为-1。
- **节点平衡因子**：节点左子树的高度减去节点右子树的高度，空节点的平衡因子为0。
   - 设平衡因子为`f`，则一颗AVL树的任意节点的平衡因子都满足`-1 <= f <= 1`。
# AVL树的旋转：

- **AVL树**在插入和删除节点之后会出现**失衡**，通过“**旋转**”操作，在保持二叉搜索树和平衡二叉树性质的前提下，使**AVL树**恢复平衡。
- **AVL树**共有**四种基本旋转方式**：左旋、右旋、先左旋后右旋、先右旋后左旋。
## 左旋：

- 从二叉树的**底部向上看**，对于**第一个失衡节点**，其“**右子树失衡(即平衡因子 < -1)，并且执行一次左旋即可恢复平衡**”。

![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1722054711843-ccd82c94-d662-41fa-93c3-40e8b1499b73.png#averageHue=%23fcfafa&clientId=ua24a53a4-5f13-4&from=paste&height=357&id=ub12ab0a3&originHeight=713&originWidth=1357&originalType=binary&ratio=2&rotation=0&showTitle=false&size=144809&status=done&style=none&taskId=u94cf661b-fa5c-4294-a29f-a7b19ee1a52&title=&width=678.5)

- 以`child`为**旋转中心**，将`node`节点向左旋转，即作为`child`的左子树，同时将`grand_child`作为`node`的右子树。
## 右旋：

- 从二叉树的**底部向上看**，对于**第一个失衡节点**，其“**左子树失衡(平衡因子 > 1)，并且执行一次右旋即可恢复平衡**”。

![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1722055126360-255eea20-1c39-4890-8dc9-2db94db3b6e2.png#averageHue=%23fcfafa&clientId=ua24a53a4-5f13-4&from=paste&height=350&id=u973c6d0c&originHeight=699&originWidth=1343&originalType=binary&ratio=2&rotation=0&showTitle=false&size=142480&status=done&style=none&taskId=u57aa3c7a-2a64-40ef-bc47-77a2affa361&title=&width=671.5)

- 以`child`为**旋转中心**，将`node`节点向右旋转，即作为`child`的右子树，同时将`grand_child`作为`node`节点的左子树。
## 先左旋后右旋：

- 从二叉树的**底部向上看**，对于**第一个失衡节点**，其“**左子树失衡(即平衡因子 > 1)，但执行右旋并不能恢复平衡**”，此时需要执行先左旋后右旋。
- **本质原因**：`child`没有左子树，即**child的平衡因子 < 0**。

![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1722055590024-7f362a9f-457f-4244-b4d7-5bb89e9959e5.png#averageHue=%23fbf9f9&clientId=ua24a53a4-5f13-4&from=paste&height=344&id=ua3f55849&originHeight=687&originWidth=1359&originalType=binary&ratio=2&rotation=0&showTitle=false&size=128280&status=done&style=none&taskId=u78050811-d425-4e0f-9aa2-8bb3817f09b&title=&width=679.5)

- 本质原因是`child`没有**左子树**，那么就更换一个**child**，让`new_child`有左子树。
- 将`child`左旋，得到`new_child`，`new_child`有左子树，**但一定没有右子树**。
- 以`new_child`为旋转中心，将`node`向右旋转，即作为`new_child`的右子树。
## 先右旋后左旋：

- 从二叉树的**底部向上看**，对于**第一个失衡节点**，其“**右子树失衡(即平衡因子 < -1)，但执行左旋并不能恢复平衡**”，此时需要先右旋后左旋。
- **本质原因**：`child`没有右子树，即**child的平衡因子 > 0**。

![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1722056175037-0ca9ebe7-9e17-4d8d-9d39-e530ad14ba9d.png#averageHue=%23fbf9f9&clientId=ua24a53a4-5f13-4&from=paste&height=336&id=u3b03e6d3&originHeight=671&originWidth=1349&originalType=binary&ratio=2&rotation=0&showTitle=false&size=128545&status=done&style=none&taskId=u32687c69-7491-40ab-88ba-8eb47df3b9e&title=&width=674.5)

- 将`child`右旋，得到`new_child`，`new_child`有右子树，**但一定没有左子树**。
- 以`new_child`为旋转中心，将`node`向左旋转，即作为`new_child`的左子树。
## AVL旋转的选择：
### 旋转方式选择：
![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1722057951507-82f6b63d-eded-4c5c-a044-1eabed2d3b7c.png#averageHue=%23fefefe&clientId=uf0a2b6c9-9c81-4&from=paste&height=244&id=ub2268bf1&originHeight=487&originWidth=1089&originalType=binary&ratio=2&rotation=0&showTitle=false&size=51974&status=done&style=none&taskId=udcafc9bd-88f0-4b4d-87e5-dd6686b1e4d&title=&width=544.5)
### 旋转子操作：
```java
//空节点的高度是-1，其他节点高度是node.height(叶节点的高度是0)
int height(TreeNode node){
    if (node == null){
        return -1;
    }
    return node.height;
}
```
```java
void updateHeight(TreeNode node){
    int leftHeight = height(node.left);
    int rightHeight = height(node.right);
    node.height = Math.max(leftHeight, rightHeight) + 1;
    //当前节点的高度等于最高子树的高度 + 1(+1表示加上该节点)
}
```
```java
//空节点的平衡因子为0
int balanceFactor(TreeNode node){
    if (node == null){
        return 0;
    }
    return height(node.left) - height(node.right);
}
```
```java
//右子树失衡，左旋
TreeNode leftRotate(TreeNode node){
    TreeNode child = node.right;
    TreeNode grandChild = child.left;

    //左旋
    child.left = node;
    node.right = grandChild;

    //更新节点高度
    //只有node和child节点的高度发生变化
    updateHeight(node);
    updateHeight(child);

    //返回旋转后的根节点
    return child;
}
```
```java
//左子树失衡，右旋
TreeNode rightRotate(TreeNode node){
    TreeNode child = node.left;
    TreeNode grandChild = child.right;

    //右旋
    child.right = node;
    node.left = grandChild;

    //更新节点高度
    //只有node和child节点的高度发生辩护
    updateHeight(node);
    updateHeight(child);

    //返回旋转后的根节点
    return child;
}
```
### 旋转：

- 先判断`node`节点的**平衡因子**，再判断`child`节点的**平衡因子**，进而选择旋转方式。
```java
TreeNode rotate(TreeNode node){
    //node表示失衡节点

    int nodeBF = balanceFactor(node);
    //判断左子树失衡还是右子树失衡
    if (nodeBF > 1){
        //左子树失衡
        TreeNode child = node.left;
        int childBF = balanceFactor(child);
        //判断执行“右旋” or “先左旋后右旋(child无左子树)”
        if (childBF >= 0){
            //右旋
            return rightRotate(node);
        }
        else if (childBF < 0){
            //先左旋后右旋
            TreeNode newChild = leftRotate(child);
            node.left = newChild;
            return rightRotate(node);
        }
    }
    else if (nodeBF < -1){
        //右子树失衡
        TreeNode child = node.right;
        int childBF = balanceFactor(child);
        //判断执行“左旋” or “先右旋后左旋(child无右子树)”
        if (childBF <= 0){
            //左旋
            return leftRotate(node);
        }
        else if (childBF > 0){
            //先右旋后左旋
            TreeNode newChild = rightRotate(child);
            node.right = newChild;
            return leftRotate(node);
        }
    }
}
```
# AVL树的常用操作：
## 插入节点：

- **AVL树**本质上是**时刻保持平衡的二叉搜索树**，因此插入节点的操作和二叉搜索树类似。
- **区别**：	
   - 在**AVL树**中插入节点后，从**该节点到根节点**的路径(即**插入路径**)上可能会出现一系列失衡节点。
      - 失衡节点一定出现在**插入路径**上！！！
   - 从该节点开始，**自底向上**执行旋转操作，使所有失衡节点恢复平衡。
      - 这是一个递归操作！！！
      - 插入操作不能使用迭代，应该使用递归，插入完成后，会自动的按照**插入路径**返回，随后对插入路径上的每一层节点进行旋转。
```java
TreeNode insertNode(TreeNode root, int val){
    return insertHelper(root, val);
    //由于要递归，因此创建一个专门递归的函数
    //降低代码的耦合度
}
TreeNode insertHelper(TreeNode node, int val){
    if (node == null){
        //找到插入位置，递归终止条件
        return new TreeNode(val);
    }
    else if (node.val > val){
        //进入左子树
        node.left = insertHelper(node.left, val);
    }
    else if (node.val < val){
        //进入右子树
        node.right = insertHelper(node.right, val);
    }
    else if (node.val == val){
        //说明插入节点已存在，停止插入
        return node;
    }

    //递归操作
    //需要更新插入路径上的每一个节点的高度
    updateHeight(node);
    //对插入路径上的每一个节点进行旋转
    rotate(node);
    return node;//正常返回每一层的节点
}
```
## 删除节点：

- **AVL树**删除节点和**二叉搜索树**类似，区别在于**AVL树**删除节点后从该节点到根节点的**删除路径**上会出现一系列**失衡节点**。
- 需要从**该节点**开始，**自底向上(递归)**执行旋转操作，使所有失衡节点恢复平衡。
   - **递归删除的好处**：不需要使用`pre`记录父节点。
```java
TreeNode deleteNode(TreeNode root, int val){
    return deleteHelper(root, val);
}
TreeNode deleteHelper(TreeNode node, int val){
    if (node == null){
        //说明没找到待删除节点，返回
        return;
    }
    else if (node.val > val){
        //进入左子树
        node.left = deleteHelper(node.left, val);
    }
    else if (node.val < val){
        //进入右子树
        node.right = deleteHelper(node.right, val);
    }
    else (node.val == val){
        //找到待删除节点
        
        //判断节点的度
        int nodeDegree = 0;
        if (node.left != null){
            nodeDegree++;
        }
        if (node.right != null){
            nodeDegree++;
        }

        //选择删除方式
        if (nodeDegree == 0 || nodeDegree == 1){
            return ((node.left == null) ? node.right : node.left);
        }
        else if (nodeDegree == 2){
            TreeNode nex = node.right;
            while (nex != null){
                nex = nex.left;
            }
            deleteHelper(node, nex.val);
            node.val = nex.val;
            //这一层的node节点的高度和旋转节点在调用上面删除语句
            //的时候已经更新了，因此这层不需要更新，直接返回就好
            //但是这样写也可以，就是要在更新一次
        }
    }

    //更新节点高度
    updateHeight(node);
    //旋转节点
    rotate(node);
    return node;
}
```
## 查找节点：

- **AVL树**查找节点和**二叉搜索树**查找节点的方法完全一致。
# 二叉搜索树变AVL树：

- 在讨论二叉搜索树之前，先讨论一下如何将一组**有序数列**转换成**AVL树**：
   - 仔细观察**AVL树**，会发现**AVL树**严格遵循**二分思想**，即**AVL树**是一组数据二分的结果。

![image.png](https://cdn.nlark.com/yuque/0/2024/png/35940756/1722069567705-ec18d03b-e401-479f-ba9f-afbfa09b7783.png#averageHue=%23fbfbfb&clientId=uaff2e4f2-8be5-4&from=paste&id=uc0100e03&originHeight=112&originWidth=119&originalType=url&ratio=2&rotation=0&showTitle=false&size=2578&status=done&style=none&taskId=uf41ce560-9aef-48b2-92a8-54c463f365a&title=)

   - 上述**AVL树**是有序数列**[1, 2, 3, 4, 5, 6]**二分的结果：
      - `mid`左边的所有元素小于`mid`，即作为`mid`的左树。
      - `mid`右边的所有元素大于`mid`，即作为`mid`的右树。
   - 由于树具有父子连接关系，因此使用二分思想创建二叉树的时候，**递归**最合适。
- 分析完有序数列，我们再来分析**二叉搜索树**：
   - 二叉搜索树的**中序遍历**结果是有序的，因此可以先得到二叉搜索树的中序遍历结果，基于遍历结果创建新的**AVL树**。
## 题目描述：
[1382. 将二叉搜索树变平衡 - 力扣（LeetCode）](https://leetcode.cn/problems/balance-a-binary-search-tree/description/)
## 题解：

- 二分法创建AVL树的过程类似于细胞分裂，**时间复杂度是O(2****n****)**，呈**指数**上涨。
```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    public TreeNode balanceBST(TreeNode root) {
        List<Integer> list = new ArrayList<>();
        inOrder(root, list);
        return buildBST(list, 0, list.size() - 1);
    }
    private void inOrder(TreeNode node, List<Integer> list){
        if (node == null){
            return;
        }
        inOrder(node.left, list);
        list.add(node.val);
        inOrder(node.right, list);
    }
    private TreeNode buildBST(List<Integer> list, int left, int right){
        if (left > right){
            return null;
        }
        int mid = (left + right) / 2;
        TreeNode node = new TreeNode(list.get(mid));
        node.left = buildBST(list, left, mid - 1);
        node.right = buildBST(list, mid + 1, right);
        return node;
    }
}
```
