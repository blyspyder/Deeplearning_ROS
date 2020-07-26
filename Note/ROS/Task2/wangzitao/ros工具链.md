# catkin_make:构建
# `rospack`:软件包管理

## 软件包结构
    <package_name>
        CmakeLists.txt
        package.xml
[package.xml规范](http://wiki.ros.org/catkin/package.xml)
## 创建软件包
    catkin_create_pkg <package_name> [depends]...
## 查询依赖
    rospack depends <package_name>
![avator](ros工具链/rospack%20depends.png)
# `rosnode`:节点管理
## 显示全部节点
    rosnode list 
![avator](ros工具链/rosnode%20list.png)
## 显示节点信息
    rosnode info <node>
![avator](ros工具链/rosnode%20info.png)
## 启动节点
    rosrun <package_name> <node_name>
## ping节点
    rosnode ping <node>
![avator](ros工具链/rosnode%20ping.png)
# `rostopic`:话题管理
[wiki](http://wiki.ros.org/cn/ROS/Tutorials/UnderstandingTopics#ROS_Messages)
## `rqt_graph`:图形工具
    rosrun rqt_graph rqt_graph
![avator](ros工具链/rqt_grapg.png)
## `rostopic echo`:监听话题
    rostopic echo <topic>
![avator](ros工具链/rostopic%20echo.png)
## `rostopic list`:显示所有话题
    rostopic list -v
![avator](ros工具链/rostopic%20list.png)
## `rostopic type`:查看话题类型
    rostopic type <topic>
![avator](ros工具链/rostopic%20type.png)
## `rosmsg show`:查看类型组成
    rosmsg show <type>
![avator](ros工具链/rosmsg%20show.png)
## `rostopic pub`:发布消息
    rostopic pub [参数] <topic> <type> <data>
![avator](ros工具链/rostopic%20pub.png)
![avator](ros工具链/rostopic%20pub%20turtle.png)
## `rostopic hz`:查看发布频率
    rostopic hz <topic>
![avator](ros工具链/rostopic%20hz.png)
## `rqt_plot`:实时监控数据
    rosrun rqt_plot rqt_plot
# `rosservice`:服务管理
## `rosservice list`:列出服务
    rosservice list
![avator](ros工具链/rosservice%20list.png)
## `rosservice type`:显示类型
    rosservice type clear
![avator](ros工具链/rosservice%20type.png)
## `rosservice call`:调用
    rosservice call <service>
## `rossr show`:查看服务详细类型
    rosservice type <serice> | rossrv show
![avator](ros工具链/rosservice%20type|rossr%20type.png)
# 参数管理
##　`rosparam list`：查看全部
    rosparam list
![avator](ros工具链/rosparam%20list.png)
## `rosparam set`：设置
    rosparam set ＜param＞
## `rosparam get`：获取
    rosparam get ＜param＞
![avator](ros工具链/rosparam%20get.png)
## `rosparam dump`：保存
    rosparam dump <file>
## `rosparam load`:加载
    rosparam load <file> <param>
# 日志管理
## 日志级别管理
    rosrun rqt_logger_level rqt_logger_level
![avator](ros工具链/rqt_logger_level.png)
## 查看日志
    rosrun rqt_console rqt_console
![avator](ros工具链/rqt_console.png)
# `rosdep`:依赖管理 
## 安装软件包
    rosdep install [package]
# `rosbag`:话题录制回放
##　`rosbag info`:获取录制文件信息
    rosbag info　<file>
##　`rosbag play`:回放
    rosbag play <file>
## `rosbag record -a`:录制全部
    rosbag record -a
## 录制
    rosbag record -O <file> <topic>...