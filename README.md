# Health assistant: Eating, Sleep, and Exercise Tracking / 健康助理：饮食、睡眠与运动数据追踪评估

## Overview / 概述

**Health Copilot** is a comprehensive health-management skill that bridges the gap between raw data recognition and long-term reporting. It combines advanced analysis of meals, sleep, and exercise with automated Feishu (Lark) persistence and derived health assessments.

**Health Copilot（健康助理）** 是一个面向个人健康追踪场景的可复用分析型 skill
- 帮助记录每餐摄入、睡眠质量以及运动锻炼恢复情况，并提供参考建议
- 支持拍照识别每餐的热量以及主要营养成分
- 支持通过截图识别Apple健康以及主流Android智能手表的睡眠和运动数据
- 每天晚上会提供每天营养摄入评估提醒
- 每周日会提结合营养摄入以及睡眠、运动数据情况提供每周健康综合评估报告
- 识别的数据支持自动创建/记录到飞书表格中，并提供种图表视图
<img width="2808" height="1746" alt="image" src="https://github.com/user-attachments/assets/04027191-19fe-4d8e-bac0-cad8018ed259" />
<img width="2804" height="1666" alt="image" src="https://github.com/user-attachments/assets/fee00fa7-ac98-4340-ba4b-8f3bfad59213" />
<img width="2796" height="1648" alt="image" src="https://github.com/user-attachments/assets/8e6a9813-a540-4181-ba08-ef8af7a40116" />
<img width="2788" height="1744" alt="image" src="https://github.com/user-attachments/assets/318b69c5-6bfc-49d0-8859-da833bad5183" />
<img width="2760" height="1754" alt="image" src="https://github.com/user-attachments/assets/b72ef9a0-01e9-4392-be01-b043cea5afa2" />



---

## Key capabilities / 关键能力

### 1. Recognition & Analysis / 识别与分析
- **Nutrition**: Photo-based calorie and macro estimation from meals.
- **Sleep**: Screenshot-based extraction of sleep stages and recovery signals (Apple Health, Android).
- **Exercise**: Extraction of workout metrics and training load from app screenshots (Garmin, Strava, etc.).
- **Weekly Reassessment**: Cross-domain interpretation of nutrition, sleep, and exercise signals.

### 2. Persistence & Automation / 持久化与自动化
- **Automated Bootstrapping**: Create all required Bitable tables, fields, and views from a config file.
- **Daily Rollups**: Automated aggregation of raw logs into a `Monthly Health Calendar`.
- **Weekly Assessments**: Automated generation of comprehensive weekly reports with risk scoring.
- **Dashboards**: Automated creation/refresh of monthly health overview dashboards with trends.

### 3. Architecture / 架构特性
- **English-Only Core**: Reliable internal schema using English field names for stable reporting scripts.
- **Bilingual documentation**: Full EN/ZH documentation for human users.
- **Config-Driven**: Customize any threshold, label, or wording without touching code.

---

## What it does / 主要功能

This skill handles four primary domains / 这个 skill 涵盖四大领域：

1.  **Nutrition / 营养**
    - Analyze photos -> Estimate nutrients -> Log to Feishu.
    - 拍照分析 -> 营养估算 -> 飞书落库。
2.  **Exercise / 运动**
    - Analyze screenshots -> Extract metrics -> Assess load -> Log to Feishu.
    - 截图分析 -> 指标提取 -> 负荷评估 -> 飞书落库。
3.  **Sleep / 睡眠**
    - Analyze screenshots -> Extract recovery/HRV -> Log to Feishu.
    - 截图分析 -> 恢复/HRV 提取 -> 飞书落库。
4.  **Cross-domain reporting / 跨域报表**
    - Rebuild monthly calendar -> Rebuild weekly assessment -> Refresh dashboard.
    - 重建月度日历 -> 重建周度评估 -> 刷新看板。

---

## Quick start / 快速开始

1.  **Install**: `clawdhub install personal-health-router`
2.  **Configure**: Create `config.json` based on `references/config-template.md`.
3.  **Bootstrap**: `node scripts/bootstrap_health_tables.js config.json`
4.  **Track**: Use the router to recognize food, sleep, or workouts.
5.  **Report**: Run the Python/Node scripts in `scripts/` to generate summaries and dashboards.

---

## Version note / 版本说明

**v1.0.0**: Major update consolidating the analysis router with the Feishu persistence engine. This version introduces an English-only internal table schema for enhanced reliability of reporting scripts.

**v1.0.0**: 重大更新，将分析路由与飞书持久化引擎深度融合。此版本引入了纯英文内部表结构，以提升自动化报表脚本的稳定性。

---

## Installation / 安装

```bash
clawdhub install personal-health-router
```

Update to the latest version / 更新到最新版本：

```bash
clawdhub update personal-health-router
```
