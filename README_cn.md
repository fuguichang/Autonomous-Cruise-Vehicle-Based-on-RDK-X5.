# 农业喷洒机器人自动导航系统

本项目基于 RDKX5 平台，集成激光雷达 SLAM、自主路径规划、YOLOv5 目标识别与状态反馈，实现农业环境中的智能化农药补给与自动喷洒任务。

## 📌 项目功能

- 使用激光雷达构建环境地图，完成 SLAM 定位
- 通过 YOLOv5 识别农药补给标识物，记录坐标点
- 建图完成后，机器人回到起点并进行路径规划
- 循环导航至各标识点并停留十秒
- 支持路径闭环控制与任务反馈

## 🛠️ 技术栈与依赖

- **平台**：RDKX5（含雷达与运动控制模块）
- **操作系统**：Linux / ROS2 (可根据项目实际配置)
- **激光雷达**：支持 SLAM 算法（如 GMapping、Cartographer）
- **目标识别**：YOLOv5（PyTorch 实现）
- **路径规划**：A* 算法
- **语言**：Python / C++ 混合编程
- **通信**：串口/Socket 与上位机进行通信
- **依赖库**：
  - `OpenCV`
  - `PyTorch`
  - `numpy`
  - `rospy` / `rclpy`
  - `serial` 

## 🚀 项目运行方式

1. **启动 SLAM 模块**
   ```bash
   roscore
   roslaunch racecar Run_gmapping.launch
   roslaunch racecar amcl_nav.launch.launch
   roslaunch racecar Run_car.launch.launch