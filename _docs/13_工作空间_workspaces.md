# 工作空间设置
如果打开.bashrc查看，会看到在文件的末尾，我们用source和--extend，包含了很多工作空间。

```
source /opt/ros/kinetic/setup.bash
source ~/catkin_ws/devel/setup.bash --extend
source ~/tianbot_ws/devel/setup.bash --extend
source ~/study_ws/devel/setup.bash --extend
source ~/cartographer_ws/install_isolated/setup.bash --extend
```

在ROS2GO中， catkin_ws中并没有放置内容，是留给大家自己放入自己的代码的。  
tianbot_ws中，是放置天之博特的机器人代码。暂时只有racecar的功能包。逐步会开源我们所有的代码。
study_ws中，就是给大家放置的大量的学习用的源码。包括官网最火的ros_tutorials，古月老师的marm和mrobot，小课堂的stdr_tutorials和ros_voice， 还有慕课ros课程的源码。
cartographer_ws中放入的则是cartographer的源码。

# 工作空间开关
 
大家可能觉得在.bashrc中，这种工作空间的设置的方式和许多人的设置方式都不太一样。但是这是田老师在工作研发以及教学中，总结出的比较好的工作空间设置方式。  

如此设置工作空间的好处，就是我们可以随意的开关各个工作空间。比如你正在看古月老师的书，想完整的从编译开始做一遍，那么可以先关闭study_ws，方法就是将这一行注释掉。你可以使用catkin_ws来下载古月老师的代码，在这个工作空间中进行学习。  
同样的道理，如果你暂时没有使用天之博特的任何产品，也可以先把tianbot_ws关闭。  
你可以通过注释或去除注释，轻松的打开或者关闭一个工作空间。  

关于如何能够这样去建立工作空间，请先仔细看睿慕课的ROS入门课程第三讲《试着在ROS中自由翱翔放飞自我》中的1-2小节， “解答工作空间的相关问题，比如source等”。

在你还不足够了解工作空间的原理，还经常被source问题困扰的时候，暂时不要尝试去改动.bashrc中关于工作空间的设置。尝试改动时，也记得先要备份。
