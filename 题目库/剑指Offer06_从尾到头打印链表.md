#### 题目 剑指 Offer 06. 从尾到头打印链表
输入一个链表的头节点，从尾到头反过来返回每个节点的值（用数组返回）。

 

示例 1：

输入：head = [1,3,2]
输出：[2,3,1]
 

限制：

0 <= 链表长度 <= 10000

#### 思路：
可以用栈FIFO特性，主要考察栈的操作

```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public int[] reversePrint(ListNode head) {
        Stack<ListNode> stack = new Stack<ListNode>();
        ListNode temp = head;
        while(temp!=null){
            stack.push(temp);
            temp=temp.next;
        }
        int len = stack.size();
        int[] printArray =new int[len];
        for(int i=0;i<len;i++){
            printArray[i] = stack.pop().val;
        }
        return printArray;
    }
}
```

