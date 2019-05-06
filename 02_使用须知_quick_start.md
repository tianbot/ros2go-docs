---
title: "使用须知 Quick Start"
permalink: /quick_start/
--- 

购买之前，请务必详细阅读本节内容。运气好的话，插上ROS2GO直接开机，就可以进入Ubuntu系统了，但这毕竟只是一部分情况。即便如此，为了享受ROS2GO提供的极大便携性，最好也是仔细了解一下我们电脑的启动相关知识。

## 安全无风险的双系统
ROS2GO接入电脑后，会产生两个可以启动的设备。一个是USB外接移动硬盘（简称HDD模式） Tianbot ROS2GO 1.00，一个是USB外接光盘驱动器 Tianbot CD-ROM on Flash 1.00  （简称LiveCD模式。不必纠结哪里来的光盘驱动器，这是一个仿出来的光盘驱动器，可以当做就是多外接了一个真正的光盘驱动器）。因为是外接设备，所以不会对电脑的原有系统产生任何影响，ROS2GO的启动设置和数据存储都与原电脑没有关系。因此**希望在原电脑上安装双系统但是害怕出问题的用户，可以完全打消顾虑，在不插入ROS2GO时，原系统是不受任何影响的。**  

## 为什么要在ROS2GO中放入硬盘和光盘？有什么不一样？  
首先要说明，两种启动方式进入的系统是一样的，也就是都可以运行我们介绍的各种例程。但是光盘驱动器进入LiveCD模式，无论怎么更改，下次启动后又都恢复如初了。因为光盘是无法写入保存数据的！如果要进行开发，保存自己写的程序，所做的更改，就需要从外界硬盘启动！

## 怎样设置从硬盘启动还是光盘启动？

要能够从ROS2GO启动，必须要在启动前就将ROS2GO插入电脑的USB口。大多数不是太旧的电脑，都可以在启动时按某一个按钮选择启动项。幸运的话就可以直接选择Tianbot ROS2GO <版本号> 或者Tianbot CD-ROM onFlash <版本号>  

如果你没有这么顺利。而且你也不是很了解计算机启动的一些常识，建议首先阅读一下阮一峰的博文：  
http://www.ruanyifeng.com/blog/2013/01/secure_boot.html  
**注意理解里面几个我们要在后面提到的名词：Legacy，UEFI，Secure Boot。**  
我们简单的解释一下：  
**Legacy，看英文就知道是传统模式，现在不怎么用的。**    
**UEFI， Unified Extensible Firmware Interface， 统一的拓展固件接口。也就是现在我们常用的启动方式。一般会把启动需要的文件放在硬盘的EFI分区（你平常看不到）。**  
**Secure Boot， 微软强硬的要求使用安全启动方式，在UEFI模式下，只认windows的启动用EFI文件。很多预装Windows的机器都设置在UEFI的Secure Boot模式。**  

这样就是说，我们现在用Ubuntu 16.04，应该是在UEFI的模式下然后关闭Secure Boot，可以明白吧？  

然后明确一下：  

**我们要能够从ROS2GO HDD启动，要保证我们的BIOS设置成UEFI模式，关闭Secure Boot，外部USB硬盘为第一启动顺序。**  
如果您曾经尝试过安装Windows+Ubuntu双系统，那么很大概率您已经设置过外部设备启动并关闭了Secure Boot（安全启动模式，新一点的电脑Bios比较多已经是中文系统），很大概率您在使用ROS2GO时会一次成功。  

&#x1F538;***如果您是第一次尝试使用双系统（本质上ROS2GO还是双系统），使用ROS2GO之前，一定要先清楚您的电脑在UEFI的模式下如何从外部USB设备启动，如何关闭Secure Boot。***  

还有的情况比如Acer的Bios还要明确选择启动文件，在ROS2GO中，启动文件为/EFI/boot/bootx64.efi。有任何疑问请咨询您的电脑经销商。 我们也会维护常见的BIOS设置方式。  

**不论是UEFI还是Legacy，都可以启动LiveCD。**

还有问题的话，建议先百度，Bing，Google，尝试自己解决问题。当然，**我们的技术工程师永远是您坚实的后盾。与老司机同在！**



## 快速使用ROS TO GO：  
1、关机状态下将U盘插入电脑。  
2、进入Bios，需要打开UEFI启动方式，选择启动项为Tianbot ROS TO GO  

现代电脑最常用的进入Bios按键为：F1，F2，F12，同时还有很多使用 Del，ESC，F9，F10，可以开机时重复快速按压试验。一般都可以成功看到Bios的画面。

一些不同的按键我们记录在下，大家如果有常见的电脑但是按键与以上不同的可以给我们提交Pull Request。
|  笔记本品牌  |    按键     |
|    ---      |     ---     |
|  Thinkpad   |  Enter之后F1  |
|  Mac        |  Option      |
|  Sony Vaio  |  Assist    |

3、进入grub，选择Ubuntu
![ros2go grub](https://github.com/tianbot/ros2go/raw/master/assets/images/grub.png)  

 - 我们提供了不同的内核供大家选择
   - HWE 硬件增强版，新硬件的功能支持更好
   - LTS 长期支持版，老配置的电脑更加稳定
![ros2go kernels](https://github.com/tianbot/ros2go/raw/master/assets/images/kernels.png) 

4、现在是一个纯净的Ubuntu + ROS Kinetic，开始使用！  


## 将系统装入自己的电脑：  
1、关机状态下将U盘插入电脑。  
2、进入Bios，选择启动项为Tianbot Ubuntu Live CD  
![ros2go livecd](https://github.com/tianbot/ros2go/raw/master/assets/images/livecd.png) 
3、就可以使用Live System（无法保存更改）或者安装Tianbot Ubuntu的镜像了  

## 进入系统
不论是使用HDD还是LiveCD，看到如下画面就说明已经成功启动了！  
![ros2go desktop](https://github.com/tianbot/ros2go/raw/master/assets/images/desktop.png) 