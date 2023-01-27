# notetaking
数据结构与STL

第一章 c++中的类

第一章主要是回顾和复习之前学的面向对象知识

第二章 容器类的存储结构

2.1 指针&动态变量

动态变量：（new出来的变量）编程者在程序运行时显示创建和撤销的变量，在需要时才分配存储区域。存在堆中。

指针：存在栈中。

注：
1.与普通变量不同，动态变量决不能直接访问，而总是通过指针变量访问。
指针变量存在栈中，动态变量存在堆中。指针变量！=动态变量

2.
<img width="449" alt="image" src="https://user-images.githubusercontent.com/116830062/215089044-3935f3d7-8c51-4fef-9fc3-6c0665230f77.png">


2.2 引用参数

引用参数：是一个不可修改的指针，但在函数体中自动解引用。对其一切操作解释成对变量本身操作。

<img width="99" alt="image" src="https://user-images.githubusercontent.com/116830062/215090041-dc66de11-1cab-4202-b24a-3f31937fe5be.png">

最终输出j的值：3

过程：

1.i是引用参数，是指针。

j的地址被拷贝到i中，i指向j

<img width="152" alt="image" src="https://user-images.githubusercontent.com/116830062/215090391-be36a05e-9490-4cf8-835f-fdc0e212344e.png">

2.对i的一切操作解释成对*i操作。

i = 3 等价于*i = 3，等价于j = 3

<img width="133" alt="image" src="https://user-images.githubusercontent.com/116830062/215091352-f22cda70-08d7-46db-8d0d-3efc487a4871.png">

2.3 指针&数组

<img width="445" alt="image" src="https://user-images.githubusercontent.com/116830062/215091816-ef8fe281-3592-43cd-a8e8-0ee7aa9747e7.png">



