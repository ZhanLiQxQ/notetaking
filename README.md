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

11.1 堆 heap
什么是堆？

一种逻辑结构

从上到下整体有序的完全二叉树，每一子树的根都是最大的。

任何支持迭代器随机访问的容器都可以充当堆：数组，向量，双端队列等

<img width="221" alt="image" src="https://user-images.githubusercontent.com/116830062/215457532-d4b44880-6bf9-44a4-937e-62ff8a190b8d.png">

用数组表示：（原则是父母子女下标的对应关系满足公式）
<img width="243" alt="image" src="https://user-images.githubusercontent.com/116830062/215457788-9fae94b5-5cb1-4b63-b2c8-b8950b4183c6.png">

1. 下标：
    父母：i = (j-1)/2
    孩子：j = 2i+1 , 2i+2
    
2. push_heap:
   自下而上，siftUp数据上浮
   （大根堆为例）
   先放在最后叶节点处，若比父母大，交换；直至根节点。
   
   worstTime（n）=O（logn） 
   注：堆是逻辑结构，所以不考虑resize的O（n），当然若由向量或队列实现worsttime成线性。
   
   由于大部分节点都集中在叶子，平均比较次数不会超过3次，所以：
   avgTime(n) = O（1）
   并且，若考虑resize（用向量或队列实现堆），其amortizedTime依旧为常数。

3. pop_heap（将根节点放到最后）
    自上而下，siftDown数据下沉
    （大根堆为例）
    将根与最后一个叶节点互换，该叶节点从根开始，与两个孩子中较大的比较，直至比较到叶；然后用push_heap(数据上浮）调整到合适位置。
    
    
<img width="233" alt="image" src="https://user-images.githubusercontent.com/116830062/215450581-94cc012f-c48e-4442-9995-825adf1ec72a.png">

<img width="321" alt="image" src="https://user-images.githubusercontent.com/116830062/215438836-537b4f2b-bc1b-4a5b-ae81-e4a1d253ea6d.png">

<img width="335" alt="image" src="https://user-images.githubusercontent.com/116830062/215454448-039d1cee-5eb5-4ddc-8550-52c5314f7a83.png">

下沉至叶节点后，调用push_heap插入55

<img width="356" alt="image" src="https://user-images.githubusercontent.com/116830062/215454710-6067ffe2-b2e1-4cdf-99ad-ab0bd8c607a0.png">

为什么不直接比较父母节点与孩子节点的值，而是一直下沉到叶，再push_heap数据上浮？

个人认为可以提速。这样避免父母节点与孩子比较，提高效率；又由于元素大都集中在最后一层，push_heap只需调整几轮即可，时间复杂度平均为常数，所以这样更好。


  4 .建立堆
  法一：
      push_heap逐个添加法
      最坏时间复杂度worstTime（n）=O（n * logn）
      
  法二：（更快）
      先将元素放好，再调整堆
      
      从叶节点的父母节点开始，自下而上的siftDown数据下沉。
      
![629160091efb4cbfa070b7d39f70d435](https://user-images.githubusercontent.com/116830062/215455181-6a23e62e-1fdb-452c-92cc-a750973571af.gif)
    
    时间复杂度avgTime（n）=O（n）
     
     <img width="265" alt="image" src="https://user-images.githubusercontent.com/116830062/215774615-7ab8e7c4-9bb9-459b-a343-13db1b70389c.png">

 5. sort_heap堆排序   
    pop_heap不会将根节点erase，只是将它放到最后一个位置，所以：
    连续调用可以实现堆排序，每次将最大的放到最后，将排好的放好不动，再排序前面的
    
     void sort_heap(_RandomAccessIterator __first, _RandomAccessIterator __last)
     
     {
     
     while (last - first > 1)
     
     pop_heap(first, last--);
     
     }
     
     堆排序的前提是他本来就是个堆！
    
    n个元素排序：avgTime（n）=O（n * logn）
 
    堆排序虽然需要先建堆，但即便如此也更优化，原因是：
    
      ① 选择排序：O（n^2）
      
      ② 堆排序：avgTime（n）= 建堆 + 堆排序 = O（n）+ O（n * logn）= O（n*logn）
      
        堆排序可以说是排序的极限。
        
二 .堆的使用
 ① 建堆make_heap
 
  #include<algorithm>

  <img width="500" alt="image" src="https://user-images.githubusercontent.com/116830062/215795088-9d705e86-40a4-4d4b-a239-5a6bb7c74c3b.png">
  
  输出：（大根堆和小根堆）
  
<img width="500" alt="image" src="https://user-images.githubusercontent.com/116830062/215795827-bc97ac1e-d38f-4ddf-9a8f-16bc9cf271ca.png">

  以大根堆nums_max为例的构造过程示意图：
  
  ![629160091efb4cbfa070b7d39f70d435](https://user-images.githubusercontent.com/116830062/215455181-6a23e62e-1fdb-452c-92cc-a750973571af.gif)
  
  自下而上再自上而下，最终：

  <img width="800" alt="image" src="https://user-images.githubusercontent.com/116830062/215793070-fe0869db-2ce4-414f-bc27-416e2e778dea.png">
  
  ②向堆中插入元素
  向大根堆中插入20

  <img width="238" alt="image" src="https://user-images.githubusercontent.com/116830062/215799119-fa267dc0-f6dd-45bb-a45c-510fad449bf0.png">
  <img width="704" alt="image" src="https://user-images.githubusercontent.com/116830062/215801881-470800f8-8394-47e7-b3b7-644a112af247.png">


11.2 优先队列 priority_queue

  1. 定义：一种容器，根据一定方式为项分配优先级，只有优先级最高的可以被访问和删除
     ① 优先队列的T模板类要求支持迭代器随机访问！可以是vector或deque但不能为list类！优先级最高的放在最前面
     ② **形参compare对应缺省变元是内置函数类less，大的优先级高，大->小。
        **greater为小的优先级高，小->大。
   
  在标准c++中，优先队列的pop和push应用了堆的函数pop_heap 和 push_heap。
    1 .push插入：avgTime(n)=O(1)，
                worstTime(n)=O(n)
        
   <img width="130" alt="image" src="https://user-images.githubusercontent.com/116830062/215746276-0a80664e-b432-44f5-a662-27a4fb0da78f.png">

    2 .pop：worstTime（n）=O(logn)

   <img width="129" alt="image" src="https://user-images.githubusercontent.com/116830062/215746241-e84322cc-ccbf-45bd-b18c-b52c50de4df8.png">

words升序（greater），score降序（默认缺省less）

<img width="187" alt="image" src="https://user-images.githubusercontent.com/116830062/215748612-f90c520b-96be-4095-8d56-0f5f87d442f0.png">

<img width="175" alt="image" src="https://user-images.githubusercontent.com/116830062/215748730-6ff2a0cf-d527-427a-8aa7-f087bb25405c.png">

注：

在标准c++中，只有用堆实现优先队列是合法的，但用set和列表实现也各有各的优点。

<img width="705" alt="image" src="https://user-images.githubusercontent.com/116830062/215768493-210c6a79-d8f2-4a57-a7ee-c8dea1d8acea.png">

2 .优先级队列的应用

哈夫曼编码：

    1 .无前缀变长编码，且无二义性
    2 .利用优先队列，优先级越高越靠近根，**字母出现频率越低优先级越高。
    3 .自下而上生成二叉树，每个字符放在叶节点上

哈夫曼树生成过程（自下而上）：
 ① 将字符按频数放入优先队列（频数升序排列）
 
<img width="378" alt="image" src="https://user-images.githubusercontent.com/116830062/215763202-c8d626d0-eb2d-47b6-8364-638bb74d31b9.png">

优先级：高->低，频数：低->高

 ② pop（）优先级最高的两个，合成pair
 
 <img width="82" alt="image" src="https://user-images.githubusercontent.com/116830062/215763291-383fdda1-28a4-46c1-b202-0660430aa930.png">
 

 ③ 将新得到的pair再push（）进优先队列，再次按照优先级排序（频率升序）
 
 <img width="324" alt="image" src="https://user-images.githubusercontent.com/116830062/215763532-f8be80fa-2e2a-4f62-b3f2-266ebefac973.png">


 ④ pop（）优先级最高的两个，合成pair
 
 <img width="113" alt="image" src="https://user-images.githubusercontent.com/116830062/215763578-101eec0a-69ed-4df2-af40-653e1bc68a49.png">
   
 ⑤ 将新得到的pair再push（）进优先队列，再次按照优先级排序（频率升序）
 
 ...
 
 <img width="275" alt="image" src="https://user-images.githubusercontent.com/116830062/215762632-f97d4a13-4083-4f20-ba2d-319cd106250d.png">
 
 pop<img width="100" alt="image" src="https://user-images.githubusercontent.com/116830062/215764438-66f8cb0e-5e43-4963-a4f8-cfbed8ce0e87.png">
合成pair：
 
<img width="204" alt="image" src="https://user-images.githubusercontent.com/116830062/215763097-9b33115a-dde6-4387-bfbe-3a5589fb8fe8.png">

<img width="219" alt="image" src="https://user-images.githubusercontent.com/116830062/215763666-f1227d16-79fd-4f1b-8456-828f2a2dc9ee.png">

pop <img width="100" alt="image" src="https://user-images.githubusercontent.com/116830062/215764720-96bc3db7-d19a-472f-97e4-87808fb6dd02.png">
合成pair：

<img width="377" alt="image" src="https://user-images.githubusercontent.com/116830062/215763737-bf152b1b-4c1c-4cae-8341-0b563042a4b9.png">

pop <img width="100" alt="image" src="https://user-images.githubusercontent.com/116830062/215764925-eb47e9fe-c3fb-46d3-9fa2-d9277ff2c798.png">
合成pair：

<img width="301" alt="image" src="https://user-images.githubusercontent.com/116830062/215763815-fbaa14a4-5095-48c9-b7ca-48df7908b85c.png">

最终huffman编码为：

<img width="71" alt="image" src="https://user-images.githubusercontent.com/116830062/215763886-52cb57bb-dd89-4dd6-9eb7-13c40e56a13a.png">

 
<img width="500" alt="image" src="https://user-images.githubusercontent.com/116830062/215767839-7bc1c5dc-1c60-4f2a-89e1-19aa023cec3e.png">
