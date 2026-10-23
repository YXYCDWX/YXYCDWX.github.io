---
title: "MaixCam 颜色目标检测系统"
description: "端侧实时目标检测：YOLO 剪枝量化 + MaixCam 部署 + OpenCV 颜色后处理"
tags: ["YOLO", "MaixCam", "端侧部署"]
categories: ["项目"]
links:
  - name: "GitHub 仓库"
    url: "https://github.com/YXYCDWX"
---

> 示例成果页，替换为你的真实项目。

## 概述

在 MaixCam 端侧设备上实现实时的颜色目标检测与跟踪：

- YOLO 模型剪枝 + 量化，经 MaixHub 工具链转换后在 MaixCam 上推理
- OpenCV 颜色后处理辅助校验检测结果
- 面板可实时调参：Conf、Win、IoU、Age、MOE

## 技术要点

| 模块 | 方案 |
|------|------|
| 检测 | YOLO（剪枝） |
| 部署 | MaixHub 量化转换，MaixPy 推理 |
| 后处理 | C/C++ 加速 + OpenCV 颜色过滤 |
