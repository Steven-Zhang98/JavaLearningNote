## Bit
### 什么是bit？
bit（字节）是binary digit的缩写。计算机中存储和处理数据的基本单位。

### 计算机如何利用bit处理和存储数据？
在二进制系统中，bit只有两个可能的值，0（表示关）或1（表示开）
通过将文本、图像、音频通过特定算法转换成0和1排列的数字，计算机就可以通过bit来存储数据


## Byte
### 什么是byte？
8位bit组成一个byte，也叫字节
### byte有什么用？
通过将8位bit组合成byte可以表示2^8 256个不同的值，可以表示ASCII码表中的字符，比如大小写英文字母、数字、标点符号等。这开启了自然语言与机器语言的连接通道。
数据量可以通过字节的组合形式来表达，1KB = 1024字节，1MB = 1024KB，1GB = 1024MB

### ASCII码表

```java
public class ByteAsciiExameple{
	pblic class void main{String[] args}{
	byte asciiByte = (byte)'A';
	System.out.println("The byte value of 'A':"+ asciiByte);
	
	char asciiChar = (char)asciiByte;
	System.out.println("The ASCII character of 65:" + asciiChar);
}
}
```
ASCII是7位二进制数，所以可以被用byte类型来储存和表示ASCII字符
而要将其byte值转换成对应的ASCII字符，需要通过将‘byte’值强制转换成‘char’类型

### char和byte的区别？
char 占用两字节，用于表示Unicode字符，byte占用1字节，用于表示8位二进制数-128到127
### 原码补码反码

## Int
### 为什么计算机表示数通常用int
范围，取值范围从-2^31-2^31-1，足以表示需要用到的数字
性能，32位计算机系统中，计算机可以一次性处理完对int的操作
可读性与编程习惯，int在许多编程语言中都作为默认值


