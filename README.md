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
Output: 1,2,3,4,5,6,"过",8,9,10.....
```

## 解题思路
循环1——100之间的数字，并判断该输入是否是7或者7的倍数，如果是则打印“过”，如果不是则打印该数字

## 代码示例
``` java
public static void feng7Guo() {
        for (int i = 0; i < 101; i++) {
            if (i % 10 == 7 || i / 7 == 0){
                System.out.println("过!");
            }
            else {
                System.out.println(i);
            }
        }
    }
``` 
### 注意事项

## Oo and class 
### Object oriented
how to object
``` java
public class Student {
   String name;
   int age;

    public  void sayHello(String name) {
        System.out.println("局部变量:" + name);
        System.out.println("成员变量:" + this.name);
    }

    public static void main(String[] args) {
        Student stu = new Student();
        stu.name = "钢门吹雪";
        stu.age = 23;
        stu.sayHello("西域狂鸭");
    }
}
```
## Memory stack vs heap
## Basic data structure vector vs list
## Binary tree
## Hash table
## Advanced oo
