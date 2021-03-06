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
+ IEEE802委员会:专门制定局域网和城域网标准的机构
	- IEEE802.1-桥接/体系结构
	- IEEE802.3-CSMA/CD
	- IEEE802.11-无线局域网
	- IEEE802.15-无线个人区域网
	- IEEE802.16-宽带无线接入
	....
+ 数据报多次分片,片偏移的值仍是相对原始数据报
+ TTL设置为0,则数据报只能在局域网中传送
+ 连个路由器一定要直连一下,才好转发吗,?不一定
+ $网络地址145.13.0.0,网络号145.13$
+ 本单位以外的网络看不见本单位多少子网;交换路由信息时交换掩码,???
+ 判断直接交付,细节,?信息在哪儿获取,?
	- 主机发送数据报,主机自己有一个路由,主机也有一个自己的掩码,用掩码算目的地址的网络号,看和自己是否匹配
	- **主机的直接交付,和路由器的直接交付**
+ ICMP是应用层直接使用网络层ICMP的一个例子	
+ 在路由表中使用0.0.0.0来表示默认路由
+ 特殊的IP地址:P120,???
+ RIP:UDP,520
+ OSPF:IP,"89"
+ BGP:TCP,179
+ 路由中的"网关"是因为历史上把路由叫成了网关
+ RIP:距离向量;OSPF:链路状态;BGP:路径向量
+ ASN自治系统号,是一个16位的全球唯一的ICANN分配的号
+ IP中IP:隧道-->ip数据报协议字段值
+ 局域网和专用网;使用全球IP到局域网
+ 以太网的组播/硬件多播,这样理解:(对吗)
	- 主机的每一个适配器不但有一个全球唯一的MAC地址
	**还有一个可以分配/赋值的组播地址**
	- IP多播到达局域网时,把这个D类地址(后23位)映射成多播MAC地址的后23赋值给多播组成员
	这样就可以利用硬件多播来实现IP多播了
	??这就是IP->MAC映射??的由来,?
+ ??169.254是DHCP的APIPA使用的地址,
	- APIPA是一个DHCP故障转移机制。当DHCP服务器出故障时， 
	APIPA在169.254.0.1到 169.254.255.254的私有空间内分配地址，
	所有设备使用默认的网络掩码255.255.0.0。客户机调整它们的地址使用它们在使用ARP的局域网中是唯一的。
	APIPA可以为没有DHCP服务器的单网段网络提供自动配置TCP/IP协议的功能。
		+ Automatic Private IP Addressing :APIPA
+ blackhole server使用的IP地址,invserse query
+ iana:internet assigned number authority
+ 路由器之间交换信息就用到了局域网内的组播技术
+ 目前有四种类型的广播地址：受限的广播、指向网络的广播、指向子网的广播和指向所
有子网的广播。最常用的是指向子网的广播。受限的广播通常只在系统初始启动时才会用到。
```

"blackhole" servers

"Autoconfiguration" IP Addresses:

        169.254.0.0 - 169.254.255.255 
Addresses in the range 169.254.0.0 to 169.254.255.255 are used automatically by most network devices when they are configured to use IP, do not have a static IP Address assigned and are unable to obtain an IP address using DHCP. 
This traffic is intended to be confined to the local network, so the administrator of the local network should look for misconfigured hosts. Some ISPs inadvertently also permit this traffic, so you may also want to contact your ISP. 

getmac.exe
组群成员的网卡接口除了硬件MAC地址 (unicast MAC)，还有组播MAC地址 (multicast MAC)
```
+ Special IP addresses/特殊的IP地址
	- 专用网/本地网(而非局域网)保留的IP地址:这些IP地址永远不可能出现在因特网上,路由器不转发这类IP地址
		+ A:10/8
		+ B:172.16/12
		+ C:192.168/16
	- DHCP协议中的APIPA使用的IP地址:169.254.0.1-169.254.255.254
	- D类IP地址用于多播目的地址
	- 网络地址/Network address:网络号+主机号全0
		+ 所以主机号全0不分配
	- ![specialipd][2]


[0]:http://cjhgo.sinaapp.com/CS/ComputerNetwork/images/bandwidth1.gif

[1]:http://cjhgo.sinaapp.com/CS/ComputerNetwork/images/bandwidth2.gif
[2]:http://cjhgo.sinaapp.com/CS/ComputerNetwork/images/specialip.gif