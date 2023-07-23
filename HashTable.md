### 什么是哈希算法？  
哈希表把一些很大范围的数字映射（map）到更小的范围的方法，比如把 60000 多个汉字映射到 26 个字母的组合，通过 26 个子母快速找到对应的哈希值，哈希表体现了为了快速查找想要的值，利用用空间换时间的思想。
### 为什么要用 hashmap？有什么好处？二叉搜索跟 hash 搜索有什么区别？
哈希表不进行排序，在理想情况下，哈希表提取某一个值的时间复杂度是 O(1)，二叉树是 O(logn)-->文章  



### 如何设计一个简单的哈希算法？
哈希表（HashMap）有不同的实现方法，在这个代码中，我利用数组这个最基本的数据结构实现一个简单哈希表，而一个哈希表中哈希函数（hash function）是最重要的，他是将键值（key）转换成哈希表中唯一的地址值，从而快速找到这个键值所对应的值（value）。比如，26 个字母就是一种键值，通过 26 个子母能快速找到其所对应的值（value）。要实现哈希函数，需要一个哈希种子（hash seed）。  
有了哈希种子，在理想状态下，我们就可以将键值（key）转换成哈希值（hash value），有了哈希值我们就知道 键值对应的值存在于这个数组的哪个位置。进而快速存取想要的值。

```java
class HashMap
{
    private int [] m_hash_vals;
    private int m_hash_seed;
    
    public HashMap(int size)
    {
        m_hash_seed = size+1;
        System.out.println("hash seed should be a prime number:"+m_hash_seed);
        m_hash_vals = new int[m_hash_seed];
    }
    
    private int get_hash(int key)
    {
        return key%m_hash_seed;
    }
    
    public void insert(int key, int val)
    {
        int index = get_hash(key);
        m_hash_vals[index] = val;
    }
    
    public int get(int key)
    {
        int index = get_hash(key);
        return m_hash_vals[index];
    }
}

```
为了验证我们实现的哈希函数，我们首先进行了一个基本的测试，创建一个长度为 10 的数组，然后插入 100 和 243 两个值，并尝试提取出这个两个值。  
然后进行了一个循环测试，对于i在1到100之间，每次增加10，都将i和i*10插入到hash_map中，然后再获取并打印出来。

``` java
public class Main {
    public static void main(String[] args) {
        
        // Basic test
        {
            HashMap hash_map = new HashMap(10);
            hash_map.insert(100, 243);
            int get_val = hash_map.get(100);
            System.out.println("get val from hashmap:"+get_val);
        }
        
        //for loop test
        {
            HashMap hash_map = new HashMap(10);
            for(int i = 1; i<100; i+=10)
            {
                hash_map.insert(i, i*10);
            }
            
            for(int i = 1; i<100; i+=10)
            {
                int get_val = hash_map.get(i);
                System.out.println("for loop test key, val:"+i+":"+get_val);
            }
        }
        System.out.println("done");
    }
}
```
### 哈希冲突的解决
链表 -->https://github.com/mincongzhang/MentoringMaterial/blob/main/BASICS/BASICS_9_hash_table.md
### 哈西冲突解决的示意图
