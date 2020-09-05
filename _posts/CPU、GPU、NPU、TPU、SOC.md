## CPU、GPU、NPU、TPU、SOC

**CPU，全称是Central Processing Unit，即中央处理器。**

这个缩写相信大家最熟悉，它是计算机系统的“大脑”

CPU主要包括运算器、控制单元、若干寄存器、高速缓存器和它们之间通讯的数据、控制及状态的总线。

它的工作思路是：存储程序，按顺序执行。它最擅长于逻辑控制。由于CPU需要大量的空间去放置存储单元和控制逻辑，计算能力就受限制，所以就有了GPU出场。

目前CPU技术上没有革命性的技术变革，只要我们按照科学的程序，一步步努力，不冒进，早晚能赶上。

**GPU全称是Graphics Processing Unit, 即图像处理器；**

GPU主要解决并行运算问题。举个生活中的例子。超市收银台前，顾客有100人排队。如果只有一个收银员，那么即使他操作速度再快，也要大家排队耗时间。如果有50个收银员同时收款，很快就解决问题。GPU解决的就是这个问题。这个问题在图形图处理时问题最突出，故改变算法规则，由GPU芯片来解决。但GPU不能独立工作，必须由CPU控制。

**NPU全称是Neural network Processing Unit, 即神经网络处理器;**

NPU，神经网络处理器，在电路层模拟人类神经元和突触，并且用深度学习指令集直接处理，一条指令对应一组神经元的任务。由于实现存储和计算一体化，故计算效率大大提高。

**TPU全称是Tensor Processing Unit, 即张量处理器；**

是一种为通过基于神经网络运算能力的一种ASIC，即专用集成电路。他把微处理器、模拟IP核、数字IP核和存储器集成在一个芯片上。这是解决运算速度的另外一个思路，就是专项任务，专项解决。它通常根据特定运算任务开发，指向特定用途。比如人机大战中的AlphaGo。

**SOC全称是System on a Chip**，其本质上就是上面说的ASIC。可以叫作系统级芯片,或者叫片上系统

[AI芯片之战：TPU/GPU/FPGA谁称雄？](http://www.eepw.com.cn/article/201808/390001.htm)

[CPU、GPU 和 TPU有什么区别？TPU为什能碾压GPU?](http://www.eepw.com.cn/article/201809/391689.htm)

[GPU、FPGA、ASIC、TPU四大AI芯片简单剖析！](http://www.elecfans.com/rengongzhineng/788557.html)