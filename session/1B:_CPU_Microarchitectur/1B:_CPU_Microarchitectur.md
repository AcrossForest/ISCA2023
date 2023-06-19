
# Orinoco: Ordered Issue and Unordered Commit with Non-Collapsible Queues

| Key | Value |
:----- | :----: 
|**Time** | 9:15 AM – 9:30 AM |
|**Authors** | Dibei Chen, Tairan Zhang, Yi Huang, Jianfeng Zhu, Yang Liu, Pengfei Gou, Chunyang Feng, Binghua Li, Shaojun Wei, Leibo Liu |
|**LocalPDF** | [PDF File](Chen%20et%20al.%20-%202023%20-%20Orinoco%20Ordered%20Issue%20and%20Unordered%20Commit%20with%20N.pdf) |



miss掉了，没有参加。





# SPADE: A Flexible and Scalable Accelerator for SpMM and SDDMM

| Key | Value |
:----- | :----: 
|**Time** | 9:30 AM – 9:45 AM |
|**Authors** | Gerasimos Gerogiannis, Serif Yesil, Damitha Lenadora, Dingyuan Cao, Charith Mendis, Josep Torrellas |
|**LocalPDF** | [PDF File](Gerogiannis%20et%20al.%20-%202023%20-%20SPADE%20A%20Flexible%20and%20Scalable%20Accelerator%20for%20SpM.pdf) |


听了一点点，没有概念。但似乎重点是做了一个Out-of-order的架构来隐藏Sparse data访问的到达时间不确定的问题。






# DynAMO: Improving Parallelism Through Dynamic Placement of Atomic Memory Operations

| Key | Value |
:----- | :----: 
|**Time** | 9:45 AM – 10:00 AM |
|**Authors** | Víctor Soria-Pardos, Adrià Armejach, Darío Suárez-Gracia, Tiago Mück, José A. Joao, Alejandro Rico, Miquel Moretó |
|**LocalPDF** | [PDF File](Soria-Pardos%20et%20al.%20-%202023%20-%20DynAMO%20Improving%20Parallelism%20Through%20Dynamic%20Plac.pdf) |

## 术语AM
AMO: Atomic Memory Operation

## 背景
Atomic操作需要把cacheline拉到Core的附近而无论Cacheline是否被复用

## 意图
预测一个Cacheline是否会被复用。区分两种情况:
+ Near AMO: 该Cacheline会被复用
+ Far AMO: 该Cacheline不会被复用

## 设计
能支持远程的AMO操作的执行的硬件  + 能进行类似分支预测那样的预测机构。

## 挑战

一个观众提出了如下观点：
通常有一个编程的方式，是总是将数据的Lock和被这个Lock保护的数据放在同一个Cacheline当中。（这似乎有很多直接的好处）。这样的话，这个方法就不会有什么用了。






# μManycore: A Cloud-Native CPU for Tail at Scale

| Key | Value |
:----- | :----: 
|**Time** | 10:00 AM – 10:15 AM |
|**Authors** | Jovan Stojkovic, Chunao Liu, Muhammad Shahbaz, Josep Torrellas |
|**LocalPDF** | [PDF File](Stojkovic%20et%20al.%20-%202023%20-%20μManycore%20A%20Cloud-Native%20CPU%20for%20Tail%20at%20Scale.pdf) |

## 背景

网络上的服务用Microservice搭建起来的，和Processor设计的目标显著不同。

## 观察

+ Tail Latency 显著比平均值高
+ Context Switch很高

## 设计
+ 对Cache Coherance的阉割
+ 对Context Switch的加速

## 质疑
降低Tail Latency可以理解？为什么会有15.5的吞吐量的提高？这是否国羽逆天。









# MESA: Microarchitecture Extensions for Spatial Architecture Generation

| Key | Value |
:----- | :----: 
|**Time** | 10:15 AM – 10:30 AM |
|**Authors** | Dong Kai Wang, Jiaqi Lou, Naiyin Jin, Edwin Mascarenhas, Rohan Mahapatra, Sean Kinzer, Soroush Ghodrati, Amir Yazdanbakhsh, Hadi Esmaeilzadeh, Nam Sung Kim |
|**LocalPDF** | [PDF File](Wang%20et%20al.%20-%202023%20-%20MESA%20Microarchitecture%20Extensions%20for%20Spatial%20Arc.pdf) |


## 背景
+ 现代处理器包含集成的加速器（？真的吗）
+ 集成的加速器有点难用，所以会有idle。既然idle，就可能借给加速器使用。


## 设计
以一种JIT的方式将CPU的workload Offload到加速器上，

指令流 -> 计算图 -> （设计算的算算法） 用Greedy算法最小化预期的总延迟

Non-intrusive CPU Core design


## 限制（作者自己说的）
1.有一系列的限制使用条件


## 疑问
动态地解析CPU的代码然后分析其中的data flow graph 然后动态的生成加速器的配置？这可能吗？


## Presentation
在开场的时候用一个一页的Outline来快速的过了一遍Motivation到Solution







# Imprecise Store Exceptions

| Key | Value |
:----- | :----: 
|**Time** | 10:30 AM – 10:45 AM |
|**Authors** | Siddharth Gupta, Yuanlong Li, Qingxuan Kang, Abhishek Bhattacharjee, Babak Falsafi, Yunho Oh, Mathias Payer |
|**LocalPDF** | [PDF File](Gupta%20et%20al.%20-%202023%20-%20Imprecise%20Store%20Exceptions.pdf) |

## 背景
CPU执行需要精确的异常处理。对于Store的情况需要保留太久的数据。

## 设计
让核心的执行不需要处等待Store的Page Walk的判决结果，直接retire（让核心继续执行），但使用一个缓冲保留着已经retire但是没有complete的store。如果出现了Page Fault, 让操作系统解决了page fault后再clean up后续没有完成Store。

## 实验
基于香山核的Full-system Prototype， Formal的证明。



# Supply Chain Aware Computer Architecture

| Key | Value |
:----- | :----: 
|**Time** | 10:45 AM – 11:00 AM |
|**Authors** | August Ning, Georgios Tziantzioulis, David Wentzlaff |
|**LocalPDF** | [PDF File](Ning%20et%20al.%20-%202023%20-%20Supply%20Chain%20Aware%20Computer%20Architecture.pdf) |


建立了一套关于供应链的模型，从而在架构设计(Architecture) 和供应链稳定性之间建立联系。





