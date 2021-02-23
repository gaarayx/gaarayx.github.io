参考：
https://blog.csdn.net/xiaozy115/article/details/102502634

LLC（Logic Link Control Sub Layer）：逻辑链路层 主要负责站点间的帧交换，差错控制，流量控制，应答功能

IEEE 802.11是以 IEEE 802.2的逻辑链路控制来封装上层协议
当有线网络 Ethernet帧需要在Wi-Fi中传输时，首先转换为LLC帧，增加4个字段，然后再封装为IEEE 802.11MAC帧。
SNAP（Sub Network Access Protocol）：子网络访问协议
DSAP（Destination Service Access Point）：目标服务接入点
SSAP（Source Service Access Point）：源服务接入点
Control （Unnumbered information）：控制字段，控制位被设定为0x03
OUI（Organizationally Unique Identifier）：组织代码，固定为0x000000
