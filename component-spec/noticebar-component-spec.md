---
component: NoticeBar
description: HyperOS 信息提示组件，用于在页面内以横条形式展示提示、强调、提醒或警告信息
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=90794-65267
figma_node_id: "90794:65267"
variants: "2 component sets: 提示条 (8 variants: 4 colors × 2 modes), 提示图标 (2 types)"
tokens_used: 14
---

# 信息提示 NoticeBar

> HyperOS 系统级信息提示横条组件，用于在内容区域顶部或嵌入位置向用户展示不同紧急程度的提示信息。支持灰色默认、蓝色强调、黄色提醒、红色警告四种语义颜色，以及 Light/Dark 双模式。右侧提供详情跳转或关闭操作，左侧可选扩展图标。

## 预览

![信息提示 NoticeBar 全部变体预览](figma-screenshot-90794-65267.png)

---

## 组件结构

```
信息提示 NoticeBar                                  // SECTION | 90794:65267
├── 提示条                                          // COMPONENT_SET | 1212:87575
│   ├── 颜色=灰色-默认, 模式=Light                  // COMPONENT | 1212:87576
│   │   └── 提示条 (内层容器)                       // FRAME
│   │       └── 内容行                              // FRAME (flex row)
│   │           ├── [左侧扩展图标] (可选)            // INSTANCE | album (20×20)
│   │           ├── 提示文字                         // TEXT (flex: 1)
│   │           └── 提示图标 (右侧操作)              // INSTANCE (20×20)
│   ├── 颜色=灰色-默认, 模式=Dark                   // COMPONENT | 51633:104066
│   ├── 颜色=蓝色-强调, 模式=Light                  // COMPONENT | 1212:87611
│   ├── 颜色=蓝色-强调, 模式=Dark                   // COMPONENT | 51633:104242
│   ├── 颜色=黄色-提醒, 模式=Light                  // COMPONENT | 1212:87601
│   ├── 颜色=黄色-提醒, 模式=Dark                   // COMPONENT | 51633:104348
│   ├── 颜色=红色-警告, 模式=Light                  // COMPONENT | 1212:87606
│   └── 颜色=红色-警告, 模式=Dark                   // COMPONENT | 51633:104439
└── 提示图标                                        // COMPONENT_SET | 89510:16512
    ├── 类型=详情                                   // COMPONENT | 89510:16500
    └── 类型=关闭                                   // COMPONENT | 89510:16505
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| 提示条 | COMPONENT_SET | `1212:87575` | 主体横条组件，4 种颜色 × 2 种模式 |
| 提示图标 | COMPONENT_SET | `89510:16512` | 右侧操作图标，支持详情箭头和关闭按钮 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 外层容器（间距控制层）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `flex-start` | — |
| `padding-top` | `4px` | — |
| `padding-bottom` | `8px` | — |
| `padding-left` | `12px` | `hyperos_theme_container_margin_base_horizontal` |
| `padding-right` | `12px` | — |

### 内层容器（提示条主体）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `min-height` | `44px` | — |
| `padding` | `12px 16px` | — |
| `overflow` | `clip` | — |
| `width` | `100%` | — |
| `border-radius` (Light) | `20px` | `hyperos_theme_radius_medium` |
| `border-radius` (Dark) | `16px` | `hyperos_theme_radius_common` |

> **设计注释**: Light 模式圆角为 20px（从旧版 12px 调整），Dark 模式使用 16px。

### 内容行

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex` | `1 0 0` | — |
| `align-items` | `center` | — |
| `gap` | `8px` | — |

### 子组件: 左侧扩展图标（可选）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `20px` | — |
| `height` | `20px` | — |
| `font-family` | `HyperOS_Symbols_VF` | — |
| `font-size` | `15px` | — |
| `color` | 跟随当前颜色变体的前景色 | — |

### 子组件: 提示文字

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `flex` | `1 0 0` | — |
| `font-family` | MiSans | — |
| `font-style` | Regular | — |
| `font-size` | `14px` | `hyperos_font_size_body2` |
| `font-weight` | `330` | `hyperos_font_weight_body2` |
| `line-height` | `normal` | — |
| `letter-spacing` | `0` | — |
| `color` | 跟随当前颜色变体的前景色 | — |

### 子组件: 提示图标（右侧操作）

| CSS 属性 | 值 (类型=详情) | 值 (类型=关闭) | Token |
|---------|----|-------|-------|
| `width` | `20px` | `20px` | — |
| `height` | `20px` | `20px` | — |
| `font-family` | `HyperOS_Symbols_UI_VF` | `HyperOS_Symbols_VF` | — |
| `font-size` | `15px` | `10.71px` | — |
| `color` | 跟随当前颜色变体的前景色 | 同左 | — |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| 提示文字 | MiSans | 14px | 330 (Regular) | normal | 0 | 按颜色变体 | `Body/Body 2` |

---

## 颜色方案

### Light 模式

| 颜色变体 | 背景色 | 背景 Token | 前景色（文字/图标） | 前景 Token |
|---------|-------|-----------|----------------|-----------|
| 灰色-默认 | `rgba(0,0,0,0.04)` | `hyperoscolor_container_notice_bar` | `rgba(0,0,0,0.6)` | `hyperos-color-on-surface-tertiary` |
| 蓝色-强调 | `rgba(52,130,255,0.08)` | `hyperos-color-secondary` | `#2E72E0` | — |
| 黄色-提醒 | `rgba(255,159,5,0.1)` | `hyperos-color-caution-container` | `#E08C04` | — |
| 红色-警告 | `rgba(250,56,46,0.08)` | `hyperos-color-error-container` | `#DC3128` | — |

### Dark 模式

| 颜色变体 | 背景色 | 背景 Token | 前景色（文字/图标） | 前景 Token |
|---------|-------|-----------|----------------|-----------|
| 灰色-默认 | `rgba(255,255,255,0.14)` | `hyperoscolor_container_notice_bar` | `rgba(255,255,255,0.5)` | `hyperos-color-on-surface-tertiary` |
| 蓝色-强调 | `rgba(71,136,255,0.25)` | `hyperos-color-secondary` | `#4788FF` | `hyperos-color-primary` |
| 黄色-提醒 | Dark 模式语义 Token 对应值 | `hyperos-color-caution-container` | Dark 模式语义色 | — |
| 红色-警告 | Dark 模式语义 Token 对应值 | `hyperos-color-error-container` | Dark 模式语义色 | — |

> **注意**: 蓝色强调变体的右侧图标在 Light 模式下使用 `#3482FF`（`hyperos-color-primary`），与文字色 `#2E72E0` 存在微小差异。

---

## 变体

### 维度定义

#### 提示条

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 颜色 | `颜色` | `灰色-默认` / `蓝色-强调` / `黄色-提醒` / `红色-警告` | 信息语义级别 |
| 模式 | `模式` | `Light` / `Dark` | 亮暗模式适配 |

共计 **8 个变体**（4 颜色 × 2 模式）。

#### 提示图标

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `类型` | `详情` / `关闭` | 右侧操作图标类型 |

共计 **2 个变体**。

### 变体差异表

#### 按颜色分组（Light 模式为基准）

| 属性 | `灰色-默认` | `蓝色-强调` | `黄色-提醒` | `红色-警告` |
|-----|-----------|-----------|-----------|-----------|
| 背景色 | `rgba(0,0,0,0.04)` | `rgba(52,130,255,0.08)` | `rgba(255,159,5,0.1)` | `rgba(250,56,46,0.08)` |
| 文字色 | `rgba(0,0,0,0.6)` | `#2E72E0` | `#E08C04` | `#DC3128` |
| 图标色 | `rgba(0,0,0,0.6)` | `#3482FF` | `#E08C04` | `#DC3128` |
| 内容行 gap | `8px` | `8px` | `8px`（左图标）+ `12px`（文字与右图标） | `8px` + `12px` |

#### Light vs Dark 差异

| 属性 | Light | Dark |
|-----|-------|------|
| `border-radius` | `20px` (`hyperos_theme_radius_medium`) | `16px` (`hyperos_theme_radius_common`) |
| 灰色背景 | `rgba(0,0,0,0.04)` | `rgba(255,255,255,0.14)` |
| 灰色前景 | `rgba(0,0,0,0.6)` | `rgba(255,255,255,0.5)` |
| 蓝色背景 | `rgba(52,130,255,0.08)` | `rgba(71,136,255,0.25)` |
| 蓝色前景 | `#2E72E0` | `#4788FF` |

---

## 交互状态

> NoticeBar 是静态展示型组件，不具备复杂的交互状态变化。交互行为由右侧操作图标驱动。

| 操作 | 图标类型 | 行为 |
|-----|---------|------|
| 点击详情图标 | `类型=详情`（右箭头） | 跳转至详情页面或展开更多信息 |
| 点击关闭图标 | `类型=关闭`（×） | 隐藏/关闭当前提示条 |
| 点击整条提示 | — | 可选：整条可点击跳转（取决于业务） |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

### 提示条

```typescript
interface NoticeBarProps {
  /** 颜色语义 */
  color: '灰色-默认' | '蓝色-强调' | '黄色-提醒' | '红色-警告';
  /** 亮暗模式 */
  mode: 'Light' | 'Dark';
  /** 是否显示左侧扩展图标 */
  showLeftIcon?: boolean; // 默认 false
  /** 提示文字内容 */
  text: string;
}
```

### 提示图标

```typescript
interface NoticeBarIconProps {
  /** 图标类型 */
  type: '详情' | '关闭';
}
```

| Figma 属性名 | 类型 | 对应组件 | 对应 Prop | 默认值 | 说明 |
|-------------|------|---------|----------|-------|------|
| 颜色 | Variant | 提示条 | `color` | `灰色-默认` | 信息语义级别 |
| 模式 | Variant | 提示条 | `mode` | `Light` | 亮暗模式 |
| propValue | Boolean | 提示条 | `showLeftIcon` | `false` | 控制左侧扩展图标显隐 |
| 类型 | Variant | 提示图标 | `type` | `详情` | 右侧操作图标类型 |

---

## 使用指南

### 何时使用

- **默认灰色**: 一般性信息提示，如功能建议、同步状态等低优先级通知
- **蓝色强调**: 需要用户关注的功能性提示，如新功能引导、重要更新
- **黄色提醒**: 需要用户留意的非紧急提醒，如安全设置、账户状态
- **红色警告**: 需要用户立即关注的紧急信息，如安全风险、服务异常

### 何时不使用

- **临时性反馈**: 操作成功/失败的即时反馈应使用 Toast 组件
- **需要用户确认**: 强制用户做出选择应使用 Dialog 组件
- **全局性通知**: 全局通知应使用系统通知栏，而非页面内 NoticeBar
- **大段说明文字**: 超过两行的内容应使用专门的说明区域或帮助页面

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 提示文字保持简短，一行以内 | 放置超过两行的冗长文字 | 横条设计不适合大段文字展示 |
| 使用语义正确的颜色变体 | 所有提示都用红色 | 用户会对颜色信号产生麻木 |
| 可关闭的提示使用关闭图标 | 始终使用详情箭头 | 用户需要明确的关闭入口 |
| 根据系统模式切换 Light/Dark | 固定使用一种模式 | 需要跟随系统主题适配 |
| 放置在内容区域顶部或相关内容附近 | 悬浮在页面中央 | NoticeBar 是嵌入式组件，非模态 |
| 左侧图标用于补充语义（如图标强调内容类型） | 左侧图标仅做装饰 | 图标应帮助用户快速理解提示类型 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 (Light) | 值 (Dark) | 类型 | 引用位置 |
|-------|-----------|-----------|------|---------|
| `hyperoscolor_container_notice_bar` | `rgba(0,0,0,0.04)` | `rgba(255,255,255,0.14)` | color | 灰色默认背景 |
| `hyperos-color-secondary` | `rgba(52,130,255,0.08)` | `rgba(71,136,255,0.25)` | color | 蓝色强调背景 |
| `hyperos-color-caution-container` | `rgba(255,159,5,0.1)` | — | color | 黄色提醒背景 |
| `hyperos-color-error-container` | `rgba(250,56,46,0.08)` | — | color | 红色警告背景 |
| `hyperos-color-on-surface-tertiary` | `rgba(0,0,0,0.6)` | `rgba(255,255,255,0.5)` | color | 灰色文字/图标色 |
| `hyperos-color-primary` | `#3482FF` | `#4788FF` | color | 蓝色图标色 |
| `hyperos-color-caution` | `#FF9F05` | — | color | 黄色系参考基色 |
| `hyperos-color-error` | `#FA382E` | — | color | 红色系参考基色 |
| `hyperos-color-on-surface` | `#000000` | — | color | 基础文字色 |
| `hyperos_theme_radius_medium` | `20px` | — | radius | Light 模式提示条圆角 |
| `hyperos_theme_radius_common` | `16px` | — | radius | Dark 模式提示条圆角 |
| `hyperos_theme_container_margin_base_horizontal` | `12px` | — | spacing | 外层容器水平内边距 |
| `hyperos_font_size_body2` | `14px` | — | font-size | 提示文字字号 |
| `hyperos_font_weight_body2` | `330` | — | font-weight | 提示文字字重 |
| `Body/Body 2` | `MiSans, Regular, 14px, 330, lh:100%, ls:0` | — | typography | 提示文字完整样式 |

---

## 设计注释

> 1. **圆角差异**: Light 模式使用 `20px`（`hyperos_theme_radius_medium`），Dark 模式使用 `16px`（`hyperos_theme_radius_common`）。Figma 标注说明圆角从旧版 `12px` 调整为 `20px`，Dark 模式可能尚未同步更新。
> 2. **最小高度 44px**: 单行文字时提示条高度为 44dp，上下各 12px 内边距，符合触摸目标最小尺寸要求。
> 3. **右侧图标使用字体图标**: 图标均使用 HyperOS Symbols 字体渲染（`HyperOS_Symbols_UI_VF` 和 `HyperOS_Symbols_VF`），尺寸统一 20×20，替代了旧版的 SVG 图标方案。
> 4. **左侧扩展图标**: 由 boolean 属性 `propValue` 控制显隐，大小为 20×20（Figma 标注说明为 24×24，但实际渲染为 20×20，以实际代码为准）。
> 5. **蓝色变体前景色差异**: Light 模式下文字使用 `#2E72E0`，而右侧图标使用 `#3482FF`（`hyperos-color-primary`），两者色相相近但亮度不同，实现时需注意区分。
> 6. **黄色/红色变体内容行结构**: 这两种变体在左侧图标与文字之间使用 `8px` gap，但文字与右侧操作图标之间使用 `12px` gap，与灰色/蓝色变体的统一 `8px` gap 有所不同。
> 7. **提示条宽度**: Figma 中固定为 `392px`（含外层 padding），实际使用时应为 `100%` 宽度跟随父容器，不应固定宽度。
> 8. **`overflow: clip`**: 内层容器设置了 `overflow: clip`，当文字过长时会被裁剪而非溢出。
