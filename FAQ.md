viewport:width=device-width,initial-scale=1

目录

[TOC]

+ 脑海里能直观形象的理解数据字节流在介质中传输,理解宽带的概念
+ 带宽更高的正确理解
	- 不是指数据在介质里的传输速度更快了--------光纤中的传播速度更慢了
	宽带线路和窄带线路上比特的传播速率是一样的.
	信号在介质中的传播速度跟信号的频率有关,带宽变高是指频率的范围变高
	- 不是指能同时传更多数据位了--------这就并行传输
	- 而是指,串行传输,相同的时间内能传输更多数据位了
		+ 之前1s能传4个码元,现在1s能传8个码元,这就是更高速的带宽
	![bandwidth1][0]		
	- 用高速路作比喻
		+ 车道增加,这就采用并行传输提高了数据传送率
		+ 车内载人更多,这就通过增加码元代表的数据位提高了数据传送率
		+ 车距变小,相同时间内通过更多车辆,这是速度更高的带宽
	- ...暂且这么理解吧,,,,
	- 本质的理解:介质能够通过的频率的范围加大了
	根据奈奎斯特公式和香农定理,也可以看出B变大C变大
相关图片
![bandwithd2][1]
+ 计算机网络中的传输速度中的比例是1000
计算机组成原理中的存储容量中的单位是1024
(包括组成原理中的总线的传输速度中M也是10^6,而不是2^20)
+ 描述相位的域是什么域
+ the number of data elements carried by a signal element
+ 波特率是什么,是一种约定,约定好了,每秒钟发送多少个码元/signal element
那么接收方按照这样一个速度/时间间隔接收信号
然后
一个码元携带了多少个data element 决定了此次数据传输过程中的数据传输率
	- 所以不要纠结为什么digital transmission中一个signale element 是一个波形
	analog transmission中一个signal element是好几个波形
	它们的本质是1s发送n个码元,一个码元持续1/n的时间
	根据调幅,调频,调相,一个码元内发送几个波形都是有可能的
+ 波特率是发送码元的一种速度/时间间隔约定

[0]:http://cjhgo.sinaapp.com/CS/ComputerNetwork/images/bandwidth1.gif
[1]:http://cjhgo.sinaapp.com/CS/ComputerNetwork/images/bandwidth2.gif