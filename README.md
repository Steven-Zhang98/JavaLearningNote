# JavaLearningNote
This is a note documenting my learning progress.my instructor,[Mr.Zhang](https://github.com/mincongzhang),mentioned that teaching is an effective way for studying.I believe he is right,and thus,i will continue to pratice it.
I 
## Contents
> The presence of a ✅ indicates that I have completed the subject, while the absence of a ✅ means i have not finished it.
* [if loop fuction](#if-loop-fuction) 
* [oo and class](#oo-and-class)
* [memory stack vs heap](#memory-stack-vs-heap)
* [basic data structure vector vs list](#basic-data-structure-vector-vs-list)
* [binary tree](#binary-tree)
* [hash table](#hash-table)
* [advanced oo](#advanced-oo)

## If loop fuction
### 问题引入

### 代码的定义

### 与原来知识点联系起来

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
