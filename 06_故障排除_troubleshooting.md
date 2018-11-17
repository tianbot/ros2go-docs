# 常见的故障排除 Trouble Shooting

首先要和各位ROS2GO的用户们说一下，非常感谢大家的支持!  
相信大家都了解到了，Ubuntu和ROS都是开源而且免费的。 整个社区的发展离不开每一个人的力量。
ROS2GO只是一个承载了开源免费软件的平台，我们会尽量把ROS2GO做完善，也会把大家使用中的常见问题维护在这里。我们并不能保证为大家解决每一个使用Ubuntu或者ROS中的问题，我们希望大家可以在各个社群里寻求答案，也贡献自己的力量帮助后来者，寻求大家的共同进步。

- 启动问题（从开机一直到进入桌面这个过程） About booting
  - 为什么一开机我的系统还是直接进入Windows？ 
    检查一下您的ROS2GO是否在开机前插入了电脑，是否插好。检查一下您的Bios设置是不是设置为UEFI模式，有没有关闭Secure Boot，有没有设置USB设备为最先启动顺序。
    您可以尝试在Windows中插入ROS2GO，看一看设备是否正确识别。在重启前一直按住shift键，这样选择重启后，系统会提示是否使用外置设备修复。可以在这时看看能否选择Tianbot ROS2GO HDD作为启动设备。
    
  - 为什么进入grub菜单后，我点击Ubuntu无法进入桌面？

- Ubuntu使用问题 askubuntu.com
  - 进入Ubuntu后无法访问原来的Windows下的硬盘？ Error mounting /dev/sda? at /media/tianbot/???  
  这时一个使用双系统时常见的问题，最常见的原因是没有关闭Windows的快速启动，这样Windows并不是完全正常的关闭。请参考：
  https://askubuntu.com/questions/145902/unable-to-mount-windows-ntfs-filesystem-due-to-hibernation
  如果您需要了解详情，参考第一条答案。如果需要修复方法，参考第二条答案。  
  修复的常用做法是，如果报错 Error mounting /dev/sda2  
  那么就使用  
  ```
  sudo ntfsfix /dev/sda2  
  ```
  来修复。


- ROS使用问题 answers.ros.org
