# Paper Reading | Towards Autonomous Parking using Vision-only Sensors (2021, IROS)

> Y. Yang et al., "[Towards Autonomous Parking using Vision-only Sensors](https://ieeexplore.ieee.org/document/9636106)," 2021 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS), Prague, Czech Republic, 2021, pp. 2038-2044, doi: 10.1109/IROS51168.2021.9636106.
>
> 作者： [Yi Yang](https://ieeexplore.ieee.org/author/37899921700) , [https://ieeexplore.ieee.org/author/3789992170](https://ieeexplore.ieee.org/author/37899921700)
>
> 北京理工大学：[https://bit.edu.cn/](https://bit.edu.cn/)

## 0. 摘要

* 本文提出了一种**仅通过视觉传感器**实现了自主停车的方法；
* 通过适当的**深度估计算法**实现了对停车环境的精确感知（包括像素级深度估计和构建稠密点云）；
* 通过**改进的Radon变换方法**实现了更好的停车位检测效果；
* 效果：在中等计算平台上实现了5Hz以上的处理速度。

## 1. 简介

* 现有的自动泊车系统方案大多依赖**特殊标志**\[1]、**预先构建的地图**\[2]或**精确的测距传感器**\[3]\[4]来实现对停车环境的感知，而本方案在没有先验地图的条件下只依靠视觉传感器实现；
* 本研究按以下步骤实现这一功能：
  1. 获得图像的尺度信息。通过车身的四个鱼眼相机，并采用**基于机器学习的单目深度预测算法**获得像素级的图像深度信息，可以达到类似LiDAR的感知效果；
  2. 优化方案的实时性。对生成的点云地图进行采样。
  3. 获得更好的停车位检测效果。对鱼眼相机采集的图像进行**去畸变**和**逆透视**，变换为二维地平面，再使用基于**Radon变换**的方法检测停车位。
  4. 提出一种自主停车框架用来描述泊车任务，可分为三部分：度量空间、语义空间和行为空间。          度量空间包括环境的几何信息、车辆和相机的位姿描述；                                                                 语义空间包括提取的高级环境信息；                                                                                                  行为空间包括车辆的规划和控制信息。                                              &#x20;
* <mark style="color:red;">**本文贡献**</mark>：
  * 将基于深度学习的单目深度预测方法应用到低成本鱼眼相机中，实现了类似于LiDAR的测距和传感效果。
  * 提出了一种基于Radon变换的停车位检测方法，更好地从鱼眼摄像机中检测停车位。

## 2. 相关研究

* 特殊标志：\[1] 通过基准标签实现定位，包括二维码和停车位ID。
* 预建地图：\[2] 使用主动学习来检测停车位，从而预先构建停车位的语义图，用于定位。
* 高精度激光雷达：                                                                                                                                     \[3] 通过从LiDAR点云中提取感兴趣区域来完成检测和定位的任务。                                                    \[4] 利用LiDAR检测周围障碍物，提出了一种基于车辆通信的协同导航方法

### 2.1 自动停车系统的两个关键方面：

#### 2.1.1 识别环境中的可通行区域 ：

#### 2.1.2 停车位检测：



## R. 参考文献

* [ ] \[1] Y. Huang, J. Zhao, X. He, S. Zhang and T. Feng, "[Vision-based Semantic Mapping and Localization for Autonomous Indoor Parking](https://ieeexplore.ieee.org/document/8500516)," 2018 IEEE Intelligent Vehicles Symposium (IV), Changshu, China, 2018, pp. 636-641, doi: 10.1109/IVS.2018.8500516.
* [ ] \[2] H. Grimmett et al., "[Integrating metric and semantic maps for vision-only automated parking](https://ieeexplore.ieee.org/abstract/document/7139484)," 2015 IEEE International Conference on Robotics and Automation (ICRA), Seattle, WA, USA, 2015, pp. 2159-2166, doi: 10.1109/ICRA.2015.7139484.
* [ ] \[3] Lee, B., Wei, Y., and Guo, I. Y.: [AUTOMATIC PARKING OF SELF-DRIVING CAR BASED ON LIDAR](https://isprs-archives.copernicus.org/articles/XLII-2-W7/241/2017/isprs-archives-XLII-2-W7-241-2017.pdf), Int. Arch. Photogramm. Remote Sens. Spatial Inf. Sci., XLII-2/W7, 241–246, https://doi.org/10.5194/isprs-archives-XLII-2-W7-241-2017, 2017.
* [ ] \[4] B. Li, L. Yang, J. Xiao, R. Valde, M. Wrenn and J. Leflar, "[Collaborative Mapping and Autonomous Parking for Multi-Story Parking Garage](https://ieeexplore.ieee.org/document/8307497)," in IEEE Transactions on Intelligent Transportation Systems, vol. 19, no. 5, pp. 1629-1639, May 2018, doi: 10.1109/TITS.2018.2791430.
