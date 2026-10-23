---
title: "YOLOv8 训练到 K230 部署全流程"
description: "从数据集准备、训练、剪枝到 nncase 量化转换的完整链路记录"
date: 2026-10-23
tags: ["YOLOv8", "模型部署", "nncase", "K230"]
categories: ["端侧部署"]
---

> 本文为示例文档，展示文章的编写格式。替换为你的真实内容即可。

## 1. 数据集准备

使用 Ultralytics 标准目录结构，注意以下约束：

- 单进程 DataLoader，避免 Windows 平台死锁
- 数据增强只做亮度/光照/饱和度类光学变换，避免破坏颜色特征

## 2. 训练

```bash
yolo detect train model=yolov8n.pt data=dataset.yaml epochs=200 imgsz=640
```

训练完成后检查中间保存的权重，对比最新一轮的 mAP。

## 3. 剪枝与导出

```bash
yolo export model=best.pt format=onnx opset=12
```

## 4. nncase 量化转换

使用 nncase 2.9.0 进行 16 位定点量化，适配 K230 KPU。

## 相关阅读

- [教学视频：同主题视频教程](/videos/)
