## 对象Object是什么?类Class是什么？
对象是一种具有属性和行为(方法)的编程结构，是 class 的具体实例。比如说类是手机设计图，对象就是由设计图设计出来的一个又一个手机。  
举一个具体的例子：假设你有一个“Dog”类。这个类定义了一些属性（如名字、年龄、颜色）和行为（如吠叫、跑动）。然后，你可以使用这个狗类创建一群狗，比如一个名为“dog1”的狗，一个名为“dog2”的狗，等等。每个狗对象都有自己的名字、年龄和颜色，可以执行吠叫和跑动的动作。
``` java
public class {
    // 属性
    private String color;
    private String name;
    private String type;

    // 构造方法
    public Dog(String name, String type, String color) {
        super(name, type);
        this.color = color;
    }

    // get和set方法
    public String getColor() {
        return color;
    }

    public void setColor(String color) {
        this.color = color;
    }

    // 狗叫
    public void bark() {
        System.out.println(getName() + " is barking.");
    }
}
```
## 我想再添加一个 "猫", 也具有同样的功能: 我们直接复制 "狗" 的代码改改拿来用可以吗?
不行，因为这会导致逻辑问题因为“猫”不是“狗”  
并且还会导致可扩展性差：如果你想要添加更多的动物，比如"鸟"或"马"，那么你可能需要复制和修改更多的代码。  
所以我们可以创建一个名为 Animal 的父类

``` java
public class Animal {
    // 属性
    private String name;
    private String type;

    // 构造方法
    public Animal(String name, String type) {
        this.name = name;
        this.type = type;
    }

    // 其他方法
    public void eat() {
        System.out.println(this.name + " is eating.");
    }

    public void sleep() {
        System.out.println(this.name + " is sleeping.");
    }
}
```

有了父类后能很容易的创建猫类，猫还增加了抓老鼠的功能  

``` java
public class Cat extends Animal {
    // 新增属性
    private String furColor;

    // 构造方法
    public Cat(String name, String type, String furColor) {
        super(name, type);
        this.furColor = furColor;
    }

    }

    // 猫抓老鼠
    public void catchMouse() {
        System.out.println(getName() + " is catching a mouse.");
    }
}

```
鸟类增加了飞翔的功能
``` java
public class Bird extends Animal {
    // 新增属性
    private double wingSpan;

    // 构造方法
    public Bird(String name, String type, double wingSpan) {
        super(name, type);
        this.wingSpan = wingSpan;
    }

    // 鸟飞翔
    public void fly() {
        System.out.println(getName() + " is flying.");
    }
}

```
测试功能
