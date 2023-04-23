# JavaLearningNote
## Class
Class note1 how to 
## Object oriented
how to object
```
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
