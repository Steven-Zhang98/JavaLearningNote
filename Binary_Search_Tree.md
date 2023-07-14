## 如何写一个二叉搜索树（Binary Search Tree，简称 BST）？
这玩意干嘛的? 有什么用? 能解决什么问题？
### 1.写一个 Node
为什么要先定义 node 类才定义二叉搜索树？因为每个节点都有一些共享的特性，比如一个值和指向其他节点的指针（通常是左右子节点）。这些特性可以很好地用一个类来表示。  
而定义 Node 很简单，只需要记住他有 3 个属性：  
1. value：一个 int 类型的变量，用于存储节点的值。
2. left：一个 Node 类型的变量，用于指向该节点的左子节点。
3. right：一个 Node 类型的变量，用于指向该节点的右子节点。  
之后便有一个构造函数和 get set 方法即可
``` java
public class Node {
    private int value;
    private Node left;
    private Node right;

    public Node(int value) {
        this.value = value;
        this.left = null;
        this.right = null;
    }

    public int getValue() {
        return value;
    }

    public void setValue(int value) {
        this.value = value;
    }

    public Node getLeft() {
        return left;
    }

    public void setLeft(Node left) {
        this.left = left;
    }

    public Node getRight() {
        return right;
    }

    public void setRight(Node right) {
        this.right = right;
    }
}

```
### 2. 定义一个BinarySearchTree
定义 BST 需要先定义了树的根节点（私有的 Node 类型名字叫 root ）。在构造函数中，将这个属性初始化为 null。  

然后，我们定义了一个 insert 方法，这个方法用于在 BST 中插入一个新的值。这个方法调用了一个私有的递归方法 insertRec 来完成插入操作。在 insertRec 方法中，我们根据新的值和当前节点的值的比较结果来决定是向左子树还是向右子树插入新的节点。如果树是空的（即 root 为 null），那么新的值就会成为根节点。
``` java
public class BinarySearchTree {
    private Node root;

    public BinarySearchTree() {
        this.root = null;
    }

    public void insert(int value) {
        this.root = this.insertRec(this.root, value);
    }

    private Node insert(Node root, int value) {
        if (root == null) {
            root = new Node(value);
            return root;
        }

        if (value < root.getValue()) {
            root.setLeft(this.insertRec(root.getLeft(), value));
        } else if (value > root.getValue()) {
            root.setRight(this.insertRec(root.getRight(), value));
        }

        return root;
    }
}
```
然后，我们需要对二叉树进行遍历，常见的遍历方式有先序遍历、中序遍历和后序遍历。这里我们添加一个中序遍历的方法，即先打印该节点值，在遍历左子树，然后是右子树。
``` java
public void visit() {
        this.visitRec(this.root);
    }

    private void visitRec(Node node) {
        if (node != null) {
            System.out.println(node.getValue());
            visitRec(node.getLeft());
            visitRec(node.getRight());
        }
    }
```
![image](https://github.com/Steven-Zhang98/JavaLearningNote/assets/115378528/6acec8fb-9f5d-4295-945f-e9e05745674e)

最终结果会打印出124356
