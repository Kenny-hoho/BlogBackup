---
title: 百人计划-动画TA-动作理论基础
date: 2023-03-29
index_img: "/img/bg/West2.jpg"
tags: [百人计划]
categories: 
   -[动画TA]
---

[百人计划-动画TA-动作理论基础](https://www.bilibili.com/video/BV1Bh411t7AF?p=2&vd_source=93b215eab72b2548f75d0772e28f8b20)
<!-- more -->

# 动画基础知识

## 什么是运动

运动（translation）包括平移（position），旋转（rotation）和缩放（scale）（缩放一般用于夸张的卡通动画效果）。计算机角色动画的基础是骨骼动画，骨骼动画就是用某种方式驱动顶点的移动。

![](/article_img/2023-03-29-13-40-25.png)

## 蒙皮（Skining）

蒙皮字面意思理解就是给骨骼蒙上一层皮肤，蒙皮系统以某种方式驱动哪些顶点去到哪里。

![](/article_img/2023-03-29-13-43-09.png)

常见的蒙皮算法：
1. **LBS(Linear Blending Skining)线性混合蒙皮**，大步幅蒙皮都是这种方式，但是会有挤压重叠（可以添加辅助骨骼保持关节形状）
2. **DQS(Dual Quaternion Skining)双四元数蒙皮**，游戏引擎不支持，如DAZ的模型
3. **JCM(Joint Controlled Morphs)骨骼驱动变形**，等于PSD（Pose space deformations），用骨骼驱动morphs变形，如Metahuman
4. **RBF(Radial Basis Function)辅助骨骼驱动**，除了关节还可以做一些肌肉的驱动
5. **RTSS(Real-time Skeletal Skining)基于优化旋转中心的实时骨骼蒙皮**，比较新的概念

## 动画类型

1. **逐帧动画**：sprite（精灵）动画
2. **骨骼动画**：3D动画，spine动画（2D骨骼）
3. **顶点动画**：物理模拟后的动画数据，用于不便于用骨骼驱动的布料，流体和破碎等等；
   VAT(vertex animation texture)将每帧顶点数据记录到贴图上，贴图尺寸：帧数*顶点数
   shader顶点动画，在vertex shader中控制顶点按照一定规律和公式做偏移动画，常用于草地摆动，海浪等
   离线定点动画，离线渲染完成后导出abc文件到引擎

## FK和IK

正向运动学和反向运动学，在DCC中的绑定用到了IK，在引擎中可以实时计算IK实现脚部对地面倾斜度的适配，牵手适配不同身高

# 动画质量和流畅度

好的动画符合运动规律，运动轨迹是弧线

## 如何营造打击感

首先打击感是结合视觉、听觉、特效等方面的综合表现营造的

1. **合理的打击反馈**，被大机房在受到攻击时一般会做出相应的受击反馈
2. **打击抽帧和顿帧**
   击打后停顿的是抽帧，击打后震动的是顿帧
   攻击的前摇后摇
3. **攻击节奏和按键反馈**
4. **硬直和打断**

## 夸张的魅力

1. **挤压和拉伸**
   挤压程度最大，表现出物体越Q弹；3D中起跳的先下蹲再伸展也是挤压和拉伸
2. **拖尾和变形**
   二次元中是视觉残留，3D中就是运动模糊
3. **不正确的透视**
4. **时间操控**

# 动画表现提升点

## 表情

1. 写实：基本是动捕
2. 美式卡通：挤压拉伸
3. 日式卡通：保证五官形状

## 交互体验

## 动作状态融合

[ALS](https://www.unrealengine.com/marketplace/zh-CN/product/advanced-locomotion-system-v1)

![](/article_img/2023-03-29-14-23-17.png)

# 参考资料（下饭）

[动画十二法则](https://www.bilibili.com/video/BV1Qt411v7ih/?spm_id_from=333.337.search-card.all.click&vd_source=93b215eab72b2548f75d0772e28f8b20)
[动画师生存手册](https://www.bilibili.com/video/BV1Mt4y1X7oB/?spm_id_from=333.337.search-card.all.click&vd_source=93b215eab72b2548f75d0772e28f8b20)