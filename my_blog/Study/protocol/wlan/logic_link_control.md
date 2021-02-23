协议：802.2-1998.pdf



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

Control（控制）字段，8或16位比特
为了便于区分，有三种LLC PDU控制字段，分别叫做U，I，S帧。
U（Unnumbered）帧，8位的控制字段，特别用于无连接的应用
I（Information）帧，16位的控制和帧编号字段，用于面向连接的应用
S（Supervisory）帧，16位的控制字段，用于在LLC层中进行管理监督。
在这三种格式中，只有U帧在广泛使用。用第一个字节的最后两位来区分这三种PDU帧格式。
