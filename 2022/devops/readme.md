# devops

## 安装系统
在自己的机器上安装对应的虚拟机，并且安装Linux中Centos和Ubuntu，期间遇到安装Centos tab键的问题，卡了几个小时，内心还是有点不舒服，但是好在最终得到解决。

安装详细步骤和总结[link](https://github.com/zzzfwww/daydayup/tree/master/linux-os-install)

## 安装k8s
这个k8s在脑海中一直想要去完成自己的从0开始安装成功，并且能使用，在这个探索的过程中也走了不少弯路，其中就是想当然的在最新的Centos 7.9版本下去安装，然后也通过网上找到对应的安装文档教程，其中segmentfault里面民工博客写的很详细，但是在我安装k8s1.23版本中一直不成功，后面就开始B站找资料，找视频，也找了几天，并且实践，发现还是有很多坑，直到找到这个B站内容[k8s](https://www.bilibili.com/video/BV1cW4y1x7VB/?spm_id_from=333.1007.top_right_bar_window_custom_collection.content.click),这个课程就是最宝藏的，里面详细告诉你怎么去安装，并且每一步都给出具体的内容，然后前面也踩坑了一段路，这就直接能让我安装起来

安装笔记：[note](https://github.com/zzzfwww/daydayup/tree/master/environment-configuration/k8s)

## 其他内容
在确定安装成功k8s之后，就需要去踩一遍其它服务的坑，安装整套CI/CD需要的工具链

gitlab+jenkins+docker+k8s+harbor+sonarqube

这里的安装和使用教程我也自己总结了一份，虽然也是和上面说的B站里面差不多，至少按照这个逻辑跑通[link](https://github.com/zzzfwww/daydayup/tree/master/environment-configuration/devops)

## 明年规划
1. 继续在这个devops上深入
2. 在工作中也能在这种技术领域深入