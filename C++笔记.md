# C++核心编程
## 内存分区模型
C++在执行程序时，大致将内存分为四个区域
* 代码区：存放函数体的二进制代码，由操作系统进行管理，编译后就会生成。
* * 特点：共享的，只读的
* 全局区：存放全局变量，静态变量和全局常量，字符串常量，编译就会生成，在程序结束后，系统会释放（局部常量不在里面）
* 静态变量和全局变量的区别：
* * 静态局部变量具有局部作用域只对定义自己的函数可见，只被初始化一次，自从初始化一次之后直到程序运行期间一直都在。
* * 静态全局变量具有全局作用域作用于定义它的程序文件但是不能作用于项目里的其它文件，这一点和全局变量不同。静态全局变量可以被多次初始化。
* *  把局部变量改变为静态变量之后是改变了它的存储方式和生命期。
* *  把全局变量改变为静态变量之后是改变了它的作用域，限制了使用范围
* 栈区：由编译器自动分配释放，存放函数的参数值，局部变量（局部常量）等，程序运行后生成，不要返回局部变量的地址
* 堆区：由程序员分配和释放，不释放的话，程序结束时由系统回收，在C++中主要利用new来开辟数据，用delete来释放，用new来创建数组int * arr = new int[10]
用delete释放数组 delete[] arr;
## 存在的意义：不同区中的数据会有不同的生命周期

## 引用
* int&b = a //a和b使用同一内存，同时改变
* 引用必须初始化 int&b是错误的
* 引用后就不能更改了
#
引用用作函数参数
* 可以用引用的技术让形参修饰实参
* 可以简化指针的引用
#
引用用作函数的返回值
* 不要返回局部变量的引用
* 函数的调用可以用做左值
##
引用的本质
* 引用的本质是在C++内部实现一个指针常量
#
常量引用
* 主要用来修饰形参防止误操作，常量引用不能被改变

