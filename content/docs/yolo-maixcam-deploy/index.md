---
title: "YOLO 训练到 MaixCam 部署全流程"
description: "从数据集准备、训练、剪枝量化到 MaixCam 端侧部署的完整链路记录"
date: 2026-10-23
tags: ["YOLO", "模型部署", "MaixCam"]
categories: ["端侧部署"]
---

> 本文为示例文档，展示文章的编写格式。替换为你的真实内容即可。

## 1. 数据集准备

使用 Ultralytics 标准目录结构，注意以下约束：

- 单进程 DataLoader，避免 Windows 平台死锁
- 数据增强只做亮度/光照/饱和度类光学变换，避免破坏颜色特征

## 2. 训练

```bash
yolo detect train data=dataset.yaml epochs=200 imgsz=640
```

训练完成后检查中间保存的权重，对比最新一轮的 mAP。

## 3. 剪枝与量化

对检测模型做通道剪枝降低参数量，再进行量化，在精度与端侧推理速度之间取平衡。

## 4. MaixCam 端侧部署

通过 MaixHub 完成模型量化与转换，使用 MaixPy 在 MaixCam 上加载模型、调用摄像头推理，C/C++ 完成后处理加速。

## 相关阅读

- [教学视频：同主题视频教程](/videos/)
