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
``` java
public class Dog {
    private String m_name;
    private int[] m_position;

    public Dog(String name,int[] position){
        this.m_name = name;
        this.m_position = position;
        System.out.println(this.m_name + "born at position(" + this.m_position[0] + "," + this.m_position[1] +")");
    }

    public void  walk(int[] newPosition){
        System.out.println(this.m_name + "moved from(" + this.m_position[0] + "," + this.m_position[1] +
                ")to("+ newPosition[0] + "," + newPosition[1] + ")");
        this.m_position = newPosition;
    }

    public static void main(String[] args) {
        Dog d1 = new Dog("dog1",new int[]{1,1});
        Dog d2 = new Dog("dog2",new int[]{1,2});
        d1.walk(new int[]{3,4});
        d2.walk(new int[]{3,6});

        System.out.println("===========more dogs coming===========");
        Dog d4 = new Dog("dog1",new int[]{1,6});
        Dog d5 = new Dog("dog1",new int[]{98,04});
        Dog d6 = new Dog("dog1",new int[]{25,8});
    }
}
```
### 继承
``` java
public class Cat extends Dog {

    public Cat(String name, int[] position) {
        super(name, position);
        System.out.println(name + " is a cat, and it was born at position(" + position[0] + "," + position[1] + ")");
    }

    public void meow() {
        System.out.println(getName() + " says: Meow!");
    }

    public static void main(String[] args) {
        Cat c1 = new Cat("cat1", new int[]{2, 2});
        Cat c2 = new Cat("cat2", new int[]{2, 3});

        c1.walk(new int[]{4, 5});
        c2.walk(new int[]{4, 7});

        c1.meow();
        c2.meow();

        System.out.println("===========more cats coming===========");
        Cat c4 = new Cat("cat3", new int[]{1, 7});
        Cat c5 = new Cat("cat4", new int[]{97, 5});
        Cat c6 = new Cat("cat5", new int[]{26, 9});
    }
}

```
## Memory stack vs heap
## Basic data structure vector vs list
## Binary tree
## Hash table
## Advanced oo
