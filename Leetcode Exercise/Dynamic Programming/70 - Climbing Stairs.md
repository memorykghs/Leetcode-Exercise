# 70 - Climbing Stairs

* [Climbing Stairs](https://leetcode.com/problems/climbing-stairs/)

## Related Topics
* Dynamic Programming
* Math
* Memoization

## Well Solution
![](/images/70-1.png)

整體的動態看影片會比較準XD

![](/images/70-2.png)

* `4 - 5`：只有一種方法，也就是踏一階才能到 5，而 5 自己則只能踏 0 階，代表都只有一種方式可以到達

* `3 - 5`：3 要到 5 階，有兩種選擇，根據第一張圖可以知道**每一個結果等於前一個 + 前前一個結果**，所以由此可知，此階段會有 `4`(1) + `5`(1) = 2 種解法

* `2 - 5`：同理，此階段有 `3`(2) + `4`(1) = 3 種解法
* `1 - 5`：共有 `2`(3) + `3`(2) = 5 種解法 
* `0 - 5`：共有 `1`(5) + `2`(3) = 8 種解法

```java
public int climbStairs(int n) {
    int oneStep = 1;
    int twoSteps = 1;

    while (n-- > 0) {
        twoSteps += oneStep;
        oneStep = twoSteps - oneStep;
    }
    
    return oneStep;
}
```

## 參考
#### 影片
* https://www.youtube.com/watch?v=Y0lT9Fck7qI