# 题目描述：
[面试题 17.14. 最小K个数 - 力扣（LeetCode）](https://leetcode.cn/problems/smallest-k-lcci/description/)

- 在无序数组中，找出最小的K个元素。
# 题解：
## 排序：

- 将无序数组按照**从小到大**的顺序排列，取出前K个元素即可。
- 显然，该方法“**超额**”完成了任务，我们只需要找到最小的K个元素，不需要对数组的其他元素进行排序。
```java
class Solution {
    public int[] smallestK(int[] arr, int k) {
        //对数组从小到大进行排序
        Arrays.sort(arr);
        //返回含有前K个元素的新数组
        return Arrays.copyOf(arr, k);
    }
}
```
## 堆：

- 创建一个**最大堆**，遍历无序数组，将前K个元素依次入堆，从第K + 1个元素开始，若当前元素小于堆顶元素，将当前元素入堆(堆顶元素先出堆)。
- 遍历完成后，**堆**中存储的就是最小K个元素。
   - **排序是最快的方式，但堆提供了更加优秀的思路**。
```java
class Solution {
    public int[] smallestK(int[] arr, int k) {
        int[] arrTmp = new int[k];
        if (k == 0){
            return arrTmp;
        }
        Queue<Integer> maxHeap = new PriorityQueue<>((a, b) -> b - a);
        //将前K个元素依次入堆
        for (int i = 0; i < k; i++){
            maxHeap.offer(arr[i]);
        }
        //若当前元素小于堆顶元素，将当前元素入堆
        for (int i = k; i < arr.length; i++){
            if (arr[i] < maxHeap.peek()){
                maxHeap.poll();//堆顶元素出堆
                maxHeap.offer(arr[i]);//当前元素入堆
            }
        }

        //创建最小K个元素的数组
        for (int i = 0; i < k; i++){
            arrTmp[i] = maxHeap.poll();
        }
        return arrTmp;
    }
}
```
