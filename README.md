<div align="center">

# DramaMatrix ID

**Indonesian Short-Drama Clipping & Multi-Channel Publishing Assistant**
**面向印尼竖屏短剧的本地化剪辑、多渠道发布辅助与投放分析工具**

> Turn a licensed high-performing drama clip into localized variants (Indonesian hooks, subtitles, voice-over), reviewed by a human before publishing to TikTok, YouTube Shorts & Shopee Video.
> 把一条**已获授权**的高光短剧切片，本地化为多条印尼语版本（Hook、字幕、配音），经人工审核后再发布到各平台。

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](./LICENSE)
[![Python](https://img.shields.io/badge/python-3.11+-3776AB?logo=python&logoColor=white)](https://www.python.org)
[![Market](https://img.shields.io/badge/market-Indonesia-red)](#overview--项目概述)
[![Status](https://img.shields.io/badge/status-planning-lightgrey)](#project-status--当前状态)

[Overview](#overview--项目概述) · [Compliance](#compliance--合规原则) · [Architecture](#planned-architecture--规划架构) · [Features](#planned-features--规划功能) · [Quick Start](#quick-start--快速开始) · [Commercialization](#commercialization--商业化设想)

</div>

---

## Project Status / 当前状态

**规划阶段。** 仓库目前只有 `README.md`、`requirements.txt`（规划中的依赖清单）和 `LICENSE`。下文的架构、功能模块和目录结构都是**规划中**的设计，尚未实现；`core/`、`dispatch/`、`config/`、`.env.example`、`clip_engine.py` 等均未入库。

This repository is in the **planning stage**: it currently contains only this README, a planned `requirements.txt`, and the MIT `LICENSE`. Everything below describes planned design, not shipped code.

---

## Overview / 项目概述

**DramaMatrix ID** is a lightweight, cost-effective pipeline for the **Indonesian vertical-drama (竖屏短剧)** market, aimed at One-Person Companies (OPC) and small growth teams that hold distribution rights to drama content.

DramaMatrix ID 面向**中国出海 OPC（单人公司）/ 小团队**，用「参数化轻量剪辑 + 印尼语本地化 + 人工审核后发布 + 投放效果分析」的方式，降低重型 AI 生成模型的算力门槛。

---

## Compliance / 合规原则

- **只处理有授权的内容**：仅用于自有或已获得发行/二创授权的短剧素材，尊重版权方和各平台的版权规则。
- **不使用指纹浏览器、不使用代理或住宅 IP 池**，不伪装设备或地理位置，不批量注册或操纵账号。
- **不规避平台的重复内容检测**：本项目不以「绕过去重 / 判重」为目标；本地相似度检查仅用于提示内容是否有实质性差异，帮助避免重复发布。
- **遵守各平台规则**：遵守 TikTok、YouTube、Shopee 的社区准则、服务条款与 API 使用条款，优先使用官方 API / 官方发布工具。
- **发布前人工审核**：每条成片在发布前都由人工确认内容、字幕、链接与授权信息，不做无人值守的自动发布。
- **如实披露**：推广、带货与联盟链接按平台要求做广告/联盟标识。

---

## Planned Architecture / 规划架构

```text
 [Market insights]  ──▶  选题与素材授权确认
        │
        ▼
 [1. Parameterized Drama Clipper]  --> FFmpeg + 印尼语 Hook 模板
        │                              (No heavy GPU required / 零显卡负担)
        ▼
 [2. Localization]                 --> Edge-TTS 印尼语配音 + 双语字幕
        │
        ▼
 [3. Similarity check & QA]        --> pHash 相似度提示 + 人工审核队列
        │
        ▼
 [4. Publishing assistant]         --> 官方 API / 官方工具发布，人工确认后执行
        │
        ▼
 [5. Ads & ROI Analytics]          --> CTR / CVR 统计 + 投放建议
```

---

## Planned Features / 规划功能

| 模块 | 说明 | 价值 |
|------|------|------|
| 🎬 印尼本地化切片（Clipper） | 印尼语黄金 3 秒 Hook 模板、Edge-TTS 印尼语配音、自动双语字幕 | 解决不懂印尼语、文案与配音难的问题 |
| ⚡ 轻量化剪辑（Editing） | 基于 FFmpeg 的参数化剪辑、调色、字幕排版 | 不依赖昂贵大模型，几秒钟出成片 |
| 🔍 相似度提示与质检（QA） | pHash 相似度提示、画质与字幕校验、授权信息核对 | 发布前发现重复或低质内容 |
| ✅ 人工审核与发布辅助（Publishing） | 审核队列；审核通过后经官方 API / 官方工具发布 | 每条内容都经人工确认，遵守平台规则 |
| 🔗 链接与归因（Monetization） | 按平台规则添加短剧 App 落地页 / Bio 链接并标识推广 | 打通「播放 - 试看 - 充值」的效果追踪 |
| 📊 投放分析（Ads Guidance） | 统计各切片 Hook 的 CTR，生成投放建议 | 判断哪条素材值得投广告 |

---

## Quick Start / 快速开始

> 代码尚未入库，以下仅为准备环境的步骤。运行入口（如 `clip_engine.py`）和 `.env.example` 仍在规划中。

**Prerequisites**

- Python 3.11+
- FFmpeg

```bash
# Clone repository
git clone https://github.com/vfvincentwong2026/DramaMatrix-ID.git
cd DramaMatrix-ID

# Install planned dependencies
pip install -r requirements.txt
```

---

## Commercialization / 商业化设想

DramaMatrix ID 以 MIT 协议开源，也可在合规前提下作为服务落地：

- **SaaS 订阅**：为已获授权的团队提供印尼语短剧本地化剪辑与发布辅助工具（月费制）。
- **素材测试与投放咨询**：帮助团队测试高 CTR 切片，提供印尼本地 TikTok Ads 投放优化建议。
- **CPA / CPS 分成**：通过短剧 App 官方联盟/推广计划的归因链接，按约定分成，并按平台要求标识推广。

---

## Planned Project Structure / 规划目录结构

以下目录**均为规划中，尚未入库**：

```text
DramaMatrix-ID/
├── README.md
├── requirements.txt
├── LICENSE
├── config/                  # 印尼语 Hook 模板与语言包（规划中）
├── core/                    # （规划中）
│   ├── clipper.py           # FFmpeg 参数化剪辑
│   ├── similarity_check.py  # pHash 相似度提示
│   └── tts_engine.py        # 印尼语 TTS 与字幕
├── publish/                 # （规划中）
│   └── review_queue.py      # 人工审核队列与官方发布接口
└── analytics/               # （规划中）
    └── ads_advisor.py       # CTR 统计与投放建议
```

---

## License

[MIT](./LICENSE) © 2026 Vincent Wong (vfvincentwong2026)
