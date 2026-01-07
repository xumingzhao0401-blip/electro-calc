# ⚡ Electro-Plating Assistant (电镀工艺助手)

> 一个专为半导体及集成电路从业者设计的轻量级电镀工艺计算器。
> A lightweight, mobile-first plating process calculator for IC engineers.

![Version](https://img.shields.io/badge/version-3.0-blue) ![Platform](https://img.shields.io/badge/platform-Mobile%20%7C%20Web-success) ![License](https://img.shields.io/badge/license-MIT-green)

## 📖 简介 (Introduction)

**电镀工艺助手** 是一款单文件 HTML 网页应用，旨在帮助工艺工程师（PE）和科研人员快速计算电镀过程中的关键参数。它无需安装、不依赖服务器、完全本地运行，并且针对 iOS 和 Android 手机浏览器进行了深度优化。

主要用于解决以下两个核心场景：
1.  **药水寿命管理**：根据目标 Ah/L 计算寿命耗尽时间。
2.  **膜厚预测**：基于法拉第定律，反推达到目标厚度所需的电镀时间。

## ✨ 核心功能 (Features)

* **📱 移动端原生体验**：
    * 针对手机屏幕优化的 UI，支持 iOS/Android。
    * **分体式输入框 (V3)**：数值与单位物理隔离，杜绝输入重叠，视觉清晰。
    * 适配刘海屏与虚拟键盘。
* **🎯 晶圆快速预设**：
    * 一键填充 **4" / 6" / 8" / 12"** 晶圆面积。
    * 支持自定义不规则样片面积输入。
* **🔄 双模式切换**：
    * **Mode 1: 药水寿命 (Bath Life)** - 监控安时（Ah）消耗。
    * **Mode 2: 膜厚计算 (Thickness)** - 支持 Cu, Ni, Sn, Au 四种常用金属。
* **🧮 智能计算**：
    * 自动处理单位换算（mL -> L, min -> s）。
    * 根据时间长短自动切换显示格式（秒 / 分 / 时+分）。

## 🚀 使用方法 (Usage)

### 方式一：在线使用 (推荐)
访问 GitHub Pages 链接直接使用（请在仓库 Settings -> Pages 中开启）：
> **[点击这里打开电镀助手] (https://<你的用户名>.github.io/<仓库名>/)**

### 方式二：本地运行
1.  下载本仓库中的 `index.html` 文件。
2.  通过微信/QQ发送到手机。
3.  使用手机浏览器直接打开。

## ⚙️ 技术原理 (Calculations)

本工具基于以下电化学公式进行计算：

### 1. 药水寿命 (Bath Life)
$$Total Charge (Ah) = Target Life (Ah/L) \times Volume (L)$$
$$Time = \frac{Total Charge}{Current (A)}$$

### 2. 膜厚预测 (Thickness - Faraday's Law)
基于法拉第电解定律：
$$h = \frac{I \cdot t \cdot \eta \cdot M}{z \cdot F \cdot \rho \cdot A} \times 10^4$$

其中：
* $h$: 厚度 ($\mu m$)
* $I$: 电流 (A)
* $\eta$: 电流效率 (%)
* $M$: 摩尔质量 (g/mol)
* $z$: 电子转移数
* $\rho$: 密度 (g/cm³)
* $A$: 面积 ($dm^2$)

## 🛠️ 数据参数 (Database)

内置常用电镀金属物理常数：

| Metal | Symbol | Valency (z) | M (g/mol) | Density (g/cm³) |
| :--- | :---: | :---: | :---: | :---: |
| **Copper** | Cu | 2 | 63.55 | 8.96 |
| **Nickel** | Ni | 2 | 58.69 | 8.90 |
| **Tin** | Sn | 2 | 118.71 | 7.30 |
| **Gold** | Au | 1 | 196.97 | 19.32 |

## 🔒 隐私说明 (Privacy)
本应用为纯前端静态页面（Single File HTML），所有计算均在**本地浏览器**完成。**不会**上传任何工艺数据到服务器，请放心使用。

---
*Created by [Your Name] for IC Process Engineering.*
