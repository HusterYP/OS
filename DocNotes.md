### 一. 前言

* 这是阅读[Ucore文档及实验细节](https://chyyuu.gitbooks.io/simple_os_book/content/zh/preface/ucore.html) 笔记

### 二. [文档](https://chyyuu.gitbooks.io/simple_os_book/content/zh/preface/osabstract.html)

- IO外设把它的访问接口映射为一块内存区域，操作系统通过来用通常的内存读写指令来管理设备; 或者CPU提供了特定的IO操作指令，操作系统通过这些特定的指令来完成对IO外设的访问 
- 在UNIX中（ucore是模仿UNIX），大部分外设都可以以文件的形式来访问 
- 操作系统的四大基本抽象概念（操作系统的其他基本概念都是基于这四个操作系统抽象概念的

> 1. 中断：分为：外设中断（Device Interrupt）、陷阱中断（Trap Interrupt）和故障中断（Fault Interrupt，也称为exception，异常） 
> 2. 进程：一个进程是一个具有一定独立功能的程序在一个数据集合上的一次动态执行过程 
> 3. 虚存：虚存就是操作系统通过处理器中的[MMU](https://blog.csdn.net/ipmux/article/details/19167605)硬件的支持而给应用程序和用户提供一个大的（超过计算机中的内存条容量）、一致的（连续的地址空间）、私有的（其他应用程序无法破坏）的存储空间。这需要操作系统将内存和硬盘结合起来管理 
> 4. 文件：文件管理的任务是有效地支持文件的存储、检索和修改等操作

- 操作系统特征：需要看一下[文档](https://chyyuu.gitbooks.io/simple_os_book/content/zh/preface/osfeature.html)，讲的比较好

> 1. 虚拟性（Virtualization） ：空间大小虚拟化，时间虚拟化 
> 2. 并发性（concurrency） 
> 3. 异步性 
> 4. 共享性 
> 5. 持久性（persistency） 

* [实验目标](https://chyyuu.gitbooks.io/simple_os_book/content/zh/preface/ucore.html)
* MMU都是硬件实现的，只是MMU中的ＴＬＢ单元产生了ＴＬＢ项缺失的时候，是硬件自动完成从页表到ＴＬＢ的拷贝，还是硬件产生中断，由软件来完成这个拷贝工作 