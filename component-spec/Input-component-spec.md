---
component: Input
description: 单行文本输入框组件，支持前缀/后缀布局、套卡/通栏样式、多种位置圆角和交互状态
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=82713-133185
figma_node_id: "82713:133185"
variants: "4 dimensions, 48 variants + 3 error variants"
tokens_used: 18
---

# 单行输入框 Input

> 用于接收用户单行文本输入的表单控件，支持前缀标签和后缀图标两种布局模式，可适配套卡（白底）和通栏（灰底）两种容器风格，以及在列表中不同位置（独立/上/中/下）的圆角变化。

## 预览

![单行输入框全部变体预览](http://localhost:3845/assets/screenshot-82713-133185.png)

### 单行输入框变体总览

![单行输入框变体矩阵](http://localhost:3845/assets/screenshot-2795-27119.png)

### 报错状态预览

![单行输入框报错状态](http://localhost:3845/assets/screenshot-43336-45632.png)

---

## 组件结构

```
单选 Input                                    // FRAME | 82713:133185
├── 表头_Component&Instance                    // INSTANCE | 82713:133187
├── 单行输入框                                 // FRAME | 2795:27119
│   ├── [套卡] 前缀输入框-独立-默认态            // COMPONENT | 2795:27473
│   │   └── 输入框背景                         // FRAME | 2795:27474
│   │       ├── 前缀文本区                     // FRAME | 2795:27475
│   │       │   └── 前缀文本                   // TEXT | 2795:27476
│   │       └── 后缀区域                       // FRAME | 2795:27477
│   │           ├── 输入提示                   // TEXT | 2795:27479
│   │           └── 后缀图标                   // INSTANCE | 2795:27480
│   ├── [套卡] 后缀输入框-独立-默认态            // COMPONENT | 2795:27144
│   │   └── 输入框背景                         // FRAME | 2795:27145
│   │       ├── 输入提示文本区                   // FRAME | 2795:27146
│   │       │   └── 输入提示                   // TEXT | 2795:27147
│   │       └── 后缀图标区                     // FRAME | 2795:27148
│   │           └── 后缀图标                   // INSTANCE | 2795:27149
│   ├── [套卡] 前缀输入框-独立-激活态            // COMPONENT | 2795:27520
│   │   └── 外层容器                           // FRAME | 2795:27521
│   │       └── 输入框背景                     // FRAME | 2795:27522
│   │           ├── 前缀文本区                 // FRAME | 2795:27523
│   │           └── 输入区域                   // FRAME | 2795:27525
│   │               ├── 输入内容+光标           // FRAME | 2795:27526
│   │               └── 后缀图标               // INSTANCE | 2795:27532
│   ├── [通栏] 前缀输入框-独立-默认态            // COMPONENT | 12966:35429
│   │   └── 输入框背景 (灰底)                   // FRAME | 12966:35430
│   │       └── ...（结构同套卡）
│   ├── ... (其余 44 个变体)
│   └──
├── 单行输入框报错                              // FRAME | 43336:45632
│   ├── 白色版-报错                            // COMPONENT | 231:14557
│   │   ├── .输入框                            // FRAME | 231:14558
│   │   │   └── 按钮文字 (含光标+文本)          // FRAME | 231:14559
│   │   └── 内容错误的提示                      // FRAME | 231:14565
│   │       └── 错误提示                       // TEXT | 231:14567
│   ├── 灰色版-报错                            // COMPONENT | 43336:45629
│   │   └── 单行输入框报错 (实例)               // INSTANCE | 17730:63508
│   └── 带辅助信息                             // COMPONENT | 88712:13198
│       ├── 后缀输入框-输入态                   // INSTANCE
│       └── 辅助说明文字                        // INSTANCE
└── 标注文字组 (多个)                           // FRAME
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| 单行输入框 | FRAME | `2795:27119` | 主要变体容器，包含所有输入框变体 |
| 输入框背景 | FRAME | `2795:27474` | 输入框的可视容器，承载背景色和圆角 |
| 前缀文本 | TEXT | `2795:27476` | 左侧固定标签文字 |
| 后缀区域 | FRAME | `2795:27477` | 右侧内容区，包含占位文字和图标 |
| 后缀图标 | INSTANCE | `2795:27480` | 右侧操作图标（如眼睛图标） |
| 光标 | FRAME | `2795:27530` | 激活态/输入态的闪烁光标 |
| 内容错误的提示 | FRAME | `231:14565` | 报错状态下的错误信息容器 |
| 单行输入框报错 | FRAME | `43336:45632` | 报错变体容器 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器（外层包裹）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `392px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `padding-left` | `12px` | — |
| `padding-right` | `12px` | — |

### 输入框背景（套卡-默认态）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `height` | `56px` | — |
| `display` | `flex` | — |
| `flex` | `1 0 0` | — |
| `align-items` | `center` | — |
| `background-color` | `#FFFFFF` | `元素色/container_list` |
| `border-radius` | `20px`（独立位置，四角相同） | `miuix_theme_radius_medium` |
| `overflow` | `hidden` | — |
| `border` | 无 | — |

### 输入框背景（通栏-默认态）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `height` | `56px` | — |
| `display` | `flex` | — |
| `flex` | `1 0 0` | — |
| `align-items` | `center` | — |
| `background-color` | `rgba(0,0,0,0.06)` | `miuix_default_color_surface_container_low` |
| `border-radius` | `20px`（独立位置，四角相同） | `miuix_theme_radius_medium` |
| `overflow` | `hidden` | — |
| `border` | 无 | — |

### 输入框背景（激活态/输入态）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `height` | `56px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `background-color` | 继承默认态背景 | — |
| `border` | `2px solid #3482FF` | `miuix_default_color_primary` |
| `border-radius` | `16px`（因 2px 边框内缩） | — |
| `overflow` | `hidden` | — |

### 子组件: 前缀文本区（前缀输入框类型）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex` | `1 0 0` | — |
| `align-items` | `center` | — |
| `padding-left` | `16px` | `spacing-xl` |
| `padding-right` | `10px` | — |
| `padding-top` | `16.5px` | — |
| `padding-bottom` | `16.5px` | — |

### 子组件: 后缀区域（前缀输入框类型-默认态）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `width` | `116px` | — |
| `flex-shrink` | `0` | — |
| `align-items` | `center` | — |
| `justify-content` | `flex-end` | — |
| `gap` | `12px` | — |
| `padding-right` | `16px` | `spacing-xl` |

### 子组件: 占位文本区（后缀输入框类型）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex` | `1 0 0` | — |
| `align-items` | `center` | — |
| `padding` | `16.5px 16px` | — |

### 子组件: 后缀图标区（后缀输入框类型）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-shrink` | `0` | — |
| `align-items` | `center` | — |
| `height` | `100%` | — |
| `padding-left` | `10px` | — |
| `padding-right` | `16px` | `spacing-xl` |

### 子组件: 后缀图标

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `24px` | — |
| `height` | `24px` | — |
| `flex-shrink` | `0` | — |
| `color` | `#000000` （推测，来自图标 Token） | `✦/_icon/icon-default` |

### 子组件: 光标（激活态/输入态）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `2.18px` | — |
| `background-color` | `#3482FF` | `miuix_default_color_primary` |
| `border-radius` | `0.73px` | — |
| `position` | `absolute` | — |

### 子组件: 报错容器

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `392px` | — |
| `height` | `99px` | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `padding-top` | `8px` | — |
| `padding-bottom` | `16px` | — |
| `padding-left` | `12px` | — |
| `padding-right` | `12px` | — |

### 子组件: 报错输入框

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `height` | `56px` | — |
| `width` | `100%` | — |
| `background-color` | `#FFFFFF`（白色版） / `rgba(0,0,0,0.06)`（灰色版） | `元素色/container_list` / `miuix_default_color_surface_container_low` |
| `border` | `2px solid #3482FF` | `miuix_default_color_primary` |
| `border-radius` | `20px` | `miuix_theme_radius_medium` |

### 子组件: 错误提示文字

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `padding-left` | `8px` | — |
| `padding-right` | `8px` | — |

### 子组件: 带辅助信息-辅助文字

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `padding-top` | `8px` | — |
| `padding-bottom` | `20px` | — |
| `padding-left` | `28px` | — |
| `padding-right` | `28px` | — |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| 前缀标签 | MiSans | 17px | 380 (Medium) | 100% | 0 | `#000000` | `Headline/Headline 1` |
| 占位文字（前缀模式右侧） | MiSans | 16px | 330 (Regular) | 100% | 0 | `rgba(0,0,0,0.3)` | `Body/Body 1` |
| 占位文字（后缀模式左侧） | MiSans | 17px | 380 (Medium) | 100% | 0 | `rgba(0,0,0,0.3)` | `Headline/Headline 1` |
| 输入内容（激活/输入态） | MiSans | 16px | 330 (Regular) | 100% | 0 | `rgba(0,0,0,0.3)`（激活） / `#000000`（输入） | `Body/Body 1` |
| 错误提示 | MiSans | 14px | 380 (Medium) | 100% | 0 | `#FA382E` | — |
| 辅助说明 | MiSans | 13px | 330 (Regular) | 100% | 0 | `rgba(0,0,0,0.6)` | — |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 输入框背景（套卡） | `#FFFFFF` | `元素色/container_list` |
| 输入框背景（通栏） | `rgba(0,0,0,0.06)` | `miuix_default_color_surface_container_low` |
| 激活边框色 | `#3482FF` | `miuix_default_color_primary` |
| 光标色 | `#3482FF` | `miuix_default_color_primary` |
| 前缀文字色 | `#000000` | `miuix_default_color_on_surface` |
| 占位文字色 | `rgba(0,0,0,0.3)` | `miuix_default_color_on_surface_octonary` |
| 输入文字色 | `#000000` | `miuix_default_color_on_surface` |
| 错误提示色 | `#FA382E` | `miuix_default_color_error` |
| 辅助说明色 | `rgba(0,0,0,0.6)` | `miuix_default_color_on_surface_tertiary` |
| 图标色 | `rgba(0,0,0,0.9)` | `✦/_icon/icon-default` |

---

## 变体

### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 容器风格 | `套卡/通栏` | `套卡` / `通栏` | 套卡为白色背景，通栏为灰色背景 |
| 类型 | `类型` | `前缀输入框` / `后缀输入框` | 前缀模式左侧有固定标签，后缀模式为全宽输入 |
| 位置 | `位置` | `独立` / `上` / `中` / `下` | 控制输入框在列表中的圆角位置 |
| 状态 | `状态` | `默认态` / `激活态` / `输入态` | 控制输入框的交互状态 |

共计 **2 × 2 × 4 × 3 = 48 个变体** + **3 个报错变体**。

### 变体差异表

> 仅列出各变体之间**有差异**的属性。未列出的属性与默认变体（套卡/前缀输入框/独立/默认态）相同。

#### 按容器风格分组

| 属性 | `套卡` | `通栏` |
|-----|--------|--------|
| `background-color`（输入框背景） | `#FFFFFF` (`元素色/container_list`) | `rgba(0,0,0,0.06)` (`miuix_default_color_surface_container_low`) |

#### 按类型分组

| 属性 | `前缀输入框` | `后缀输入框` |
|-----|------------|------------|
| 左侧内容 | 固定标签文字（"前缀"），黑色，17px Medium | 占位提示文字（"输入提示"），rgba(0,0,0,0.3)，17px Medium |
| 左侧 `padding` | `16px 10px 16.5px 16px` | `16.5px 16px` |
| 右侧内容 | 占位文字 + 后缀图标 | 仅后缀图标 |
| 右侧 `width` | `116px`（固定） | `auto`（自适应） |
| 右侧 `text-align` | `right` | — |
| 占位文字 `font-size` | `16px` (Body 1) | — |
| 占位文字 `color` | `rgba(0,0,0,0.3)` | — |

#### 按位置分组

| 属性 | `独立` | `上` | `中` | `下` |
|-----|--------|------|------|------|
| `border-radius` 左上 | `20px` | `20px` | `20px` | `0` |
| `border-radius` 右上 | `20px` | `20px` | `20px` | `0` |
| `border-radius` 左下 | `20px` | `0` | `20px` | `20px` |
| `border-radius` 右下 | `20px` | `0` | `20px` | `20px` |
| 外层容器 `overflow` | — | — | — | `hidden`，`border-radius: 0 0 16px 16px` |

#### 按状态分组

| 属性 | `默认态` | `激活态` | `输入态` |
|-----|---------|---------|---------|
| `border` | 无 | `2px solid #3482FF` | `2px solid #3482FF` |
| 输入框内 `border-radius` | `20px` | `16px`（因 border 内缩） | `16px`（因 border 内缩） |
| 外层布局 | 单层 flex row | 双层：column 包裹 → row 内容 | 双层：column 包裹 → row 内容 |
| 光标 | 不显示 | 显示，`#3482FF` | 显示，`#3482FF` |
| 右侧输入文字色 | `rgba(0,0,0,0.3)` | `rgba(0,0,0,0.3)` | `#000000` |
| 右侧输入文字内容 | "输入提示" | "输入内容" | "输入内容" |

#### 报错变体

| 属性 | `白色版-报错` | `灰色版-报错` | `带辅助信息` |
|-----|-------------|-------------|-------------|
| 容器高度 | `99px` | `99px` | `auto`（hug） |
| 输入框 `background-color` | `#FFFFFF` | `rgba(0,0,0,0.06)` | `#FFFFFF` |
| 输入框 `border` | `2px solid #3482FF` | `2px solid #3482FF` | `2px solid #3482FF` |
| 错误提示文字 | 显示，红色 14px | 显示，红色 14px | 不显示 |
| 辅助说明文字 | 不显示 | 不显示 | 显示，13px rgba(0,0,0,0.6) |
| 容器 `padding` | `8px 12px 16px` | `8px 12px 16px` | `0` |

---

## 交互状态

> 以「默认态」为基准，其他状态仅列出**发生变化**的属性。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态） | — |
| `active` | 输入框获得焦点（tap / click） | `border` | `2px solid #3482FF` | `miuix_default_color_primary` |
| `active` | 输入框获得焦点 | `border-radius`（内层） | `16px` | — |
| `active` | 输入框获得焦点 | 光标 `visibility` | `visible` | — |
| `active` | 输入框获得焦点 | 光标 `background-color` | `#3482FF` | `miuix_default_color_primary` |
| `active` | 输入框获得焦点 | 右侧文字内容 | 由"输入提示"变为"输入内容" | — |
| `input` | 用户正在输入文字 | `border` | `2px solid #3482FF` | `miuix_default_color_primary` |
| `input` | 用户正在输入文字 | 输入文字 `color` | `#000000` | `miuix_default_color_on_surface` |
| `input` | 用户正在输入文字 | 光标 `visibility` | `visible` | — |
| `error` | 输入内容校验失败 | `border` | `2px solid #3482FF` | `miuix_default_color_primary` |
| `error` | 输入内容校验失败 | 错误提示 `visibility` | `visible` | — |
| `error` | 输入内容校验失败 | 错误提示 `color` | `#FA382E` | `miuix_default_color_error` |
| `disabled` | Figma 未定义 | — | Figma 未定义，请由设计团队补充 | — |
| `hover` | Figma 未定义 | — | Figma 未定义，请由设计团队补充 | — |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

```typescript
interface InputProps {
  /** 容器风格：套卡为白色背景卡片，通栏为灰色背景 */
  variant: '套卡' | '通栏';
  /** 输入框类型：前缀输入框左侧有固定标签，后缀输入框为全宽输入区域 */
  type: '前缀输入框' | '后缀输入框';
  /** 在列表中的位置，控制圆角显示 */
  position: '独立' | '上' | '中' | '下';
  /** 交互状态 */
  state: '默认态' | '激活态' | '输入态';
  /** 是否显示后缀图标 */
  showSuffixIcon?: boolean; // 默认: true
  /** 前缀标签文字（仅前缀输入框类型有效） */
  prefixLabel?: string; // 默认: "前缀"
  /** 占位提示文字 */
  placeholder?: string; // 默认: "输入提示"
  /** 输入内容 */
  value?: string;
  /** 后缀图标（Instance Swap） */
  suffixIcon?: ReactNode; // 默认: 眼睛图标
}

interface InputErrorProps {
  /** 报错类型 */
  type: '白色版-报错' | '灰色版-报错' | '带辅助信息';
  /** 输入内容 */
  value?: string;
  /** 错误提示文字（仅报错类型有效） */
  errorMessage?: string;
  /** 辅助说明文字（仅带辅助信息类型有效） */
  helperText?: string;
  /** 是否显示后缀图标 */
  showSuffixIcon?: boolean; // 默认: true
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 套卡/通栏 | Variant | `variant` | `套卡` | 容器背景风格 |
| 类型 | Variant | `type` | `前缀输入框` | 输入框布局类型 |
| 位置 | Variant | `position` | `独立` | 列表位置圆角 |
| 状态 | Variant | `state` | `默认态` | 交互状态 |
| propValue | Boolean | `showSuffixIcon` | `true` | 是否显示后缀图标 |

---

## 使用指南

### 何时使用

- **表单输入场景**：需要用户输入单行文本（如姓名、手机号、密码等），使用前缀输入框类型配合描述性标签
- **搜索/筛选场景**：仅需简单文本输入时，使用后缀输入框类型配合搜索图标
- **设置项输入**：在设置列表中嵌入输入框，使用对应位置变体（上/中/下）保持与列表的圆角一致性
- **套卡风格**：在灰色页面背景上使用白色输入框，突出输入区域
- **通栏风格**：在白色卡片内部使用灰色输入框，与卡片融合

### 何时不使用

- **多行文本输入**：应使用 TextArea 组件代替
- **仅展示/只读信息**：应使用 ListItem 或 Text 组件代替
- **选择操作**：应使用 Select / Picker 组件代替
- **搜索框（带独立搜索栏 UI）**：应使用 SearchBar 组件代替

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 前缀标签保持简短（2-4字） | 使用过长的前缀标签 | 前缀标签占用固定宽度，过长会挤压输入区域 |
| 输入提示文字说明预期输入格式 | 使用无意义的占位文字（如"请输入"） | 有效的提示文字可以降低用户输入错误率 |
| 错误提示紧跟输入框下方显示 | 使用 Toast 或弹窗显示输入错误 | 就近反馈帮助用户快速定位问题 |
| 在列表中使用正确的位置变体 | 所有输入框都使用独立变体 | 正确的圆角衔接保持列表视觉连续性 |
| 套卡/通栏风格与页面背景匹配 | 在白色背景上使用套卡（白色）输入框 | 白底白框缺乏对比，用户难以识别输入区域 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `元素色/container_list` | `#FFFFFF` | color | 套卡输入框背景 |
| `miuix_default_color_surface_container_low` | `rgba(0,0,0,0.06)` | color | 通栏输入框背景 |
| `miuix_default_color_primary` | `#3482FF` | color | 激活边框、光标颜色 |
| `miuix_default_color_on_surface` | `#000000` | color | 前缀文字、输入文字 |
| `miuix_default_color_on_surface_octonary` | `rgba(0,0,0,0.3)` | color | 占位文字颜色 |
| `miuix_default_color_on_surface_tertiary` | `rgba(0,0,0,0.6)` | color | 辅助说明文字 |
| `miuix_default_color_on_surface_quaternary` | `rgba(0,0,0,0.4)` | color | 次级文字 |
| `miuix_default_color_error` | `#FA382E` | color | 错误提示文字 |
| `miuix_default_color_on_primary` | `#FFFFFF` | color | 主色上的文字 |
| `miuix_default_color_surface` | `#FFFFFF` | color | 表面色 |
| `miuix_default_color_surface_low` | `#F3F3F3` | color | 低层表面色 |
| `✦/_icon/icon-default` | `rgba(0,0,0,0.9)` | color | 默认图标颜色 |
| `miuix_theme_radius_medium` | `20px` | radius | 输入框圆角 |
| `miuix_theme_radius_big` | `36px` | radius | 大圆角 |
| `miuix_theme_radius_demi_big` | `24px` | radius | 中大圆角 |
| `spacing-xl` | `16px` | spacing | 内边距 |
| `miuix_font_size_headline1` | `17px` | font-size | 标题/标签字号 |
| `miuix_font_weight_headline1` | `380` | font-weight | 标题/标签字重 |
| `miuix_font_size_body1` | `16px` | font-size | 正文/输入字号 |
| `miuix_font_weight_body1` | `330` | font-weight | 正文/输入字重 |
| `Headline/Headline 1` | `MiSans, Medium, 17px, 380, lh:100%, ls:0` | typography | 标签/占位文字样式 |
| `Body/Body 1` | `MiSans, Regular, 16px, 330, lh:100%, ls:0` | typography | 输入内容文字样式 |

---

## 设计注释

> 1. **前缀输入框**与**后缀输入框**的核心区别在于布局结构：前缀模式左侧为固定标签区，右侧为输入+图标区；后缀模式左侧为全宽输入区，右侧仅有图标。
> 2. **激活态**与**输入态**的主要区别在于输入文字颜色：激活态的输入内容为占位色 `rgba(0,0,0,0.3)`，输入态为实际文字色 `#000000`。
> 3. **位置变体**的圆角规则遵循小米 HyperOS 列表卡片系统：独立项四角圆角，首项仅上方圆角，中间项保留圆角（由容器裁剪），末项仅下方圆角。
> 4. **报错状态**独立于主变体系统，采用不同的组件结构（COMPONENT 而非 COMPONENT_SET 的子变体），白色版和灰色版对应套卡/通栏两种风格。
> 5. **带辅助信息**变体在输入框下方增加了说明文字区域，字号 13px、颜色 `rgba(0,0,0,0.6)`，用于提供补充说明。
> 6. 后缀图标默认为 `24×24px` 的 Instance Swap 组件，可替换为任意图标。
> 7. 光标宽度为 `2.18px`，颜色跟随主题色 `miuix_default_color_primary`。
