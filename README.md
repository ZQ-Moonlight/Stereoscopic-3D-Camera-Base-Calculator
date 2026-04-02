# Stereoscopic 3D Camera Base Calculator  
**双机立体拍摄轴距计算器**

[![Website](https://img.shields.io/badge/Website-Online_Calculator-007AFF?style=for-the-badge&logo=google-chrome)](https://zq-moonlight.github.io/Stereoscopic-3D-Camera-Base-Calculator/)
[![License: AGPL v3](https://img.shields.io/badge/License-AGPL_v3-blue.svg?style=for-the-badge)](https://www.gnu.org/licenses/agpl-3.0)

[简体中文](#简体中文) | [English](#english)

<a name="简体中文"></a>

## 🇨🇳 简体中文

一个用于双机立体拍摄（3D 电影、VR）的轴距计算工具。  
输入场景距离、镜头焦距、银幕尺寸等参数，算出相对安全的摄影机轴距（Base / IA），同时给出后期合成需要的像素平移量。

---

### 为什么做这个

我在网上找了很久，发现几乎找不到现在还能正常用的立体轴距计算软件或网页。能找到的大多是十几年前的老教程、失效的链接、或者早已不维护的桌面工具。  
立体摄影这块本来就小众，很多资料随着时间丢失了。挺可惜的，也有点难过。

所以自己从头写了一个。公式参考了前人的经验（Bercovitz 公式、1/30 法则、Davis 保护等），代码用 AI 辅助完成。  
**还没有在实际片场验证过**，数学上应该是对的，但真到拍摄时请务必用立体监视器复核。

---

### 版本更新

#### V1（最初版）
- 实现基础的 Bercovitz 公式计算
- 输出轴距 (Base) 和简单的像素平移量
- 手动输入所有参数，无可视化交互

#### V2
- 增加 1D 空间轨道，支持拖拽 N/S/L 标记点（基础防冲突）
- 引入后期工程分辨率参数，直接输出像素平移量
- 增加角视差提示和 Davis 强制约束（L ≥ 2N）
- 报告生成改用 html2canvas，支持导出参数卡片

#### V3（当前版本）
- 重构视差预算系统：独立控制正视差上限（% 屏幕宽）、负视差上限、IPD 硬锁
- 增加角视差二次钳制（输入观众距离、最大角度）
- 增加辅屏模式，同时计算主屏和辅屏的安全轴距
- 交互轨道升级：防碰撞自动调整 N/S/L，Davis 保护实时生效
- 现场联通单内容更完整（包含预算、几何、后期偏移）
- 视觉海报独立渲染，可导出高清 PNG
- 增加术语表、拍摄指南面板
- 支持深色主题、中英文界面切换

---

### 基本功能

- 输入 **最近景物距离 (N)**、**零视差面距离 (S)**、**最远景物距离 (L)**
- 输入 **镜头焦距 (mm)**、**传感器宽度 (mm)**、**放映屏幕宽度 (mm)**
- 选择或输入 **后期时间线分辨率**（用于计算像素平移量）
- 输出：
  - 安全轴距 (mm)
  - 后期 HIT 像素平移量（左眼/右眼各移多少像素）

附带一个可拖拽的深度示意条，用来直观调整 N / S / L 的位置。  
另外有一个“辅屏模式”，可以同时计算另一个屏幕（比如电视）对应的轴距。

高级选项里有视差百分比上限、瞳距硬锁、角视差限制等，一般用默认值就够了。

---

### 使用方式

1. 打开 **[在线计算器](https://zq-moonlight.github.io/Stereoscopic-3D-Camera-Base-Calculator/)**（纯前端，单 HTML 文件）
2. 按实际情况填写参数
3. 读取轴距结果，交给摄影组
4. 读取像素平移量，交给后期合成

---

### 注意

- 计算结果仅供参考。实拍中请用立体监视器和视差波形图最终确认。
- 轴距小于 65mm 时，两台摄影机无法并排放置，需要用反射式支架（Mirror Rig）。
- 本项目基于 AGPL v3 协议开源。

---

💡 *希望这个工具能帮到还在坚持立体摄影的人。也祝观众的双眼看完片子后还能正常对焦。*

<br>

---

<a name="english"></a>

## 🇬🇧 English

A simple interaxial distance calculator for dual‑camera stereoscopic 3D shooting.  
Enter scene depths, focal length, sensor size, screen width — it gives you a reasonably safe camera base (IA) and the pixel shift needed for post‑production.

---

### Why this exists

I searched online and found almost no working software or website for stereoscopic base calculation. Most resources are from 10+ years ago — broken links, abandoned tools.  
That’s a bit sad. This field is niche, and a lot of knowledge has slowly disappeared.

So I wrote this from scratch. The formulas are based on existing work (Bercovitz, 1/30 rule, Davis clamp). The code was written with AI assistance.  
**It hasn’t been tested on a real set yet** — mathematically it should be fine, but always double‑check with a stereoscopic monitor on set.

---

### Version History

#### V1 (Initial)
- Basic Bercovitz formula calculation
- Outputs camera base and simple pixel shift
- All parameters manually entered, no visualization

#### V2
- Added 1D spatial track with draggable N/S/L markers (basic collision prevention)
- Introduced timeline resolution parameter for pixel shift calculation
- Added angular parallax hint and Davis clamp (L ≥ 2N)
- Upgraded report generation with html2canvas for exporting parameter cards

#### V3 (Current)
- Refactored parallax budget: independent positive/negative limits (% screen width), IPD hard lock
- Added angular parallax secondary clamp (viewing distance + max angle)
- Added secondary target mode: calculates safe IA for both main and secondary screens simultaneously
- Enhanced interactive track: auto‑adjust N/S/L with collision avoidance, real‑time Davis enforcement
- More complete on‑set report (budget, geometry, post shift)
- Standalone visual poster rendering, exportable as high‑res PNG
- Added glossary and shooting guide panels
- Dark theme and bilingual UI (Chinese/English)

---

### Basic features

- Input **Near (N)**、**Zero Parallax Plane (S)**、**Far (L)**
- Input **focal length (mm)**、**sensor width (mm)**、**screen width (mm)**
- Input or select **timeline resolution** (for pixel shift calculation)
- Output:
  - Safe interaxial distance (mm)
  - HIT pixel shift (how many pixels to shift left/right eye)

A draggable depth bar helps adjust N/S/L visually.  
There’s also a “secondary target” mode for calculating IA for another screen (e.g., TV).

Advanced options (parallax percentage limits, IPD hard cap, angular parallax) are available — default values work for most cases.

---

### How to use

1. Open the **[online calculator](https://zq-moonlight.github.io/Stereoscopic-3D-Camera-Base-Calculator/)** (pure frontend, single HTML)
2. Fill in parameters
3. Give the IA result to the camera crew
4. Give the pixel shift to the post team

---

### Disclaimer

This is a theoretical tool. Always verify with a stereoscopic monitor and real‑time waveforms during production.  
If the IA is below 65mm, you’ll need a mirror rig — two cameras won’t fit side‑by‑side.  
This project is licensed under AGPL v3.

---

💡 *Hope this helps the few people still shooting stereoscopic. And may your audience’s eyes stay comfortably converged after watching your film.*
