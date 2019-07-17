---
title: "已知问题 Known Issues"
permalink: /known_issues/
---

## ROS2GO官方不提供安装到本地PC的服务与支持
- ROS2GO设计的初衷就是非常安全的在本地PC上快速进入带有ROS的Ubuntu系统，具有快捷启动、便捷移动、安全方便的特点。在本机安装ROS2GO的系统，理论上是完全可行的，但是可能会出现功能异常。
- 如果有时间可以自己折腾，可以参考csdn用户“静精进境”的文章[ROS2GO 与WIN10 双系统安装](https://blog.csdn.net/fzx1443678836/article/details/88718959)，但是同样不做任何保障，对本机进行任何操作之前请备份重要数据。  

## :heavy_exclamation_mark: 不要安装RealVNC Viewer，会出现兼容性问题  
- 很多初学者在操作实际机器人时，希望可以用远程桌面进行操作。这并不需要给ROS2GO上安装RealVNC， 可以使用系统内的Remmina Remote Desktop Client， 选择VNC的模式连接即可。已经有安装VNC导致无法进入桌面或者显示问题的案例，请不要在ROS2GO上安装VNC。

## ROS2GO的一些已知兼容性问题（注意此处大多数都是因为您的电脑与Ubuntu的兼容问题。如果您还没有选购电脑，应该尽量排除以下型号）

- 在某些型号的电脑上不能正常关机。暂时未充分测试，现象各异，但是强关对您的电脑并无损伤。

惠普暗影精灵三代15.6寸Pro i5 1050Ti 128G+1T  （17寸的暗影精灵没有问题）  

联想小新 锐7000 可以查阅 [小新锐7000安装Ubuntu系统一直异常？](https://www.zhihu.com/question/295711588)    
联想 拯救者  Y7000  

## 网卡驱动篇(主要是一些过新或奇葩的无线网卡)

- 华为 MateBook 13寸(Intel Wireless-AC 9260)

这款无线网卡的情况: 能驱动, 但网络很卡, 容易掉线, 完全不如Windows系统下的表现, 现在附上解决方案如下: 

> 本方案出处: [PSA for owners of Intel Wireless-AC 9260
](https://www.reddit.com/r/Ubuntu/comments/a61qq1/psa_for_owners_of_intel_wirelessac_9260/)

1. 先确认你是不是这块卡, 命令如下:

```shell
lspci -v | grep Network
# 输出如下的话可以确认
00:14.3 Network controller: Intel Corporation Device 9df0 (rev 30)
```

2. 接下来你需要做的就是`升级内核`, 没错, 新的内核改善了这款网卡在 Linux 下的性能表现, 起码不会时断时续了

```shell
sudo apt-add-repository -y ppa:teejee2008/ppa
sudo apt update
sudo apt install ukuu  # 这是一个比较好用的gui应用, 可以帮助你升级当前系统的内核
```

3. 可选的额外操作

介于`ipv6`现在还没什么卵用的情况下, 你可以选择禁掉这货来获得可能的网络性能提升, via: [how-to-disable-ipv6-in-ubuntu](https://www.neuraldump.net/2016/11/how-to-disable-ipv6-in-ubuntu-16-04-xenial-xerus/#comment-22453)

```shell
# create the long-life config file
echo "net.ipv6.conf.all.disable_ipv6 = 1
net.ipv6.conf.default.disable_ipv6 = 1
net.ipv6.conf.lo.disable_ipv6 = 1" | sudo tee /etc/sysctl.d/99-my-disable-ipv6.conf

# ask the system to use it
sudo service procps reload

# check the result, if it says 1, it worked
cat /proc/sys/net/ipv6/conf/all/disable_ipv6
```
