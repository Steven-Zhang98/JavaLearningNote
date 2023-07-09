### 什么是哈希算法？  
把一些很大范围的数字映射到更小的范围的方法  
比如把 60000 多个汉字映射到 26 个字母的组合
### 如何设计一个简单的哈希算法？
#### 1. 设计一个键值对
什么是键值对？  
用于表示两个数据元素之间的关系。键值对由两部分组成：键（Key）和值（Value）。例如，如果你有一个电话簿，你可能会将人的名字作为键，将他们的电话号码作为值。这样，当你需要查找某人的电话号码时，你可以使用他们的名字（键）来快速找到电话号码（值）。
```java
public class Entry {
    int key;
    String value;
    Entry next;

    public Entry(int key, String value) {
        this.key = key;
        this.value = value;
        this.next = null;
    }
}

```
问题 1：为什么要设计一个 next？

#### 2. 如何设计一个 hash map？
问题 2：当插入进去的位置已经有数据存在该怎么办?
问题 3：如何理解 next？
