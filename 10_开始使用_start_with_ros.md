---
title: "开始使用 Start with ROS"
permalink: /start_with_ros/
---

如果大家完成了之前的任务，成功从UEFI的外接硬盘启动，HWE或者LTS内核没问题能够进入，能够成功的进入桌面，并且网卡可以驱动，
那么恭喜现在我们可以开始高兴的玩耍ROS了。  

注意这里并不是一个完整的ROS教程。你可以进入10G的只读盘，里面有很多我们准备好的ROS资料。

当然，这里最推荐的还是参加关注各位老师的书籍以及视频。初学的话，可以看看睿慕课田老师的《给傻瓜的ROS入门课程》。有一些基础的话，可以看古月君的《ROS机器人开发实践》。

首先打开终端。 Ctrl + Alt + t, 输入

``` bash
roscore
```

启动成功的话，再打开一个终端（Ctrl + Alt + t）或者终端标签页（Ctrl + Shift + t）

```
rosrun turtlesim turtlesim_node
```

就可以看到熟悉的小海龟了！ 还可以再打开一个新的终端输入

```
rosrun turtlesim turtle_teleop_key
```
记得保持这个键盘控制的终端在最上方聚焦的状态，就可以控制小海龟运动啦！

一般我们做完一个Demo，最好是把所有的终端全部关闭再开始下一个，保持这个习惯会减少一些不必要的疑惑。

我们再来试一试turtlebot的导航仿真。新开终端并输入

```
roslaunch turtlebot_stage turtlebot_in_stage.launch
```
稍等片刻就会在顶端出现一个配置很完善的RViz界面，可以用2D Nav Goal按钮来给turtlebot设置目标地点。左键单击按下去设定位置，不要松开，转动设定方向，然后松开左键。
我们就能看到Turtlebot在迷宫中自主导航了！

关于Gazebo中PR2和UR5的Demo，大家可以参考下古月君的博客。这两个Demo我们已经帮大家安装好了的， 忽略安装的部分。
这里是传送门。

[ROS探索总结（四十八）——ROS机器人实例 （PR2）](http://www.guyuehome.com/1753)  

```
roslaunch pr2_gazebo pr2_empty_world.launch
roslaunch pr2_teleop teleop_keyboard.launch
```
[ROS探索总结（五十）——ROS机器人实例 （Universal Robots）](http://www.guyuehome.com/1834)

```
roslaunch ur_gazebo ur5.launch
roslaunch ur5_moveit_config ur5_moveit_planning_execution.launchsim:=true
roslaunch ur5_moveit_config moveit_rviz.launch config:=true
```
基本的ROS测试就是这样了，祝大家使用愉快～

