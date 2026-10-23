# DramaMatrix-ID
Indonesian Short-Drama Matrix Engine &amp; Automatic Distribution Platform（印尼竖屏短剧矩阵与自动分发引擎）。
<div align="center">

# DramaMatrix ID

**Indonesian Short-Drama Matrix Engine & Automated Distribution Platform**  
**专为印尼短剧出海打造的自动化混剪、矩阵分发与投流指导平台**

> Turn 1 high-performing drama clip into 50 unique, policy-safe variants and auto-distribute to TikTok, YouTube Shorts & Shopee Video 24/7.  
> 让一条高光短剧切片，安全裂变为五十条爆款变体，24小时无人值守分发至印尼全平台。

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](./LICENSE)
[![Python](https://img.shields.io/badge/python-3.11+-3776AB?logo=python&logoColor=white)](https://www.python.org)
[![Node](https://img.shields.io/badge/node-20+-339933?logo=node.js&logoColor=white)](https://nodejs.org)
[![Market](https://img.shields.io/badge/market-Indonesia-red)]()

[Overview](#overview) · [Core Architecture](#core-architecture) · [Features](#features) · [Quick Start](#quick-start) · [OPC Commercialization](#opc-commercialization)

</div>

---

## Overview / 项目概述

**DramaMatrix ID** is a lightweight, cost-effective automation pipeline engineered specifically for the **Indonesian vertical-drama (竖屏短剧)** market. Built for One-Person Companies (OPC) and small growth teams, it bridges the gap between raw drama assets and automated monetization.

克服重型 AI 生成模型的昂贵算力门槛，DramaMatrix ID 专为**中国出海 OPC (单人公司) / 小团队**设计，采用“参数化轻量混剪 + 静态住宅 IP 防风控 + 24小时矩阵分发 + 投流 ROI 归因”的全链路方案。

---

## Core Architecture / 核心架构

```text
 [DramaPulse ID] ➔ (Market Insights & Complaints)
        │
        ▼
 [1. Parameterized Drama Clipper]  --> FFmpeg + Localized Hook Templates
        │                              (No heavy GPU required / 零显卡负担)
        ▼
 [2. Lightweight Dedup Guard]     --> Visual pHash + Audio Pitch Shift + Subtitles
        │                              (Passes TikTok/Shopee deduplication)
        ▼
 [3. Anti-Detect Dispatcher]      --> Playwright + Static Residential IPs
        │                              (24/7 Automated posting + Deeplink insertion)
        ▼
 [4. Ads & ROI Analytics]          --> CTR/CVR Tracking + TikTok Ads Target Guidance
Features / 核心功能模块功能说明给 OPC / 团队带来的价值🎬 印尼本地化切片 (Clipper)内置印尼语黄金 3 秒 Hook 模板、Edge-TTS 印尼配音、自动双语字幕解决不懂印尼语、懂文案配音难的问题⚡ 轻量化混剪去重 (Dedup)基于 FFmpeg 速度重映射、画面微调、pHash 检测、调色去重替代昂贵大模型，几秒钟出成片，100% 避开平台限流🛡️ 矩阵防风控分发 (Dispatcher)集成指纹浏览器 + 印尼静态住宅 IP + Playwright 模拟人类发布解决国内发布 0 播放、频繁封号问题🔗 自动引流挂链 (Monetization)视频发布时自动挂载短剧 App Deeplink、Bio 落地页链接实现“播放 - 试看 - 充值”全自动闭环📊 投流指导与归因 (Ads Guidance)实时监控各切片 Hook CTR，自动生成 TikTok Ads 受众包配置明确告诉 OPC 哪条素材值得烧广告费Quick Start / 快速开始PrerequisitesPython 3.11+Node.js 18+FFmpeg installedIndonesian Static Residential IP Proxy (SOCKS5/HTTP)Bash# Clone repository
git clone [https://github.com/your-username/DramaMatrix-ID.git](https://github.com/your-username/DramaMatrix-ID.git)
cd DramaMatrix-ID

# Install dependencies
pip install -r requirements.txt
npm install

# Configure environment
cp .env.example .env
# Fill in your Indonesian Proxies and Drama Deeplink tracking parameters

# Run lightweight clipper & auto-dispatcher
python clip_engine.py --input raw_drama.mp4 --variants 30
python dispatcher.py --platform tiktok --schedule auto
OPC Commercialization / OPC 商业化变现DramaMatrix ID 不仅是一个开源工具，更可作为 SaaS 或代运营服务商业化落地：SaaS 订阅服务：提供印尼短剧自动化混剪与矩阵发布工具包（月费制）。素材测爆与代投：帮 OPC 团队测试高 CTR 切片，提供印尼本地 TikTok Ads 投流优化指导。CPA / CPS 分成：绑定短剧 App 充值归因链接，按导流充值金额抽取佣金。Project Structure / 目录结构PlaintextDramaMatrix-ID/
├── README.md
├── requirements.txt
├── config/                  # 印尼 Hook 模板与语言包
├── core/
│   ├── clipper.py           # FFmpeg 参数化切片引擎
│   ├── dedup_guard.py       # pHash 与音频去重校验
│   └── tts_engine.py        # 印尼语 TTS & 字幕挂载
├── dispatch/
│   ├── browser_pool.py      # 指纹浏览器与代理池管理
│   └── platform_tiktok.py   # TikTok / YouTube Shorts 自动发布脚本
└── analytics/
    └── ads_advisor.py       # CTR 监控与投流建议生成
LicenseMIT
