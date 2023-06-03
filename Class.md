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

    // get和set方法
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getType() {
        return type;
    }

    public void setType(String type) {
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
继承
``` java
public class Dog extends Animal {
    // 新增属性
    private String color;

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
猫类
``` java
public class Cat extends Animal {
    // 新增属性
    private String furColor;

    // 构造方法
    public Cat(String name, String type, String furColor) {
        super(name, type);
        this.furColor = furColor;
    }

    // get和set方法
    public String getFurColor() {
        return furColor;
    }

    public void setFurColor(String furColor) {
        this.furColor = furColor;
    }

    // 猫抓老鼠
    public void catchMouse() {
        System.out.println(getName() + " is catching a mouse.");
    }
}

```
鸟类
``` java
public class Bird extends Animal {
    // 新增属性
    private double wingSpan;

    // 构造方法
    public Bird(String name, String type, double wingSpan) {
        super(name, type);
        this.wingSpan = wingSpan;
    }

    // get和set方法
    public double getWingSpan() {
        return wingSpan;
    }

    public void setWingSpan(double wingSpan) {
        this.wingSpan = wingSpan;
    }

    // 鸟飞翔
    public void fly() {
        System.out.println(getName() + " is flying.");
    }
}

```
