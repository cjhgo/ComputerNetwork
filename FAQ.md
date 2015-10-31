viewport:width=device-width,initial-scale=1

目录

[TOC]

+ througput & bandwidth
+ 非周期信号的傅立叶变换所得频域图像是连续的,而不像上图那样离散.
+ 脑海里能直观形象的理解数据字节流在介质中传输,理解宽带的概念
+ **带宽更高的正确理解**
	- ~~不是指数据在介质里的传输速度$m/s$更快了~~
	宽带线路和窄带线路上比特的传播速率是一样的.
	信号在介质中的传播速度跟信号的频率有关,带宽变高是指频率的范围变高
		+ 实际上光纤中的传播速度更慢了
	- ~~是指在同一个时刻能传更多数据位了~~
		+ 这是并行传输
		![bandwithd2][1]
	- 而是指,串行传输,<u>在一个时间段内能传输更多数据位了</u>
		+ 之前1s能传4个码元,现在1s能传8个码元,这就是更高速的带宽
	![bandwidth1][0]		
	- 用高速路作比喻
		+ 车道增加,这就采用并行传输提高了数据传送率
		+ 车内载人更多,这就通过增加码元代表的数据位提高了数据传送率
		+ 车距变小,相同时间内通过更多车辆,这是速度更高的带宽
	- ...暂且这么理解吧,,,,
	- 本质的理解:介质能够通过的频率的范围加大了
	根据奈奎斯特公式和香农定理,也可以看出B变大C变大
+ **速度与容量单位的不同**
计算机网络中的传输速度中的比例是1000
计算机组成原理中的存储容量中的单位是1024
(包括组成原理中的总线的传输速度中M也是10^6,而不是2^20)
+ 描述相位的域是什么域
+ **波特率与比特率的正确理解**
	- one measures data (the throughput of a channel) and the other transitions (called the signaling rate).
	波特率测量的是变化,信号的变化,在每个信号单元内无论有几个波形,它们的3个属性频率,振幅,相位一致
	- 波特率
	```
	波特率(Baud)即调制速率,指的是有效数据信号调制载波的速率,
	即单位时间内载波调制状态变化的次数.
	它是对符号传输速率的一种度量,1波特即指每秒传输1个符号,
	而通过不同的调制方式,可以在一个码元符号上负载多个bit位信息.
	```
	- 波特率是什么,是一种约定,约定好了,每秒钟发送多少个码元/signal element
	那么接收方按照这样一个速度/时间间隔接收信号
	然后一个码元携带了多少个data element 
	决定了此次数据传输过程中的数据传输率
		+ 所以不要纠结为什么digital transmission中一个signale element 是一个波形
		analog transmission中一个signal element是好几个波形
		它们的本质是1s发送n个码元,一个码元持续1/n的时间
		根据调幅,调频,调相,一个码元内发送几个波形都是有可能的
	- 波特率是发送码元的一种速度/时间间隔约定,人为设定
	- 波特率和the number of data elements carried by a signal element这两个量决定了数据传输速率
+ **数据电平和信号电平**
+ baseband:信号不通过调制直接以数字形式传输的方法 (适合于短时间的传输),line code
```
Digital baseband transmission
Main article: Line code

Digital baseband transmission, also known as line coding,
aims at transferring a digital
bit stream over baseband channel, 
typically an unfiltered wire, 
contrary to passband transmission,
also known as carrier-modulated transmission.
Passband transmission makes communication possible 
over a bandpass filtered channel, 
such as the telephone network local-loop or 
a band-limited wireless channel.

Baseband transmission in Ethernet

The word "BASE" in Ethernet physical layer standards, 
for example 10BASE5, 100BASE-T and 1000BASE-SX, 
implies baseband digital transmission 
(i.e. that a line code and an unfiltered wire are used).
```
+ 路由器之间在交换路由信息时,根据使用的路由协议的不同,也可能使用运输层(第四层)协议
+ 电磁波在1km电缆中的传播时延为5$\mu s$
	- contention period in ethernet
+ 为什么集线器方式中还只能是半双工

[0]:http://cjhgo.sinaapp.com/CS/ComputerNetwork/images/bandwidth1.gif
[1]:http://cjhgo.sinaapp.com/CS/ComputerNetwork/images/bandwidth2.gif