- [FE-interview](#fe-interview)
  - [HTML](#html)
  - [CSS](#css)
    - [CSS选择器](#CSS选择器)
    - [什么是BFC,BFC有什么用](#什么是BFC,BFC有什么用)
    - [display:none与visibility:hidden区别](#display:none与visibility:hidden区别)
  - [JS](#JS)
   - [JS基础数据类型](#JS基础数据类型)
  - [框架](#frame)
  - [算法和数据结构](#算法和数据结构)
    - [数组](#数组)
    - [栈](#栈)
  - [web综合知识点](#web综合知识)

  # FE-interview
    这是我个人复习前端知识收集和整理的资料, 希望在阅读文章的朋友, 这篇文章也能帮助到你
  
  ## HTML
  ## CSS
    ### CSS选择器
    1231321
    ### 什么是BFC,BFC有什么用
    BFC(block formatting context)直译为块级格式上下文。

    怎么才能触发BFC
    1. 根元素
    2. float属性不为none;
    3. display属性为 inline-block, table-cell, inline-flex
    4. position属性不为 static, relative
    5. overflow属性不为 visible

    BFC的规则
    1. 内部的盒子会在垂直方向上一个接一个放置
    2. 垂直方向的距离由margin决定(属于同一个BFC的两个相邻盒子之间margin会发生重叠)
    3. 每个元素的margin box的左边， 与包含块border box的左边相接触(对于从左往右的格式化，否则相反)。即使存在浮动也是如此。
    4. BFC区域不会和float的元素重叠
    5. 计算BFC的高度时，浮动子元素也参与计算
    6. BFC就是页面上的一个隔离的独立容器，容器里面的子元素不会影响到外面元素，反之亦然
看到以上的几条约束。

  利用BFC的规则可以实现一些常见的效果
  1. 不合浮动元素重合 如： 自适应两栏布局
  2. 图片文本环绕
  3. 清除盒子内浮动带来影响
  4. 解决垂直方向的margin坍塌

  ### display:none与visibility:hidden区别
  相同点: 它们都能让元素不可见
  区别：
  1. display:none; 会让元素完全从渲染树中消失，渲染的时候不占据任何空间；visibility: hidden;不会让元素从渲染树消失，渲染时元素继续占据空间，只是内容不可见。
  2. display: none;是非继承属性，子孙节点消失由于元素从渲染树消失造成，通过修改子孙节点属性无法显示；visibility: hidden;是继承属性，子孙节点由于继承了 hidden 而消失，通过设置 visibility: visible，可以让子孙节点显示。
  3. 修改常规流中元素的 display 通常会造成文档重排。修改 visibility 属性只会造成本元素的重绘。
  ## JS
    ### JS基础数据类型
    基本数据类型，Number、String、Boolean、Undefined、Null、Symbol ，BigInt。
    引用数据类型： Object (function、Array、Date等都属于Object)
    ### typeof 返回值

    ### JS原型
    js中，我们通常会使用构造函数来创建一个对象，每一个构造函数的内部都有一个prototype属性，这个属性对应的值是一个对象，这个对象它包含了可以由该构造函数的所有实例都共享的属性和方法，我们把它称为原型。
    原型分为显示原型和隐式原型，一般称prototype为显示原型，__proto__称为隐式原型。
    ![原型](images/prototype.webp)
  ## webpack
  ## node
  ## frame
  ## 算法和数据结构
       数据结构是ADT(抽象数据类型 Abstract Data Type)的物理实现
    ### 数组
    原生JS已经实现数组不在扩展

    数组的优点：
    1. 可以通过下标访问，查找速度快
    数组的缺点:
    1. 数组的扩容慢（在高级语言里，扩展数组长度可能需要开辟新的空间，把原来的数组里的数据再拷贝到新数组的空间里）
    2. 数组的插入和删除效率比较低 （插入数据和删除数据需要移动数组操作下标之后的所有元素）
    ### 栈
    栈是一种受限的线性表，表现为后进先出(LIFO).
    1. 其限制是仅允许在表的一端进行插入和删除运算.这一端被称为栈顶，相对的把另一端称为栈底。
    2. LIFO(last in first out)表示就是后进入的元素，第一个弹出栈空间。
    3. 向一个栈插入新元素又称为进栈、入栈或者压栈，它是把新元素放到栈顶元素的上面,使之成为新的栈顶元素。
    4. 从一个栈删除元素又称为出栈或者退栈，它是把栈顶元素删掉,使其相邻的元素成为新的栈顶元素。

    常见题型： 
    有六个元素6、5、4、3、2、1的顺序进栈，问哪个是不合法的出栈顺序（） // C  
    A. 5 4 3 6 1 2   B. 4 5 3 2 1 6 C. 3 4 6 5 2 1 D. 2 3 4 1 5 6  

    栈的实现
    ```
    function Stack() {
      this.items = []
      // 入栈
      Stack.prototype.push = function(element) {
        this.items.push(element)
      }
      // 出栈
      Stack.prototype.pop = function(element) {
        return this.items.pop()
      }
      // 查看栈顶元素
      Stack.prototype.peek = function(element) {
        return this.items(this.items.length -1)
      }
      // 判断栈是否为空
      Stack.prototype.isEmpty = function(element) {
        return this.items.length === 0
      }
      // 获取栈里的元素数量
      Stack.prototype.size = function(element) {
        return this.items.length
      }
      Stack.prototype.toString = function(element) {
        let resString = ''
        this.items.forEach(item => {
          resString = `${resString}  ${item}`
        })
        return resString
      }
    }

    let stack = new Stack()
    ```
  ## web综合知识