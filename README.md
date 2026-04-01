# 🎥 Stereoscopic 3D Camera Base Calculator  
**双机立体拍摄最佳轴距计算器**

[![Website](https://img.shields.io/badge/Website-Online_Calculator-007AFF?style=for-the-badge&logo=google-chrome)](https://zq-moonlight.github.io/Stereoscopic-3D-Camera-Base-Calculator/)
[![License: MIT](https://img.shields.io/badge/License-MIT-success.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

[简体中文](#简体中文) | [English](#english)

<a name="简体中文"></a>

## 🇨🇳 简体中文

一款面向影视级双机立体拍摄与 VR 视频创作的最佳物理轴距实时计算工具。

基于光学成像原理与人类视觉生理特性，辅助立体摄影师、摄影指导及后期合成师精确控制出入屏视差，实现从前期拍摄到后期制作的全流程立体参数协同。

🌐 **[在线使用](https://zq-moonlight.github.io/Stereoscopic-3D-Camera-Base-Calculator/)**

---

### ✨ 主要功能

* 🧮 **核心算法**  
  采用 **Bercovitz 公式** 作为底层计算模型，每次运算后自动与传统“1/30 经验法则”进行比对并给出偏差提示，确保参数可靠性。
* 🛡️ **视差安全约束**  
  系统自动将最大屏幕物理视差限制在人体安全瞳距范围内（默认 50 mm），有效避免观众产生复视及视觉疲劳。
* 🎬 **前后期协同**  
  为摄影组提供**最佳物理轴距**与**云台类型建议**，同时为后期合成组输出精确的**零视差面像素偏移量**。
* 📷 **工业级预设**  
  内置主流影视设备参数（ARRI Alexa 35/65、RED、Sony Venice 2、iPhone Pro）、工程分辨率标准（DCI Scope/Flat、UHD）及常见放映终端（移动端、标准影院、IMAX、Vision Pro）。
* 📇 **双模式数据输出**  
  * **现场精简模式**：一键生成符合场记规范的纯文本数据单，便于现场快速沟通。  
  * **视觉报告模式**：本地生成 9:16 比例的高清参数海报，支持保存与分享。
* ⚡ **离线可用与状态记忆**  
  纯前端实现，单 HTML 文件即可运行，自动保存用户配置，适应无网络环境。

---

### 🚀 V2.0 版本更新说明

相较于 V1.0 的基础公式验证版本，V2.0 进行了全面重构，定位为工业级生产力工具：

* **[新增] 空间交互预演**：引入可视化空间轨道，支持直接拖拽近景、主体、远景标记点，内置防冲突机制，实现实时反馈。
* **[重构] 像素偏移计算**：新增工程分辨率参数，直接输出适用于 Nuke / DaVinci Resolve 的精确像素偏移量。
* **[新增] 角视差与 Davis 保护**：引入基于观看距离的角视差模型，并增加针对浅景深镜头的 Davis 强制约束。
* **[重构] 报告生成**：采用 `html2canvas` 渲染引擎，支持一键生成并下载专业排版的参数卡片。

---

### 📖 使用说明

1. 访问 **[在线计算器](https://zq-moonlight.github.io/Stereoscopic-3D-Camera-Base-Calculator/)**。
2. 设置放映屏幕宽度、传感器尺寸、工程分辨率及镜头焦距。
3. 输入场景距离或拖拽轨道上的近景、主体、远景标记点。
4. 将计算所得的**最佳物理轴距**交付摄影组，**像素偏移量**交付后期合成组。

> **免责声明**：本工具计算结果基于理论光学模型。实际拍摄中，请结合现场测试与立体监视器波形图进行最终确认。

---

💡 *祝轴距精准，也祝观众的双眼始终安然无恙。*

🎧 *本项目采用 vibe coding 构建*

<br>

---

<a name="english"></a>

## 🇬🇧 English

A real-time optimal interaxial distance calculator designed for cinematic dual-camera stereoscopic 3D shooting and VR video production.

Built upon optical formulas and human visual physiology, it assists stereographers, cinematographers, and compositors in precisely controlling depth budgets, streamlining stereoscopic data workflows from production to post-production.

🌐 **[Try it Online](https://zq-moonlight.github.io/Stereoscopic-3D-Camera-Base-Calculator/)**

---

### ✨ Core Features

* 🧮 **Core Algorithm**  
  Powered by the **Bercovitz Formula**, with automatic comparison against the conventional "1/30 rule" and deviation warnings.
* 🛡️ **Parallax Safety Lock**  
  Enforces a hard cap on maximum screen parallax within the safe human interpupillary distance (default 50 mm) to prevent diplopia and visual discomfort.
* 🎬 **Production to Post Integration**  
  Provides **optimal interaxial distance** and **rig type recommendations** for camera crews, along with precise **pixel shift values** for post-production compositing.
* 📷 **Industry-Standard Presets**  
  Includes specifications for mainstream cinema cameras (ARRI Alexa 35/65, RED, Sony Venice 2, iPhone Pro), timeline resolutions (DCI Scope/Flat, UHD), and display targets (Mobile, Standard Cinema, IMAX, Vision Pro).
* 📇 **Dual-Mode Output**  
  * **On-Set Mode**: One-click copy of a compact text slate for rapid on-set communication.  
  * **Visual Poster Mode**: Locally renders and exports a 9:16 HD parameter card for documentation and sharing.
* ⚡ **Offline Capable & State Persistence**  
  Fully front-end, runs as a single HTML file. Automatically saves user settings via LocalStorage.

---

### 🚀 What's New in V2.0

V2.0 represents a complete overhaul, evolving from a basic formula validator into an industrial-grade tool:

* **[NEW] Interactive Depth Visualizer**: Introduces a spatial track with draggable near, subject, and far markers. Real-time feedback with collision prevention.
* **[REBUILT] Pixel Shift Calculation**: Adds timeline resolution parameter to output precise pixel shift values for Nuke or DaVinci Resolve.
* **[NEW] Angular Parallax & Davis Constraints**: Incorporates viewing-distance-based angular parallax models and a Davis clamp for shallow depth-of-field scenarios.
* **[REBUILT] Export System**: Leverages `html2canvas` to generate and download professionally formatted parameter cards with a single click.

---

### 📖 How to Use

1. Open the **[Online Calculator](https://zq-moonlight.github.io/Stereoscopic-3D-Camera-Base-Calculator/)**.
2. Configure screen width, sensor size, timeline resolution, and focal length.
3. Enter scene distances or adjust markers on the interactive track.
4. Provide the **optimal interaxial distance** to the camera team and the **pixel shift value** to the post-production team.

> **Disclaimer**: Calculations are based on theoretical optical models. In actual production, final parameters should be validated with on-set tests and stereoscopic monitor waveforms.

---

💡 *May your interaxial always be on point, and may your audience’s eyes never diverge.*

🎧 *This project is built with vibe coding.*

---

*Happy stereoscopic shooting.*
