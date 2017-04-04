题目描述：

给定数组，找出连续子数组，使子数组的数字和为最大值，子数组至少包含一个数字。

例如：

[−2,1,−3,4,−1,2,1,−5,4], the contiguous subarray [4,−1,2,1] has the largest sum = 6.

思路：

动态规划，如果一个下标为i的数字比之前i-1个数字最大的和都大，则舍弃之前i-1个数字。

解决方案：

```
 public int maxSubArray(int[] A) {
       int newsum=A[0];
       int max=A[0];
       for(int i=1;i<A.length;i++){
           newsum=Math.max(newsum+A[i],A[i]);
           max= Math.max(max, newsum);
       }
       return max;
    }
```
