# 55 - Jump Game

* [Jump Game](https://leetcode.com/problems/jump-game/)

## Related Topics
* Array
* Dynamic Programming Greedy
* Greedy

## My Solution
雖然花不少時間，不過自己有寫出來還是蠻爽的，優化!優化!優化!

#### 解題思路
一開始被其他 Button Up 方法誤導xD推理錯誤如下：
![](/images/55-2.png)

```java
public boolean canJump(int[] nums) {
    int distance = 0;

    // if first step is 0 and length of nums is greater than 1, return false
    if (nums[0] == 0 && nums.length > 1) {
        return false;
    }

    for (int i = nums.length - 1; i > 0; i--) {
        distance++;
        
        if (i > 0 && nums[i - 1] >= distance) {
            distance = 0;
        }
    }
    
    boolean canJump = true;
    if(distance > 0) {
        canJump = false;
    }

    return canJump;
}
```

總之計算每一步的距離，如果遇到 0 且 0 的下一步步距沒有大於 distance，則 distance++。

```
Buttom Up: 由後往前評估
step = 3
step = 0
    distance++ → distance = 1
step = 2
    distance++ → distance = 2
    step >= distance → distance = 0
step = 1
    distance++ → distance = 1
    step >= distance → distance = 0
step = 3
    distance++ → distance = 1
    step >= distance → distance = 0
step = 2
    distance++ → distance = 1
    step >= distance → distance = 0

最後判斷 distance 是否等於 0
```

![](/images/55-1.gif)

## Well Solution
```java

```