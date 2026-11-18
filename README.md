<p align="center">
  <a href="https://getartcraft.com/">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="docs/brand/artcraft-logo-white.svg">
      <img alt="ArtCraft" src="docs/brand/artcraft-logo.svg" width="200">
    </picture>
  </a>
</p>

<p align="center">
  <img src="assets/app-icon/hicolor/256x256/apps/ai.storyteller.photocraft.png" width="128" height="128" alt="PhotoCraft 图标：蓝色方砖上的九尾狐浮雕">
</p>

<h1 align="center">PhotoCraft</h1>

<p align="center">
  <b>图像编辑软件：以纯 Rust 从零实现，通过净室方式重新实现 Adobe Photoshop 的功能，完全开源。</b><br>
  支持图层、蒙版、调整图层、图层样式、文字、矢量、画笔，以及真正的 PSD 文件，<br>
  全部集成在纯 Rust 编写的原生应用中。开源、离线运行，由你掌控。
</p>

<p align="center">
  <img alt="100% Rust" src="https://img.shields.io/badge/100%25-Rust-b7410e?style=flat-square&logo=rust">
  <img alt="macOS · Windows · Linux · FreeBSD · Web" src="https://img.shields.io/badge/macOS%20%C2%B7%20Windows%20%C2%B7%20Linux%20%C2%B7%20FreeBSD%20%C2%B7%20Web-native-2f7bf5?style=flat-square">
  <img alt="许可证：MIT 或 Apache-2.0" src="https://img.shields.io/badge/license-MIT%20%2F%20Apache--2.0-3a3a3a?style=flat-square">
  <img alt="状态：早期 Alpha 测试版" src="https://img.shields.io/badge/status-early%20alpha-d69e2e?style=flat-square">
  <br>
  <a href="https://sonarcloud.io/project/overview?id=storytold_photocraft"><img alt="由 SonarCloud 扫描" src="https://img.shields.io/badge/Scanned_by-SonarCloud-4b9fd5?style=flat-square&logo=sonarqubecloud&logoColor=white"></a>
  <a href="https://coderabbit.ai"><img alt="由 CodeRabbit 审查" src="https://img.shields.io/coderabbit/prs/github/storytold/photocraft?style=flat-square&label=Reviewed%20by%20CodeRabbit&logo=coderabbit"></a>
</p>

<p align="center">
  <a href="https://discord.gg/artcraft"><img alt="加入 Discord 上的 ArtCraft 社区" src="https://img.shields.io/badge/Join%20us%20on%20Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white" height="40"></a>
</p>

<p align="center">
  <a href="https://getartcraft.com/apps/photocraft"><b>访问 PhotoCraft 产品主页</b></a> ·
  <a href="https://getartcraft.com/">ArtCraft</a> ·
  <a href="https://getartcraft.com/apps">所有创作应用</a>
</p>

<br>

<p align="center">
  <img src="docs/images/photocraft-demo.jpg" alt="PhotoCraft 编辑《神奈川冲浪里》：带投影的说明卡片、标题和署名文字图层、自然饱和度与曲线调整，以及覆盖直方图的曲线编辑器" width="100%">
  <br>
  <sub>带投影的说明卡片、可编辑文字及自然饱和度和曲线调整图层，曲线编辑器处于打开状态。<br><i>神奈川冲浪里</i>，葛饰北斋，约 1831 年</sub>
</p>

> [!NOTE]
> **ArtCraft 是汇聚各领域艺术家的社区。**数字艺术、生成式创作、音乐、游戏——只要你在创造，你就是我们的一员。**[来 Discord 打个招呼吧](https://discord.gg/artcraft)。**

<p align="center">
  <a href="#features">功能亮点</a> ·
  <a href="#everything-in-the-box">完整功能</a> ·
  <a href="#psd-without-compromise">PSD</a> ·
  <a href="#built-for-agents">智能体</a> ·
  <a href="#under-the-hood">技术架构</a> ·
  <a href="#get-started">快速开始</a> ·
  <a href="#downloads">下载</a> ·
  <a href="#the-crafting-apps">创作工具系列</a> ·
  <a href="https://discord.gg/artcraft">Discord</a>
</p>

<br>

<table>
  <tr>
    <td width="25%" valign="top">
      <h3>🎛️ 熟悉的操作体验</h3>
      菜单、快捷键、面板和工具都位于你熟悉的位置，从 ⌘J 到 ⇧⌘D。如果你熟悉 Photoshop，就能迅速上手 PhotoCraft。
    </td>
    <td width="25%" valign="top">
      <h3>⚡ 原生且高效</h3>
      基于 wgpu 的 GPU 合成器，支持 Metal、Vulkan、DX12 和 WebGPU；搭配写时复制图块及多线程滤镜。没有 Electron，没有内嵌网页视图，响应迅速。
    </td>
    <td width="25%" valign="top">
      <h3>🗂️ 真正的 PSD 文件</h3>
      打开、编辑并保存分层 Photoshop 文档。在 psd-tools 的 309 个测试文件中，307 个文件重新保存后仍保持相同的渲染结果。
    </td>
    <td width="25%" valign="top">
      <h3>🤖 支持智能体操作</h3>
      每项操作都是命令，因此可以通过界面、命令行、JSON 控制通道或 MCP 服务器驱动同一个引擎。
    </td>
  </tr>
</table>

<br>

<a id="features"></a>

## 功能亮点

此处每张截图均来自真实应用：使用公有领域艺术作品，通过控制通道进行离屏渲染。

<table>
  <tr>
    <td width="50%" valign="top">
      <img src="docs/images/photocraft-adjustments.jpg" alt="《日出·印象》与色阶、自然饱和度调整图层，右侧打开色阶编辑器及显示均值、标准差和中位数的直方图面板" width="100%">
      <br>
      <sub>色阶和自然饱和度调整图层，以及实时直方图面板。<br><i>日出·印象</i>，克洛德·莫奈，1872 年</sub>
      <h3>随时调整，无损编辑</h3>
      调整图层让每次修改都保持可编辑。叠加色阶、曲线、自然饱和度、色相/饱和度等十余种调整，使用蒙版限定区域、改变顺序或关闭效果，原始像素始终保持不变。
      <br><br>
      <b>16 种调整图层</b>，也可直接作用于像素，包括支持分通道编辑的曲线、带实时直方图的色阶、黑白、通道混合器、渐变映射、照片滤镜、可选颜色及颜色查找（.cube、.3dl、.look）。还提供阴影/高光、替换颜色、匹配颜色、HDR 色调、去色和色调均化。
    </td>
    <td width="50%" valign="top">
      <img src="docs/images/photocraft-layer-styles.jpg" alt="《地出》照片上的 EARTHRISE 文字图层正在编辑外发光，同时启用描边" width="100%">
      <br>
      <sub>在图层样式对话框中为可编辑文字添加外发光和描边。<br><i>地出</i>，威廉·安德斯 / NASA，1968 年</sub>
      <h3>让画面更出彩的样式</h3>
      投影、内阴影、外发光、内发光、斜面和浮雕、光泽、描边，以及颜色、渐变和图案叠加，都可实时应用于任意图层，包括文字。图案来自图案库（内置图案、“编辑 › 定义图案”、<code>.pat</code> 导入/导出）以及 PSD 的 <code>Patt</code> 数据块。
      <br><br>
      可在图层之间复制粘贴样式，一次隐藏全部效果，也能直接读取 PSD 中的样式，并以匹配 Photoshop 的方式渲染。
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <img src="docs/images/photocraft-masks.jpg" alt="《戴珍珠耳环的少女》面部周围的椭圆选区，以及让面部以外区域变灰的色相/饱和度图层蒙版" width="100%">
      <br>
      <sub>椭圆选区转换为色相/饱和度图层的蒙版，让只有面部保留颜色。<br><i>戴珍珠耳环的少女</i>，约翰内斯·维米尔，约 1665 年</sub>
      <h3>理解图像的选区工具</h3>
      使用选框、套索和魔棒精确选择；使用快速选择、对象选择及选择主体让电脑自动勾选；使用“选择并遮住”细化发丝级边缘。
      <br><br>
      支持羽化、扩展、收缩、平滑、扩大选取和重新选择。任何选区都可转换为图层蒙版、矢量路径或形状。智能选择在本机运行，无需云端或账号。
    </td>
    <td width="50%" valign="top">
      <img src="docs/images/photocraft-type.jpg" alt="《加利福尼亚内华达山脉之间》上的 Georgia 字体标题、署名及段落文字，字符与段落控件已打开" width="100%">
      <br>
      <sub>在画布中直接编辑标题，同时排版署名和正文段落。<br><i>加利福尼亚内华达山脉之间</i>，阿尔伯特·比尔施塔特，1868 年</sub>
      <h3>精美的文字排版</h3>
      直接在画布上编辑点文字和段落文字，完整支持字符与段落设置：字体、字重、字号、行距、字距、对齐和颜色。<a href="docs/color-picker.md">完整的文字拾色器</a>还支持带像素放大镜的屏幕取色。
      <br><br>
      文字图层保持可编辑，支持图层样式，并可通过 PSD 格式保存后再次读取。
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <img src="docs/images/photocraft-vector.jpg" alt="《睡莲》上的莲花、水、太阳、徽章和点状圆环形状图层，莲花路径锚点已选中" width="100%">
      <br>
      <sub>由形状图层组成的徽章：渐变填充的莲花、星形和点状圆环。<br><i>睡莲</i>，克洛德·莫奈，1906 年</sub>
      <h3>像素级精准的矢量图形</h3>
      支持矩形、椭圆、三角形、多边形、直线，以及钢笔、自由钢笔和弯度钢笔工具；形状图层不受分辨率限制，支持渐变填充、虚线及描边对齐。
      <br><br>
      组合形状（联合、减去、相交、排除），在路径面板中保存路径，将其用作矢量蒙版，或对路径描边和填充。PSD 样本库中的 116 个形状图层全部达到与 Photoshop 像素一致的效果。
    </td>
    <td width="50%" valign="top">
      <img src="docs/images/photocraft-filters.jpg" alt="《星月夜》椭圆选区内实时预览角度 320 度的旋转扭曲滤镜" width="100%">
      <br>
      <sub>旋转扭曲滤镜仅在选区内实时预览。<br><i>星月夜</i>，文森特·梵高，1889 年</sub>
      <h3>应用之前，实时预览</h3>
      每个滤镜对话框都会在画布上实时预览，并遵循当前选区。包括模糊（高斯、方框、动感、径向、表面、智能、镜头、形状，以及模糊画廊中的移轴、光圈、场景、旋转和路径模糊）、锐化、减少杂色、扭曲（旋转扭曲、波浪、波纹、置换、切变、水波等）、像素化、风格化（油画、风、凸出等）、渲染（云彩、纤维、镜头光晕、光照效果）等。
      <br><br>
      在智能对象上应用滤镜后仍可随时编辑：修改、隐藏、重新排序或添加蒙版。
      <br><br>
      大半径模糊通过运行和算法的方框滤波遍历利用所有核心：对 360 万像素图像应用半径 180 的高斯模糊，耗时不到一秒。
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <img src="docs/images/photocraft-transform.jpg" alt="《提顿山与蛇河》旋转副本周围的自由变换控制柄，历史面板显示打开、复制图层及自由变换等操作" width="100%">
      <br>
      <sub>对旋转的照片进行自由变换，历史记录列出每一步操作。<br><i>提顿山与蛇河</i>，安塞尔·亚当斯，1942 年</sub>
      <h3>自由变换，随心塑形</h3>
      自由变换支持缩放、旋转、斜切、扭曲和透视，以及精确的 90°、180° 旋转、翻转和再次变换。图层、文字、形状、蒙版及选区可一起变换。
      <br><br>
      完整历史记录、“切换上一个状态”和历史记录画笔让每一步都能撤销，甚至可以逐笔撤销。
    </td>
    <td width="50%" valign="top">
      <img src="docs/images/photocraft-export-light.jpg" alt="《吻》上方的浅色主题导出对话框：JPG 质量 90、缩放 50%，提供预览及约 684K 文件大小估算" width="100%">
      <br>
      <sub>浅色主题下的“导出为”对话框，包含预览与文件大小估算。<br><i>吻</i>，古斯塔夫·克里姆特，1907–1908 年</sub>
      <h3>轻松导出，随处使用</h3>
      “导出为”支持格式、质量、透明度和缩放设置，同时提供预览及即时文件大小估算。也可一键快速导出 PNG。
      <br><br>
      可选深色 Pro 主题、清爽的 Studio 主题或 Classic 经典外观。
    </td>
  </tr>
</table>

<br>

<a id="everything-in-the-box"></a>

## 完整功能

<table>
  <tr>
    <td width="33%" valign="top">
      <h4>🧰 69 种工具</h4>
      移动 · 画板 · 矩形和椭圆选框 · 单行选框 · 单列选框 · 套索 · 多边形套索 · 磁性套索 · 对象选择 · 快速选择 · 魔棒 · 裁剪 · 透视裁剪 · 切片 · 切片选择 · 图框 · 吸管 · 颜色取样器 · 标尺 · 注释 · 计数 · 移除 · 污点修复画笔 · 修复画笔 · 修补 · 内容识别移动 · 红眼 · 画笔 · 铅笔 · 混合器画笔 · 颜色替换 · 仿制图章 · 图案图章 · 历史记录画笔 · 历史记录艺术画笔 · 橡皮擦 · 背景橡皮擦 · 魔术橡皮擦 · 渐变 · 油漆桶 · 模糊 · 锐化 · 涂抹 · 减淡 · 加深 · 海绵 · 钢笔 · 自由钢笔 · 弯度钢笔 · 添加锚点 · 删除锚点 · 转换点 · 横排和直排文字 · 横排和直排文字蒙版 · 路径选择 · 直接选择 · 矩形 · 椭圆 · 三角形 · 多边形 · 星形 · 直线 · 自定形状 · 抓手 · 旋转视图 · 缩放
    </td>
    <td width="33%" valign="top">
      <h4>🖌️ 完善的画笔引擎</h4>
      支持形状动态、散布、纹理、双重画笔、颜色动态、传递、画笔笔势、湿边、建立和平滑（包括拉绳模式），由笔压、倾斜、旋转和方向驱动。支持画笔预设、从选区定义画笔，以及确定性、可重放的笔触。
    </td>
    <td width="33%" valign="top">
      <h4>🗃️ 完整的图层系统</h4>
      支持组、剪贴蒙版、像素及矢量蒙版、填充图层（纯色、渐变、图案）、调整图层、带智能滤镜及无损变换和变形的实时智能对象；支持多图层选择、对齐、分布及链接，Alpha 通道和快速蒙版；提供 27 种 Photoshop 混合模式和 6 种 Paint.NET 变体，不透明度与填充、锁定、颜色标签、图层类型筛选、合并、拼合、栅格化、通过拷贝/剪切建立图层及贴入。
    </td>
  </tr>
  <tr>
    <td width="33%" valign="top">
      <h4>🎨 多种颜色模式与位深</h4>
      支持 RGB、灰度、CMYK 和 Lab 文档，每通道可用 8、16 或 32 位。位深和颜色模型由运行时数据决定，因此每种工具都可用于各种位深。
      <br><br>
      纯 Rust 实现完整 ICC 色彩管理：嵌入配置文件、指定和转换配置文件，支持全部四种渲染意图和黑点补偿；GPU 上执行软打样（⌘Y）和色域警告（⇧⌘Y）。
    </td>
    <td width="33%" valign="top">
      <h4>🗂️ 文件格式</h4>
      支持 PSD、PSB，以及分层 TIFF（TIFF 内嵌 Photoshop 图层数据，支持两种字节序读写）；<a href="docs/pdn.md">Paint.NET PDN3（只读，支持可编辑图层和全部 14 种混合模式）</a>；<a href="docs/ora.md">OpenRaster（可读写，支持图层、组和混合模式，适用于 Krita、MyPaint 和 GIMP）</a>；<a href="docs/xcf.md">GIMP XCF（只读，支持图层、组、蒙版、混合模式、通道和选区）</a>；<a href="docs/kra.md">Krita .kra（只读，支持绘画图层、组、混合模式和透明度蒙版）</a>；SVG（打开为形状图层，置入为矢量智能对象）。还支持平面 PNG、JPEG、TIFF、WebP（有损和无损）、GIF、BMP、TGA、ICO、QOI、PNM、OpenEXR、Radiance HDR 和 FITS（天文图像：8/16 位和 32 位浮点、灰度或 RGB，保留文件头），以及原生 <code>.pcraft</code> 格式。平面格式保留其支持的位深：PNG 保留 8/16 位采样，TIFF 保留 8/16 位和 32 位浮点采样，OpenEXR 保留半精度/浮点采样；JPEG、WebP 等 8 位格式会降低更高位深采样，并在导出时提示。各格式详情见<a href="https://github.com/storytold/craft-libs/tree/main/crates/image-codecs#capability-matrix-default-build">编解码能力矩阵</a>。iPhone 和 Mac 的 HEIC 照片仅支持读取（官方构建包含；源码构建可选 <code>--features heif</code>）。AVIF 仅支持写入，需启用可选的 <code>avif</code> 构建特性；暂不支持 AVIF 解码及 JPEG XL。Affinity 文档（<code>.af</code>、<code>.afdesign</code>、<code>.afphoto</code>、<code>.afpub</code>）可原生只读打开，支持画板、图层、矢量、文字、图像和蒙版；效果、调整等未支持内容会列于警告中，不支持导出 Affinity 格式。
    </td>
    <td width="33%" valign="top">
      <h4>🪄 日常必备功能</h4>
      自动色调、对比度和颜色 · 色调均化 · 图像大小和画布大小 · 裁剪和裁切 · 显示全部 · 编辑 › 填充和描边 · 合并拷贝 · 原位粘贴 · 参考线、标尺、网格与吸附 · 动作录制和回放 · 命令面板（⌘F）。
    </td>
  </tr>
</table>

<br>

<a id="psd-without-compromise"></a>

## 完整的 PSD 支持

PhotoCraft 的 PSD 支持由独立 crate 提供，根据 Adobe 公开规范编写，并使用真实文件样本集进行测试。

- **忠实的读写往返：**打开后重新保存文档，psd-tools 测试集的 309 个文件中有 307 个、混合 ag-psd/psd-tools 测试集的 170 个文件中有 169 个保持相同渲染结果（见 `crates/io/tests/it/corpus.rs`；用 `cargo xtask corpus --psd-tools` 获取 psd-tools 样本集）。尚未建模的数据（原始数据块、描述符、附加数据）会保留而非丢弃。重新保存的文件并非逐字节等同于原文件：PhotoCraft 会重写图像资源、图层记录和合成图像。只有独立的 `craft-psd` crate 在不经过文档模型、直接解析与写入文件时，才会逐字节重现所有可解析的样本文件（`craft-psd/tests/it/corpus.rs`）。
- **像素匹配：**合成结果基准测试会将本项目的渲染与 Photoshop 自身的合并图像比较，覆盖渐变插值（经典、感知、线性）、图层效果、形状描边、剪贴及填充不透明度。
- **大型文档：**原生打开 PSB、16 位及 32 位文件，以及 CMYK 和 Lab 文档。

<a id="built-for-agents"></a>

## 为智能体而设计

每个菜单项、工具和对话框都会调用统一注册表中的命令，其中包含 500 多条命令。界面、CLI、JSON 控制通道和 MCP 服务器共用这些命令，因此任何能点击完成的操作，脚本或 AI 智能体也能完成。

```sh
# 无界面模式：打开、编辑、保存
photocraft-cli run wave.psd \
  --cmd filter.sharpen.smartSharpen     --params '{"amount":80}' \
  --cmd layer.newAdjustmentLayer.curves --params '{"points":[[0,0],[64,48],[192,212],[255,255]]}' \
  --out wave-final.png

# 将同一动作列表应用于整个图像文件夹
photocraft-cli batch --actions grade.json --in ./raw --out ./graded

# 查看各子命令的帮助
photocraft-cli batch --help

# 让智能体通过 MCP 操作（无界面模式，或桥接正在运行的应用）
photocraft-cli mcp
```

桌面应用还提供经过身份验证、仅限回环地址的控制通道（`photocraft --control`），用于检查界面状态、以指针事件操作工具及获取离屏截图。本 README 中的每张图像都由此生成。详见 [`docs/control-protocol.md`](docs/control-protocol.md)。

<a id="under-the-hood"></a>

## 技术架构

- **引擎优先：**纯数据文档模型与命令引擎，上层仅保留轻量 egui 界面。24 个 crate 之间在构建时强制执行分层约束。
- **双合成器：**CPU 合成器作为参考基准，wgpu 合成器负责 GPU 画布渲染，两者相互对照测试。
- **写时复制图块：**256² 稀疏图块降低撤销成本，让超大画布也保持轻量；效果映射按图层状态缓存。
- **浏览器运行：**整个引擎和界面均可编译为 WebAssembly。
- **净室实现：**仅根据公开规范和观察到的行为实现，不含专有代码、着色器或素材。
- **充分测试：**超过 1,700 项测试，涵盖 PSD 读写往返、合成样本生成器、合成器参考验证和多位深检查。

<a id="get-started"></a>

## 快速开始

```sh
git clone https://github.com/storytold/photocraft
cd photocraft
cargo run --release -p photocraft -- image.psd   # 桌面应用
cargo test --workspace                           # 测试套件
```

界面和文字工具使用的日文字体来自 [craft-fonts](https://github.com/storytold/craft-fonts)，属于可选构建输入（桌面发行构建始终包含）。缺少时，PhotoCraft 使用系统的中日韩字体：

```sh
git clone https://github.com/storytold/craft-fonts ../craft-fonts
CRAFT_FONTS_DIR="$PWD/../craft-fonts" cargo run --release -p photocraft
```

新贡献者和 AI 智能体：请先阅读 [`AGENTS.md`](AGENTS.md)，再阅读 [`docs/`](docs/)。

每次 [GitHub 发布](https://github.com/storytold/photocraft/releases)均附带 macOS、Windows、Linux、FreeBSD 和 Web 版本。Linux 可选择 AppImage、`.deb`、`.rpm`、tar 压缩包或 Flatpak 包。Flatpak 需要 [Flathub](https://flathub.org/setup) 的 freedesktop 运行时，安装时 `flatpak` 会提示一并安装：

```sh
flatpak install --user photocraft-<version>-linux-x86_64.flatpak   # 或 -linux-aarch64
flatpak run ai.storyteller.photocraft
```

Flatpak 通过宿主机的 CUPS 套接字打印（“文件 › 打印”直接使用 IPP，无需 `lp`）；没有 CUPS 或打印机时，通过打印门户打开系统打印对话框。参见[打印说明](docs/printing.md)。

AppImage 无需安装：首次运行会在 `~/.local/share` 注册启动器图标和菜单项，让 Wayland 的程序坞显示 PhotoCraft 图标。设置 `PHOTOCRAFT_NO_DESKTOP_INTEGRATION=1` 可跳过此步骤；撤销方法见 [`docs/releasing.md`](docs/releasing.md) 的 Linux 部分。

使用内置 CLI：运行 `./photocraft-<version>-linux-x86_64.AppImage --cli --help`；使用 `--cli mcp` 则通过标准输入输出启动 MCP 服务器。CLI 启动不进行桌面集成。名为 `photocraft-cli` 的符号链接也会启用 CLI，见 [`docs/development.md`](docs/development.md#headless-cli)。

Wayland 会话中暂不支持将文件拖入窗口打开：egui 底层窗口库 winit 0.30 尚不支持 Wayland 拖放（#386）。请使用“文件 › 打开”，或在文件管理器中复制图像后按 Ctrl+V 粘贴。若需拖放，可通过 XWayland 启动：`WAYLAND_DISPLAY= photocraft`、`WAYLAND_DISPLAY= ./photocraft-<version>-linux-x86_64.AppImage`，或 `flatpak run --nosocket=wayland --socket=x11 ai.storyteller.photocraft`。Wayland 下会显示适用于当前安装方式的命令提示，直至你关闭提示。在“首选项 › 性能 › Linux 显示服务器”中设为 X11，可每次使用相同方式启动。采用 125%、150%、175% 等分数缩放时，XWayland 窗口先以较低分辨率绘制，再由合成器放大，界面会模糊；原生 Wayland 则保持清晰（#1072）。

macOS 命令行工具打包为 `photocraft-cli-<version>-macos-universal.zip`。二进制文件使用与应用相同的 Developer ID 签名，并经过 Apple 公证。独立二进制文件不像 DMG 那样能够附带公证票据，因此首次运行时 macOS 会联网验证。可自行检查：

```sh
ditto -x -k photocraft-cli-<version>-macos-universal.zip .
spctl --assess --type install -vv photocraft-cli-<version>-macos-universal/photocraft-cli
# ... accepted, source=Notarized Developer ID
```

FreeBSD 14（x86_64）发行包采用类似 `/usr/local` 的目录结构。先安装运行库，再解压到该目录：

```sh
pkg install libxkbcommon wayland libX11 libXcursor libXrandr libXi libxcb mesa-libs vulkan-loader gtk3 fontconfig freetype2 alsa-lib
tar -xzf photocraft-<version>-freebsd-x86_64.tar.gz --strip-components 1 -C /usr/local
photocraft
```

维护者：发布版本的构建、签名及发布流程见 [`docs/releasing.md`](docs/releasing.md)。

> [!IMPORTANT]
> **状态：**PhotoCraft 处于早期 Alpha 阶段。我们希望如实说明：虽然已以不同程度实现 Photoshop 的大量功能，**它尚不能替代 Photoshop 承担日常专业工作**。主要缺口包括 AI/生成式功能、15 种尚未实现的工具、文字排版和专业工作流的深度，以及插件兼容性。每个 Photoshop 菜单项都已连接到命令（[`docs/parity-checklist.md`](docs/parity-checklist.md)），但这仅代表命令接入，并不代表行为一致。逐项评估及后续方向详见[路线图](ROADMAP.md)和[功能对等评估](docs/target-app-parity.md)。可能仍有不完善之处，欢迎提交问题，并附上操作系统、文档大小、图层数量及截图。也可在 [Discord](https://discord.gg/artcraft) 反馈故障。

## 社区软件包

这些安装包由社区成员维护，而非 PhotoCraft 团队。

Gentoo 用户可通过 [::snakebyte overlay](https://github.com/switch87/snakebyte-overlay) 安装 Linux 发行包 `media-gfx/photocraft-bin`：

```sh
eselect repository add snakebyte git https://github.com/switch87/snakebyte-overlay.git
emaint sync -r snakebyte
echo 'media-gfx/photocraft-bin ~amd64' >> /etc/portage/package.accept_keywords/photocraft
emerge --ask media-gfx/photocraft-bin
```

## 文档

开发、架构、自动化、格式及安全文档集中维护于 [PhotoCraft 文档手册](book/)。

使用 Docker 自托管浏览器版本，请参阅 [Docker Web 托管](packaging/web/README.md#docker)。

## 安全

安全架构、威胁建模、解析器加固、模糊测试和漏洞报告，见[安全文档](book/src/security/)及仓库的[安全政策](SECURITY.md)。

## 测试样本集

PhotoCraft 使用真实文件测试：既包括 [photocraft-corpus](https://github.com/storytold/photocraft-corpus) 中由 Photoshop 制作的参考 PSD，也包括 psd-tools、ag-psd 和 PngSuite 样本集。所有样本均固定版本并通过 SHA256 校验。使用 `cargo xtask corpus --all` 获取，使用 `cargo xtask test-corpus` 测试，详见 [开发文档](docs/development.md#test-corpora)。

<a id="downloads"></a>

## 下载

**初次使用 PhotoCraft？**请前往 [getartcraft.com 上的 PhotoCraft 页面](https://getartcraft.com/apps/photocraft)下载，这是最简单的安装方式。

**需要特定构建或格式？**GitHub 的[最新版本](https://github.com/storytold/photocraft/releases/latest)包含下表所有构建；[全部版本](https://github.com/storytold/photocraft/releases)提供历史版本及发布说明。文件名中的 `<ver>` 表示版本号，`SHA256SUMS.txt` 列出了每个文件的校验和。

### Windows

| 架构 | 安装包 | 便携版 |
|---|---|---|
| x64（64 位 Intel/AMD） | `photocraft-<ver>-windows-x64.msi` | `photocraft-<ver>-windows-x64-portable.zip` |
| arm64（骁龙及其他 ARM 电脑） | `photocraft-<ver>-windows-arm64.msi` | `photocraft-<ver>-windows-arm64-portable.zip` |
| x86（32 位） | `photocraft-<ver>-windows-x86.msi` | `photocraft-<ver>-windows-x86-portable.zip` |

安装包和可执行文件均经过代码签名。

### macOS

| 构建 | 文件 | 说明 |
|---|---|---|
| 应用，通用版（Apple 芯片 + Intel） | `photocraft-<ver>-macos-universal.dmg` | 已签名并公证 |
| 命令行工具，通用版 | `photocraft-cli-<ver>-macos-universal.zip` | 已签名并公证 |

### Linux

| 格式 | x86_64 | aarch64（ARM64） | 说明 |
|---|---|---|---|
| AppImage | `photocraft-<ver>-linux-x86_64.AppImage` | `photocraft-<ver>-linux-aarch64.AppImage` | 可直接运行；通过以下工具自动更新： [AppImageUpdate](https://github.com/AppImageCommunity/AppImageUpdate) （`.zsync` 文件） |
| Flatpak | `photocraft-<ver>-linux-x86_64.flatpak` | `photocraft-<ver>-linux-aarch64.flatpak` | 沙盒运行； `flatpak install --user <file>` |
| Debian/Ubuntu | `photocraft-<ver>-linux-x86_64.deb` | `photocraft-<ver>-linux-aarch64.deb` | |
| Fedora/RHEL/openSUSE | `photocraft-<ver>-linux-x86_64.rpm` | `photocraft-<ver>-linux-aarch64.rpm` | |
| tar 压缩包 | `photocraft-<ver>-linux-x86_64.tar.gz` | `photocraft-<ver>-linux-aarch64.tar.gz` | 可解压至任意位置 |

RISC-V（riscv64）：仅提供 `photocraft-<ver>-linux-riscv64.tar.gz`，基于 Ubuntu 24.04 构建，需要 glibc 2.39 或更新版本。

### FreeBSD

| 架构 | 文件 |
|---|---|
| x86_64 | `photocraft-<ver>-freebsd-x86_64.tar.gz` |

### Web (WebAssembly)

| 构建 | 文件 | 说明 |
|---|---|---|
| 静态站点 | `photocraft-web-<ver>.zip` | 在现代浏览器运行，可托管于任意静态服务器 |

<a id="the-crafting-apps"></a>

## Crafting Apps 创作工具系列

PhotoCraft 是 **Crafting Apps** 的一员。这是 [ArtCraft](https://getartcraft.com/) 团队打造的免费开源创作工具系列，每款都以 Rust 从零编写，也都能独立使用。

| | 应用 | 用途 | 源码 | 了解更多 |
|:-:|---|---|---|---|
| <img src="https://raw.githubusercontent.com/storytold/photocraft/main/assets/app-icon/hicolor/64x64/apps/ai.storyteller.photocraft.png" alt="" width="32" height="32"> | **PhotoCraft** | 图像编辑：图层、蒙版、文字及真正的 PSD 文件 | [GitHub](https://github.com/storytold/photocraft) | [官网](https://getartcraft.com/apps/photocraft) |
| <img src="https://raw.githubusercontent.com/storytold/vectorcraft/main/assets/app-icon/hicolor/64x64/apps/ai.storyteller.vectorcraft.png" alt="" width="32" height="32"> | **VectorCraft** | 矢量插画 | [GitHub](https://github.com/storytold/vectorcraft) | [官网](https://getartcraft.com/apps/vectorcraft) |
| <img src="https://raw.githubusercontent.com/storytold/filmcraft/main/assets/app-icon/hicolor/64x64/apps/ai.storyteller.filmcraft.png" alt="" width="32" height="32"> | **FilmCraft** | 视频剪辑、调色与声音处理 | [GitHub](https://github.com/storytold/filmcraft) | [官网](https://getartcraft.com/apps/filmcraft) |
| <img src="https://raw.githubusercontent.com/storytold/lightcraft/main/assets/app-icon/hicolor/64x64/apps/ai.storyteller.lightcraft.png" alt="" width="32" height="32"> | **LightCraft** | 照片管理与 RAW 显影 | [GitHub](https://github.com/storytold/lightcraft) | [官网](https://getartcraft.com/apps/lightcraft) |
| <img src="https://raw.githubusercontent.com/storytold/pdfcraft/main/assets/app-icon/hicolor/64x64/apps/ai.storyteller.pdfcraft.png" alt="" width="32" height="32"> | **PdfCraft** | PDF 阅读、整理与保护 | [GitHub](https://github.com/storytold/pdfcraft) | [官网](https://getartcraft.com/apps/pdfcraft) |
| <img src="https://raw.githubusercontent.com/storytold/effectcraft/main/assets/app-icon/hicolor/64x64/apps/ai.storyteller.effectcraft.png" alt="" width="32" height="32"> | **EffectCraft** | 动态图形与视觉特效 | [GitHub](https://github.com/storytold/effectcraft) | [官网](https://getartcraft.com/apps/effectcraft) |
| <img src="https://raw.githubusercontent.com/storytold/designcraft/main/assets/app-icon/hicolor/64x64/apps/ai.storyteller.designcraft.png" alt="" width="32" height="32"> | **DesignCraft** | 页面排版与出版 | [GitHub](https://github.com/storytold/designcraft) | [官网](https://getartcraft.com/apps/designcraft) |
| <img src="https://raw.githubusercontent.com/storytold/figcraft/main/assets/app-icon/hicolor/64x64/apps/ai.storyteller.figcraft.png" alt="" width="32" height="32"> | **FigCraft** | 界面设计与原型制作 | [GitHub](https://github.com/storytold/figcraft) | [官网](https://getartcraft.com/apps/figcraft) |
| <img src="https://raw.githubusercontent.com/storytold/wordcraft/main/assets/app-icon/hicolor/64x64/apps/ai.storyteller.wordcraft.png" alt="" width="32" height="32"> | **WordCraft** | 文字处理与文档 | [GitHub](https://github.com/storytold/wordcraft) | [官网](https://getartcraft.com/apps/wordcraft) |
| <img src="https://raw.githubusercontent.com/storytold/soundcraft/main/assets/app-icon/hicolor/64x64/apps/ai.storyteller.soundcraft.png" alt="" width="32" height="32"> | **SoundCraft** | 音频录制与编辑 | [GitHub](https://github.com/storytold/soundcraft) | [官网](https://getartcraft.com/apps/soundcraft) |
| <img src="https://raw.githubusercontent.com/storytold/deckcraft/main/assets/app-icon/hicolor/64x64/apps/ai.storyteller.deckcraft.png" alt="" width="32" height="32"> | **DeckCraft** | 演示文稿与幻灯片 | [GitHub](https://github.com/storytold/deckcraft) | [官网](https://getartcraft.com/apps/deckcraft) |
| <img src="https://raw.githubusercontent.com/storytold/cadcraft/main/assets/app-icon/hicolor/64x64/apps/ai.storyteller.cadcraft.png" alt="" width="32" height="32"> | **CADCraft** | 计算机辅助设计 | [GitHub](https://github.com/storytold/cadcraft) | [官网](https://getartcraft.com/apps/cadcraft) |
| <img src="https://raw.githubusercontent.com/storytold/gridcraft/main/assets/app-icon/hicolor/64x64/apps/ai.storyteller.gridcraft.png" alt="" width="32" height="32"> | **GridCraft** | 电子表格与数据 | [GitHub](https://github.com/storytold/gridcraft) | [官网](https://getartcraft.com/apps/gridcraft) |
| <img src="https://raw.githubusercontent.com/storytold/texturecraft/main/assets/app-icon/hicolor/64x64/apps/ai.storyteller.texturecraft.png" alt="" width="32" height="32"> | **TextureCraft** | 3D 纹理绘制 | [GitHub](https://github.com/storytold/texturecraft) | [官网](https://getartcraft.com/apps/texturecraft) |
| <img src="https://raw.githubusercontent.com/storytold/craft-anything/main/assets/app-icon/hicolor/64x64/apps/ai.storyteller.craft-anything.png" alt="" width="32" height="32"> | **Craft Anything** | 了解软件如何运作，再打造自己的软件 | [GitHub](https://github.com/storytold/craft-anything) | [官网](https://getartcraft.com/apps/craft-anything) |
| <img src="https://raw.githubusercontent.com/tangency-labs/solidcraft/main/assets/icons/app/linux/exports/hicolor/64x64/apps/io.tangencylabs.solidcraft.png" alt="" width="32" height="32"> | **SolidCraft** | Tangency Labs 开发的参数化 3D CAD（社区应用） | [GitHub](https://github.com/tangency-labs/solidcraft) | |

还有 [**ArtCraft**](https://getartcraft.com/) 本身：为希望真正掌控创作过程的艺术家提供的 AI 图像和视频工作室。

Crafting Apps 采用共同规范：净室实现、纯 Rust 编写，原生运行于 macOS、Windows 和 Linux，通过 WebAssembly 在浏览器运行，并可由智能体完整控制。

<br>

<p align="center">
  <a href="https://discord.gg/artcraft"><img alt="加入 Discord 上的 ArtCraft 社区" src="https://img.shields.io/badge/Join%20us%20on%20Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white" height="40"></a>
</p>

<h3 align="center">和我们一起创作</h3>

<p align="center">
  我们的 Discord 汇聚了绘画、摄影、插画、剪辑、排版等各类创作者，也欢迎仍在探索兴趣的人。分享你的作品、寻求帮助、报告问题，或告诉我们你希望这些工具具备哪些能力。无论使用什么媒介，无论经验多少，这里都欢迎你。
</p>

<p align="center">
  <a href="https://discord.gg/artcraft"><b>discord.gg/artcraft</b></a> ·
  <a href="https://getartcraft.com/">getartcraft.com</a> ·
  <a href="https://getartcraft.com/apps">Crafting Apps 创作工具系列</a> ·
  <a href="https://getartcraft.com/apps/photocraft">PhotoCraft</a>
</p>

---

## 许可证与致谢

PhotoCraft 采用双许可证，你可以选择 [MIT](LICENSE-MIT) 或 [Apache-2.0](LICENSE-APACHE)。
版权所有 (c) 2026 ArtCraft 团队及 PhotoCraft 贡献者。必须保留的声明见 [NOTICE](NOTICE)。

随附字体、图标、图像及其他素材保留各自的开放许可证；作者、来源和许可证逐项列于 [ATTRIBUTION.md](ATTRIBUTION.md)。

所有展示的艺术作品均属于公有领域（来源包括 Wikimedia Commons、NASA 和美国国家档案馆）；来源清单见 [`docs/images/SOURCES.md`](docs/images/SOURCES.md)。

[`docs/brand/`](docs/brand/) 中的 ArtCraft 名称、文字标识和徽标是 ArtCraft 团队的商标，不在上述许可证授权范围内。根据 [`docs/brand/LICENSE-brand.txt`](docs/brand/LICENSE-brand.txt)，仅允许在本仓库和 PhotoCraft 中原样使用，不得修改。分叉项目和修改版必须移除这些标识。

<sub>Adobe、Photoshop、Illustrator、Premiere Pro、Lightroom、Acrobat、After Effects 和 InDesign 是 Adobe Inc. 在美国和/或其他国家的商标或注册商标。PhotoCraft 是独立开源项目，与 Adobe Inc. 无关联，也未获其赞助或认可；这些名称仅用于说明兼容的工作流。</sub>

<p align="center">
  <a href="https://getartcraft.com/"><img alt="ArtCraft" src="docs/brand/artcraft-mark.svg" width="28"></a><br>
  <sub>由 <a href="https://getartcraft.com/">ArtCraft</a> 团队与社区共同打造。</sub>
</p>

## Star 历史

[![Star 历史图表](https://api.star-history.com/svg?repos=storytold/photocraft&type=Date&legend=top-left)](https://www.star-history.com/?repos=storytold%2Fphotocraft&type=date&legend=top-left)
