---
title: "K230 颜色目标检测系统"
description: "端侧实时目标检测：YOLOv8 剪枝量化 + K230 KPU 部署 + OpenCV 颜色后处理"
tags: ["YOLOv8", "K230", "端侧部署"]
categories: ["项目"]
links:
  - name: "GitHub 仓库"
    url: "https://github.com/YXYCDWX"
---

> 示例成果页，替换为你的真实项目。

## 概述

在 K230 端侧设备上实现实时的颜色目标检测与跟踪：

- YOLOv8n 剪枝 + 16 位定点量化，kmodel 部署于 KPU
- OpenCV 颜色后处理辅助校验检测结果
- 面板可实时调参：Conf、Win、IoU、Age、MOE

## 技术要点

| 模块 | 方案 |
|------|------|
| 检测 | YOLOv8n（剪枝） |
| 量化 | nncase 2.9.0，16 位定点 |
| 后处理 | C/C++ K230 后处理 + OpenCV 颜色过滤 |
