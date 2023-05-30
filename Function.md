``` java
public class Operations {
    // 加法
    public static int add(int num1, int num2) {
        return num1 + num2;
    }

    // 减法
    public static int subtract(int num1, int num2) {
        return num1 - num2;
    }

    // 乘法
    public static int multiply(int num1, int num2) {
        return num1 * num2;
    }

    // 除法
    public static double divide(int num1, int num2) {
        if(num2 != 0){
            return (double) num1 / num2;
        }else{
            return false;
        }
    }
}
``` 
