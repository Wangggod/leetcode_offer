#### 题目 剑指 Offer 05. 替换空格
请实现一个函数，把字符串 s 中的每个空格替换成"%20"。

 

示例 1：

输入：s = "We are happy."
输出："We%20are%20happy."
 

限制：

0 <= s 的长度 <= 10000

#### 思路：
最土的办法就是一个一个遍历，但这题的难点在于空格是一个位置，而替换的是3个位置，此时需要考虑1、赋值的数组要多长？2、怎样减少遍历次数？
最初的版本中我直接按照题目需求将数组长度设置为10000，但仔细一想这就跳坑了。因为题目限定的10000是s的长度，假设最坏的情况，s全部是空格，
此时就需要特别的注意了。

最简单粗暴的方式就是直接按照下文那样，设置为原来的3倍，但可能出现浪费空间的情况。
#### 解法：

```
class Solution {
    public String replaceSpace(String s) {
        int len = s.length();
        int size = 0;
        char[] A = new char[len*3];
        for(int i=0;i<len;i++){
            char c = s.charAt(i);
            if(c==' '){
                A[size++]='%';
                A[size++]='2';
                A[size++]='0';
            }else{
                A[size++]=c;
            }
        }
        String newStr = new String(A, 0, size);
        return newStr;
    }
}
```

