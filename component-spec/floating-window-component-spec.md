---
component: FloatingWindow
description: 系统级浮窗面板，支持混色模糊玻璃和纯色面板两种材质风格，适配亮色/深色模式
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=43336-50271
figma_node_id: "43336:50271"
variants: "2 dimensions, 6 variants"
tokens_used: 18
---

# 浮窗 FloatingWindow

> 系统级浮窗面板组件，用于承载临时性内容（如创建表单、详情预览等）。支持混色模糊玻璃、纯色面板（灰）、纯色面板（白）三种材质风格，并适配亮色与深色两种主题模式。

## 预览

### 浮窗整体预览（含标题栏）

![FloatingWindow 整体预览 - 三种亮色材质变体](截图见 Figma nodeId 42765:69873)

### 玻璃材质变体预览（亮色 + 深色）

![FloatingWindow 玻璃材质 6 种变体](截图见 Figma nodeId 87083:224779)

---

## 组件结构

```
浮窗_Floating Window                           // SECTION | 43336:50271
├── 浮窗_Floating Window                       // FRAME | 42765:69873
│   ├── FloatingWindow (混色模糊)              // COMPONENT | 75:3833
│   │   ├── _玻璃材质                          // FRAME | 87160:232648
│   │   │   ├── 模糊层1 (rgba overlay)         // FRAME
│   │   │   ├── 模糊层2 (soft-light)           // FRAME
│   │   │   ├── 模糊层3 (hard-light+blur)      // FRAME
│   │   │   └── 内阴影层                       // FRAME
│   │   └── 创建生日 (内容容器)                // FRAME | 75:3834
│   │       └── 标题栏 Navigation Bar          // INSTANCE | 94022:3625
│   │           ├── 左 (关闭按钮)              // FRAME
│   │           │   └── Close                  // INSTANCE | 86954:12902
│   │           ├── 标题文字                    // TEXT
│   │           └── 右 (更多按钮)              // FRAME
│   │               └── More                   // INSTANCE | 86954:12904
│   ├── FloatingWindow (纯色面板·灰)           // COMPONENT | 75:3829
│   │   ├── _玻璃材质                          // FRAME | 87160:232650
│   │   └── 创建生日 (内容容器)                // FRAME | 75:3830
│   │       └── 标题栏 Navigation Bar          // INSTANCE | 94022:3637
│   └── FloatingWindow (纯色面板·白)           // COMPONENT | 87160:232779
│       ├── _玻璃材质                          // FRAME | 87160:232798
│       └── 创建生日 (内容容器)                // FRAME | 87160:232781
│           └── 标题栏 Navigation Bar          // INSTANCE | 94022:3649
├── 表头_Component&Instance                    // INSTANCE | 87083:224757
└── _玻璃材质                                  // FRAME | 87083:224779
    ├── 混色模糊 · 亮色                        // COMPONENT | 87083:224780
    ├── 纯色面板 · 亮色                        // COMPONENT | 87083:224781
    ├── 纯色面板（白）· 亮色                   // COMPONENT | 87160:232797
    ├── 混色模糊 · 深色                        // COMPONENT | 88347:68724
    ├── 纯色面板 · 深色                        // COMPONENT | 88347:68725
    └── 纯色面板（白）· 深色                   // COMPONENT | 88347:68726
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| _玻璃材质 | FRAME | `87160:232648` | 背景材质层，绝对定位覆盖整个容器，负责呈现毛玻璃或纯色效果 |
| 创建生日 (内容容器) | FRAME | `75:3834` | 主内容区域，包含标题栏和内容插槽 |
| 标题栏 Navigation Bar | INSTANCE | `94022:3625` | 导航栏实例，包含关闭按钮、标题文字和更多操作按钮 |
| 左 (关闭按钮区域) | FRAME | `91243:106928` | 左侧操作区，包含关闭图标 |
| Close | INSTANCE | `86954:12902` | 关闭图标，使用 HyperOS Symbols 字体图标 |
| 右 (更多按钮区域) | FRAME | `91243:107410` | 右侧操作区，包含更多操作图标 |
| More | INSTANCE | `86954:12904` | 更多操作图标，使用 HyperOS Symbols 字体图标 |
| 标题文字 | TEXT | `1890:3395` | 居中标题文字，支持单行省略 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器（FloatingWindow 根节点）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `546px` | — |
| `height` | `636px` | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `stretch` | — |
| `border-radius` | `36px` | `hyperos_theme_radius_big` |
| `position` | `relative` | — |

### 子组件: _玻璃材质（背景材质层）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `position` | `absolute` | — |
| `inset` | `0` | — |
| `border-radius` | `36px` | `hyperos_theme_radius_big` |
| `border-width` | `1px` | — |
| `border-style` | `solid` | — |
| `border-color` | `#F9F9F9`（混色模糊·亮色） | `Stroke/Glass_Stroke_None_Light` |
| `overflow` | `clip` | — |

#### 混色模糊 · 亮色 — 多层叠加结构

毛玻璃效果通过 4 个绝对定位子层叠加实现：

| 层级 | CSS 属性 | 值 | 说明 |
|-----|---------|---|------|
| 层1 | `background-color` | `rgba(0, 0, 0, 0.15)` | 暗色叠加底 |
| 层1 | `border-radius` | `36px` | `hyperos_theme_radius_big` |
| 层2 | `background-color` | `rgba(255, 255, 255, 0.8)` | 亮色混合层 |
| 层2 | `mix-blend-mode` | `soft-light` | — |
| 层3 | `background-color` | `rgba(255, 255, 255, 0.8)` | 模糊玻璃层 |
| 层3 | `mix-blend-mode` | `hard-light` | — |
| 层3 | `backdrop-filter` | `blur(30px)` | — |
| 层4 | `box-shadow` | `inset 0px 2px 2px 0px #9D9D9D` | 内阴影层 |
| 层4 | `border-radius` | `inherit` | `FrostShadow/FrostEffect_Thick_ShadowOff` |

### 子组件: 内容容器（创建生日）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `546px` | — |
| `height` | `636px` | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `stretch` | — |
| `padding-top` | `6px` | — |
| `border-radius` | `32px`（混色模糊）/ `36px`（纯色面板） | — / `hyperos_theme_radius_big` |
| `overflow` | `clip` | — |
| `position` | `relative` | — |

### 子组件: 标题栏 Navigation Bar

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `flex-start` | — |
| `justify-content` | `center` | — |
| `width` | `100%`（fill） | — |
| `padding-top` | `6px` | — |
| `padding-bottom` | `6px` | — |
| `padding-left` | `12px` | `padding/padding_sm` |
| `padding-right` | `12px` | `padding/padding_sm` |
| `backdrop-filter` | `blur(33px)` | — |

#### 标题栏内部布局（Container）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `justify-content` | `space-between` | — |
| `align-items` | `center` | — |
| `width` | `100%` | — |

### 子组件: 左侧操作区（关闭按钮）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `max-width` | `44px` | — |

#### 按钮容器

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `44px` | — |
| `height` | `44px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `padding` | `8px` | — |
| `border-radius` | `1000px`（圆形） | — |

### 子组件: 右侧操作区（更多按钮）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `flex-end` | — |
| `max-width` | `96px` | — |

#### 按钮容器

与左侧按钮容器相同：`44px × 44px`，`border-radius: 1000px`，`padding: 8px`。

### 子组件: 图标 (Close / More)

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `28px` | — |
| `height` | `28px` | — |
| `font-family` | `HyperOS_Symbols_VF` | — |
| `font-size` | `21px` | — |
| `color` | `#000000`（亮色）| `hyperos-color-on-surface` |

### 子组件: 标题文字

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `position` | `absolute` | — |
| `left` | `50%` | — |
| `top` | `22px` | — |
| `transform` | `translate(-50%, -50%)` | — |
| `width` | `256px` | — |
| `height` | `28px` | — |
| `text-align` | `center` | — |
| `white-space` | `nowrap` | — |
| `overflow` | `hidden` | — |
| `text-overflow` | `ellipsis` | — |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| 标题文字 | MiSans | 18px | 380 (Medium) | 100% | 0 | `#000000` | `Title/Title 4` |
| 图标文字 | HyperOS_Symbols_VF | 21px | Regular | normal | 0 | `#000000` | — |

### 颜色一览

| 语义用途 | 亮色值 | 深色值 | Token |
|---------|-------|-------|-------|
| 混色模糊边框 | `#F9F9F9` | `#333333` | `Stroke/Glass_Stroke_None_Light` / `Dark` |
| 纯色面板（灰）背景 | `#F3F3F3` | `#242424` | `hyperoscolor_Surface_popwindow_pop window` / `Base/Window_Dark` |
| 纯色面板（白）背景 | `#FFFFFF` | `#242424` | `hyperos-color-surface-high` / `Base/Popup_Dark` |
| 文字色 | `#000000` | — | `hyperos-color-on-surface` |
| 图标色 | `rgba(0, 0, 0, 0.9)` | — | `var(--color-icon)` |
| 模糊层1 底色 | `rgba(0, 0, 0, 0.15)` | `rgba(0, 0, 0, 0.1)` | — |
| 模糊层2 混合色 | `rgba(255, 255, 255, 0.8)` | `rgba(87, 87, 87, 0.6)` | `Pured/Pured_Thick_Glass_Light` / `Dark` |
| 模糊层3 玻璃色 | `rgba(255, 255, 255, 0.8)` | `rgba(6, 6, 6, 0.6)` | `Pured/Pured_Thick_Glass_Light` / `Dark` |
| 内阴影色 | `#9D9D9D` | `#9D9D9D` | `FrostShadow/FrostEffect_Thick_ShadowOff` |

---

## 变体

### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 材质类型 | `propValue` | `混色模糊` / `纯色面板（灰）` / `纯色面板（白）` | 控制浮窗背景材质样式 |
| 主题模式 | `propValue1` | `亮色模式` / `深色模式` | 控制亮色/深色主题适配 |

共计 **3 × 2 = 6 个变体**。

### 变体差异表

> 仅列出各变体之间**有差异**的属性。未列出的属性与默认变体（混色模糊·亮色）相同。

#### 按材质类型分组（亮色模式）

| 属性 | `混色模糊` | `纯色面板（灰）` | `纯色面板（白）` |
|-----|-----------|---------------|---------------|
| `background-color` | 无（多层叠加） | `#F3F3F3` | `#FFFFFF` |
| `border-color` | `#F9F9F9` | `rgba(255,255,255,0)`（透明） | `rgba(255,255,255,0)`（透明） |
| 模糊叠加层 | 4 层（详见设计规范） | 无 | 无 |
| `box-shadow` | `inset 0px 2px 2px 0px #9D9D9D` | 无 | 无 |
| `backdrop-filter` | `blur(30px)` | 无 | 无 |
| 内容容器 `border-radius` | `32px` | `36px` | `36px` |

#### 按材质类型分组（深色模式）

| 属性 | `混色模糊` | `纯色面板（灰）` | `纯色面板（白）` |
|-----|-----------|---------------|---------------|
| `background-color` | 无（多层叠加） | `#242424` | `#242424` |
| `border-color` | `#333333` | `rgba(0,0,0,0)`（透明） | `rgba(0,0,0,0)`（透明） |
| 模糊层1 | `rgba(0,0,0,0.1)` | — | — |
| 模糊层2 | `rgba(87,87,87,0.6)` + `luminosity` | — | — |
| 模糊层3 | `rgba(6,6,6,0.6)` + `soft-light` + `blur(30px)` | — | — |

#### 混色模糊 — 亮色 vs 深色 差异

| 属性 | 亮色 | 深色 |
|-----|------|------|
| 材质层 `border-color` | `#F9F9F9` | `#333333` |
| 层1 `background-color` | `rgba(0,0,0,0.15)` | `rgba(0,0,0,0.1)` |
| 层2 `background-color` | `rgba(255,255,255,0.8)` | `rgba(87,87,87,0.6)` |
| 层2 `mix-blend-mode` | `soft-light` | `luminosity` |
| 层3 `background-color` | `rgba(255,255,255,0.8)` | `rgba(6,6,6,0.6)` |
| 层3 `mix-blend-mode` | `hard-light` | `soft-light` |

---

## 交互状态

> 以「默认态」为基准，其他状态仅列出**发生变化**的属性。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态） | — |
| `hover` | 鼠标悬停关闭/更多按钮 | Figma 未定义，请由设计团队补充 | — | — |
| `active` | 鼠标按下关闭/更多按钮 | Figma 未定义，请由设计团队补充 | — | — |
| `focused` | 键盘聚焦 | Figma 未定义，请由设计团队补充 | — | — |
| `disabled` | — | 该组件不涉及此项 | — | — |

> **注意**：标题栏组件说明中提到"组件提供了默认状态与浮层状态的切换展示，但部分原始组件不包含浮层样式时会自动回退为默认样式"。

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

```typescript
interface FloatingWindowProps {
  /** 控制浮窗背景材质样式 */
  materialType: '混色模糊' | '纯色面板' | '纯色面板（白）';
  /** 主题模式（亮色/深色） */
  theme?: '亮色模式' | '深色模式';
  /** 标题栏标题文字 */
  title?: string;
  /** 左侧操作按钮（默认为关闭按钮） */
  leftAction?: ReactNode;
  /** 右侧操作按钮（默认为更多按钮） */
  rightAction?: ReactNode;
  /** 浮窗主体内容 */
  children?: ReactNode;
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| propValue | Variant | `materialType` | `混色模糊` | 材质类型：混色模糊 / 纯色面板（灰）/ 纯色面板（白） |
| propValue1 | Variant | `theme` | `亮色模式` | 主题模式：亮色模式 / 深色模式 |
| 标题文字 | Text | `title` | `小标题` | 导航栏居中标题 |
| Close | Instance Swap | `leftAction` | Close 图标 | 左侧操作按钮 |
| More | Instance Swap | `rightAction` | More 图标 | 右侧操作按钮 |

---

## 使用指南

### 何时使用

- **临时任务/表单场景**：使用「混色模糊」材质，营造沉浸式的悬浮操作体验，如创建生日、编辑信息
- **信息预览/快捷操作**：使用「纯色面板（灰）」材质，与系统设置风格一致
- **高对比内容展示**：使用「纯色面板（白）」材质，提供最纯净的白色背景，适合阅读型内容

### 何时不使用

- **全屏内容页面**：应使用全屏 Page 或 Sheet 组件代替
- **简短提示信息**：应使用 Dialog 或 Toast 组件代替
- **上下文菜单操作**：应使用 Popover 或 ActionSheet 组件代替
- **底部弹出面板**：应使用 BottomSheet / Drawer 组件代替

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 在有壁纸/图片背景时使用混色模糊材质 | 在纯色背景上使用混色模糊材质 | 毛玻璃效果需要背景内容透出才有视觉意义 |
| 标题文字保持简短（建议不超过 10 个汉字） | 标题文字过长被截断 | 标题区域宽度限制为 256px，过长会省略 |
| 保持左侧为关闭/返回、右侧为辅助操作的布局 | 交换左右按钮的功能 | 遵循 HyperOS 系统级导航规范 |
| 深色模式使用对应的深色变体 | 亮色模式下使用深色变体的配色 | 确保主题一致性和可读性 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `hyperos_theme_radius_big` | `36px` | radius | 容器圆角、材质层圆角 |
| `hyperos_theme_radius_medium` | `20px` | radius | 备用圆角尺寸 |
| `radius-3xl` | `20px` | radius | 通用大圆角 |
| `hyperoscolor_Surface_popwindow_pop window` | `#F3F3F3` | color | 纯色面板（灰）亮色背景 |
| `hyperos-color-surface-high` | `#FFFFFF` | color | 纯色面板（白）亮色背景 |
| `hyperos_color_surface` | `#FFFFFF` | color | 通用表面色 |
| `hyperos-color-on-surface` | `#000000` | color | 文字色、图标色 |
| `hyperos-color-primary` | `#3482FF` | color | 主色调（强调色） |
| `var(--color-icon)` | `rgba(0, 0, 0, 0.9)` | color | 图标颜色 |
| `Base/Window_Light` | `#F3F3F3` | color | 亮色窗口基底色 |
| `Base/Window_Dark` | `#242424` | color | 深色窗口基底色 |
| `Base/Popup_Light` | `#FFFFFF` | color | 亮色弹窗背景 |
| `Base/Popup_Dark` | `#242424` | color | 深色弹窗背景 |
| `Stroke/Glass_Stroke_None_Light` | `#FFFFFF` | color | 亮色玻璃边框 |
| `Stroke/Glass_Stroke_None_Dark` | `#000000` | color | 深色玻璃边框 |
| `white/color-white-solid-30` | `#242424` | color | 深色模式纯色面板背景 |
| `Pured/Pured_Thick_Glass_Light` | `#000000, #FFFFFF, #FFFFFF` | gradient | 亮色厚毛玻璃混合色系 |
| `Pured/Pured_Thick_Glass_Dark` | `#000000, #575757, #060606` | gradient | 深色厚毛玻璃混合色系 |
| `FrostShadow/FrostEffect_Thick_ShadowOff` | `inset 0px 2px 2px #9D9D9D` + `blur(60px)` | effect | 毛玻璃内阴影 + 背景模糊 |
| `模糊数值/Default` | `blur(66px)` | effect | 默认背景模糊值 |
| `padding/padding_sm` | `12px` | spacing | 标题栏水平内边距 |
| `spacing-xl` | `16px` | spacing | 通用间距 |
| `hyperos_font_size_title4` | `18px` | font-size | 标题字号 |
| `hyperos_font_weight_title4` | `380` | font-weight | 标题字重 |
| `Title/Title 4` | `MiSans Medium 18px / 100% / 0` | typography | 标题文字样式 |
| `新增色彩变量/container_nav` | `rgba(0, 0, 0, 0.05)` | color | 导航栏容器色 |
| `全系统色板/Violet` | `#B74AF7` | color | 紫色系统色板 |

---

## 设计注释

> 1. **标题栏 Navigation Bar**：组件提供了默认状态与浮层状态的切换展示。当切换为浮层状态时，部分原始组件不包含浮层样式会自动回退为默认样式，这是正常表现。
> 2. **混色模糊材质**：毛玻璃效果通过 4 层绝对定位子元素叠加实现，包含 `rgba` 叠加层、`mix-blend-mode`（soft-light / hard-light）混合层以及 `backdrop-filter: blur(30px)` 模糊层。深色模式下混合模式切换为 `luminosity` 和 `soft-light`。
> 3. **内容容器圆角差异**：混色模糊变体的内容容器圆角为 `32px`（比外层 `36px` 小 `4px`，为边框预留空间），纯色面板的内容容器圆角与外层一致为 `36px`。
> 4. **标题栏 `backdrop-filter`**：标题栏自身带有 `blur(33px)` 的背景模糊，用于在滚动内容时保持标题栏的半透明毛玻璃效果。
> 5. **图标字体**：关闭和更多操作按钮使用 `HyperOS_Symbols_VF` 字体图标，不是 SVG 图标。实现时需确保该字体可用，或替换为等效的 SVG 图标。
