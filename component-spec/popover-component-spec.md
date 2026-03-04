---
component: Popover
description: 近手浮窗组件，用于在屏幕底部弹出的玻璃质感浮层面板，支持高/中/低三档高度
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=80408-353645
figma_node_id: "80408:353645"
variants: "1 dimension, 3 variants"
tokens_used: 12
---

# 近手浮窗 Popover

> 近手浮窗是一个从屏幕底部弹出的玻璃质感浮层面板组件，主要用于系统级功能面板（如控制中心、通知面板等）。通过「档位」维度控制浮窗展开高度，分为高（Max）、中（Medium）、低（Min）三档，内部包含标题栏导航区域和可扩展的内容区域。

## 预览

![近手浮窗 全部变体预览](figma-screenshot:80445:13004)

### 档位=高 Max

![近手浮窗 档位=高 Max](figma-screenshot:80445:13003)

### 档位=中 Medium

![近手浮窗 档位=中 Medium](figma-screenshot:80445:13001)

### 档位=低 Min

![近手浮窗 档位=低 Min](figma-screenshot:80445:13002)

---

## 组件结构

```
近手浮窗 Popover                                    // FRAME | 80445:13004
├── 档位=高 Max                                     // COMPONENT | 80445:13003
│   ├── _玻璃材质                                   // FRAME | 101827:4969 (Pured 磨砂玻璃)
│   │   ├── glass-layer-base                        // FRAME (bg rgba(0,0,0,0.15))
│   │   ├── glass-layer-soft-light                  // FRAME (bg rgba(255,255,255,0.8) mix-blend-mode: soft-light)
│   │   └── glass-layer-hard-light                  // FRAME (bg rgba(255,255,255,0.8) mix-blend-mode: hard-light + backdrop-blur)
│   └── 顶部                                       // FRAME | 80440:12720
│       └── 标题栏 Navigation Bar                   // INSTANCE | 87160:234024
│           └── Container                           // FRAME
│               ├── 左                              // FRAME (返回按钮区域)
│               │   └── chevron_backward            // INSTANCE (返回图标)
│               ├── 标题                            // TEXT (小标题)
│               └── 右                              // FRAME (更多按钮区域)
│                   └── more                        // INSTANCE (更多图标)
├── 档位=中 Medium                                  // COMPONENT | 80445:13001
│   ├── _玻璃材质/玻璃材质(OS4禁用)/亮色模式         // FRAME | 87160:234121 (标准玻璃)
│   │   ├── glass-layer-base                        // FRAME (bg rgba(0,0,0,0.15) mix-blend-mode: multiply)
│   │   ├── glass-layer-soft-light                  // FRAME (bg rgba(255,255,255,0.8) mix-blend-mode: soft-light)
│   │   ├── glass-layer-hard-light                  // FRAME (bg rgba(255,255,255,0.4) mix-blend-mode: hard-light)
│   │   └── glass-inner-shadow                      // FRAME (inner shadow)
│   └── 顶部                                       // FRAME | 80445:63725
│       └── 标题栏 Navigation Bar                   // INSTANCE | 87160:234055
└── 档位=低 Min                                     // COMPONENT | 80445:13002
    ├── _玻璃材质/玻璃材质(OS4禁用)/亮色模式         // FRAME | 80445:63980 (标准玻璃)
    └── 顶部                                       // FRAME | 80445:63754
        └── 标题栏 Navigation Bar                   // INSTANCE | 87160:234071
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| 近手浮窗 Popover | FRAME | `80445:13004` | 组件集合容器 |
| 档位=高 Max | COMPONENT | `80445:13003` | 高档位变体，最大展开高度 |
| 档位=中 Medium | COMPONENT | `80445:13001` | 中档位变体，中等展开高度 |
| 档位=低 Min | COMPONENT | `80445:13002` | 低档位变体，最小展开高度 |
| _玻璃材质 | FRAME | `101827:4969` | Pured 磨砂玻璃材质层（高档位） |
| _玻璃材质/玻璃材质(OS4禁用)/亮色模式 | FRAME | `87160:234121` | 标准玻璃材质层（中/低档位） |
| 顶部 | FRAME | `80440:12720` | 顶部区域，包含标题栏 |
| 标题栏 Navigation Bar | INSTANCE | `87160:234024` | 导航栏实例，含返回、标题、更多操作 |
| Container | FRAME | — | 导航栏内部布局容器 |
| chevron_backward | INSTANCE | `86954:12701` | 返回箭头图标 |
| more | INSTANCE | `86954:12904` | 更多操作图标（竖排三点） |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器（以「档位=高 Max」为基准）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `392px` | — |
| `height` | `664px` | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `stretch` | — |
| `gap` | `10px` | — |
| `border-radius` | `36px` | `hyperos_theme_radius_big` |
| `border` | `1px solid #F9F9F9` | `Stroke/Glass_Stroke_Big_Light` |
| `overflow` | `hidden` | — |

### 子组件: 玻璃材质层 — Pured 磨砂玻璃（高档位）

| CSS 属性 | 值 | Token / 样式名 |
|---------|----|---------------|
| `position` | `absolute` | — |
| `inset` | `0` | — |
| `border-radius` | `36px` | `hyperos_theme_radius_big` |
| `box-shadow` | `0px 0px 60px 0px rgba(0,0,0,0.06), 0px 36px 80px 0px rgba(0,0,0,0.08)` | `FrostShadow/FrostEffect_Thick_ShadowOn` |
| `pointer-events` | `none` | — |
| 层叠结构 | 见下方 | `Pured/Pured_Thick_Glass_Light` |

**Pured 磨砂玻璃层叠结构：**

| 层级 | `background` | `mix-blend-mode` | `backdrop-filter` |
|-----|-------------|------------------|--------------------|
| Layer 1 (base) | `rgba(0,0,0,0.15)` | `normal` | — |
| Layer 2 (soft-light) | `rgba(255,255,255,0.8)` | `soft-light` | — |
| Layer 3 (hard-light) | `rgba(255,255,255,0.8)` | `hard-light` | `blur(30px)` |

### 子组件: 玻璃材质层 — 标准玻璃（中/低档位）

| CSS 属性 | 值 | Token / 样式名 |
|---------|----|---------------|
| `position` | `absolute` | — |
| `inset` | `0` | — |
| `border-radius` | `36px` | `hyperos_theme_radius_big` |
| `box-shadow` | `0px 10px 16px 0px rgba(0,0,0,0.04), 0px 14px 45px 0px rgba(0,0,0,0.12)` | `GlassShadow/GlassEffect_Thick_ShadowOn` |
| `内阴影` | `inset 0px 2px 2px 0px #B9B9B9` | `GlassShadow/GlassEffect_Thick_ShadowOn` |
| `pointer-events` | `none` | — |
| 层叠结构 | 见下方 | `Glass/Fill_Thick_TintGary_Base_Light` |

**标准玻璃层叠结构：**

| 层级 | `background` | `mix-blend-mode` | `backdrop-filter` |
|-----|-------------|------------------|--------------------|
| Layer 1 (base) | `rgba(0,0,0,0.15)` | `multiply` | — |
| Layer 2 (soft-light) | `rgba(255,255,255,0.8)` | `soft-light` | — |
| Layer 3 (hard-light) | `rgba(255,255,255,0.4)` | `hard-light` | — |
| Inner Shadow | `inset 0px 2px 2px #B9B9B9` | — | — |

### 子组件: 顶部

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `stretch` | — |
| `height` | `66px` | — |
| `padding-top` | `6px` | — |
| `position` | `relative` | — |
| `width` | `100%` | — |

### 子组件: 标题栏 Navigation Bar

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `flex-start` | — |
| `justify-content` | `center` | — |
| `padding` | `6px 12px` | `padding/padding_sm` |
| `backdrop-filter` | `blur(33px)` | `模糊数值/Default`（近似） |
| `width` | `392px` | — |

### 子组件: Navigation Bar — Container

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `space-between` | — |
| `width` | `100%` | — |

### 子组件: 左侧按钮区域

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `max-width` | `44px` | — |

### 子组件: 左侧按钮容器（1个）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `width` | `44px` | — |
| `height` | `44px` | — |
| `padding` | `0 8px` | — |
| `border-radius` | `1000px` | — |

### 子组件: 右侧按钮区域

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `flex-end` | — |
| `max-width` | `96px` | — |

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
| `overflow` | `hidden` | — |
| `text-overflow` | `ellipsis` | — |
| `white-space` | `nowrap` | — |

### 子组件: 图标

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `28px` | — |
| `height` | `28px` | — |
| `position` | `relative` | — |

**返回图标 (chevron_backward)**

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `font-family` | `HyperOS Symbols UI` | — |
| `font-size` | `21px` | — |
| `color` | `#000000` | `hyperos-color-on-surface` |

**更多图标 (more)**

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `font-family` | `HyperOS Symbols VF` | — |
| `font-size` | `21px` | — |
| `color` | `#000000` | `hyperos-color-on-surface` |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| 标题 | MiSans | 18px | 380 (Medium) | 100% | 0 | `#000000` | `Title/Title 4` |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 文字色-主 / 图标色 | `#000000` | `hyperos-color-on-surface` |
| 图标色（带透明） | `rgba(0,0,0,0.9)` | `var(--color-icon)` |
| 主色 | `#3482FF` | `hyperos-color-primary` |
| 表面色 | `#FFFFFF` | `hyperos_color_surface` |
| 玻璃边框色 | `#F9F9F9` | `Stroke/Glass_Stroke_Big_Light` |
| 导航栏背景 | `rgba(0,0,0,0.05)` | `新增色彩变量/container_nav` |

---

## 变体

### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 档位 | `档位` | `高 Max` / `中 Medium` / `低 Min` | 控制浮窗展开高度和玻璃材质类型 |

共计 **1 × 3 = 3 个变体**。

### 变体差异表

> 仅列出各变体之间**有差异**的属性。未列出的属性与默认变体（档位=高 Max）相同。

#### 按 档位 分组

| 属性 | `高 Max` | `中 Medium` | `低 Min` |
|-----|---------|------------|---------|
| `height` | `664px` | `540px` | `314px` |
| 玻璃材质样式 | `Pured/Pured_Thick_Glass_Light` | `Glass/Fill_Thick_TintGary_Base_Light` | `Glass/Fill_Thick_TintGary_Base_Light` |
| 阴影样式 | `FrostShadow/FrostEffect_Thick_ShadowOn` | `GlassShadow/GlassEffect_Thick_ShadowOn` | `GlassShadow/GlassEffect_Thick_ShadowOn` |
| `box-shadow` | `0px 0px 60px rgba(0,0,0,0.06), 0px 36px 80px rgba(0,0,0,0.08)` | `0px 10px 16px rgba(0,0,0,0.04), 0px 14px 45px rgba(0,0,0,0.12)` | `0px 10px 16px rgba(0,0,0,0.04), 0px 14px 45px rgba(0,0,0,0.12)` |
| 内阴影 | 无 | `inset 0px 2px 2px #B9B9B9` | `inset 0px 2px 2px #B9B9B9` |
| Layer 1 `mix-blend-mode` | `normal` | `multiply` | `multiply` |
| Layer 3 `background` | `rgba(255,255,255,0.8)` | `rgba(255,255,255,0.4)` | `rgba(255,255,255,0.4)` |
| Layer 3 `backdrop-filter` | `blur(30px)` | 无 | 无 |

#### 档位=高 Max 详情

![近手浮窗 档位=高 Max](figma-screenshot:80445:13003)

- 最大展开高度，适用于需要展示大量内容的场景（如完整控制中心面板）
- 使用 **Pured 磨砂玻璃** 材质，具有更强的模糊效果和更大的阴影范围
- 阴影偏移更远（36px），模糊半径更大（80px），营造更高的浮起感

#### 档位=中 Medium 详情

![近手浮窗 档位=中 Medium](figma-screenshot:80445:13001)

- 中等展开高度，适用于中等内容量的场景（如快捷设置面板）
- 使用 **标准玻璃** 材质，带有内阴影增加质感层次
- 阴影更贴近容器（14px），营造中等浮起感

#### 档位=低 Min 详情

![近手浮窗 档位=低 Min](figma-screenshot:80445:13002)

- 最小展开高度，适用于简单操作或信息展示场景（如通知预览）
- 使用与中档位相同的 **标准玻璃** 材质和阴影效果

---

## 交互状态

> 以「默认态」为基准，其他状态仅列出**发生变化**的属性。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态） | — |
| `档位切换` | 用户手势拖拽 | `height` | 在 `314px` / `540px` / `664px` 之间过渡 | — |

> Figma 未定义 hover、active、disabled 等交互状态，请由设计团队补充。
>
> 标题栏内的返回按钮和更多按钮的交互状态请参考「标题栏 Navigation Bar」组件规范。

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

```typescript
interface PopoverProps {
  /** 浮窗展开高度档位 */
  level: 'max' | 'medium' | 'min';
  /** 标题栏标题文字 */
  title?: string; // 默认: "小标题"
  /** 是否显示返回按钮 */
  showBack?: boolean; // 默认: true
  /** 是否显示更多按钮 */
  showMore?: boolean; // 默认: true
  /** 返回按钮点击回调 */
  onBack?: () => void;
  /** 更多按钮点击回调 */
  onMore?: () => void;
  /** 自定义左侧图标 */
  leftIcon?: ReactNode; // 默认: chevron_backward
  /** 自定义右侧图标 */
  rightIcon?: ReactNode; // 默认: more
  /** 内容区域插槽 */
  children?: ReactNode;
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 档位 | Variant | `level` | `max` | 控制浮窗展开高度 |
| 标题文字 | Text | `title` | `"小标题"` | 导航栏标题文本 |
| 左侧按钮 | Instance Swap | `leftIcon` | chevron_backward | 左侧操作图标 |
| 右侧按钮 | Instance Swap | `rightIcon` | more | 右侧操作图标 |

---

## 使用指南

### 何时使用

- **系统控制中心**：使用「高 Max」档位，展示完整的快捷开关、亮度/音量滑块等控制项
- **快捷设置面板**：使用「中 Medium」档位，展示部分快捷设置和通知摘要
- **通知预览**：使用「低 Min」档位，展示单条通知内容或简单操作确认
- **底部弹出面板**：任何需要从屏幕底部滑出的浮层内容场景

### 何时不使用

- **全屏页面**：应使用全屏页面组件（Page / Screen）代替
- **模态对话框**：应使用 Dialog 组件代替，Dialog 居中展示且有遮罩
- **下拉菜单**：应使用 DropdownMenu 组件代替，菜单从触发按钮处展开
- **轻提示**：应使用 Toast / Snackbar 组件代替

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 根据内容量选择合适的档位 | 始终使用高档位展示少量内容 | 过高的浮窗会遮挡过多背景内容，影响上下文感知 |
| 保持标题简洁，使用 `text-overflow: ellipsis` 截断 | 使用过长的标题文字 | 标题区域宽度有限（256px），过长文字无法完整展示 |
| 支持手势拖拽在不同档位间切换 | 仅支持固定档位不可调整 | 近手浮窗的核心交互是通过手势控制展开程度 |
| 使用系统提供的玻璃材质样式 | 自定义不符合规范的背景效果 | 玻璃材质是 HyperOS 设计语言的核心视觉特征 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `hyperos_theme_radius_big` | `36px` | radius | 容器圆角 |
| `hyperos-color-on-surface` | `#000000` | color | 标题文字、图标颜色 |
| `hyperos-color-primary` | `#3482FF` | color | 主色（可用于激活态） |
| `hyperos_color_surface` | `#FFFFFF` | color | 表面色 |
| `hyperos_font_size_title4` | `18px` | font-size | 标题字号 |
| `hyperos_font_weight_title4` | `380` | font-weight | 标题字重 |
| `padding/padding_sm` | `12px` | spacing | 标题栏水平内边距 |
| `spacing-xl` | `16px` | spacing | 通用间距 |
| `radius-3xl` | `20px` | radius | 通用大圆角 |
| `cos-rounded/sm` | `9px` | radius | 小圆角 |
| `var(--color-icon)` | `rgba(0,0,0,0.9)` | color | 图标颜色 |
| `新增色彩变量/container_nav` | `rgba(0,0,0,0.05)` | color | 导航栏容器背景 |

### 样式 Token

| 样式名 | 类型 | 值 | 引用位置 |
|-------|------|---|---------|
| `Pured/Pured_Thick_Glass_Light` | 填充 | 多层叠加（见玻璃材质层） | 高档位玻璃材质 |
| `Glass/Fill_Thick_TintGary_Base_Light` | 填充 | 多层叠加（见玻璃材质层） | 中/低档位玻璃材质 |
| `FrostShadow/FrostEffect_Thick_ShadowOn` | 阴影 | `0px 0px 60px rgba(0,0,0,0.06), 0px 36px 80px rgba(0,0,0,0.08)` + `blur(60px)` | 高档位阴影 |
| `GlassShadow/GlassEffect_Thick_ShadowOn` | 阴影 | `0px 14px 45px rgba(0,0,0,0.12), 0px 10px 16px rgba(0,0,0,0.04)` + `inset 0px 2px 2px #B9B9B9` + `blur(70px)` | 中/低档位阴影 |
| `Stroke/Glass_Stroke_Big_Light` | 边框 | `1px solid #F9F9F9` | 玻璃材质边框 |
| `Title/Title 4` | 文字 | `MiSans / Medium / 18px / 380 / 100% / 0` | 标题文字样式 |
| `模糊数值/Default` | 效果 | `backdrop-blur(66px)` | 默认背景模糊 |

---

## 设计注释

> 1. 该组件属于系统团队维护的母组件（❖ 母组件集合_勿动），业务使用请复制场景实例，效果同母组件一致。组件使用中若发现问题可飞书联系 @设计系统小组。
> 2. 标题栏 Navigation Bar 组件提供了默认状态与浮层状态的切换展示。由于部分原始组件并不包含浮层样式，当切换为浮层状态时会自动回退为默认样式，这是正常表现。
> 3. 高档位（Max）使用 Pured 磨砂玻璃材质，具有更强的模糊和更大的阴影；中/低档位使用标准玻璃材质，阴影较轻并附带内阴影增加质感。
> 4. 三个档位的宽度固定为 392px，仅高度不同。内容区域（顶部以下）可自由填充业务内容。
