---
component: Actionsheet
description: 底部弹出的操作面板，用于提供一组与当前上下文相关的操作选项
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=82713-134400
figma_node_id: "82713:134400"
variants: "2 dimensions (类型 × 主题), 4 variants (陈列型/近手型 × Light/Dark)"
tokens_used: 22
---

# 行动操作列表 Actionsheet

> 从屏幕底部滑入的模态操作面板，提供一组上下文相关的操作按钮。支持「陈列型」和「近手型」两种布局，适用于手机端和 Pad 端。常用于确认操作、分享、删除等需要二次确认的场景。

## 预览

![Actionsheet 全部变体预览](http://localhost:3845/assets/screenshot-82713-134400.png)

---

## 组件结构

```
行动操作列表 Actionsheet                     // FRAME | 82713:134400
├── 表头_Component&Instance                  // INSTANCE | 82713:134401
├── Actionsheet (预览)                       // FRAME | 80248:41937
├── .Actionsheet 元件                        // FRAME (COMPONENT_SET) | 42239:22489
│   ├── 类型=陈列型                           // COMPONENT | 42239:22079
│   │   ├── 操作面板                          // FRAME | 42239:22016
│   │   │   ├── Background                   // FRAME | 42239:22036
│   │   │   └── 操作按钮组                    // FRAME | 42239:22018
│   │   │       ├── .Description             // FRAME | 42239:22019
│   │   │       │   └── 描述文字              // TEXT
│   │   │       ├── .Buttons (按钮1)          // FRAME | 42239:22020
│   │   │       ├── .Buttons (按钮2)          // FRAME | 42239:22393
│   │   │       ├── .Buttons (按钮3)          // FRAME | 42239:22396
│   │   │       ├── .Buttons (按钮4)          // FRAME | 42239:22102
│   │   │       └── .Buttons (取消)           // INSTANCE | Cancel
│   │   │           └── 默认按钮              // FRAME | 74210:1039
│   │   └── ...
│   └── 类型=近手型                           // COMPONENT | 82080:4312
│       └── 操作面板                          // FRAME | 82080:4313
│           └── 操作按钮组                    // FRAME | 82080:4317
│               ├── .Description             // FRAME | 82080:4318
│               ├── .Buttons (按钮1)          // FRAME | 82080:4319
│               ├── .Buttons (按钮2)          // FRAME | 82080:4320
│               ├── .Buttons (按钮3)          // FRAME | 82080:4321
│               └── .Buttons (按钮4)          // FRAME | 82080:4322
├── .Buttons                                 // FRAME | 42097:116239
│   ├── State=Default                        // COMPONENT | 42097:116238
│   ├── State=Destructive                    // COMPONENT | 42097:116237
│   ├── State=Default Disable                // COMPONENT | 42097:116236
│   ├── State=Destructiv Disablee            // COMPONENT | 42315:15203
│   └── State=Cancel                         // COMPONENT | 42097:116448
└── .Description                             // FRAME | 42097:116244
    └── Property 1=Light Description         // COMPONENT | 42097:116242
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| .Actionsheet 元件 | COMPONENT_SET | `42239:22489` | Actionsheet 核心组件集，包含「陈列型」「近手型」两个变体 |
| 类型=陈列型 | COMPONENT | `42239:22079` | 标准布局，宽 368px，适用于手机端 |
| 类型=近手型 | COMPONENT | `82080:4312` | 紧凑布局，宽 336px，底部留有 12px 间距 |
| 操作面板 | FRAME | `42239:22016` | 面板主容器，包含背景和按钮组 |
| 操作按钮组 | FRAME | `42239:22018` | 垂直排列的按钮列表容器 |
| .Description | FRAME | `42239:22019` | 描述信息区域，位于按钮列表上方 |
| .Buttons | COMPONENT_SET | `42097:116239` | 按钮子组件集，包含 5 种状态 |
| .Description | FRAME | `42097:116244` | 独立的描述信息组件 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器：操作面板（陈列型）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `368px` | — |
| `height` | `auto`（hug） | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `justify-content` | `flex-end` | — |
| `background-color` | `#FFFFFF` | `miuix_default_color_surface_highest` |
| `border-radius` | `36px` | `miuix_theme_radius_big` |
| `overflow` | `hidden`（Background 层） | — |

### 容器：操作面板（近手型）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `336px` | — |
| `height` | `auto`（hug） | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `justify-content` | `flex-end` | — |
| `padding-bottom` | `12px`（外层容器） | — |
| `background-color` | `#FFFFFF` | `miuix_default_color_surface_highest` |
| `border-radius` | `36px` | `miuix_theme_radius_big` |

### 子组件: 操作按钮组

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `flex-start` | — |
| `width` | `100%`（fill） | — |

### 子组件: .Buttons（默认按钮行）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `width` | `100%`（fill） | — |
| `max-width` | `368px`（陈列型）/ `336px`（近手型） | — |
| `padding-top` | `16.5px` | — |
| `padding-bottom` | `16.5px` | — |
| `padding-left` | `24px` | — |
| `padding-right` | `24px` | — |

### 子组件: .Buttons（取消按钮行）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `flex-start` | — |
| `width` | `100%`（fill） | — |
| `padding-top` | `16px` | — |
| `padding-bottom` | `24px` | — |
| `padding-left` | `24px` | — |
| `padding-right` | `24px` | — |

### 子组件: 取消按钮（默认按钮）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `width` | `100%`（fill） | — |
| `max-width` | `336px` | — |
| `padding-top` | `13.5px` | — |
| `padding-bottom` | `13.5px` | — |
| `padding-left` | `20px` | — |
| `padding-right` | `20px` | — |
| `background-color` | `rgba(0,0,0,0.06)` | `miuix_default_color_tertiary` |
| `border-radius` | `16px` | `miuix_theme_radius_common` |

### 子组件: .Description

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `width` | `100%`（fill） | — |
| `max-width` | `368px`（陈列型）/ `336px`（近手型） | — |
| `padding-top` | `24px` | — |
| `padding-bottom` | `16px` | — |
| `padding-left` | `24px` | — |
| `padding-right` | `24px` | — |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| 操作按钮文字 | MiSans | 17px | 380 | 100% | 0 | `#000000` | `Headline/Headline 1` |
| 描述信息文字 | MiSans | 14px | 330 | 100% | 0 | `rgba(0,0,0,0.6)` | `Body/Body 2` |
| 取消按钮文字 | MiSans | 17px | 380 | 100% | 0 | `rgba(0,0,0,0.8)` | `Button/Button` |
| 警示按钮文字 | MiSans | 17px | 380 | 100% | 0 | `#FA382E` | `Headline/Headline 1` |
| 禁用按钮文字 | MiSans | 17px | 380 | 100% | 0 | `rgba(0,0,0,0.3)` | `Headline/Headline 1` |

### 颜色一览

| 语义用途 | 值（Light） | 值（Dark） | Token |
|---------|-----------|-----------|-------|
| 面板背景色 | `#FFFFFF` | `#2C2C2C` | `miuix_default_color_surface_highest` |
| 操作按钮文字色 | `#000000` | `rgba(255,255,255,0.95)` | `miuix_default_color_on_surface` |
| 描述信息文字色 | `rgba(0,0,0,0.6)` | `rgba(255,255,255,0.5)` | `miuix_default_color_on_surface_tertiary` |
| 取消按钮背景色 | `rgba(0,0,0,0.06)` | 未定义 | `miuix_default_color_tertiary` |
| 取消按钮文字色 | `rgba(0,0,0,0.8)` | 未定义 | `miuix_default_color_on_tertiary` |
| 警示色 | `#FA382E` | 未定义 | `miuix_default_color_error` |
| 禁用按钮文字色 | `rgba(0,0,0,0.3)` | 未定义 | `miuix_default_color_on_surface_octonary` |
| 警示禁用色 | `rgba(229,44,32,0.3)` | 未定义 | `系统色-dark/primary-disable/red` (30% opacity) |

---

## 变体

### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `类型` / `propValue` | `陈列型` / `近手型` | 控制面板布局模式。陈列型宽 368px（手机端标准），近手型宽 336px（紧凑模式） |
| 主题 | `propValue1` | `Light` / `Dark` | 控制面板配色模式 |
| 材质 | `propValue` (外层) | `纯色` | OS4 仅使用纯色材质（玻璃、混色已禁用） |

共计 **2 × 2 = 4 个有效变体**（陈列型/近手型 × Light/Dark）。

> **注意**：Figma 中存在「玻璃」和「混色」材质变体（`80248:41938`、`88247:92633`、`80248:42109`、`88247:92593`），但均标注为 **OS4 禁用**（`hidden="true"`），不应在 OS4 中使用。

### 变体差异表

> 仅列出各变体之间**有差异**的属性。未列出的属性与默认变体（陈列型 Light）相同。

#### 按「类型」分组

| 属性 | `陈列型` | `近手型` |
|-----|---------|---------|
| `width`（操作面板） | `368px` | `336px` |
| `max-width`（按钮行） | `368px` | `336px` |
| `max-width`（描述区） | `368px` | `336px` |
| 外层容器 `padding-bottom` | `0` | `12px` |
| 取消按钮 | 包含独立的取消按钮（带背景色） | Figma 中未定义取消按钮 |

#### 按「主题」分组

| 属性 | `Light` | `Dark` |
|-----|---------|--------|
| 面板 `background-color` | `#FFFFFF` | `#2C2C2C` |
| 操作按钮 `color` | `#000000` | `rgba(255,255,255,0.95)` |
| 描述信息 `color` | `rgba(0,0,0,0.6)` | `rgba(255,255,255,0.5)` |

---

## 交互状态

> 以「默认态」为基准，其他状态仅列出**发生变化**的属性。

### 操作按钮状态

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `Default` | — | — | （基准状态） | — |
| `Destructive` | 按钮语义为警示/危险操作 | `color` | `#FA382E` | `miuix_default_color_error` |
| `Default Disable` | `disabled=true` | `color` | `rgba(0,0,0,0.3)` | `miuix_default_color_on_surface_octonary` |
| `Destructiv Disable` | 警示按钮 + `disabled=true` | `color` | `rgba(229,44,32,0.3)` | — |
| `Cancel` | 取消按钮 | 整体样式变化 | 添加背景色容器，见「取消按钮」子组件规范 | — |

> **hover / active / focused 状态**：Figma 未定义，请由设计团队补充。

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

```typescript
interface ActionsheetProps {
  /** 面板布局类型：陈列型（368px 标准宽度）或近手型（336px 紧凑宽度） */
  type: '陈列型' | '近手型';
  /** 是否显示描述信息区域 */
  showDescription?: boolean; // 默认: true
  /** 是否显示按钮1 */
  showButton1?: boolean; // 默认: true
  /** 是否显示按钮2 */
  showButton2?: boolean; // 默认: true
  /** 是否显示按钮3 */
  showButton3?: boolean; // 默认: true
  /** 是否显示按钮4 */
  showButton4?: boolean; // 默认: true
  /** 是否显示取消/警示按钮（仅陈列型） */
  showDestructiveButton?: boolean; // 默认: true
}

interface ActionsheetContainerProps {
  /** 材质类型（OS4 仅支持纯色） */
  material: '纯色';
  /** 主题模式 */
  theme: 'Light' | 'Dark';
}

interface ActionsheetButtonProps {
  /** 按钮状态 */
  state: 'Default' | 'Destructive' | 'Default Disable' | 'Destructiv Disable' | 'Cancel';
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 类型 / propValue | Variant | `type` | `陈列型` | 控制面板宽度和布局 |
| showDescription | Boolean | `showDescription` | `true` | 控制描述信息区域的显隐 |
| showButton1 | Boolean | `showButton1` | `true` | 控制按钮1的显隐 |
| showButton2 | Boolean | `showButton2` | `true` | 控制按钮2的显隐 |
| showButton3 | Boolean | `showButton3` | `true` | 控制按钮3的显隐 |
| showButton4 | Boolean | `showButton4` | `true` | 控制按钮4的显隐 |
| showDestructiveButton | Boolean | `showDestructiveButton` | `true` | 控制取消按钮的显隐（仅陈列型） |
| propValue (外层) | Variant | `material` | `纯色` | 材质，OS4 仅纯色 |
| propValue1 | Variant | `theme` | `Light` | 主题模式 |
| State (Buttons) | Variant | `state` | `Default` | 按钮状态 |

---

## 使用指南

### 何时使用

- **确认危险操作**：使用「陈列型」+ `Destructive` 按钮，用于删除、退出登录等不可逆操作的二次确认
- **分享/更多操作**：使用「陈列型」，展示分享到微信、QQ 等操作选项列表
- **快捷操作**：使用「近手型」，在 Pad 端或需要紧凑布局时提供快速操作入口
- **带说明的操作**：启用 `showDescription`，在按钮列表上方展示操作说明文字

### 何时不使用

- **仅需简单确认**：如只需「确认/取消」两个选项，应使用 **Dialog（对话框）** 代替
- **需要表单输入**：如需用户填写信息，应使用 **弹窗表单** 或 **页面** 代替
- **操作项过多**：超过 5 个操作项时，应考虑使用 **菜单 Menu** 或 **列表页面** 代替
- **非模态操作**：如不需要阻断当前流程，应使用 **ContextMenu** 或 **Popover** 代替

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 将最常用的操作放在列表顶部 | 将取消按钮放在操作列表中间 | 取消按钮应始终在底部，保持一致的位置认知 |
| 警示操作使用 `Destructive` 状态标红 | 所有按钮都使用默认黑色 | 红色文字能有效警示用户，防止误操作 |
| 不可用的操作使用 `Disable` 状态 | 隐藏不可用的操作 | 保持界面一致性，让用户知晓操作的存在 |
| 描述信息保持简短（一行为佳） | 在描述区域放置大段文字 | 操作面板应快速决策，过多文字增加认知负担 |
| 手机端使用「陈列型」（368px） | 手机端使用「近手型」 | 陈列型宽度与手机屏幕适配更佳 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值（Light） | 值（Dark） | 类型 | 引用位置 |
|-------|-----------|-----------|------|---------|
| `miuix_default_color_surface_highest` | `#FFFFFF` | `#2C2C2C` | color | 面板背景色 |
| `miuix_default_color_on_surface` | `#000000` | `rgba(255,255,255,0.95)` | color | 操作按钮文字色 |
| `miuix_default_color_on_surface_tertiary` | `rgba(0,0,0,0.6)` | `rgba(255,255,255,0.5)` | color | 描述信息文字色 |
| `miuix_default_color_on_surface_quaternary` | `rgba(0,0,0,0.4)` | 未定义 | color | 描述信息文字色（备用） |
| `miuix_default_color_on_surface_octonary` | `rgba(0,0,0,0.3)` | 未定义 | color | 禁用按钮文字色 |
| `miuix_default_color_tertiary` | `rgba(0,0,0,0.06)` | 未定义 | color | 取消按钮背景色 |
| `miuix_default_color_on_tertiary` | `rgba(0,0,0,0.8)` | 未定义 | color | 取消按钮文字色 |
| `miuix_default_color_error` | `#FA382E` | 未定义 | color | 警示按钮文字色 |
| `miuix_default_color_primary` | `#3482FF` | 未定义 | color | 主色（预留） |
| `miuix_default_color_surface` | `#FFFFFF` | 未定义 | color | 页面背景色 |
| `miuix_default_color_outline` | `rgba(0,0,0,0.1)` | 未定义 | color | 分割线颜色（预留） |
| `miuix_theme_radius_big` | `36px` | — | radius | 面板容器圆角 |
| `miuix_theme_radius_common` | `16px` | — | radius | 取消按钮圆角 |
| `miuix_theme_radius_medium` | `20px` | — | radius | 备用中等圆角 |
| `miuix_theme_radius_demi_big` | `24px` | — | radius | 备用大圆角 |
| `radius-3xl` | `20px` | — | radius | 系统 3XL 圆角 |
| `miuix_font_size_headline1` | `17px` | — | font-size | 操作按钮字号 |
| `miuix_font_weight_headline1` | `380` | — | font-weight | 操作按钮字重 |
| `miuix_font_size_body2` | `14px` | — | font-size | 描述信息字号 |
| `miuix_font_weight_body2` | `330` | — | font-weight | 描述信息字重 |
| `miuix_font_size_button` | `17px` | — | font-size | 取消按钮字号 |
| `miuix_font_weight_button` | `380` | — | font-weight | 取消按钮字重 |
| `spacing-xl` | `16px` | — | spacing | 系统 XL 间距 |

---

## 设计注释

> 1. **OS4 材质限制**：Figma 中存在「玻璃」（`Actionsheet/Light/玻璃`）和「混色」（`Actionsheet/Light/混色`）两种材质变体，但均已标注为 **OS4 禁用**（节点设置 `hidden="true"`）。OS4 仅使用**纯色材质**。
> 2. **按钮数量灵活**：通过 `showButton1` ~ `showButton4` 和 `showDestructiveButton` 布尔属性控制按钮显隐，支持 1~5 个操作按钮的灵活配置。
> 3. **近手型无取消按钮**：「近手型」变体在 Figma 中未定义独立的取消按钮样式，仅包含操作按钮列表。
> 4. **按钮状态命名**：Figma 中 `Destructiv Disablee` 为拼写错误，实际应为 `Destructive Disable`（警示按钮禁用态）。
> 5. **Dark 模式**：Dark 模式下取消按钮的背景色和文字色 Figma 未明确定义，需由设计团队补充。
> 6. **默认按钮组件**：取消按钮内部使用了独立的「默认按钮」组件（nodeId: `75:787`），该组件有独立的设计规范说明，详见 [Figma 链接](https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=87366-9372)。
