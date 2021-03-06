# 一切都是对象
## 用引用操作对象
一切皆对象，操纵的标示符为引用，类似于“遥控器”与电视的关系
## 对象的存储
1. 寄存器：处理器内部，最快的区域，数量与空间有限，不能直接控制（C/C++ 允许你向编译器建议寄存器的分配方式）
2. 堆栈：位于通用RAM中，速度仅次于寄存器，向下移动堆栈指针分配内存，向下移动释放内存（编译器需要知道所有项的存活时间），存储了对象的引用与基本类型变量。
3. 堆：也位于通用RAM中，用于存放所有Java对象（编译器不需要知道存活时间），new 对象时自动分配存储空间
4. 常量存储
5. 非RAM存储：存活于程序之外，不受程序控制，比如流对象与持久化对象，
6. 特例：基本类型，保存于堆栈，且各个基本类型变量大小不随硬件架构而变化（得益于JVM）
7. 数组：范围检查、自动初始化（对比C/C++）

## 对象作用域与自动销毁
1. 代码块中定义的变量将作用于该代码块的所有 子代码快（不同于C/C++，C++会将较大作用域的变量隐藏起来）
2. 超过作用域的变量的“引用”将会消失，实际的对象将会由JVM垃圾清理机制进行销毁

## 类
1. 字段与方法
2. 成员的默认值：作为类的成员使用时，Java将会给基本数据类型的变量初始化默认值（不同于C++）
3. 对于局部变量，不初始化则编译器会对未初始化的变量进行报错（C++是警告）
4. static关键字：表示这个域或者方法不与该类的任何对象关联，属于整个类而不是特定对象而存在