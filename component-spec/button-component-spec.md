---
component: Button
description: HyperOS 系统级按钮组件，包含默认按钮、小号按钮、迷你按钮、按钮组和弹窗按钮组五种形态
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=82881-53844
figma_node_id: "82881:53844"
variants: "5 component sets: 默认按钮 (3 types × 3 states), 小号按钮 (2 types × 2 states), 迷你按钮 (2 types × 2 states), 按钮组 (3 layouts), 弹窗按钮组 (7 layouts)"
tokens_used: 17
---

# 按钮 Button

> HyperOS 系统级按钮组件，用于触发操作或事件。提供强调、基础、警示三种语义类型，以及默认、小号、迷你三种尺寸。同时包含按钮组和弹窗按钮组两种组合布局模式，覆盖系统弹窗、页面操作、列表行内等场景。

## 预览

![按钮 Button 全部变体预览](figma-screenshot-82881-53844.png)

---

## 组件结构

```
Buttons 按钮                                       // FRAME | 82881:53844
├── 表头_Component&Instance                        // INSTANCE | 82881:53845
├── 默认按钮                                       // COMPONENT_SET | 75:787
│   ├── 类型=强调按钮, 状态=常态                    // COMPONENT | 75:794
│   │   └── Text                                   // TEXT | 75:795
│   ├── 类型=强调按钮, 状态=按下态                  // COMPONENT | 75:796 (hidden)
│   ├── 类型=强调按钮, 状态=不可点态                // COMPONENT | 75:798
│   ├── 类型=基础按钮, 状态=常态                    // COMPONENT | 75:788
│   ├── 类型=基础按钮, 状态=按下态                  // COMPONENT | 75:790 (hidden)
│   ├── 类型=基础按钮, 状态=不可点态                // COMPONENT | 75:792
│   ├── 类型=警示按钮, 状态=常态                    // COMPONENT | 75:800
│   ├── 类型=警示按钮, 状态=按下态                  // COMPONENT | 75:802 (hidden)
│   └── 类型=警示按钮, 状态=不可点态                // COMPONENT | 75:804
├── 按钮/01默认（按钮组）                           // COMPONENT_SET | 53646:5906
│   ├── 类型=上下                                  // COMPONENT | 53646:5872
│   ├── 类型=左右                                  // COMPONENT | 53646:5883
│   └── 类型=左右（警示）                           // COMPONENT | 53646:5905
├── 弹窗按钮组                                     // COMPONENT_SET | 5580:1384
│   ├── 按钮布局=2个按钮（左右）                    // COMPONENT | 5580:1324
│   ├── 按钮布局=2个按钮（警示场景）                // COMPONENT | 42447:40482
│   ├── 按钮布局=2个按钮（均不推荐）                // COMPONENT | 74250:11529
│   ├── 按钮布局=2个按钮（上下）                    // COMPONENT | 42447:40472
│   ├── 按钮布局=1个按钮                           // COMPONENT | 5580:1343
│   ├── 按钮布局=3个按钮                           // COMPONENT | 5580:1344
│   └── 按钮布局=4个按钮（极限）                    // COMPONENT | 42506:20101
├── 小号按钮                                       // COMPONENT_SET | 75:808
│   ├── Type=强调, State=Default                   // COMPONENT | 42281:48435
│   ├── Type=基础, State=Default                   // COMPONENT | 42281:48451
│   ├── Type=强调, State=Disable                   // COMPONENT | 42281:48437
│   └── Type=基础, State=Disable                   // COMPONENT | 42281:48453
└── 迷你按钮                                       // COMPONENT_SET | 42447:2877
    ├── Type=强调, State=Default                   // COMPONENT | 42447:2878
    ├── Type=基础, State=Default                   // COMPONENT | 42927:154728
    ├── Type=强调, State=Disable                   // COMPONENT | 42447:2882
    └── Type=基础, State=Disable                   // COMPONENT | 42927:154730
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| 默认按钮 | COMPONENT_SET | `75:787` | 标准尺寸按钮，3 种语义类型 × 3 种状态 |
| 按钮/01默认（按钮组） | COMPONENT_SET | `53646:5906` | 默认按钮的组合布局（上下/左右） |
| 弹窗按钮组 | COMPONENT_SET | `5580:1384` | 弹窗专用按钮组合布局，7 种排列 |
| 小号按钮 | COMPONENT_SET | `75:808` | 小尺寸按钮，胶囊圆角 |
| 迷你按钮 | COMPONENT_SET | `42447:2877` | 最小尺寸按钮，用于列表行内等紧凑场景 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 默认按钮（基准：类型=强调按钮, 状态=常态）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `336px` | — |
| `max-width` | `336px` | — |
| `height` | `50px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `padding` | `8px 20px` | — |
| `background-color` | `#3482FF` | `hyperos-color-primary` |
| `border-radius` | `16px` | `hyperos_theme_radius_common` |
| `color` | `#FFFFFF` | `hyperos-color-on-primary` |
| `overflow` | `hidden` | — |
| `text-overflow` | `ellipsis` | — |
| `white-space` | `nowrap` | — |

### 小号按钮（基准：Type=强调, State=Default）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `auto`（hug） | — |
| `min-width` | `76px` | — |
| `height` | `36px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `padding` | `9px 20px` | — |
| `background-color` | `#3482FF` | `hyperos-color-primary` |
| `border-radius` | `999px` | `hyperos_theme_radius_circle` |
| `color` | `#FFFFFF` | `hyperos-color-on-primary` |

### 迷你按钮（基准：Type=强调, State=Default）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `auto`（hug） | — |
| `min-width` | `60px` | — |
| `height` | `28px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `padding` | `4px 12px` | — |
| `background-color` | `#3482FF` | `hyperos-color-primary` |
| `border-radius` | `999px` | `hyperos_theme_radius_circle` |
| `color` | `#FFFFFF` | `hyperos-color-on-primary` |

### 按钮组: 类型=上下

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `336px` | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `gap` | `12px` | — |
| `align-items` | `flex-start` | — |

### 按钮组: 类型=左右

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `336px` | — |
| `display` | `flex` | — |
| `flex-direction` | `row` | — |
| `gap` | `12px` | — |
| `align-items` | `flex-start` | — |

### 弹窗按钮组: 按钮布局=2个按钮（左右）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `304px` | — |
| `display` | `flex` | — |
| `flex-direction` | `row` | — |
| `gap` | `12px` | — |
| `align-items` | `flex-start` | — |

弹窗按钮组中每个按钮使用 `flex: 1 0 0` 均分宽度。

### 弹窗按钮组: 按钮布局=3个按钮 / 4个按钮（极限）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `304px` | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `gap` | `12px` | — |
| `align-items` | `flex-start` | — |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `text-align` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|-------------|-----------|
| 默认按钮文字 | MiSans | 17px | 380 (Medium) | 100% | 0 | center | `Button/Button` |
| 小号按钮文字 | MiSans | 14px | 380 (Medium) | 100% | 0 | center | `Subtitle/Subtitle` |
| 迷你按钮文字 | MiSans | 13px | 380 (Medium) | normal | 0 | center | `hyperos_font_size_footnote1` |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 强调按钮背景色 | `#3482FF` | `hyperos-color-primary` |
| 强调按钮文字色 | `#FFFFFF` | `hyperos-color-on-primary` |
| 基础按钮背景色 | `rgba(0,0,0,0.06)` | `hyperos-color-tertiary` |
| 基础按钮文字色 | `rgba(0,0,0,0.8)` | `hyperos-color-on-tertiary` |
| 警示按钮文字色 | `#FA382E` | `hyperos-color-error` |
| 基础禁用文字色 | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |
| 强调禁用文字色 | `#FFFFFF` | `文字图标色/on_surface_button_disable` |
| 警示禁用文字色 | `rgba(250,56,46,0.3)` | `系统功能色/error_disable` |

---

## 变体

### 维度定义

#### 默认按钮（维度：类型 × 状态）

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `类型` | `强调按钮` / `基础按钮` / `警示按钮` | 控制按钮的语义层级和视觉样式 |
| 状态 | `状态` | `常态` / `按下态` / `不可点态` | 交互状态 |

共计 **3 × 3 = 9 个变体**（按下态在 Figma 中标记为 hidden）。

#### 小号按钮 / 迷你按钮（维度：Type × State）

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `Type` | `强调` / `基础` | 控制按钮的语义层级 |
| 状态 | `State` | `Default` / `Disable` | 交互状态 |

各 **2 × 2 = 4 个变体**。

#### 按钮组（维度：类型）

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `类型` | `上下` / `左右` / `左右（警示）` | 控制按钮排列方向和语义 |

共计 **3 个变体**。

#### 弹窗按钮组（维度：按钮布局）

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 按钮布局 | `按钮布局` | `1个按钮` / `2个按钮（左右）` / `2个按钮（警示场景）` / `2个按钮（均不推荐）` / `2个按钮（上下）` / `3个按钮` / `4个按钮（极限）` | 控制弹窗内按钮数量和排列 |

共计 **7 个变体**。

### 变体差异表

#### 默认按钮 — 按「类型」分组

> 以「类型=强调按钮, 状态=常态」为基准，仅列出差异属性。

| 属性 | `强调按钮` | `基础按钮` | `警示按钮` |
|-----|-----------|-----------|-----------|
| `background-color` | `#3482FF` | `rgba(0,0,0,0.06)` | `rgba(0,0,0,0.06)` |
| `color` | `#FFFFFF` | `rgba(0,0,0,0.8)` | `#FA382E` |
| `height` | `50px`（显式） | `auto`（由 padding 决定） | `auto`（由 padding 决定） |
| `padding` | `8px 20px` | `13.5px 20px` | `13.5px 20px` |
| 背景 Token | `hyperos-color-primary` | `hyperos-color-tertiary` | `hyperos-color-tertiary` |
| 文字 Token | `hyperos-color-on-primary` | `hyperos-color-on-tertiary` | `hyperos-color-error` |

#### 按钮尺寸对比

| 属性 | 默认按钮 | 小号按钮 | 迷你按钮 |
|-----|---------|---------|---------|
| `height` | `50px` | `36px` | `28px` |
| `min-width` | — | `76px` | `60px` |
| `width` | `336px`（固定） | `auto`（hug） | `auto`（hug） |
| `padding` (强调) | `8px 20px` | `9px 20px` | `4px 12px` |
| `padding` (基础) | `13.5px 20px` | `8px 20px` | `4px 12px` |
| `border-radius` | `16px` | `999px` | `999px` |
| `font-size` | `17px` | `14px` | `13px` |
| 圆角 Token | `hyperos_theme_radius_common` | `hyperos_theme_radius_circle` | `hyperos_theme_radius_circle` |
| 字号 Token | `hyperos_font_size_button` | `hyperos_font_size_subtitle` | `hyperos_font_size_footnote1` |

#### 弹窗按钮组 — 按「按钮布局」分组

| 属性 | `1个按钮` | `2个（左右）` | `2个（上下）` | `3个按钮` | `4个（极限）` |
|-----|----------|-------------|-------------|----------|-------------|
| `width` | `304px` | `304px` | `304px` | `304px` | `304px` |
| `flex-direction` | — | `row` | `column` | `column` | `column` |
| `gap` | — | `12px` | `12px` | `12px` | `12px` |
| 按钮数量 | 1 | 2 | 2 | 3 | 4 |
| 按钮排列 | 单个全宽 | 左右均分 | 上下堆叠 | 上下堆叠 | 上下堆叠 |
| 强调按钮位置 | 唯一 | 右侧 | 顶部 | 顶部 | 顶部 |

---

## 交互状态

> 以「常态」为基准，其他状态仅列出**发生变化**的属性。

### 默认按钮 — 强调按钮

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `常态` | — | — | （基准状态） | — |
| `按下态` | 触摸/鼠标按下 | Figma 中标记为 hidden | 请由设计团队补充 | — |
| `不可点态` | `disabled=true` | `opacity` | `0.3` | — |
| `不可点态` | `disabled=true` | `color` | `#FFFFFF` | `文字图标色/on_surface_button_disable` |

### 默认按钮 — 基础按钮

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `常态` | — | — | （基准状态） | — |
| `按下态` | 触摸/鼠标按下 | Figma 中标记为 hidden | 请由设计团队补充 | — |
| `不可点态` | `disabled=true` | `color` | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |

### 默认按钮 — 警示按钮

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `常态` | — | — | （基准状态） | — |
| `按下态` | 触摸/鼠标按下 | Figma 中标记为 hidden | 请由设计团队补充 | — |
| `不可点态` | `disabled=true` | `color` | `rgba(250,56,46,0.3)` | `系统功能色/error_disable` |

### 小号 / 迷你按钮

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `Default` | — | — | （基准状态） | — |
| `Disable` | `disabled=true` | Figma 中存在独立变体 | 请由设计团队补充具体差异 | — |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

### 默认按钮

```typescript
interface ButtonProps {
  /** 按钮语义类型 */
  type: '强调按钮' | '基础按钮' | '警示按钮';
  /** 交互状态 */
  state: '常态' | '按下态' | '不可点态';
}
```

### 小号按钮

```typescript
interface SmallButtonProps {
  /** 按钮语义类型 */
  type: '强调' | '基础';
  /** 交互状态 */
  state: 'Default' | 'Disable';
}
```

### 迷你按钮

```typescript
interface MiniButtonProps {
  /** 按钮语义类型 */
  type: '强调' | '基础';
  /** 交互状态 */
  state: 'Default' | 'Disable';
}
```

### 按钮组

```typescript
interface ButtonGroupProps {
  /** 按钮排列类型 */
  type: '上下' | '左右' | '左右（警示）';
  /** 主按钮类型 */
  propValue?: '强调按钮' | '基础按钮'; // 默认: '强调按钮'
  /** 主按钮状态 */
  propValue1?: '常态'; // 默认: '常态'
}
```

### 弹窗按钮组

```typescript
interface DialogButtonGroupProps {
  /** 按钮布局方式 */
  layout: '1个按钮' | '2个按钮（左右）' | '2个按钮（警示场景）' | '2个按钮（均不推荐）' | '2个按钮（上下）' | '3个按钮' | '4个按钮（极限）';
}
```

| Figma 属性名 | 类型 | 对应组件 | 对应 Prop | 默认值 | 说明 |
|-------------|------|---------|----------|-------|------|
| 类型 | Variant | 默认按钮 | `type` | `强调按钮` | 按钮语义类型 |
| 状态 | Variant | 默认按钮 | `state` | `常态` | 交互状态 |
| Type | Variant | 小号/迷你按钮 | `type` | `强调` | 按钮语义类型 |
| State | Variant | 小号/迷你按钮 | `state` | `Default` | 交互状态 |
| 类型 | Variant | 按钮组 | `type` | `上下` | 排列方式 |
| 按钮布局 | Variant | 弹窗按钮组 | `layout` | `2个按钮（左右）` | 弹窗按钮排列方式 |
| propValue | Variant | 按钮组子按钮 | `propValue` | `强调按钮` | 子按钮类型 |

---

## 使用指南

### 何时使用

- **主要操作确认**：使用「强调按钮」作为页面或弹窗的主要操作按钮，如"确定"、"提交"
- **次要操作**：使用「基础按钮」作为辅助操作，如"取消"、"返回"
- **危险操作**：使用「警示按钮」作为破坏性操作的触发器，如"删除"、"清除数据"
- **弹窗底部**：使用「弹窗按钮组」在 Dialog 底部排列操作按钮
- **列表行内操作**：使用「小号按钮」或「迷你按钮」在列表项中提供行内操作
- **紧凑空间**：使用「迷你按钮」在空间受限的场景（如通知栏、卡片内）中触发操作

### 何时不使用

- **导航跳转**：应使用 Link 或 NavigationItem 代替
- **开关切换**：应使用 Switch 组件代替
- **图标操作**：纯图标操作应使用 IconButton 代替
- **选项选择**：应使用 Checkbox、Radio 或 Select 代替

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 一个视图中只有一个强调按钮 | 同一视图中放置多个强调按钮 | 强调按钮代表最重要的操作，多个会造成视觉竞争 |
| 弹窗中强调按钮放在右侧（左右布局）或顶部（上下布局） | 将强调按钮放在左侧或底部 | 符合 HyperOS 交互规范的操作优先级 |
| 按钮文字简洁（2~5 字） | 使用过长的按钮文字 | 按钮文字过长会被 `text-overflow: ellipsis` 截断 |
| 警示按钮搭配基础按钮使用 | 警示按钮单独使用或搭配强调按钮 | 避免同时出现两个高视觉权重的按钮 |
| 禁用态保留按钮可见性 | 禁用时隐藏按钮 | 用户需要知道操作存在但当前不可用 |
| 弹窗按钮组超过 2 个按钮时使用上下堆叠布局 | 3 个以上按钮仍使用左右并排 | 水平空间有限，多按钮并排会导致文字截断 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `hyperos-color-primary` | `#3482FF` | color | 强调按钮背景色 |
| `hyperos-color-on-primary` | `#FFFFFF` | color | 强调按钮文字色 |
| `hyperos-color-tertiary` | `rgba(0,0,0,0.06)` | color | 基础/警示按钮背景色 |
| `hyperos-color-on-tertiary` | `rgba(0,0,0,0.8)` | color | 基础按钮文字色 |
| `hyperos-color-error` | `#FA382E` | color | 警示按钮文字色 |
| `hyperos-color-on-surface` | `#000000` | color | 通用文字色 |
| `hyperos-color-on-surface-octonary` | `rgba(0,0,0,0.3)` | color | 基础按钮禁用态文字色 |
| `文字图标色/on_surface_button_disable` | `#FFFFFF` | color | 强调按钮禁用态文字色 |
| `系统功能色/error_disable` | `rgba(250,56,46,0.3)` | color | 警示按钮禁用态文字色 |
| `hyperos_theme_radius_common` | `16px` | radius | 默认按钮圆角 |
| `hyperos_theme_radius_circle` | `999px` | radius | 小号/迷你按钮圆角（胶囊形） |
| `hyperos_theme_radius_medium` | `20px` | radius | 中等圆角 |
| `hyperos_theme_radius_big` | `36px` | radius | 大圆角 |
| `hyperos_font_size_button` | `17px` | font-size | 默认按钮字号 |
| `hyperos_font_weight_button` | `380` | font-weight | 默认按钮字重 |
| `hyperos_font_size_subtitle` | `14px` | font-size | 小号按钮字号 |
| `hyperos_font_weight_subtitle` | `380` | font-weight | 小号按钮字重 |
| `hyperos_font_size_footnote1` | `13px` | font-size | 迷你按钮字号 |
| `Button/Button` | `MiSans, Medium, 17px, 380, lh:100%, ls:0` | typography | 默认按钮完整文字样式 |
| `Subtitle/Subtitle` | `MiSans, Medium, 14px, 380, lh:100%, ls:0` | typography | 小号按钮完整文字样式 |

---

## 设计注释

> 1. 按钮组件提供了 Figma 设计规范说明链接：[设计规范说明](https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=87366-9372&t=pnkzaNTGZsEGZIB2-11)，实现时建议参考。
> 2. **按下态（pressed）** 在 Figma 中标记为 `hidden`，三种类型均存在按下态变体但未公开展示，具体视觉变化需由设计团队补充确认。
> 3. **强调按钮的禁用态** 通过 `opacity: 0.3` 实现整体透明度降低，而非改变背景色，这与基础/警示按钮的禁用策略不同。
> 4. 基础按钮和警示按钮的 **背景色相同**（均为 `rgba(0,0,0,0.06)`），通过文字颜色区分语义。
> 5. 小号和迷你按钮使用 **胶囊圆角**（`999px`），而默认按钮使用 `16px` 矩形圆角，这是尺寸层级的视觉区分策略。
> 6. 弹窗按钮组的宽度为 `304px`（对应弹窗内容区宽度），而默认按钮组宽度为 `336px`，使用时需注意容器宽度适配。
> 7. 弹窗按钮组中「4个按钮（极限）」变体名称暗示这是按钮数量的上限，不建议超过 4 个按钮。
