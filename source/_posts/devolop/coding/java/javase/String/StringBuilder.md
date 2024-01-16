# StringBuilder.md

Package java.lang

<https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/StringBuilder.html>

## Constructor

```java
StringBuilder() // 空白
StringBuilder​(int capacity) // 指定了容器的初始长度
StringBuilder​(String str)
StringBuilder​(CharSequence seq) // 字符序列，String实现了这个接口
```

## method

`StringBuilder append​(所有类型)` 添加数据（添加的数据转变为字符串）；改变对象，返回对象本身

StringBuilder reverse() 反转容器中的内容

int length() 字符长度（字符出现个数）

Implementing CharSequence:
toString()
