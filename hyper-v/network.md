
hyper-v安装虚拟机联网配置方式

两种方式都会生成虚拟网卡
一、外网方式：建立的虚拟交换机类型为外部网络
    1.生成的虚拟适配器，ip获取设置成自动获取，查看状态，确保为internet可连接
    2.虚拟机内也要使用dhcp方式
    确保这两项配置，虚拟机内就可以访问外网了。  这种方式不能指定ip，如需指定ip可使用第二方式。


二、内网桥接方式：建立的虚拟交换机类型为内部网络
    1.生成的虚拟适配器，ip获取设置成自动获取
    2.本机联网的适配器（以太网），也改成自动获取的方式
    3.ctrl选择这两个网卡，右键桥接，会生成一个新的网桥适配器，按之前以太网的静态ip配置重新配置新的网桥适配器
    4.虚拟机内使用static，指定IPADDR NETMASK GATEWAY，就可以联网了。网关和路由确保和外部一致
