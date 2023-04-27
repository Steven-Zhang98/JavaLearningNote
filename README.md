# JavaLearningNote
This is a note documenting my learning progress.my instructor,[Mr.Zhang](https://github.com/mincongzhang),mentioned that teaching is an effective way for studying.I believe he is right,and thus,i will continue to pratice it.
## Contents
> The presence of a ✅ indicates that I have completed the subject, while the absence of a ✅ means i have not finished it.
## Class
Class note1 how to 
## Object oriented
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
``` py

```
