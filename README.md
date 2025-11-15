# Sora Watermark Cleaner (SoraWm)

**⚡️ 一键移除 OpenAI Sora 生成视频中的官方水印（含用户名）**  
**⚡️ One-click removal of official watermarks (including username) from OpenAI Sora videos**

<p align="center">
  <a href="#english">English</a> • 
  <a href="#中文版">中文版</a>
</p>

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)
![License](https://img.shields.io/github/license/linkedlist771/SoraWatermarkCleaner)
![Stars](https://img.shields.io/github/stars/linkedlist771/SoraWatermarkCleaner?style=social)
![Forks](https://img.shields.io/github/forks/linkedlist771/SoraWatermarkCleaner?style=social)

> Pure deep-learning solution | YOLOv11s precise detection + LaMA seamless inpainting | Batch processing | EXE / Web / API deployment  
> 纯深度学习驱动 | YOLOv11s 精准检测 + LaMA 无痕修复 | 支持批量处理 | 提供 EXE / Web / API 多部署方式

## ✨ Features / 核心特性

| Module / 功能模块      | Technology / 技术细节                           | Advantage / 特点优势                  |
|------------------------|------------------------------------------------|---------------------------------------|
| Watermark Detector     | YOLOv11s (fine-tuned for latest username watermarks) | Extremely accurate, near-zero misses |
| 水印检测器             | YOLOv11s（已针对最新含用户名水印微调）          | 定位极准，漏检率接近 0                |
| Watermark Remover      | LaMA inpainting (based on IOPaint)             | Intelligent filling, seamless result |
| 水印清除器             | LaMA 大模型修复（基于 IOPaint）                 | 智能填充，自然无痕                    |
| Batch Processing       | Native folder/multi-file support               | Process hundreds of videos at once   |
| 批量处理               | 原生支持文件夹/多文件拖拽                       | 一键处理数百个视频                    |
| Deployment Options     | EXE / Streamlit / FastAPI                      | One-click EXE or deploy as service   |
| 多端部署               | EXE / Streamlit / FastAPI                      | 无需环境一键运行或部署为在线服务      |

## 🎬 Before & After / 效果对比

| Original (with watermark) / 原始视频（带水印） | Cleaned (seamless) / 移除后（无痕） |
|------------------------------------------------|-------------------------------------|
| <video src="https://github.com/user-attachments/assets/4f032fc7-97da-471b-9a54-9-d9e2a434fa57" controls></video> | <video src="https://github.com/user-attachments/assets/8cdc075e-7d15-4d04-8fa2-53dd287e5f4c" controls></video> |

## 🚀 Quick Start / 快速开始

### 1. One-Click Portable Version (Windows Recommended 🔥)  
1. 一键便携版（Windows 推荐）

No Python or environment setup required. Download, unzip, and run.

| Platform / 平台     | Download Link / 下载链接                                                                 | Password / 提取码 | Notes / 备注             |
|---------------------|------------------------------------------------------------------------------------------|-------------------|--------------------------|
| Google Drive        | [Click to download](https://drive.google.com/file/d/...）（请替换为真实链接）            | -                 | Recommended internationally |
| Baidu Netdisk       | https://pan.baidu.com/s/1onMom81mvw2c6PFkCuYzdg?pwd=jusujusu                            | jusu              | Faster in mainland China |

### 2. Python Environment Installation  
2. Python 环境安装（适用于开发者 / Linux / Mac）

```bash
# 1. Install FFmpeg (required)
# Windows: https://www.gyan.dev/ffmpeg/builds/
# macOS: brew install ffmpeg
# Linux: sudo apt install ffmpeg -y

# 2. Clone and install dependencies (uv is recommended, very fast)
git clone https://github.com/linkedlist771/SoraWatermarkCleaner.git
cd SoraWatermarkCleaner
uv sync    # Automatically creates .venv and installs everything
