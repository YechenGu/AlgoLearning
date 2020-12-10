一个长度为n-1的递增排序数组中的所有数字都是唯一的，并且每个数字都在范围0～n-1之内。在范围0～n-1内的n个数字中有且只有一个数字不在该数组中，请找出这个数字。

 

示例 1:

输入: [0,1,3]
输出: 2



我的解法：

```java
class Solution {
    public int missingNumber(int[] nums) {
        int left = 0;
        int right = nums.length - 1;
        int mid = (left+right)/2;

        while(left<=right){
            if(nums[mid]==mid){
                left = mid+1;
            }else{
                right = mid-1;
            }
            mid = (left+right)/2;
        }
        if(right<0){
            return 0;
        }
        if(left>=nums.length){
            return nums.length;
        }
        if(nums[left]==left){
            return right;
        }
        return left;
        
    }
}
```

样例不讲武德，[0]竟然也算合法输入