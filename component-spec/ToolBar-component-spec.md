---
component: ToolBar
description: 小米 HyperOS4 底部工具栏组件，浮动胶囊样式，支持混色模糊/纯色面板两种材质及亮色/深色模式
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=97526-17417
figma_node_id: "97526:17417"
variants: "3 维度：2 种材质 × 2 种明暗模式 × 1-5 个工具数量 × 3 种交互状态"
tokens_used: 14
---

# 底部工具栏 ToolBar

> HyperOS4 系统级底部浮动工具栏组件，采用胶囊形态悬浮于页面底部，内含可变数量（1–5 个）的图标+文字工具按钮，支持混色模糊与纯色面板两种材质以及亮色/深色两种模式。OS4 中已禁用玻璃材质变体。

## 预览

![底部工具栏全部变体预览](http://localhost:3845/figma/screenshot/97526:17417)

---

## 组件结构

```
底部工具栏 ToolBar                             // FRAME | 97526:17417
├── 工具栏组件/常规                            // FRAME | 80431:27747
│   ├── 模式=浅色                              // COMPONENT | 80443:3665
│   │   └── .3个材质切换                       // INSTANCE | 84126:19900
│   │       └── 工具个数举例                   // INSTANCE
│   │           ├── .组件状态变化 ×N            // INSTANCE（每个工具按钮）
│   │           │   ├── Icon                   // FRAME（图标字体容器，28×28）
│   │           │   │   └── Symbol Text        // TEXT（HyperOS Symbols VF 字体图标）
│   │           │   └── Label                  // TEXT（按钮文字标签）
│   │           └── ...更多工具按钮
│   └── 模式=深色                              // COMPONENT | 105830:29251
│       └── .3个材质切换                       // INSTANCE | 105830:29252
│           └── （同上结构）
├── .3个材质切换                               // COMPONENT_SET | 80431:26933
│   ├── 材质=混色模糊, 深色模式=亮色模式        // COMPONENT | 80431:26936
│   ├── 材质=混色模糊, 深色模式=深色模式        // COMPONENT | 105830:29124
│   ├── 材质=纯色面板, 深色模式=亮色模式        // COMPONENT | 80431:26938
│   └── 材质=纯色面板, 深色模式=深色模式        // COMPONENT | 105830:29126
├── .组件状态变化                               // COMPONENT_SET | 80633:9802
│   ├── 状态=默认                              // COMPONENT | 52117:26485
│   ├── 状态=悬停                              // COMPONENT | 80633:9729
│   └── 状态=按下                              // COMPONENT | 95177:55537
├── 工具个数举例                                // COMPONENT_SET | 80633:14946
│   ├── 数量=5个                               // COMPONENT | 80633:14945
│   ├── 数量=4个                               // COMPONENT | 80633:14943
│   ├── 数量=3个                               // COMPONENT | 80633:14942
│   ├── 数量=2个                               // COMPONENT | 80633:14944
│   └── 数量=1个                               // COMPONENT | 80633:14941
├── 玻璃材质/亮色模式（OS4 已禁用）             // SYMBOL | 80431:26934
└── 玻璃材质/深色模式（OS4 已禁用）             // SYMBOL | 105830:23569
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| 工具栏组件/常规 | FRAME | `80431:27747` | 展示区，包含浅色和深色两个组件实例 |
| .3个材质切换 | COMPONENT_SET | `80431:26933` | 工具栏容器，控制材质和明暗模式 |
| .组件状态变化 | COMPONENT_SET | `80633:9802` | 单个工具按钮，控制交互状态 |
| 工具个数举例 | COMPONENT_SET | `80633:14946` | 工具按钮排列容器，控制按钮数量 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器（外层包裹）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `392px` | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `padding` | `0 24px 24px 24px` | — |

### 工具栏主体（胶囊容器 — 混色模糊/亮色）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `height` | `56px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `border-radius` | `28px` | — |
| `border` | `0.8px solid #F9F9F9` | `Stroke/Glass_Stroke_Middle_Light` |
| `box-shadow` | `0px 0px 40px 0px rgba(0,0,0,0.06), 0px 24px 60px 0px rgba(0,0,0,0.08), inset 0px 2px 2px 0px #9D9D9D` | `FrostShadow/FrostEffect_Thin_ShadowOn` |
| `overflow` | `hidden` | — |

#### 混色模糊背景层（三层叠加）

| 层级 | `background` | `mix-blend-mode` | `backdrop-filter` |
|-----|-------------|-----------------|-------------------|
| 底层 | `rgba(0,0,0,0.02)` | `normal` | — |
| 中层 | `rgba(255,255,255,0.6)` | `soft-light` | — |
| 顶层 | `rgba(255,255,255,0.6)` | `hard-light` | `blur(10px)` |

### 子组件: 工具按钮排列容器

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `padding` | `3px 13px 3px 3px` | — |

### 子组件: 单个工具按钮（.组件状态变化 — 默认态）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `75.6px`（5 个时为 `flex: 1 0 0`） | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `padding` | `3px` | — |
| `margin-right` | `-10px` | — |
| `background-color` | `transparent` | — |
| `border-radius` | `0` | — |

### 子组件: 图标

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `28px` | — |
| `height` | `28px` | — |
| `font-family` | `HyperOS Symbols VF` | — |
| `font-size` | `21px` | — |
| `color` | `#000000`（亮色） / `rgba(255,255,255,0.95)`（深色） | `miuix_default_color_on_surface` |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| 按钮标签 | MiSans | 11px | Medium (500) | normal | 0 | `#000000`（亮色） | `miuix_font_size_footnote2` |
| 按钮标签（深色） | MiSans | 11px | Medium (500) | normal | 0 | `rgba(255,255,255,0.95)` | `miuix_font_size_footnote2` |

### 颜色一览

| 语义用途 | 亮色模式值 | 深色模式值 | Token |
|---------|----------|----------|-------|
| 图标/文字色 | `#000000` | `rgba(255,255,255,0.95)` | `miuix_default_color_on_surface` |
| 悬停背景色 | `rgba(0,0,0,0.04)` | `rgba(0,0,0,0.04)` | `miuix_default_color_container_notice_bar` |
| 按下背景色 | `rgba(0,0,0,0.1)` | `rgba(0,0,0,0.1)` | `miuix_default_color_surface_container_high` |
| 混色模糊-底层 | `rgba(0,0,0,0.02)` | `rgba(0,0,0,0.1)` | `Pured/Pured_Regular_Glass_*` |
| 混色模糊-中层 | `rgba(255,255,255,0.6)` | `rgba(108,108,108,0.6)` | `Pured/Pured_Regular_Glass_*` |
| 混色模糊-顶层 | `rgba(255,255,255,0.6)` | `rgba(6,6,6,0.6)` | `Pured/Pured_Regular_Glass_*` |
| 纯色面板背景 | `#FFFFFF` | `#242424` | `Base/Popup_Light` / `Base/Popup_Dark` |
| 胶囊边框（混色模糊） | `#F9F9F9` | `#333333` | `Stroke/Glass_Stroke_Middle_*` |
| 纯色面板边框 | `rgba(252,252,252,0.2)` | `#262626` | `Stroke/Glass_Stroke_Small_*` |

---

## 变体

### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 材质 | `材质` | `混色模糊` / `纯色面板` | 胶囊容器的背景效果（OS4 已禁用玻璃材质） |
| 明暗模式 | `深色模式` | `亮色模式` / `深色模式` | 控制颜色方案 |
| 工具数量 | `数量` | `1个` / `2个` / `3个` / `4个` / `5个` | 工具栏内的按钮数量 |

共计 **2 × 2 = 4 种材质×模式组合**，搭配 **5 种数量变体**。

### 变体差异表

#### 按材质×模式分组

> 以「混色模糊 + 亮色模式」为默认基准。

| 属性 | 混色模糊 + 亮色 | 混色模糊 + 深色 | 纯色面板 + 亮色 | 纯色面板 + 深色 |
|-----|---------------|---------------|---------------|---------------|
| 背景实现 | 三层叠加 + blur | 三层叠加（无 blur） | 纯色 `#FFFFFF` | 纯色 `#242424` |
| `border` | `0.8px solid #F9F9F9` | `0.8px solid #333` | `0 solid rgba(252,252,252,0.2)` | `0 solid #262626` |
| `box-shadow` | 高阴影 + 内阴影 | 低阴影，无内阴影 | 高阴影 + 内阴影 | 高阴影 + 内阴影 |
| `mix-blend-mode`（中层） | `soft-light` | `luminosity` | — | — |
| `mix-blend-mode`（顶层） | `hard-light` | `soft-light` | — | — |
| `backdrop-filter` | `blur(10px)` | — | — | — |
| 图标/文字 `color` | `#000000` | `rgba(255,255,255,0.95)` | `#000000` | `rgba(255,255,255,0.95)` |

#### 材质=混色模糊 详情

**亮色模式**

![混色模糊 亮色模式](http://localhost:3845/figma/screenshot/80431:26936)

- 三层绝对定位伪元素叠加在胶囊容器内部，最上层应用 `backdrop-filter: blur(10px)` 实现磨砂效果
- 内阴影 `inset 0px 2px 2px #9D9D9D` 模拟光照高光

**深色模式**

![混色模糊 深色模式](http://localhost:3845/figma/screenshot/105830:29124)

- 三层叠加配色变暗，中层使用 `mix-blend-mode: luminosity` 控制亮度
- 无 `backdrop-filter`，无内阴影
- 阴影减弱：`0px 0px 20px rgba(0,0,0,0.02), 0px 12px 40px rgba(0,0,0,0.04)`

#### 材质=纯色面板 详情

**亮色模式**

![纯色面板 亮色模式](http://localhost:3845/figma/screenshot/80431:26938)

- 背景色 `var(--miuix_default_color_surface_high, white)`
- 无混合模式层，仅纯色填充
- 内阴影 `inset 0px 2px 2px #9D9D9D`

**深色模式**

![纯色面板 深色模式](http://localhost:3845/figma/screenshot/105830:29126)

- 背景色 `var(--white/color-white-solid-30, #242424)`
- 内阴影 `inset 0px 2px 2px #9D9D9D`

#### 按工具数量分组

![工具个数举例](http://localhost:3845/figma/screenshot/80633:14946)

| 属性 | `5个` | `4个` | `3个` | `2个` | `1个` |
|-----|-------|-------|-------|-------|-------|
| 容器 `width` | `344px` | `332px` | `auto` (hug) | `auto` (hug) | `100px` |
| 容器 `padding` | `3px 13px 3px 3px` | `3px 13px 3px 3px` | `3px 13px 3px 3px` | `3px 13px 3px 3px` | `3px` |
| 容器 `flex-direction` | `row` | `row` | `row` | `row` | `column` |
| 按钮 `width` | `flex: 1 0 0` | `92px`（min `66px`） | `min-width: 88px` | `88px`（min `88px`） | `100%` |
| 按钮 `margin-right` | `-10px` | `-10px` | `-10px` | `-10px` | `0` |
| 标签文字 | 短文本 | 短文本 | 短文本 | 最多四字 | 最多四字 |

---

## 交互状态

> 以「默认态」为基准，其他状态仅列出**发生变化**的属性。作用于单个工具按钮（`.组件状态变化`）。

![交互状态对比](http://localhost:3845/figma/screenshot/80633:9802)

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态，无背景） | — |
| `hover` | 鼠标悬停 | `background-color` | `rgba(0,0,0,0.04)` | `miuix_default_color_container_notice_bar` |
| | | `border-radius` | `36px` | `miuix_theme_radius_big` |
| `pressed` | 鼠标按下 / 触摸 | `background-color` | `rgba(0,0,0,0.1)` | `miuix_default_color_surface_container_high` |
| | | `border-radius` | `36px` | `miuix_theme_radius_big` |
| `disabled` | Figma 未定义 | — | Figma 未定义，请由设计团队补充 | — |
| `focused` | Figma 未定义 | — | Figma 未定义，请由设计团队补充 | — |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

```typescript
interface ToolBarProps {
  /** 材质类型，控制胶囊容器的背景效果 */
  material: 'blurred' | 'solid';
  /** 明暗模式 */
  mode: 'light' | 'dark';
  /** 工具按钮列表，每项包含图标和标签 */
  items: ToolBarItem[];
}

interface ToolBarItem {
  /** HyperOS Symbols 字体图标的 Unicode 码点 */
  icon: string;
  /** 按钮下方的文字标签 */
  label: string;
  /** 点击回调 */
  onPress?: () => void;
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 材质 | Variant | `material` | `blurred`（混色模糊） | 胶囊容器背景效果 |
| 深色模式 | Variant | `mode` | `light`（亮色模式） | 明暗模式切换 |
| 数量 | Variant | `items.length` | `5` | 工具按钮数量（1–5） |
| 状态 | Variant | 由交互自动切换 | `default` | 单个按钮的交互状态 |

---

## 使用指南

### 何时使用

- **多选操作工具栏**：在列表/内容页长按或进入编辑模式后，底部浮出工具栏提供批量操作（如发送、编辑、收藏、删除、更多）
- **内容详情页操作**：在图片/文件查看页面底部固定显示相关操作按钮
- **简单动作入口**：仅需 1–2 个操作时，使用少按钮变体保持界面简洁

### 何时不使用

- **页面级主导航**：应使用 `BottomNavigation` 底部导航栏代替
- **仅有单一主操作**：应使用 `FAB`（浮动操作按钮）代替
- **上下文菜单/弹出菜单**：操作项超过 5 个时，应使用 `ActionSheet` 或 `PopupMenu` 代替

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 工具按钮数量控制在 1–5 个 | 放置超过 5 个工具按钮 | 胶囊宽度有限，按钮过多会导致标签截断或触控区过小 |
| 每个按钮配合简短标签（2–4 字） | 使用过长的标签文字 | 按钮宽度自适应有限，长文本会溢出 |
| 混色模糊材质用于需要透出底层内容的场景 | 在纯色背景上使用混色模糊 | 混色模糊在纯色背景上效果不明显，浪费渲染性能 |
| 遵循亮色/深色模式一致性 | 在深色页面使用亮色工具栏 | 破坏视觉一致性和可读性 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `miuix_default_color_on_surface` | `#000000`（亮色） / `rgba(255,255,255,0.95)`（深色） | color | 图标颜色、按钮标签颜色 |
| `miuix_font_size_footnote2` | `11px` | font-size | 按钮标签字号 |
| `miuix_theme_radius_big` | `36px` | radius | 悬停/按下状态圆角 |
| `miuix_default_color_container_notice_bar` | `rgba(0,0,0,0.04)` | color | 悬停态背景 |
| `miuix_default_color_surface_container_high` | `rgba(0,0,0,0.1)` | color | 按下态背景 |
| `miuix_default_color_surface_high` | `#FFFFFF` | color | 纯色面板亮色背景 |
| `white/color-white-solid-30` | `#242424` | color | 纯色面板深色背景 |
| `Pured/Pured_Regular_Glass_Light` | `#000000, #FFFFFF, #FFFFFF` | fill-style | 混色模糊亮色三层填充色 |
| `Pured/Pured_Regular_Glass_Dark` | `#000000, #6C6C6C, #060606` | fill-style | 混色模糊深色三层填充色 |
| `Stroke/Glass_Stroke_Middle_Light` | `#F9F9F9` | stroke | 混色模糊亮色边框 |
| `Stroke/Glass_Stroke_Middle_Dark` | `#333333` | stroke | 混色模糊深色边框 |
| `FrostShadow/FrostEffect_Thin_ShadowOn` | `DROP_SHADOW(0,24,60,#00000014) + DROP_SHADOW(0,0,40,#0000000F) + INNER_SHADOW(0,2,2,#9D9D9D) + BLUR(20)` | effect | 混色模糊亮色阴影+模糊 |
| `Shadow/Shadow_Low` | `DROP_SHADOW(0,12,40,#0000000A) + DROP_SHADOW(0,0,20,#00000005)` | effect | 混色模糊深色阴影 |
| `Base/Popup_Light` | `#FFFFFF` | color | 纯色面板亮色背景（别名） |
| `Base/Popup_Dark` | `#242424` | color | 纯色面板深色背景（别名） |
| `Stroke/Glass_Stroke_Small_Light` | `rgba(252,252,252,0.2)` | stroke | 纯色面板亮色边框 |
| `Stroke/Glass_Stroke_Small_Dark` | `#262626` | stroke | 纯色面板深色边框 |

---

## 设计注释

> 1. **OS4 已禁用玻璃材质**：Figma 文件中存在 `玻璃材质/亮色模式` 和 `玻璃材质/深色模式` 两个变体，但标注了"os4禁用玻璃材质"，实际实现中不应支持此材质。
> 2. **图标字体**：工具按钮图标使用 `HyperOS Symbols VF`（Regular 字重）和 `HyperOS Symbols UI`（Regular 字重）两种字体，均为小米自研图标字体，通过 Unicode 码点渲染。
> 3. **按钮间负间距**：相邻工具按钮使用 `margin-right: -10px` 实现紧凑排列，使图标之间的视觉间距更符合设计预期。
> 4. **胶囊总宽度自适应**：5 个按钮时容器固定 `344px`，4 个按钮 `332px`，3 个及以下由内容撑开（hug），确保胶囊不会过宽。
> 5. **单按钮特殊布局**：当仅有 1 个按钮时，容器改为纵向排列（`flex-direction: column`），宽度缩至 `100px`，标签可容纳最多 4 个汉字。
