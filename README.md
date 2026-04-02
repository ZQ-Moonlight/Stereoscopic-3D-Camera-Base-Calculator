# 🎥 Stereoscopic 3D Camera Base Calculator  
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

### 主要功能

- **轴距计算**：基于 Bercovitz 公式，输入 N（最近）、S（零视差面）、L（最远）及镜头、传感器、银幕参数，输出安全轴距（mm）。
- **后期 HIT 平移**：根据时间线分辨率，输出左右眼需要内移的像素量，直接用于 Nuke / DaVinci Resolve。
- **实际架设反算**：输入现场实际使用的轴距，实时显示当前产生的正视差（入屏）、负视差（出屏）和总视差厚度，并与安全预算对比（超出标红）。
- **正负视差独立预算**：可分别设置正视差上限（% 银幕宽）、负视差上限（% 银幕宽），以及 IPD 硬锁、角视差二次钳制。
- **辅屏模式**：同时为主屏（如影院）和辅屏（如电视）计算各自的安全轴距，满足多版本交付。
- **可拖拽深度轨道**：直观调整 N/S/L 位置，自动防冲突和 Davis 保护。
- **预设库**：内置常用银幕尺寸、传感器规格（电影机、无反、手机等）、时间线分辨率。
- **现场联通单**：一键复制纯文本参数单，包含轴距、视差、几何、后期偏移。
- **视觉海报**：生成 9:16 高清参数卡片，支持导出 PNG。
- **深色主题 & 中英文界面**。

---

### 使用方式

1. 打开 **[在线计算器](https://zq-moonlight.github.io/Stereoscopic-3D-Camera-Base-Calculator/)**（纯前端，单 HTML 文件）
2. 按实际情况填写参数
3. 读取“极限安全轴距”，然后用“实际架设轴距”滑块模拟不同轴距下的实际视差
4. 将最终轴距交给摄影组，像素平移量交给后期合成

---

### 注意

- 计算结果仅供参考。实拍中请用立体监视器和视差波形图最终确认。
- 轴距小于 65mm 时，两台摄影机无法并排放置，需要用反射式支架（Mirror Rig）。
- 本项目基于 AGPL v3 协议开源。

---

💡 *希望这个工具能帮到还在坚持立体摄影的人。也祝观众的双眼看完片子后还能正常对焦。*

<details>
<summary>📋 完整更新日志（点击展开）</summary>

## [3.3.0] - 2026-04-02

### Added
- 新增 VR / AR 头显 (Headsets) 放映设备预设分类，支持 Apple Vision Pro (等效虚拟 150寸影院) 和 Meta Quest 3 (等效虚拟 120寸) 沉浸式视角的精准轴距推算。
- 大幅扩展后期时间线分辨率预设，新增标准电影工业打样画幅规格：4K/2K DCI Scope (2.39:1) 与 4K/2K DCI Flat (1.85:1)，完美匹配 DaVinci Resolve 和 Nuke 等专业工业流线。

### Fixed
- 彻底解决移动端导出数据海报时底部/边缘被异常裁切的问题。通过在 html2canvas 截图瞬间动态劫持并解除外层响应式容器的 overflow: hidden 与 scale 限制，并强制赋予视口足尺的宽高参数，保障手机端也能输出 100% 完整尺寸的高清全画幅海报。

## [3.2.0] - 2026-04-02

### Added
- 核心架构重大升级：引入「现场实际架设轴距 (Applied IA)」的正向推演系统。打破原有“吃干预算”的极限反推模式，支持摄影师通过滑块或输入框手动指定偏好的实际轴距，系统实时计算并可视化对比“实际产生视差”与“极限允许容差”。
- 新增「总视差预算 (Total Depth)」动态运算，一目了然监控画面总厚度是否超越 2% ~ 3% 的舒适区。
- 数据海报 (Visual Card) 全面扩容且升级为自适应高度：新增传感器物理宽、时间线分辨率、放大倍率 (M)、瞳距硬锁极限及独立的零视差 (ZPS) 几何展示；未启用辅屏时自动隐藏冗余行。
- 传感器预设极大丰富：按画幅重构层级，新增 ARRI Alexa 65/35、RED 8K VV/Komodo、Sony VENICE 等顶级数字电影机，并下放支持 iPhone 17/16 Pro 主摄等便携移动端规格。

### Fixed
- 彻底修复 Davis 保护介入时（最远距离小于最近距离的两倍），用户连续输入键盘数值被强行中断/覆盖的顽固交互 Bug（改为底层运算静默截断+高亮黄字警告）。
- 修复数据海报重构时意外丢失 vr-hit-px 和 vr-zps DOM 节点引发的 Cannot set properties of null 导致海报无法渲染弹出的严重报错。

## [3.1.0] - 2026-04-02

### Added
- 引入“双屏协同/多机位 (Main & Secondary Target)”推算模式：支持同时为巨幕主发出版与 TV 电视版计算独立的安全轴距，满足多机位三维剧组的现场需求。
- 全面实现中英双语 (EN/ZH) 实时无缝切换，覆盖计算器操作界面、一键复制的现场联通单 (Terminal Report) 以及生成的高清数据海报。

### Changed
- 解除旧版“负视差强行收紧至正视差 50%”的死板锁定，支持摄影师探索更激进的出屏效果。
- 结果面板逻辑重构：将“唯一最佳轴距”概念纠正为“最大安全轴距 (Max Safe IA)”，并透明化展示推演的瓶颈究竟是入屏还是出屏。
- 大幅降级“1/30 经验法则”与“轴距空间限度”的视觉层级，移动至下方的诊断分析文本中，防止大银幕精算下对摄影师造成经验性误导。

### Fixed
- 修复由于移除了冗余“安全区间”展示而引发输入框 ID 丢失，导致 JavaScript 抛出 Cannot read properties of null 阻止引擎启动的致命错误。

## [3.0.1-beta] - 2026-04-02

### Changed
- 修正核心文案与术语：纠正了界面中将“正视差”错误对应为“出屏”、“负视差”对应为“入屏”的低级翻译混淆。

### Fixed
- 修复视差预算可视进度条（Budget Bar）由于 1.1 倍溢出倍数导致末端永远留有 9% 灰色空隙的视觉 Bug，现红蓝进度条可完美填满 100% 预算。

## [3.0.0-beta] - 2026-04-02

> ⚠️ 注意：此版本为 Beta 测试版，包含部分已知问题待修复。

### Added
- 新增“ZPS 双向视差约束引擎”，支持分别独立设定“正视差上限（幕后深度）”与“负视差上限（幕前出屏）”。
- 新增“生理瞳距硬锁（IPD Hard Lock）”，强制截断超过人类平均瞳距的绝对物理视差，彻底杜绝画面“爆眼”风险。
- 增加算法瓶颈诊断提示，系统将在计算后自动分析并指出当前限制轴距的因素是前景负视差还是背景正视差。

### Changed
- 优化“1/30 经验法则”对比模块，智能评估长焦、广角及巨幕环境下的经验法则适用性，提供更专业的调整建议。
- 重构可视化拖拽轨道的边界碰撞系统，引入“双向推雪机”联动物理引擎，解决特写拖拽时的死区卡死现象。

### Known Issues
- 极端距离数值输入下（如最远距离极大而最近距离极小），拖拽可视化轨道的“推雪机”联动物理引擎会发生轻微坐标漂移。
- 移动设备在展开过多折叠面板时，调用高清海报渲染的弹窗偶尔会被底层图层异常遮挡。

## [2.2.0] - 2026-04-01

### Added
- 新增双模数据输出系统：支持一键复制极简 ASCII 格式现场联通单，以及本地渲染导出 9:16 手机竖屏比例的高清数据海报。

### Changed
- 升级响应式拟物化 UI 界面，电脑端浏览时将自适应展开为左右双栏高效布局。
- 优化导出海报图片的默认命名规范，自动抓取镜头焦距、计算轴距与当天的日期戳信息。
- 全面重绘高级数据卡片中的 8 个核心参数 SVG 矢量图标，大幅提升报告视觉专业度。

### Fixed
- 修复手机端窄屏幕下，数据卡片导出时底部内容溢出被裁切的问题（引入视口等比缩放引擎解决）。
- 修复模态弹窗无法通过点击黑色背景空白处关闭的交互体验问题。

## [2.1.0] - 2026-04-01

### Added
- 新增“后期工程/时间线分辨率”参数输入，可直接推算出后期合成软件中所需的精准左右眼像素平移量（Pixel Shift）。
- 增加“角视差（Angular Parallax）”自动推演模式，支持基于观众离屏距离与最大允许角度推算物理上限。

### Changed
- 完善影视设备预设库，更新支持 Alexa 35、RED V-Raptor 等主流数字电影机参数，以及 2K/4K DCI Scope 等工程打包分辨率预设。

## [2.0.0] - 2026-03-31

### Added
- 全新上线 1D 场景深度可视化预演轨道（Depth Visualizer）。
- 支持直观拖拽“最近距离(N)”、“主体距离(S)”、“最远距离(L)”圆点标记，底层运算支持 60fps 的参数实时重算与反馈。

### Changed
- 替换可视化轨道默认的标记圆点，全面采用更直观的 Emoji 图标（🌷 近景、👤 主体、⛰️ 远景）搭配高亮白边设计。

## [1.2.0] - 2026-03-30

### Added
- 增加家用及专业放映设备尺寸预设，包括 27寸电脑显示器 和 10米标准电影院银幕。
- 增加移动端与入门拍摄设备传感器预设，包括 iPhone Pro 主摄、安卓一英寸大底及主流微单规格。

### Changed
- 调整全局默认硬性绝对视差上限为更宽裕的 50mm。

## [1.1.0] - 2026-03-29

### Added
- 引入 Davis 浅景深强制保护机制选项，当遇到最远距离小于最近距离的两倍（$L < 2N$）时触发钳制介入。
- 新增后期水平物理位移量（HIT）毫米值的推算功能。
- 增加工业级拍摄与后期制作概念指南的隐藏折叠面板。

### Fixed
- 修复并统一底层逻辑，全面摒弃内八字（Toe-in）计算，确立绝对基于平行拍摄（Parallel Rig）与后期裁切的运算基准。

## [1.0.0] - 2026-03-28

### Added
- 发布基础计算核心，正式提供基于传统 Bercovitz 方程式的 3D 摄像机最佳物理轴距（Base/IA）计算。
- 提供基于 3% 屏幕宽度限制的全局视差容差计算辅助。
- 增加智能硬件云台类型建议提示，自动判断现场需使用垂直反射式（Beamsplitter）或并排式（Side-by-Side）云台。

</details>

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

### Key Features

- **IA calculation** – Bercovitz formula, outputs safe interaxial (mm) from N/S/L, lens, sensor, screen.
- **HIT pixel shift** – Pixel shift per eye based on timeline resolution, for Nuke/DaVinci Resolve.
- **Applied IA with real‑time feedback** – Enter actual base used on set; see actual positive/negative/total parallax compared to safe limits (red if exceeded).
- **Independent positive/negative budgets** – Set positive limit (% screen width), negative limit (% screen width), IPD hard cap, angular parallax clamp.
- **Secondary target mode** – Calculate separate safe IA for a second screen (e.g., TV).
- **Draggable depth track** – Adjust N/S/L visually with auto‑collision avoidance and Davis enforcement.
- **Presets** – Common screen sizes, sensor types (cinema, mirrorless, mobile), timeline resolutions.
- **On‑set report** – One‑click copy of a plain‑text parameter slate.
- **Visual poster** – 9:16 HD parameter card, exportable as PNG.
- **Dark theme & bilingual UI**.

---

### How to Use

1. Open the **[online calculator](https://zq-moonlight.github.io/Stereoscopic-3D-Camera-Base-Calculator/)** (pure frontend, single HTML)
2. Fill in parameters
3. Read the “Max Safe IA”, then use the “Applied IA” slider to simulate actual parallax at different bases
4. Give the final IA to the camera crew and the pixel shift to the post team

---

### Disclaimer

This is a theoretical tool. Always verify with a stereoscopic monitor and real‑time waveforms during production.  
If the IA is below 65mm, you’ll need a mirror rig — two cameras won’t fit side‑by‑side.  
This project is licensed under AGPL v3.

---

💡 *Hope this helps the few people still shooting stereoscopic. And may your audience’s eyes stay comfortably converged after watching your film.*

<details>
<summary>📋 Full Changelog (click to expand)</summary>

## [3.3.0] - 2026-04-02

### Added
- Added VR/AR headset presets: Apple Vision Pro (equivalent 150‑inch virtual cinema) and Meta Quest 3 (equivalent 120‑inch virtual screen) for accurate IA calculation in immersive viewing.
- Expanded timeline resolution presets with industry‑standard deliverables: 4K/2K DCI Scope (2.39:1) and 4K/2K DCI Flat (1.85:1), fully compatible with DaVinci Resolve and Nuke.

### Fixed
- Completely fixed mobile poster export cropping issue. By dynamically overriding overflow:hidden and scale restrictions on the outer responsive container at the moment html2canvas captures, and forcing full viewport dimensions, the poster now exports 100% complete full‑frame HD images on mobile devices.

## [3.2.0] - 2026-04-02

### Added
- Major architecture upgrade: Introduced "Applied IA" forward calculation system. Cinematographers can now manually input the actual base used on set via slider or number input, with real‑time visualization comparing actual parallax against safety limits.
- Added dynamic "Total Depth" calculation to monitor whether the total parallax exceeds the 2%–3% comfort zone.
- Visual card now fully expanded and auto‑height: added sensor width, timeline resolution, magnification (M), IPD hard limit, and independent ZPS geometry display; secondary target rows auto‑hide when not enabled.
- Greatly expanded sensor presets: reorganized by format, added ARRI Alexa 65/35, RED 8K VV/Komodo, Sony VENICE, plus mobile options like iPhone 17/16 Pro main camera.

### Fixed
- Fixed the long‑standing Davis rule bug that interrupted continuous keyboard input (now uses silent truncation + highlighted warning).
- Fixed missing DOM nodes (vr-hit-px, vr-zps) causing `Cannot set properties of null` error and preventing poster rendering.

## [3.1.0] - 2026-04-02

### Added
- Added "Main & Secondary Target" dual‑screen mode: calculates independent safe IAs for cinema main release and TV secondary release simultaneously.
- Full bilingual (EN/ZH) real‑time switching, covering UI, on‑set terminal report, and exported visual poster.

### Changed
- Removed the rigid "negative parallax forced to 50% of positive" constraint, allowing more aggressive pop‑out effects.
- Renamed "Optimal Base" to "Max Safe IA" and transparently shows which bottleneck (positive or negative) limits the result.
- Demoted the "1/30 rule" and "IA space limits" to the analysis text area to avoid misleading on large screens.

### Fixed
- Fixed missing input field IDs after removing the old "safety zone" display, which prevented the engine from starting.

## [3.0.1-beta] - 2026-04-02

### Changed
- Fixed terminology confusion: corrected swapped "positive/negative parallax" labels in the UI.

### Fixed
- Fixed budget bar visual bug where a 9% grey gap remained at the end due to a 1.1× overflow multiplier.

## [3.0.0-beta] - 2026-04-02

> ⚠️ Note: Beta release with known issues.

### Added
- Added "ZPS dual‑direction parallax constraint engine" – independent positive (behind screen) and negative (in front of screen) limits.
- Added "IPD Hard Lock" – caps physical parallax at the average human interpupillary distance to prevent eye divergence.
- Added algorithm bottleneck diagnosis – automatically indicates whether foreground negative or background positive parallax limits the IA.

### Changed
- Improved "1/30 rule" comparison module – intelligently evaluates its applicability for telephoto, wide‑angle, and large‑screen scenarios.
- Refactored drag‑and‑drop collision system with a "bidirectional snowplow" physics engine to eliminate dead zones during close‑up dragging.

### Known Issues
- Minor coordinate drift in the drag physics engine under extreme N/S/L values.
- On mobile devices, the poster rendering modal may be occluded when many accordion panels are expanded.

## [2.2.0] - 2026-04-01

### Added
- Dual‑mode data output: one‑click copy of ASCII on‑set slate and local export of 9:16 HD data poster.

### Changed
- Responsive UI now switches to two‑column layout on desktop.
- Exported poster filename includes focal length, IA, and date.
- Redesigned 8 core parameter SVG icons for better visual professionalism.

### Fixed
- Fixed poster cropping on narrow mobile screens (viewport scaling engine).
- Fixed modal not closing when tapping on background overlay.

## [2.1.0] - 2026-04-01

### Added
- Added "Timeline Resolution" parameter to calculate exact pixel shift for post‑production.
- Added "Angular Parallax" mode – calculates physical limits based on viewing distance and max allowable angle.

### Changed
- Expanded cinema camera presets (Alexa 35, RED V-Raptor) and delivery resolutions (2K/4K DCI Scope).

## [2.0.0] - 2026-03-31

### Added
- Added 1D depth visualizer track.
- Draggable markers for Near (N), Subject (S), Far (L) with 60fps real‑time feedback.

### Changed
- Replaced markers with intuitive emoji icons (🌷 Near, 👤 Subject, ⛰️ Far) and white borders.

## [1.2.0] - 2026-03-30

### Added
- Added home/professional screen presets (27" monitor, 10m cinema screen).
- Added mobile sensor presets (iPhone Pro main camera, 1‑inch type, mainstream mirrorless).

### Changed
- Default absolute parallax cap increased to 50mm.

## [1.1.0] - 2026-03-29

### Added
- Added Davis shallow depth‑of‑field protection (enforces L ≥ 2N).
- Added HIT physical shift (mm) calculation.
- Added hidden accordion panel for production/post guidelines.

### Fixed
- Unified calculation logic – fully switched to parallel rig (no toe‑in) with post‑cropping.

## [1.0.0] - 2026-03-28

### Added
- Initial release: Bercovitz‑based IA calculation.
- 3% screen‑width global parallax tolerance helper.
- Smart rig type suggestion (beamsplitter vs. side‑by‑side).

</details>

<br>

---
