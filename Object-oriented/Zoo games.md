## 类
### 什么是类？
类是对现实世界中事物的抽象表示，它描述了这些事物共有的属性和功能。在java中，类定义了数据成员（变量）和成员函数（方法），用于表示和操作对象的状态和行为。比如现实情况中，我们会把狗这一类动物抽象出它的属性（颜色、品种、高度、长度）还会觉得狗有一定的动作（叫、跑、摇尾巴）
而在计算机中我们可以创建一只电子狗，假设我们有一个名为 "dog" 的类。dog 类可以包含属性（如 position、name）以及方法（如 walk、brake 和 honk）。
``` java
public class Dog {
// Dog properties
    private String m_name;
    private int[] m_position;
    
    public dog(String name,int[] position){
        this.m_name = name;
        this.m_position = position;
        System.out.println(this.m_name + "born at position(" + this.m_position[0] + "," + this.m_position[1] +")");
    }
    // Dog's can go (function)
     public void  walk(int[] newPosition){
        System.out.println(this.m_name + "moved from(" + this.m_position[0] + "," + this.m_position[1] +
                ")to("+ newPosition[0] + "," + newPosition[1] + ")");
        this.m_position = newPosition;
    }
}
```
## 对象
此时我们只创建出狗的制造图，狗还没有动起来。接下来我们要创建两只狗，名为旺财和豆腐，并让他们狗动起来。
  ``` java
public static void main(String[] args) {
        Dog d1 = new Dog("wangcai",new int[]{1,1});
        Dog d2 = new Dog("doufu",new int[]{1,2});
        d1.walk(new int[]{3,4});
        d2.walk(new int[]{3,6});
 ```
 根据这个例子，我们就能看出，对象是根据类这个蓝图，所制造出来的类似于实体的东西，有了对象，我们能创建多只狗并让狗有了名字，能跑能跳，才真正的活了起来。
 
## 继承
如果我们不止想要狗，还要创建猫、鹅等，都具有名字、位置、颜色等属性，但具有不同动作的动物该怎么办？此时便有了继承
``` java
    public class Animal {
    private String m_name;
    private int[] m_position;

    public Animal(String name,int[] position){
        this.m_name = name;
        this.m_position = position;
        System.out.println(this.m_name + "born at position(" + this.m_position[0] + "," + this.m_position[1] +")");
    }


    public void  walk(int[] newPosition){
        System.out.println(this.m_name + "moved from(" + this.m_position[0]  "," + this.m_position[1] +
                ")to("+ newPosition[0] + "," + newPosition[1] + ")");
        this.m_position = newPosition;
        
  ``` 
  因为狗不是猫，但是狗又和猫很像，那如果让狗和猫处在同一类别呢？答案就是动物，我们将狗抽象成动物，那么狗与猫与鹅是不是在同一类中了？
  此时我们再创建狗的类和猫类

 ``` java
  public class Cat extends Animal {
  public Cat(String name, int[] position) {
        super(name, position);
        System.out.println(name + " is a cat, and it was born at position(" + position[0] + "," + position[1] + ")");
    }

    public void wang() {
        System.out.println(getName() + " says: wang!");
    }
    
    
 public class Cat extends Animal {
 public Cat(String name, int[] position) {
        super(name, position);
        System.out.println(name + " is a cat, and it was born at position(" + position[0] + "," + position[1] + ")");
    }

    public void meow() {
        System.out.println(getName() + " says: Meow!");
    }
    }
    
    
     public Goose  extends Animal {
 public Goose(String name, int[] position) {
        super(name, position);
        System.out.println(name + " is a cat, and it was born at position(" + position[0] + "," + position[1] + ")");
    }

    public void fly() {
        System.out.println("I am a goose,and I can fly");
    }
    }
    ```
   综上例子，我们可以发现狗可以产生很多狗，但是不是产生猫，因为狗和猫不是同一种生物，但是，猫可以继承来自生物的特性。计算机的逻辑不是凭空产生，而是来自现实生活中的抽象。只有抽象，我们才能发现看似相差巨大的事物，都有相同的共性。
   
   
   
