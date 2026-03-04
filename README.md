# Xiaomi HyperOS 4 组件规范库

从 Figma 组件自动生成**面向 AI 消费的结构化组件规范文档**。

生成的文档数值精确、结构一致，所有属性值可直接映射到 CSS，供下游 AI Agent 读取并实现代码。本库基于 **Xiaomi HyperOS 4 UI Kit** 设计系统构建，涵盖 32 个核心组件。

---

## 组件目录

### 导航与布局

在应用中提供页面间导航、层级结构展示和工具操作入口的组件。

| 组件 | 文件 | 说明 | 变体 |
|------|------|------|------|
| [标题栏 NavigationBar](component-spec/navigation-bar-component-spec.md) | `navigation-bar-component-spec.md` | 页面顶部展示标题、返回按钮和操作图标 | 4 维度, 36 变体 |
| [Pad标题栏 NavigationBarPad](component-spec/navigation-bar-pad-component-spec.md) | `navigation-bar-pad-component-spec.md` | Pad 端顶部导航栏，支持多种内容变体和材质风格 | 9 子组件集, ~40 变体 |
| [底部导航栏 BottomNavigation](component-spec/BottomNavigation-component-spec.md) | `BottomNavigation-component-spec.md` | 底部 Tab 栏、FAB 浮动按钮和渐变遮罩 | 多维度组合 |
| [侧边导航栏 Sidebar](component-spec/Sidebar-component-spec.md) | `Sidebar-component-spec.md` | 大屏设备一级/二级导航，支持三种显示尺寸和三种面板材质 | 2 维度, 9 组合 |
| [标签页 TabBar](component-spec/tab-bar-component-spec.md) | `tab-bar-component-spec.md` | 标签页导航，支持平面/浮起形态和多种材质效果 | 4 维度, 14+ 变体 |
| [底部工具栏 ToolBar](component-spec/ToolBar-component-spec.md) | `ToolBar-component-spec.md` | 浮动胶囊样式底部工具栏，支持混色模糊/纯色面板 | 3 维度 |
| [索引控件 IndexBar](component-spec/IndexBar-component-spec.md) | `IndexBar-component-spec.md` | 长列表右侧字母索引快速定位 | 1 维度, 4 变体 |
| [滚动条 ScrollBar](component-spec/ScrollBar-component-spec.md) | `ScrollBar-component-spec.md` | 竖向滚动条位置指示器 | 1 维度, 2 变体 |

### 数据录入

用于收集和编辑用户输入的表单类组件。

| 组件 | 文件 | 说明 | 变体 |
|------|------|------|------|
| [按钮 Button](component-spec/button-component-spec.md) | `button-component-spec.md` | 默认/小号/迷你按钮、按钮组和弹窗按钮组 | 5 组件集 |
| [单行输入框 Input](component-spec/Input-component-spec.md) | `Input-component-spec.md` | 支持前缀/后缀、套卡/通栏样式的文本输入框 | 4 维度, 48+ 变体 |
| [搜索栏 SearchBar](component-spec/search-bar-component-spec.md) | `search-bar-component-spec.md` | 平面与浮起两种视觉风格，多种交互状态 | 多组件集, 27+ 变体 |
| [多选 Checkbox](component-spec/checkbox-component-spec.md) | `checkbox-component-spec.md` | 基础和多媒体两种视觉风格的复选框 | 2 维度, 8 变体 |
| [开关 Switch](component-spec/Switch-component-spec.md) | `Switch-component-spec.md` | 两种互斥状态切换控件 | 1 维度, 4 变体 |
| [分段按钮 SegmentedControls](component-spec/segmented-controls-component-spec.md) | `segmented-controls-component-spec.md` | 同层级视图切换/筛选，支持 2-5 个分段选项 | 3 维度, 24 变体 |
| [图形选择 GraphicSelect](component-spec/Select-component-spec.md) | `Select-component-spec.md` | 带预览图的选项卡片可视化选择控件 | 5 维度, 160+ 变体 |
| [滑动选择器 Slider](component-spec/slider-component-spec.md) | `slider-component-spec.md` | 连续值或离散值的滑动选择 | — |
| [日期选择器 DatePicker](component-spec/datepicker-component-spec.md) | `datepicker-component-spec.md` | 月盘（日历）和滚筒（滚轮）两种模式，支持农历 | 4 维度, 11 变体 |

### 数据展示

用于结构化展示信息的基础 UI 组件。

| 组件 | 文件 | 说明 | 变体 |
|------|------|------|------|
| [列表原子组件 ListAtom](component-spec/list-atom-component-spec.md) | `list-atom-component-spec.md` | 基础列表项、图标列表、多选/单选/按钮列表等一系列原子组件 | 6 维度, ~256 变体 |
| [新事件提示 Badge](component-spec/badge-component-spec.md) | `badge-component-spec.md` | 数字计数、圆点指示或彩色状态标记 | 3 组件集 |
| [分割器 Divider](component-spec/divider-component-spec.md) | `divider-component-spec.md` | 水平分割线，支持两种高度模式 | 1 维度, 2 变体 |
| [加载 Loading](component-spec/loading-component-spec.md) | `loading-component-spec.md` | 加载动画图标、加载态按钮和进度条 | 3 组件集 |
| [信息提示 NoticeBar](component-spec/noticebar-component-spec.md) | `noticebar-component-spec.md` | 页面内横条形式展示提示/强调/提醒/警告信息 | 2 组件集, 8+ 变体 |
| [页面指示器 PageIndicator](component-spec/page-indicator-component-spec.md) | `page-indicator-component-spec.md` | 点状指示器，支持大小两种尺寸和溢出渐变缩小 | 3 维度, 81 变体 |

### 反馈与浮层

弹窗、抽屉、菜单等临时浮出层组件，用于操作确认、信息提示和上下文操作。

| 组件 | 文件 | 说明 | 变体 |
|------|------|------|------|
| [弹窗 Dialog](component-spec/dialog-component-spec.md) | `dialog-component-spec.md` | 确认/警示/授权/引导/输入/进度/选择七种弹窗类型 | 7 类型, 23+ 变体 |
| [行动操作列表 Actionsheet](component-spec/Actionsheet-component-spec.md) | `Actionsheet-component-spec.md` | 底部弹出操作面板，陈列型/近手型 | 2 维度, 4 变体 |
| [抽屉窗口 DrawerWindow](component-spec/drawer-window-component-spec.md) | `drawer-window-component-spec.md` | 底部弹出抽屉容器，高/中/低三档高度 | 1 维度, 3 变体 |
| [浮窗 FloatingWindow](component-spec/floating-window-component-spec.md) | `floating-window-component-spec.md` | 系统级浮窗面板，混色模糊/纯色面板材质 | 2 维度, 6 变体 |
| [菜单 Menu](component-spec/menu-component-spec.md) | `menu-component-spec.md` | 下拉菜单、选择菜单、分组菜单、二级菜单和水平操作栏 | 3 组件集 |
| [近手菜单 PopupMenus](component-spec/PopupMenus-component-spec.md) | `PopupMenus-component-spec.md` | 当前上下文中快速展示的可选操作项 | 2 组件集, 6+ 变体 |
| [近手浮窗 Popover](component-spec/popover-component-spec.md) | `popover-component-spec.md` | 屏幕底部弹出的玻璃质感浮层，三档高度 | 1 维度, 3 变体 |
| [气泡提示 TipsBubble](component-spec/tips-bubble-component-spec.md) | `tips-bubble-component-spec.md` | 触发元素附近的简短提示，8 个方向箭头定位 | 1 维度, 8 变体 |
| [配对提示 ProximityPairing](component-spec/proximity-pairing-component-spec.md) | `proximity-pairing-component-spec.md` | 蓝牙设备靠近时的连接弹窗（耳机/手柄/车载/IoT） | 4 组件集, 24+ 变体 |

---

## 快速开始

### 如何使用这些规范文档

每份组件规范文档都是**自包含的 Markdown 文件**，可以直接提供给 AI Agent 作为组件实现的参考依据。

**方式一：直接引用**

在 Cursor / Cline 等 IDE 中，通过 `@` 引用组件规范文件：

```
请根据 @component-spec/button-component-spec.md 实现 Button 组件
```

**方式二：批量引用**

引用整个 `component-spec/` 目录，让 AI 理解完整的设计系统：

```
请根据 @component-spec/ 中的组件规范，实现一个设置页面
```

**方式三：程序化解析**

每份文档的 YAML Frontmatter 包含结构化元数据，可通过脚本批量解析：

```yaml
---
component: Button          # 英文组件名 (PascalCase)
description: ...           # 一句话描述
figma_source: ...          # Figma 原始链接
figma_node_id: "..."       # 节点 ID
variants: "..."            # 变体概览
tokens_used: 17            # Token 数量
---
```

### 如何生成新的规范文档

#### 前置要求

- 配置好 [Figma MCP Server](https://github.com/nicepkg/figma-mcp)（提供 `get_metadata`、`get_design_context`、`get_screenshot`、`get_variable_defs` 等工具）
- 支持 MCP 调用的 AI Agent 环境（如 Cursor、Cline 等）

#### 生成步骤

1. 引用生成 Prompt：`@figma-component-spec-prompt.md`
2. 提供 Figma 组件链接：

```
使用 @figma-component-spec-prompt.md 帮我生成设计规范：
https://figma.com/design/abc123xyz/DesignSystem?node-id=100-42
```

3. Agent 会自动调用 Figma MCP 获取数据并输出结构化文档
4. 生成的文档保存到 `component-spec/` 目录

---

## 文档结构

每份规范文档包含以下固定 Section（AI 消费者可通过 heading 名称定位信息）：

| Section | 内容 | 用途 |
|---------|------|------|
| **YAML Frontmatter** | 组件元数据 | 机器可读的快速索引 |
| **预览** | 组件截图 | 视觉参考 |
| **组件结构** | ASCII 节点树 + 子节点清单 | 理解组件层级 |
| **设计规范** | CSS 属性 / 值 / Token 三列表格 | 精确实现样式 |
| **变体** | 维度定义 + 差异表 | 实现所有变体 |
| **交互状态** | 状态 → 样式差异 | 实现交互反馈 |
| **组件 API** | TypeScript Props 类型 | 定义组件接口 |
| **使用指南** | Do's & Don'ts | 正确使用组件 |
| **设计 Token 映射** | Token 全量汇总 | 接入 Token 系统 |
| **设计注释** | Figma 标注和备注 | 补充设计意图 |

---

## 设计原则

- **CSS-ready** — 属性名使用标准 CSS 命名，值包含单位，可直接用于代码
- **Token 双轨** — 每个值同时标注原始值和 Token 名称，适配不同项目
- **差异驱动** — 变体和状态仅描述与基准的差异，减少冗余
- **固定结构** — heading 层级和名称不变，AI 可按 heading 定位任意 section

## 项目结构

```
figma-to-guides/
├── README.md                        # 本文件 — 组件库总览与使用指南
├── figma-component-spec-prompt.md   # Agent Prompt（核心规则定义）
└── component-spec/                  # 生成的组件规范文档（32 个组件）
    ├── button-component-spec.md
    ├── dialog-component-spec.md
    ├── ...
    └── floating-window-component-spec.md
```

## License

MIT
