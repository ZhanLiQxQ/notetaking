# notetaking
数据结构与STL

1. 逻辑结构：

  用来描述数据之间的逻辑关系。
  
  分类：
  ①线性结构（线性表，栈，队列）
  ②非线性结构
  a.树（堆，二叉树）
  b.图
  c.集合
  
2. 物理结构（存储结构）：
计算机中存储方式。

分类：
  ①顺序存储结构（数组）
  ②链式存储结构（链表）
  ③散列存储结构（哈希）
  ④索引存储结构

注：
逻辑结构通常可以由多种物理存储结构实现，例如：线性表可以由链式结构（链表），也可以由顺序存储结构（数组）实现；栈既可以由链式结构组成也可以是顺序存储结构。

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

1.引用参数：是一个不可修改的指针，但在函数体中自动解引用。对其一切操作解释成对变量本身操作。

<img width="99" alt="image" src="https://user-images.githubusercontent.com/116830062/215090041-dc66de11-1cab-4202-b24a-3f31937fe5be.png">

最终输出j的值：3

过程：

1.i是引用参数，是指针。

j的地址被拷贝到i中，i指向j

<img width="152" alt="image" src="https://user-images.githubusercontent.com/116830062/215090391-be36a05e-9490-4cf8-835f-fdc0e212344e.png">

2.对i的一切操作解释成对*i操作。

i = 3 等价于*i = 3，等价于j = 3

<img width="133" alt="image" src="https://user-images.githubusercontent.com/116830062/215091352-f22cda70-08d7-46db-8d0d-3efc487a4871.png">


2.返回引用

返回引用类型的函数优点：更快速，可以赋值给等号左边

注意：
返回的值不能是临时变量，不能是存在函数栈中的变量。

所以一般返回的是堆中储存的。

2.3 指针&数组

数组变量实际是指针变量

<img width="164" alt="image" src="https://user-images.githubusercontent.com/116830062/215237582-8df1c7dc-9498-41ad-b841-9521a3fb74f8.png">

<img width="445" alt="image" src="https://user-images.githubusercontent.com/116830062/215091816-ef8fe281-3592-43cd-a8e8-0ee7aa9747e7.png">

注：
1.数组中元素时连续存储的，数组大小固定

2.数组存入元素之前必须分配完毕空间


数组变长问题：

1 . int a[100] 在堆栈上中的数组大小必须给定。

2 . 想要运行时在确定数组长度，可以用new，在堆上分配空间，例如：

<img width="104" alt="image" src="https://user-images.githubusercontent.com/116830062/215237357-e7d712cf-2e73-4bee-bab0-06304872acfc.png">

3 . 但在c99标准中已经允许数组变长，在dev c++中int a[n]已经允许，但在vs中不允许，编译器问题。

2.4 容器

容器就是保存其它对象的对 象

第三章 软件工程简介

3.1 时间复杂度

1 . 大O表示法：

如果f是g的量级的/f是O（g），则

存在非负常数C和K，使得n >= K , f(n) <= C g(n)

<img width="410" alt="image" src="https://user-images.githubusercontent.com/116830062/215239824-2cd3c785-c1ea-4ecb-b918-3dbf84378291.png">
<img width="382" alt="image" src="https://user-images.githubusercontent.com/116830062/215239832-6166e7ef-d405-4570-a264-eec0b8f13d6b.png">
<img width="309" alt="image" src="https://user-images.githubusercontent.com/116830062/215239884-cf1b3218-2336-4f28-a7a2-3de34daa3faf.png">
<img width="257" alt="image" src="https://user-images.githubusercontent.com/116830062/215239894-25c7c5d6-3766-416c-a126-9029526c21b4.png">
分析程序时间复杂度：
<img width="130" alt="image" src="https://user-images.githubusercontent.com/116830062/215239927-f00471e5-0ee8-4fed-a2e5-db3647f778ee.png">
<img width="418" alt="image" src="https://user-images.githubusercontent.com/116830062/215239960-5509d8a6-a0e2-4a02-a424-5e56b838aefb.png">

第四章 递归

汉诺塔问题 worsttime（n）= O(2^n)
<img width="287" alt="image" src="https://user-images.githubusercontent.com/116830062/215241411-82678926-9da9-4404-8632-609f49dbb9eb.png">

<img width="294" alt="image" src="https://user-images.githubusercontent.com/116830062/215241392-bbbe90a1-cab0-41aa-a630-d3c5e5d177f2.png">

第五章 向量和双端队列

5.1 vector

stl中的所有类都是模板类

<img width="98" alt="image" src="https://user-images.githubusercontent.com/116830062/215242012-ae7ee954-7d46-4387-99ac-94ad3c145d32.png">

<img width="322" alt="image" src="https://user-images.githubusercontent.com/116830062/215323719-04f6590c-5deb-436c-8d3c-d29e1bfd726f.png">

<img width="311" alt="image" src="https://user-images.githubusercontent.com/116830062/215323578-eefaefb6-c26b-4dd9-a356-ef926114d747.png">

特点：

1 .连续存储
2 .随机访问
3 .数组比向量唯一的优势是方便初始化。

<img width="441" alt="image" src="https://user-images.githubusercontent.com/116830062/215324896-6bf40f08-22bf-4111-9b35-808c43f02bdc.png">

说明：
1 .erase后，所有后续元素前移，所以erase之后，itr将指向之前vector中目标删除元素的下一个元素

2 . .front 返回的是值，不是迭代器

3 . insert（itr，new_item）返回指向new_item的itr，6防止扩充后itr还指向就数组中的位置！

3 . 时间复杂度：

             push_back:① 加权平均时间amortizedTime（n）= 不resize概率 * O（1）+ resize概率 * O（n）= n/(n+1) * O（1）+ 1/(1+n) * O(n) = O（1）
                       ② worstTime（n）=O（n），resize
                       
             insert：① avgTime（n）= 平均插入时间 + resize情况 = O（n/2）+ 1/(n+1) * O（n）= O(n) 概率计算
                     ② worstTime（n）=O（n），resize

             erase：① avgTime（n）=O（n/2）= O(n) 
                     ② worstTime（n）=O（n）

5.2 双端队列

<img width="274" alt="image" src="https://user-images.githubusercontent.com/116830062/215386685-1189fbea-4d37-4482-9c5b-3d7f67f2ed2b.png">

1.说明：
  1. 一个map指针数组（映射数组），指向均分的连续存储的小块（可以是vector，数组等），小块大小都相等。

  2. 三个迭代器：start，finish,itr

  3. 每个迭代器有四个字段，first，current，last，node

       ① start.current:第一个元素

         finish.current:最后一个元素后面的元素
    
         itr.current:当前选中的元素

       ② first：current指向的元素所在块的第一个元素
    
       ③ last：current指向元素所在块的最后一个单元的下一个单元**
     
       ④ node：指向map中current所在的单元格
     
2.时间复杂度

             pop_front,pop_back: worstTime（n）= O（1）
             
             push_back，push_front:
                       ① 加权平均时间amortizedTime（n）= 不resize概率 * O（1）+ resize概率 * O（元素个数n/每一存储块的元素个数c）= n/(n+1) * O（1）+ 1/(1+n) *                              O(n/c) ,c是常数= O（1）
                       ② worstTime（n）= O（map元素个数）=O（k*n）,k<1 = O（n），resize
                       注：双端队列resize只影响map数组，而不需要将所有元素都重新复制，因为map是指针数组
                       
             insert：① avgTime（n）= 平均插入时间 + resize情况 = O（n/2）+ 1/(n+1) * O（n）= O(n) 概率计算
                     ② worstTime（n）=O（n），resize

             erase：① avgTime（n）=O（n/4）= O(n) 
                     ② worstTime（n）=O（n/2）= O(n)
                     **就近移动：若靠近尾部，后项前移；若靠近头部，前项后移。因此只需平均移动队列中1/4的项。       
             

第十一章 优先队列和堆

11.1 优先队列 priority_queue
1. 定义：一种容器，根据一定方式为项分配优先级，只有优先级最高的可以被访问和删除


1 .插入：avgTime(n)=O(1)

2 .删除：worstTime（n）=O(logn)

2 .优先级队列的应用

哈夫曼编码


11.2 堆 heap
什么是堆？

一种逻辑结构

从上到下整体有序的完全二叉树，每一子树的根都是最大的。

1. 下标：
    父母：i = (j-1)/2
    孩子：j = 2i+1 , 2i+2
    
2. push_heap:
   自下而上，siftUp数据上浮
   （大根堆为例）
   先放在最后叶节点处，若比父母大，交换；直至根节点。
   
   worstTime（n）=O（logn） 注：堆是逻辑结构，堆可以由链表或顺序存储结构实现，所以不考虑resize的O（n），当然若由向量或队列实现worsttime成线性。
   
   由于大部分节点都集中在叶子，平均比较次数不会超过3次，所以：
   avgTime(n) = O（1）
   并且，若考虑resize（用向量或队列实现堆），其amortizedTime依旧为常数。

3. pop_heap
    

