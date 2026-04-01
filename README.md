# 🎥 Stereoscopic 3D Camera Base Calculator 
**双机立体拍摄最佳轴距计算器**

[![Website](https://img.shields.io/badge/Website-Online_Calculator-007AFF?style=for-the-badge&logo=google-chrome)](https://zq-moonlight.github.io/Stereoscopic-3D-Camera-Base-Calculator/)
[![License: MIT](https://img.shields.io/badge/License-MIT-success.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

[简体中文](#简体中文) | [English](#english)

<a name="简体中文"></a>

## 🇨🇳 简体中文

一款专为影视级双机立体拍摄（Stereoscopic 3D）与 VR 视频创作设计的最佳物理轴距（Base / IA）实时计算器。

基于严谨的光学公式与人类生理极限，帮助立体工程师（Stereographer）、摄影指导和后期合成师精准控制出入屏视差，打通从前期实拍到后期合成的立体参数数据流。

🌐 **[点击这里开始使用 (Online Calculator)](https://zq-moonlight.github.io/Stereoscopic-3D-Camera-Base-Calculator/)**

---

### ✨ 主要功能 (Core Features)

* 🧮 **严密的核心算法体系**
  底层采用高端立体制作核心的 **Bercovitz 公式**，并会在每次运算后自动与传统的“1/30 经验法则”进行对比与偏差警告，确保参数万无一失。
* 🛡️ **生理安全视差锁**
  无论参数如何极端，系统都将强制把最大屏幕物理视差锁定在人类安全瞳距（如默认的 50mm）以内，彻底杜绝观众产生复视与眼球撕裂感。
* 🎬 **前后期全流程打通**
  不仅为前期摄影组计算出**最佳物理轴距 (Base)** 和**云台类型建议 (Beamsplitter / SBS)**，更直接为后期合成组推算出精准的**零视差面像素平移量 (Pixel Shift)**。
* 📷 **工业级全场景预设库**
  内置主流影视设备（ARRI Alexa 35/65, RED, Sony Venice 2, iPhone Pro）、工程分辨率标准（DCI Scope/Flat, UHD）以及常见放映终端（移动端、标准影院、IMAX、Vision Pro）。
* 📇 **双引擎专业数据输出**
  * **现场极简模式**: 一键拷贝符合好莱坞场记规范的纯文本联通单，便于在微信/Slack中快速丢给掌机和 DIT。
  * **高阶视觉模式**: 在本地无感渲染并导出一张极具科技感、完美符合 `9:16` 手机屏幕比例的高清参数海报，便于归档与跨部门沟通。
* ⚡ **纯前端与离线记忆**
  无需后端服务器，单 HTML 文件即可运行（完美适应无信号的深山影棚）。自动保存上一次的参数配置，随开随用。

---

### 🚀 V2.0 版本更新说明 (What's New vs V1.0)

相比于 V1.0 的基础公式验证，V2.0 进行了彻底的重构，正式升级为工业级生产力工具：

* **[新增] 场景深度交互预演 (Interactive Visualizer)**: 抛弃了 V1 枯燥的纯数字输入。新增 1D 空间轨道，支持直接拖拽“近景(N)”、“主体(S)”、“远景(L)”标记点。底层自带“推雪机”物理防卡死引擎，实现 60fps 实时演算反馈。
* **[重构] 后期 HIT 像素级推演**: V1 仅输出前期的物理轴距；V2 引入了**后期工程分辨率 (Timeline Resolution)** 参数，直接为 Nuke / DaVinci Resolve 推算出准确到个位数的左右眼像素平移量。
* **[新增] 角视差与 Davis 保护机制**: V1 仅提供固定的百分比视差限制；V2 新增了结合观众观看距离的**角视差法则 (Angular Parallax)**，以及针对特写浅景深镜头的 **Davis 强制钳制保护 ($L < 2N$)**。
* **[重构] 报告输出系统**: 彻底移除了 V1 依赖系统截图的简陋方式，引入 `html2canvas` 渲染引擎，一键生成并下载专业排版的数据卡片。

---

### 📖 如何使用

1. 在浏览器中打开 **[在线计算器](https://zq-moonlight.github.io/Stereoscopic-3D-Camera-Base-Calculator/)**。
2. 输入或在预设中选择当前的 **放映屏幕宽度**、**相机传感器尺寸**、**工程分辨率** 及 **镜头焦距**。
3. 输入场景测距数据或直接拖动轨道上的 **N (近景)**、**S (主体)**、**L (远景)** 标记点。
4. 将计算得出的 **最佳物理轴距 (Base)** 提供给摄影大助调整 3D 云台；将 **后期像素平移量** 交给后期合成师。

> **⚠️ 免责声明 (Disclaimer)**: 拍摄安全无小事。本工具计算结果基于理论物理光学模型，在实际高强度的视效项目中，请务必结合实拍测试和立体监视器的实时波形图进行最终确认。

---

💡 *祝你的轴距永远精准，更祝观众的眼球在看你的片子时不会“脱窗”离家出走！🍻*

<br>

---

<a name="english"></a>

## 🇬🇧 English

A real-time optimal camera base (interaxial distance) calculator designed specifically for cinematic dual-camera stereoscopic 3D shooting and VR video production.

Powered by rigorous optical formulas and human physiological limits, it helps Stereographers, DPs, and Compositors precisely control depth budgets and streamlines stereoscopic data workflows from on-set production to post-production.

🌐 **[Try it Online](https://zq-moonlight.github.io/Stereoscopic-3D-Camera-Base-Calculator/)**

---

### ✨ Core Features

* 🧮 **Rigorous Algorithm System**
  Utilizes the industry-standard **Bercovitz Formula** as its core, automatically comparing results with the traditional "1/30 rule" to provide deviation warnings and ensure absolute parameter safety.
* 🛡️ **Physiological Parallax Lock**
  No matter how extreme the input parameters are, the system forcibly caps the maximum physical screen parallax within the safe human interpupillary distance (default 50mm) to completely prevent diplopia and eye strain.
* 🎬 **Production to Post Workflow**
  Not only does it calculate the **Optimal Base (IA)** and suggest **Rig Types (Beamsplitter / SBS)** for the camera crew, but it also deduces the exact **Pixel Shift** required to align the Zero Parallax Setting (ZPS) for the VFX compositors.
* 📷 **Industry-Standard Presets**
  Built-in specs for mainstream cinema cameras (ARRI Alexa 35/65, RED, Sony Venice 2, iPhone Pro), timeline resolutions (DCI Scope/Flat, UHD), and projection terminals (Mobile, Standard Cinema, IMAX, Vision Pro).
* 📇 **Dual-Engine Professional Output**
  * **Minimalist On-Set Mode**: One-click copy of a compact ASCII parameter slate, perfect for quick drops into WhatsApp/Slack for Camera Operators and DITs.
  * **Visual Poster Mode**: Locally renders and downloads a sleek, sci-fi-inspired `9:16` HD parameter poster for archiving and cross-departmental communication.
* ⚡ **Pure Frontend & Auto-Save**
  No backend server required; runs perfectly as a single HTML file (ideal for remote soundstages with zero cellular signal). Automatically remembers your last configurations via LocalStorage.

---

### 🚀 What's New in V2.0 (vs V1.0)

V2.0 has been completely rebuilt from the ground up, evolving from a basic formula verifier into an industrial-grade productivity tool:

* **[NEW] Interactive Depth Visualizer**: Ditched the boring pure-number inputs of V1. Added a responsive 1D spatial track. Drag the Near (N), Subject (S), and Far (L) markers for 60fps real-time calculations, backed by a collision-prevention physics engine.
* **[REBUILT] Post-Production HIT Calculation**: V1 only output the physical camera base. V2 introduces the **Timeline Resolution** parameter to directly calculate the exact horizontal Pixel Shift needed in Nuke or DaVinci Resolve.
* **[NEW] Angular Parallax & Davis Limits**: V1 relied solely on a fixed percentage. V2 introduces the **Angular Parallax Rule** based on viewing distance, and the **Davis Clamp ($L < 2N$)** to prevent hazardous interaxial distances during macro or shallow depth-of-field shots.
* **[REBUILT] Export System**: Replaced V1's primitive screenshot-reliant method with the `html2canvas` rendering engine, allowing users to generate and download perfectly scaled, professionally formatted data cards with one click.

---

### 📖 How to Use

1. Open the **[Online Calculator](https://zq-moonlight.github.io/Stereoscopic-3D-Camera-Base-Calculator/)** in your browser.
2. Input or select your **Screen Width**, **Sensor Width**, **Timeline Resolution**, and **Focal Length**.
3. Enter your scene distances or simply drag the **N (Near)**, **S (Subject)**, and **L (Far)** markers on the interactive track.
4. Provide the calculated **Optimal Base (IA)** to the 1st AC for rig setup, and hand the **Pixel Shift** data to the Post-Production team.

> **⚠️ Disclaimer**: Safety first in stereoscopic filming. The calculations are based on theoretical physical optics models. In actual high-intensity VFX film production, please confirm the final parameters with live-action tests and real-time waveforms on a stereoscopic monitor.

---

💡 *May your interaxial distance always be precise, and may your audience's eyes never diverge out of their sockets! 🍻*
