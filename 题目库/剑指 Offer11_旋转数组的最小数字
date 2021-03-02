#### 题目：剑指 Offer 11. 旋转数组的最小数字
#### 思路：可以用二分法
#### 提示：
二分法的取中间值建议用减法，防止溢出
'''
class Solution {
    public int minArray(int[] numbers) {
        int low = 0;
        int high = numbers.length - 1;
        while (low < high) {
            int pivot = low + (high - low) / 2;
            if (numbers[pivot] < numbers[high]) {
                high = pivot;
            } else if (numbers[pivot] > numbers[high]) {
                low = pivot + 1;
            } else {
                high -= 1;
            }
        }
        return numbers[low];        
    }
}
'''
