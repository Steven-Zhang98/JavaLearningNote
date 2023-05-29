# JavaLearningNote
This is a note documenting my learning progress.my instructor,[Mr.Zhang](https://github.com/mincongzhang),mentioned that teaching is an effective way for studying.I believe he is right,and thus,i will continue to pratice it.
I 
## Contents
> The presence of a ✅ indicates that I have completed the subject, while the absence of a ✅ means i have not finished it.
* [If loop fuction](#if-loop-fuction) 
* [oo and class](#oo-and-class)
* [memory stack vs heap](#memory-stack-vs-heap)
* [basic data structure vector vs list](#basic-data-structure-vector-vs-list)
* [binary tree](#binary-tree)
* [hash table](#hash-table)
* [advanced oo](#advanced-oo)

## If loop fuction
> 需求: 朋友聚会的时候可能会玩一个游戏:逢七过。
规则是:从任意一个数字开始报数,当你要报的数字包含7或者是7的倍数时都要说:过。
为了帮助大家更好的玩这个游戏,这里我们直接在控制台打印出1-100之间的满足逢七必过规则的数据。

Example:

``` 
Input: 1,2,3,4,5,6,7,8,9,10....
Output: 1,2,3,4,5,6,"pass",8,9,10.....
```

## 解题思路
循环1——100之间的数字，在这段代码中，i % 10 == 7检查数字的个位是否为7，i / 10 == 7检查数字的十位是否为7，i % 7 == 0检查数字是否是7的倍数。这段代码可以正确处理1到100之间的数字。

## 代码示例
``` java
public class Main {
    public static void main(String[] args) {
        for (int i = 1; i <= 100; i++) {
            if (i % 10 == 7 || i / 10 == 7 || i % 7 == 0) {
                System.out.println("过");
            } else {
                System.out.println(i);
            }
        }
    }
}

```

## Memory stack vs heap
## Basic data structure vector vs list
## Binary tree
## Hash table
## Advanced oo
