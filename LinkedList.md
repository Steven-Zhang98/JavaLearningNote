### 如何搭建一个基础的单链表数据结构？
先搭建一个Node 类：表示链表中的一个节点。每个节点有一个整数值 m_val 和一个指向下一个节点的引用 m_next。它还提供了几个方法来设置和获取这些值。  
LinkedList 类：这个类表示一个单链表。它有一个 head，表示链表的头节点。它还定义了一些操作链表的方法：
构造函数、插入方法、检查方法、打印方法  

目前主要问题，只能解释这段代码，但是因为目前掌握的信息太少，不能解释得更深入。
```java
class Node {
    private int m_val;
    private Node m_next;
    public Node(int val) {
        m_val = val;
    }

    public int getVal() {
        return m_val;
    }

    public void setNext(Node n) {
        m_next = n;
    }

    public Node getNext() {
        return m_next;
    }

}

class LinkedList {
    private Node head;

    public LinkedList(int val) {
        head = new Node(val);
    }
    
    public void insert(int val) {
        Node newNode = new Node(val);
        newNode.setNext(head);
        head = newNode;
    }
    
    public boolean exist(int val) {
        Node current = head;
        while (current != null) {
            if (current.getVal() == val) {
                return true;
            }
            current = current.getNext();
        }
        return false;
    }
    
    public void print() {
        Node current = head;
        while (current != null) {
            System.out.print(current.getVal() + " ");
            current = current.getNext();
        }
        System.out.println();
    }
}
public class Main {
    public static void main(String[] args) {
        LinkedList list = new LinkedList(5);
        list.insert(4);
        list.insert(3);
        list.insert(6);
        System.out.println("6 is in linked list:" + "is"+list.exist(6));
        System.out.println("16 is not in linked list:" +" is"+ list.exist(16));
        list.print();
        System.out.println("done");
    }
}
```
