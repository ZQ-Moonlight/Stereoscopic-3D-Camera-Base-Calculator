# 🎬 Stereoscopic 3D Camera Base Calculator (双机立体拍摄最佳轴距计算器)

[English](#english) | [简体中文](#简体中文)

<a name="english"></a>

## English

> **Description**: A real-time optimal camera base (interaxial distance) calculator dedicated to cinematic dual-camera stereoscopic 3D shooting and VR video production. Powered by the Bercovitz formula, it reverse-engineers safe parallax limits based on final projection sizes to prevent audience dizziness. Ideal for 3D filmmaking, VR panoramic video creation, and stereoscopic imaging research.

🌐 **[Click here to access the Online Calculator] (Replace with your GitHub Pages link here)**

### 💡 Why Do You Need This Tool?

In Stereoscopic 3D filming, arbitrarily increasing the dual-camera interaxial distance (base) to pursue extreme "pop-out" visual effects can cause severe eye strain, dizziness, and double vision (diplopia) for the audience. Due to human physiological limits (eyes cannot comfortably diverge outwards), if the positive parallax on the screen exceeds the human interpupillary distance (approx. 63mm), stereoscopic fusion completely fails.

The traditional "1:30 rule" is based on standard 50mm lenses and standard 35mm formats, making it obsolete in today's complex shooting environments (wide/telephoto lenses, varying sensor sizes). This tool uses the **Bercovitz Formula**—the core standard in high-end stereoscopic production—combined with the 3% screen width rule. It reverse-engineers the limit parameters from the "final projection screen" back to the "camera sensor," calculating the absolute safe and **optimal physical base**.

### ✨ Core Features

* 🧮 **Rigorous Algorithm**: Built-in full Bercovitz formula and infinity simplification logic, completely replacing rough empirical estimates for stereoscopic 3D.
* 🛡️ **Giant Screen Safety Lock (IMAX / VR)**: Automatically determines projection size. When the target screen exceeds 77 inches (e.g., IMAX or VR 100-inch virtual screens), it forcibly locks the maximum on-screen parallax within the human limit of `50mm` to protect the audience's physiology.
* 📷 **Comprehensive Sensor Presets**: Includes precise physical dimensions ranging from Apple iPhone main cameras and full-frame mirrorless to ARRI Alexa 65 and IMAX 70mm film. Supports one-click selection and custom input.
* 📺 **Comprehensive Screen Presets**: Supports size conversion for mobile phones, tablets, standard cinemas (Flat/Scope), and even virtual giant screens for Apple Vision Pro / Meta Quest 3.
* 📋 **On-Set Artifact (1-Click Report)**: No need for screenshots. Generate a cleanly formatted "3D Shooting Parameter Report" text with one click, ready to be pasted into WhatsApp/WeChat or work groups to align parameters with camera operators and stereographers.
* ⚡ **Zero Dependencies & Offline Ready**: Written in pure native HTML/CSS/JS with no third-party libraries. A single file runs instantly, even on sets with zero cellular signal.

### 🚀 How to Use

**As an Online Tool (Recommended):**
Simply open the [GitHub Pages Link] on your mobile phone or tablet browser on set.

**As a Local Tool:**

1. Download the `index.html` file from this repository.
2. Double-click to open it in any modern browser. No internet connection is required.

### 📸 UI Preview

*(You can add a screenshot of the calculator running on a mobile device here later)*

### 🛠 Technical Details

* Built with HTML5 + Vanilla JavaScript.
* Responsive Design, perfectly adapted to iOS and Android mobile operation habits.
* Smart unit conversion (Inputting "Meters" automatically converts to "Millimeters" required by the formula to avoid dimensional confusion).

**Disclaimer**: Safety first in filming. The calculation results of this tool are based on rigorous theoretical physical optics models. In actual high-intensity VFX film production, please confirm the final parameters with live-action tests and real-time waveforms on a stereoscopic monitor.

<a name="简体中文"></a>

## 简体中文

> **项目简介**: 一款专为影视级双机立体拍摄（Stereoscopic 3D）与 VR 视频创作设计的最佳物理轴距（Base）实时计算器。基于行业核心的 Bercovitz 公式，结合最终放映尺寸逆向推演，精准控制 3D 立体影像的出入屏视差，避免观众产生眩晕与复视。适用于 3D 电影实拍、VR 全景视频制作及立体视觉工程。

🌐 **[点击这里访问在线计算器] (在这里替换为你的 GitHub Pages 链接)**

### 💡 为什么需要这个工具？

在 3D 立体影像拍摄中，为了追求强烈的视觉出屏效果而随意拉大双机轴距，会导致观众产生眼球撕裂般的疼痛、严重眩晕以及无法重叠的复视。由于人类眼睛生理结构的限制（无法向外翻转融合），屏幕上的正视差一旦突破瞳距（约 63mm），立体融合就会失效。

传统的“1:30 法则”基于特定的标准镜头和画幅，在当今复杂的拍摄环境（广角/长焦、大小不一的传感器）中已不再适用。本工具底层采用影视级 3D 制作的核心标准 —— **Bercovitz 公式**，结合最终放映端 3% 屏幕宽度法则，从“最终放映端”逆向推演“前期传感器端”的极限参数，为你算出绝对安全的**最佳物理轴距**。

### ✨ 核心功能与亮点

* 🧮 **严密的底层算法**：内置 Bercovitz 完整公式及无限远简化逻辑，彻底取代双机拍摄中粗略的经验估算。
* 🛡️ **巨幕安全锁 (IMAX / VR)**：自动判定放映尺寸，当目标屏幕超过 77 寸（如 IMAX 巨幕或 VR 虚拟百寸巨幕）时，自动将最大出/入屏视差强制锁定在人体极限的 `50mm` 以内，守护观众生理底线。
* 📷 **全覆盖的传感器预设**：内置从 Apple iPhone 主摄、微单全画幅到 ARRI Alexa 65 电影机大画幅、IMAX 70mm 胶片等精确物理尺寸，支持一键选择与自定义输入。
* 📺 **全覆盖的放映端预设**：支持手机、平板、标准电影院 (Flat/Scope)、甚至 Apple Vision Pro / Meta Quest 3 的虚拟巨幕尺寸换算。
* 📋 **片场神器：一键复制报告**：无需截图，一键生成排版清晰的【3D拍摄参数报告】文本，可直接粘贴发送至微信或工作群，方便掌机和立体工程师随时对齐参数。
* ⚡ **零依赖 & 离线可用**：纯原生 HTML/CSS/JS 编写，无任何第三方库，单文件即可运行。加载极快，在信号微弱的拍摄现场也能随点随用。

### 🚀 如何使用？

**作为在线工具（推荐）：**
直接使用手机或平板的浏览器打开 [GitHub Pages 链接]，即可在片场随手计算。

**作为本地工具：**

1. 下载本项目中的 `index.html` 文件。
2. 双击在任何现代浏览器中打开即可运行，完全不需要联网。

### 📸 界面预览

*(你可以稍后在这里补充一张在手机上运行计算器的截图)*

### 🛠 技术细节

* 基于 HTML5 + Vanilla JavaScript 构建。
* 采用了响应式设计 (Responsive Design)，完美适配 iOS 与 Android 移动端操作习惯。
* 包含智能单位换算（输入项“米”自动转换为公式所需的“毫米”以避免量纲混乱）。

**Disclaimer**: 拍摄安全无小事。本工具计算结果基于严谨的理论物理光学模型，在实际高强度视效电影拍摄中，请结合实拍测试和立体监视器的实时波形图进行最终确认。
