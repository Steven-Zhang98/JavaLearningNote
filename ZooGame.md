### 什么是 oo ？为什么要创建一只狗？
### 创建一只狗
如果没有 class 我们如何表示一只狗？
``` java
public class Main {
    public static void main(String[] args) {
        String dogName = "dog1";
        int[] dogPosition = {1,1};
        System.out.println(dogName + " born at position " + "(" + dogPosition[0] + "," + dogPosition[1] + ")");

        int[] newPosition = {1,3};
        System.out.println(dogName + " moved from " + "(" + dogPosition[0] + "," + dogPosition[1] + ")" + " to position " + "(" + newPosition[0] + "," + newPosition[1] + ")");
    }
} 
```
我们如何展示两只狗？三只狗？四只狗？
代码是否会重复？为了避免代码重复，我们应该把具有相同属性的代码用 class 封装起来。
### 什么是 class
什么是实例（instance）
### 进一步优化
请注意，我们在这里使用一个数组来表示（1,1）这样的坐标，为了简化我们用数组来表示。
如果你计划在代码中大量使用这样的坐标地址（1,5）组合，你可以考虑将坐标地址封装成类。
在Java中，你可以创建一个自定义的类来存储两个元素。以下是一个示例，它创建了一个名为Position的类，用于存储狗的位置信息，在这个例子中，我们创建了一个新的Position类，它有两个成员变量x和y，分别代表位置的两个维度。我们也提供了一个构造函数来初始化这些值，以及一个toString()方法来创建一个表示此对象的字符串。

然后，我们在main函数中使用这个Position类来创建和操作狗的位置。这样的话，你的代码就更容易阅读和理解，同时也可以方便地扩展来处理更复杂的位置信息，比如三维空间的位置。比如让x，y 值变为原来的两倍。实现fly 方法。
``` java
import java.util.ArrayList;
import java.util.List;
public class Main {
    public static void main(String[] args) {
        Dog d1 = new Dog("dog1", new Position(1, 1));
        Dog d2 = new Dog("dog2", new Position(1, 2));
        d1.walk(new Position(3, 4));
        d2.walk(new Position(1, 3));

        System.out.println("=====more dogs coming=====");

        Dog d3 = new Dog("dog3", new Position(1, 1));
        Dog d4 = new Dog("dog4", new Position(1, 1));
        List<Dog> animalList = new ArrayList<>();
        animalList.add(d1);
        animalList.add(d2);
        animalList.add(d3);
        animalList.add(d4);

        for (Dog dog : animalList) {
            dog.walk(new Position(10, 10));
        }
    }
}
class Dog {
    private String name;
    private Position position;

    public Dog(String name, Position position) {
        this.name = name;
        this.position = position;
        System.out.println(this.name + " born at position " + this.position);
    }

    public void walk(Position newPosition) {
        System.out.println(this.name + " moved from " + this.position + " to " + newPosition);
        this.position = newPosition;
    }
}

```


### 创建狗类
假如我们要创建2只, 再进一步创建10只, 怎么办呢?  
在这个Java代码中，我们创建了一个Dog类和一个Position类。Dog类有两个成员变量name和position，并且包含一个构造函数和一个名为walk的方法，用于改变狗的位置。
``` java
public class Main {
    public static void main(String[] args) {
        String dogName = "dog1";
        Position dogPosition = new Position(1,1);
        System.out.println(dogName + " 出生在位置 " + dogPosition);

        Position newPosition = new Position(1,3);
        System.out.println(dogName + " 从 " + dogPosition + " 移动到位置 " + newPosition);
    }
}
class Position {
    int x, y;

    // 构造函数
    public Position(int x, int y) {
        this.x = x;
        this.y = y;
    }

    // 重写 toString 方法
    @Override
    public String toString() {
        return "(" + x + "," + y + ")";
    }
}
```
在main函数中，我们创建了几个Dog对象，并使用walk方法移动这些对象。然后，我们将这些Dog对象添加到一个ArrayList中，并遍历该列表，移动列表中的每个狗。

### 想创建一只会飞的猫
这段Java代码中，我们创建了一个新的Cat类，这个类和Dog类非常相似，有两个私有成员变量name和position，以及一个构造函数和一个walk方法。Position类则和之前的完全一样，用于表示位置。在main方法中，我们创建了两个Cat对象，并调用了它们的walk方法以改变它们的位置。
``` java
class Cat {
    private String name;
    private Position position;

    public Cat(String name, Position position) {
        this.name = name;
        this.position = position;
        System.out.println(this.name + " born at position " + this.position);
    }

    public void walk(Position newPosition) {
        System.out.println(this.name + " moved from " + this.position + " to " + newPosition);
        this.position = newPosition;
    }
}

```
### 抽象 Animal 类
在这段Java代码中，我们创建了一个Animal抽象类，并定义了name、position成员变量，以及walk、swim方法。然后，我们创建了两个继承自Animal类的类：Dog和Cat。Dog类直接继承了Animal类的所有属性和行为，而Cat类覆盖了swim方法以表达猫不能游泳的事实。

在main方法中，我们创建了一个Animal对象的列表，并向其添加了一只Dog和一只Cat。然后，我们遍历这个列表，并让列表中的每个动物走路和游泳。
``` java
import java.util.ArrayList;
import java.util.List;

abstract class Animal {
    protected String name;
    protected Position position;

    public Animal(String name, Position position) {
        this.name = name;
        this.position = position;
        System.out.println(this.name + " born at position " + this.position);
    }

    public void walk(Position newPosition) {
        System.out.println(this.name + " moved from " + this.position + " to " + newPosition);
        this.position = newPosition;
    }

    public void swim(Position newPosition) {
        System.out.println(this.name + " swim from " + this.position + " to " + newPosition);
        this.position = newPosition;
    }
}

class Dog extends Animal {
    public Dog(String name, Position position) {
        super(name, position);
    }
}

class Cat extends Animal {
    public Cat(String name, Position position) {
        super(name, position);
    }

    @Override
    public void swim(Position newPosition) {
        System.out.println(this.name + " is a cat and cannot swim!");
    }
}

```
### Is-a 和 has-a 区别
这段Java代码中，我们创建了一个新的Human类，该类有三个私有成员变量：name、position和pets。pets是一个Animal对象的列表，表示人拥有的宠物。在Human的构造函数中，我们初始化了这些成员变量，并且打印出每个被收养的动物的名字。Human类也有一个walk方法，该方法不仅改变人的位置，还改变所有宠物的位置。在main方法中，我们创建了一个Cat对象、一个Dog对象和一个Human对象，并调用了Human对象的walk方法以改变所有生物的位置。
``` java
class Human {
    private String name;
    private Position position;
    private List<Animal> pets;

    public Human(String name, Position position, List<Animal> animals) {
        this.name = name;
        this.position = position;
        this.pets = animals;

        for (Animal animal : pets) {
            System.out.println(this.name + " is adopting a pet " + animal.getName());
        }
    }

    public void walk(Position newPosition) {
        System.out.println(this.name + " moved from " + this.position + " to " + newPosition);
        this.position = newPosition;

        for (Animal pet : pets) {
            pet.walk(newPosition);
        }
    }
```
