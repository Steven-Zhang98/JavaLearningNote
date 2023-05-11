## 栈Stack
### 什么是栈？
栈是一种计算机中先进后出的计算机，我创建一个类，名字叫stack来模拟栈的出栈（pop）和压栈（push）和查看栈顶元素。

``` java
    public Stack(int size) {
        maxSize = size;
        stackArray = new int[maxSize];
        top = -1;
    }

    public void push(int value) {
        if (!isFull()) {
            top++;
            stackArray[top] = value;
        } else {
            System.out.println("Stack is full. Cannot push " + value);
        }
    }

    public int pop() {
        if (!isEmpty()) {
            int poppedValue = stackArray[top];
            top--;
            return poppedValue;
        } else {
            System.out.println("Stack is empty. Cannot pop.");
            return -1;
        }
    }

    public int peek() {
        if (!isEmpty()) {
            return stackArray[top];
        } else {
            System.out.println("Stack is empty. Cannot peek.");
            return -1;
        }
    }

    public boolean isEmpty() {
        return top == -1;
    }

    public boolean isFull() {
        return top == maxSize - 1;
    }
}
``` 
接下来模拟压栈弹栈的过程
``` java
Stack stack = new Stack(3);  // 创建一个容量为 3 的栈
stack.push(1);  // 将 1 压入栈
stack.push(2);  // 将 2 压入
int poppedValue = stack.pop();  // 弹出并获取栈顶元素
System.out.println("Popped value: " + poppedValue);  // 输出弹出的元素
```

## 堆heap
