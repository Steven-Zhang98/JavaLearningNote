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
优化
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
