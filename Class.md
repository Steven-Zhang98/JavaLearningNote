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

