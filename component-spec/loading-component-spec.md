---
component: Loading
description: HyperOS 加载组件，提供加载动画图标、加载态按钮和进度条三种形式
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=90794-14633
figma_node_id: "90794:14633"
variants: "3 component sets: Loading/icon (8 variants: 2 sizes × 2 types × 2 states), Loading/按钮 (4 variants: 2 widths × 2 colors), Loading/进度条 (3 states)"
tokens_used: 15
---

# 加载 Loading

> HyperOS 系统级加载组件，在异步操作（安装、下载、数据加载等）进行期间向用户提供视觉反馈。包含三种子组件：**加载图标**（旋转动画 spinner + 可选文案）、**加载按钮**（按钮禁用加载态）和**进度条**（水平线性进度）。支持默认和小号两种尺寸，以及默认/禁用两种状态。

## 预览

![加载 Loading 全部变体预览](figma-screenshot-90794-14633.png)

---

## 组件结构

```
加载 Loading                                        // SECTION | 90794:14633
├── Loading/icon                                    // COMPONENT_SET | 28689:20114
│   ├── 型号=默认, 类型=无文案, 状态=默认            // COMPONENT | 28689:20115 | 26×26
│   │   └── 加载控件/icon 大黑                      // INSTANCE (spinner 图标)
│   ├── 型号=默认, 类型=无文案, 状态=禁用            // COMPONENT | 28689:20123 | 26×26
│   ├── 型号=小号, 类型=无文案, 状态=默认            // COMPONENT | 28689:20119 | 20×20
│   ├── 型号=小号, 类型=无文案, 状态=禁用            // COMPONENT | 28689:20127 | 20×20
│   ├── 型号=默认, 类型=有文案, 状态=默认            // COMPONENT | 45295:17562 | 48×55
│   │   ├── Loading/icon (spinner 26×26)           // INSTANCE
│   │   └── 文字 "加载中"                           // TEXT
│   ├── 型号=默认, 类型=有文案, 状态=禁用            // COMPONENT | 45295:17573 | 48×55
│   ├── 型号=小号, 类型=有文案, 状态=默认            // COMPONENT | 45295:17603 | 42×47
│   │   ├── Loading/icon (spinner 20×20)           // INSTANCE
│   │   └── 文字 "加载中"                           // TEXT
│   └── 型号=小号, 类型=有文案, 状态=禁用            // COMPONENT | 45295:17623 | 42×47
├── Loading/按钮                                    // COMPONENT_SET | 28689:20147
│   ├── Type=通栏按钮-灰色                          // COMPONENT | 28689:20148 | 336×50
│   │   ├── Loading/icon (spinner 20×20)           // INSTANCE
│   │   └── 文字 "安装中"                           // TEXT
│   ├── Type=通栏按钮-蓝色                          // COMPONENT | 80302:4888 | 336×50
│   ├── Type=1/2按钮-灰色                           // COMPONENT | 28689:20156 | 162×50
│   └── Type=1/2按钮-蓝色                           // COMPONENT | 80302:4892 | 162×50
└── Loading/进度条                                   // COMPONENT_SET | 42630:93717
    ├── Property 1=Default                          // COMPONENT | 28689:20165 | 245×6
    │   ├── 进度条背景 灰色 (轨道)                   // FRAME
    │   └── 进度填充 (蓝色渐变)                      // FRAME (absolute)
    ├── Property 1=100%                             // COMPONENT | 42630:93716 | 245×6
    └── Property 1=0%                               // COMPONENT | 42630:93688 | 245×6
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| Loading/icon | COMPONENT_SET | `28689:20114` | 加载旋转图标，2 尺寸 × 2 类型 × 2 状态 |
| Loading/按钮 | COMPONENT_SET | `28689:20147` | 加载态按钮，2 宽度 × 2 颜色 |
| Loading/进度条 | COMPONENT_SET | `42630:93717` | 水平线性进度条，3 种状态 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 子组件: Loading/icon — Spinner 图标

| CSS 属性 | 默认尺寸 | 小号尺寸 | Token |
|---------|---------|---------|-------|
| `width` | `26px` | `20px` | — |
| `height` | `26px` | `20px` | — |
| `overflow` | `clip` | `clip` | — |

> Spinner 图标通过 CSS 动画实现旋转效果，Figma 中以静态图片资产呈现。默认状态使用深色 spinner，禁用状态使用浅灰色 spinner。

### 子组件: Loading/icon — 有文案

| CSS 属性 | 默认尺寸 | 小号尺寸 | Token |
|---------|---------|---------|-------|
| `display` | `flex` | `flex` | — |
| `flex-direction` | `column` | `column` | — |
| `align-items` | `center` | `center` | — |
| `gap` | `8px` | `8px` | — |
| Spinner `size` | `26px` | `20px` | — |

#### 文案文字样式

| CSS 属性 | 默认尺寸 | 小号尺寸 | Token |
|---------|---------|---------|-------|
| `font-family` | MiSans | MiSans | — |
| `font-weight` | Medium (380) | Medium (380) | `hyperos_font_weight_Headline2` / `hyperos_font_weight_subtitle` |
| `font-size` | `16px` | `14px` | `hyperos_font_size_Headline2` / `hyperos_font_size_subtitle` |
| `line-height` | `normal` | `normal` | — |
| `letter-spacing` | `0` | `0` | — |
| `color` (默认态) | `rgba(0,0,0,0.8)` | `rgba(0,0,0,0.8)` | `hyperos-color-on-surface-secondary` |
| `text-align` | `center` | — | — |

### 子组件: Loading/按钮

| CSS 属性 | 通栏按钮-灰色 | 通栏按钮-蓝色 | 1/2按钮-灰色 | 1/2按钮-蓝色 | Token |
|---------|-------------|-------------|------------|------------|-------|
| `width` | `336px` | `336px` | `162px` | `162px` | — |
| `height` | `50px` | `50px` | `50px` | `50px` | — |
| `background-color` | `rgba(0,0,0,0.06)` | `#3382FF` | `rgba(0,0,0,0.06)` | `#3382FF` | `hyperos-color-surface-container-low` / `hyperos-color-primary` |
| `opacity` | `1` | `0.3` | `1` | `0.3` | — |
| `border-radius` | `16px` | `16px` | `16px` | `16px` | `hyperos_theme_radius_common` |
| `padding` | `0 20px` | `0 20px` | `0 20px` | `0 20px` | — |
| `display` | `flex` | `flex` | `flex` | `flex` | — |
| `align-items` | `center` | `center` | `center` | `center` | — |

#### 按钮内容行

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex` | `1 0 0` | — |
| `gap` | `8px` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |

#### 按钮内 Spinner

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `20px` | — |
| `height` | `20px` | — |

#### 按钮文字

| CSS 属性 | 灰色按钮 | 蓝色按钮 | Token |
|---------|---------|---------|-------|
| `font-family` | MiSans | MiSans | — |
| `font-weight` | Medium (380) | Medium (380) | `hyperos_font_weight_button` |
| `font-size` | `17px` | `17px` | `hyperos_font_size_button` |
| `text-align` | `center` | `center` | — |
| `color` | `rgba(0,0,0,0.3)` | `#FFFFFF` | `hyperos-color-on-surface-octonary` / `text & icon/on_Surface_button_disable` |

### 子组件: Loading/进度条

#### 容器

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `245px`（Figma 示意，实际应 `100%`） | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |

#### 轨道（背景）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `flex` | `1 0 0` | — |
| `height` | `6px` | — |
| `background-color` | `rgba(0,0,0,0.1)` | `hyperos-color-surface-container-high` |
| `border-radius` | `999px` | `hyperos_theme_radius_circle` |

#### 填充条（进度）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `position` | `absolute` | — |
| `top` | `0` | — |
| `left` | `0` | — |
| `height` | `6px` | — |
| `width` | 按进度百分比计算 | — |
| `background` | 蓝色渐变（`#0D84FF` 系） | `系统色/蓝-light` |
| `border-radius` | `999px`（继承轨道圆角） | `hyperos_theme_radius_circle` |

### 文字样式汇总

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `color` | Token |
|---------|--------------|-------------|---------------|--------------|---------|-------|
| 加载文案（默认尺寸） | MiSans | 16px | 380 (Medium) | normal | `rgba(0,0,0,0.8)` | `Headline/Headline 2` |
| 加载文案（小号尺寸） | MiSans | 14px | 380 (Medium) | normal | `rgba(0,0,0,0.8)` | `Subtitle/Subtitle` |
| 按钮文字 | MiSans | 17px | 380 (Medium) | normal | 按颜色变体 | `Button/Button` |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 加载文案 | `rgba(0,0,0,0.8)` | `hyperos-color-on-surface-secondary` |
| 灰色按钮背景 | `rgba(0,0,0,0.06)` | `hyperos-color-surface-container-low` |
| 灰色按钮文字 | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |
| 蓝色按钮背景 | `#3382FF` | `hyperos-color-primary` |
| 蓝色按钮文字 | `#FFFFFF` | `text & icon/on_Surface_button_disable` |
| 进度条轨道 | `rgba(0,0,0,0.1)` | `hyperos-color-surface-container-high` |
| 进度条填充 | `#0D84FF`（渐变） | `系统色/蓝-light` |

---

## 变体

### 维度定义

#### Loading/icon

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 型号 | `型号` | `默认` / `小号` | Spinner 尺寸 |
| 类型 | `类型` | `无文案` / `有文案` | 是否显示加载文字 |
| 状态 | `状态` | `默认` / `禁用` | 激活/禁用视觉状态 |

共计 **8 个变体**（2 尺寸 × 2 类型 × 2 状态）。

#### Loading/按钮

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| Type | `Type` | `通栏按钮-灰色` / `通栏按钮-蓝色` / `1/2按钮-灰色` / `1/2按钮-蓝色` | 按钮宽度 + 颜色组合 |

共计 **4 个变体**。

#### Loading/进度条

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| Property 1 | `Property 1` | `Default` / `100%` / `0%` | 进度状态示意 |

共计 **3 个变体**。

### 变体差异表

#### Loading/icon 按尺寸分组

| 属性 | 默认 | 小号 |
|-----|------|------|
| Spinner 尺寸 | `26 × 26px` | `20 × 20px` |
| 有文案时文字字号 | `16px` (`Headline/Headline 2`) | `14px` (`Subtitle/Subtitle`) |
| 有文案时组件总尺寸 | `48 × 55px` | `42 × 47px` |

#### Loading/icon 按状态分组

| 属性 | 默认 | 禁用 |
|-----|------|------|
| Spinner 图标 | 深色旋转图标 | 浅灰色旋转图标 |
| 文案颜色 | `rgba(0,0,0,0.8)` | 降低透明度 |

#### Loading/按钮按类型分组

| 属性 | 通栏-灰色 | 通栏-蓝色 | 1/2-灰色 | 1/2-蓝色 |
|-----|----------|----------|---------|---------|
| `width` | `336px` | `336px` | `162px` | `162px` |
| `background-color` | `rgba(0,0,0,0.06)` | `#3382FF` | `rgba(0,0,0,0.06)` | `#3382FF` |
| `opacity` | `1` | `0.3` | `1` | `0.3` |
| 文字色 | `rgba(0,0,0,0.3)` | `#FFFFFF` | `rgba(0,0,0,0.3)` | `#FFFFFF` |

#### Loading/进度条按状态分组

| 属性 | 0% | Default | 100% |
|-----|----|---------|------|
| 填充条 | 不渲染 | 部分宽度（按进度比例） | 等于轨道全宽 |

---

## 交互状态

> Loading 组件本身代表加载进行中的状态，不具备用户交互能力。

| 状态 | 说明 |
|-----|------|
| 加载中 | Spinner 持续旋转动画，按钮不可点击 |
| 加载完成 | 组件被移除或替换为完成态 UI |
| 禁用 | Spinner 和文案使用弱化颜色，表示不活跃的加载状态 |

### Spinner 动画

| 属性 | 值 |
|-----|----|
| `animation` | `rotate 360deg` |
| `animation-duration` | 由实现决定（建议 `1s`） |
| `animation-timing-function` | `linear` |
| `animation-iteration-count` | `infinite` |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

### Loading/icon

```typescript
interface LoadingIconProps {
  /** 尺寸型号 */
  size: '默认' | '小号';
  /** 是否显示加载文案 */
  showText: boolean;
  /** 状态 */
  state: '默认' | '禁用';
  /** 加载文案（有文案时生效） */
  text?: string; // 默认 "加载中"
}
```

### Loading/按钮

```typescript
interface LoadingButtonProps {
  /** 按钮类型 */
  type: '通栏按钮-灰色' | '通栏按钮-蓝色' | '1/2按钮-灰色' | '1/2按钮-蓝色';
  /** 按钮文字 */
  text?: string; // 默认 "安装中"
}
```

### Loading/进度条

```typescript
interface LoadingProgressProps {
  /** 当前进度百分比 0~100 */
  progress: number;
}
```

| Figma 属性名 | 类型 | 对应组件 | 对应 Prop | 默认值 | 说明 |
|-------------|------|---------|----------|-------|------|
| 型号 | Variant | Loading/icon | `size` | `默认` | Spinner 尺寸 |
| 类型 | Variant | Loading/icon | `showText` | `无文案` (false) | 是否显示文字 |
| 状态 | Variant | Loading/icon | `state` | `默认` | 激活/禁用 |
| Type | Variant | Loading/按钮 | `type` | `通栏按钮-灰色` | 按钮样式类型 |
| Property 1 | Variant | Loading/进度条 | `progress` | `Default` | 进度值 |

---

## 使用指南

### 何时使用

- **异步操作反馈**: 数据加载、文件上传/下载、应用安装等耗时操作
- **按钮加载态**: 用户点击按钮后操作尚未完成，使用 Loading/按钮替代原按钮
- **可量化进度**: 有明确进度百分比的操作（如下载），使用 Loading/进度条
- **页面/区域加载**: 页面或内容区域加载中，使用 Loading/icon 居中展示

### 何时不使用

- **骨架屏**: 首屏内容加载应优先使用 Skeleton 骨架屏组件
- **即时操作**: 耗时 <300ms 的操作不需要 Loading 反馈
- **后台操作**: 不影响用户当前操作的后台任务，不需要阻断式 Loading
- **下拉刷新**: 列表下拉刷新应使用专用的 PullToRefresh 组件

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 有明确进度时使用进度条 | 有进度数据却只用 spinner | 用户需要进度预期 |
| 加载按钮保持与原按钮相同宽度 | 加载后按钮宽度变化 | 避免布局跳动 |
| 蓝色按钮加载态使用 `opacity: 0.3` 整体降低 | 仅降低文字颜色 | 整体弱化表达"不可操作" |
| 灰色按钮加载态文字使用 `0.3` 透明度 | 使用完全透明文字 | 保持文字可读性表达当前状态 |
| 进度条使用蓝色渐变填充 | 进度条使用纯色填充 | 渐变增强进度方向感 |
| 加载超时后提供重试入口 | 无限加载无退出路径 | 用户需要控制权 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `hyperos-color-on-surface` | `#000000` | color | 基础文字色参考 |
| `hyperos-color-on-surface-secondary` | `rgba(0,0,0,0.8)` | color | 加载文案文字色 |
| `hyperos-color-on-surface-octonary` | `rgba(0,0,0,0.3)` | color | 灰色按钮禁用文字 |
| `hyperos-color-primary` | `#3482FF` | color | 蓝色按钮背景 |
| `hyperos-color-surface-container-low` | `rgba(0,0,0,0.06)` | color | 灰色按钮背景 |
| `hyperos-color-surface-container-high` | `rgba(0,0,0,0.1)` | color | 进度条轨道背景 |
| `text & icon/on_Surface_button_disable` | `#FFFFFF` | color | 蓝色按钮禁用文字 |
| `系统色/蓝-light` | `#0D84FF` | color | 进度条填充色 |
| `hyperos_theme_radius_common` | `16px` | radius | 按钮圆角 |
| `hyperos_theme_radius_circle` | `999px` | radius | 进度条全圆角 |
| `hyperos_font_size_Headline2` | `16px` | font-size | 默认尺寸加载文案 |
| `hyperos_font_weight_Headline2` | `380` | font-weight | 默认尺寸加载文案 |
| `hyperos_font_size_subtitle` | `14px` | font-size | 小号加载文案 |
| `hyperos_font_weight_subtitle` | `380` | font-weight | 小号加载文案 |
| `hyperos_font_size_button` | `17px` | font-size | 按钮文字 |
| `hyperos_font_weight_button` | `380` | font-weight | 按钮文字 |
| `Headline/Headline 2` | `MiSans, Medium, 16px, 380, lh:100%, ls:0` | typography | 默认尺寸加载文案完整样式 |
| `Subtitle/Subtitle` | `MiSans, Medium, 14px, 380, lh:100%, ls:0` | typography | 小号加载文案完整样式 |
| `Button/Button` | `MiSans, Medium, 17px, 380, lh:100%, ls:0` | typography | 按钮文字完整样式 |
| `Shadow/Shadow_Thick` | `DROP_SHADOW (0,36) 80px #00000014 + (0,0) 60px #0000000F` | effect | 展示区阴影（非组件本身） |

---

## 设计注释

> 1. **Spinner 动画**: Figma 中 spinner 以静态图片呈现，实际实现需添加 CSS `rotate` 无限循环动画。默认态 spinner 为深色（接近黑色），禁用态为浅灰色。
> 2. **蓝色按钮 opacity 策略**: 蓝色加载按钮对**整个按钮容器**应用 `opacity: 0.3`，而非仅对内容降低透明度。这意味着背景和文字都会受到影响。灰色按钮则不降低整体透明度，仅将文字色设为 `rgba(0,0,0,0.3)`。
> 3. **按钮宽度**: Figma 中通栏按钮为 `336px`、1/2 按钮为 `162px`，实际使用时应与原按钮保持一致宽度（通栏 100% / 1/2 约 50%），避免加载态切换时布局跳动。
> 4. **进度条填充色渐变**: 进度条填充部分使用蓝色渐变（`#0D84FF` 系），在 Figma 中以图片资产渲染，实际实现可使用 `linear-gradient` 或纯色 `#0D84FF` 替代。
> 5. **进度条容器宽度**: Figma 中固定为 `245px`，实际使用应设为 `100%` 跟随父容器宽度。轨道使用 `flex: 1 0 0` 已支持弹性布局。
> 6. **Loading/按钮内的 Spinner**: 按钮内始终使用 **小号禁用态** spinner（20×20），灰色按钮中为深灰 spinner，蓝色按钮中为白色 spinner。
> 7. **有文案时的组件尺寸**: 有文案模式下，组件整体尺寸由 spinner + gap(8px) + 文字行高自然撑开，不设固定宽高。默认尺寸约 48×55px，小号约 42×47px。
> 8. **文字样式差异**: 加载图标文案使用 `Headline 2`（16px）和 `Subtitle`（14px）两种样式；按钮文字使用 `Button`（17px）样式。三者 font-weight 相同（380/Medium），仅字号不同。
