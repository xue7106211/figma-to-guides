---
component: TipsBubble
description: 气泡提示组件，用于在触发元素附近显示简短的提示信息，支持 8 个方向的箭头定位
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=43047-257174
figma_node_id: "43047:257174"
variants: "1 dimension, 8 variants"
tokens_used: 7
---

# 气泡提示 TipsBubble

> 轻量级气泡提示组件，用于在触发元素附近弹出简短的辅助说明文字。支持上、下、左、右共 8 个方向定位，通过箭头指向触发源，帮助用户理解功能或操作。

## 预览

![气泡提示 Tips Bubble 全部变体预览](https://www.figma.com/api/mcp/asset/tips-bubble-overview)

---

## 组件结构

```
气泡提示 Tips Bubble                       // SECTION | 43047:257174
├── .Page header                           // INSTANCE | 43047:257175
├── Group 2090054897                       // FRAME | 43047:257176
│   └── Frame 2090053798                   // FRAME | 43047:257177
│       └── Component name                 // TEXT | 43047:257178
└── Popover                                // FRAME | 43068:259715
    ├── 方向=上-左                          // COMPONENT | 43068:259666
    │   ├── Background                     // FRAME | 43068:259559
    │   ├── 提示文字                        // TEXT | 43068:259561
    │   └── Arrow                          // FRAME | 43068:259562
    ├── 方向=上-中                          // COMPONENT | 43068:259677
    │   ├── Background                     // FRAME | 43068:259592
    │   ├── 提示文字                        // TEXT | 43068:259594
    │   └── Arrow                          // FRAME | 43068:259595
    ├── 方向=上-右                          // COMPONENT | 43068:259679
    │   ├── Background                     // FRAME | 43068:259600
    │   ├── 提示文字                        // TEXT | 43068:259602
    │   └── Arrow                          // FRAME | 43068:259603
    ├── 方向=左-中                          // COMPONENT | 43068:259683
    │   ├── Background                     // FRAME | 43068:259654
    │   ├── 提示文字                        // TEXT | 43068:259656
    │   └── Arrow                          // FRAME | 43464:9873
    ├── 方向=右-中                          // COMPONENT | 43068:259681
    │   ├── Background                     // FRAME | 43068:259659
    │   ├── 提示文字                        // TEXT | 43068:259661
    │   └── Arrow                          // FRAME | 43464:9892
    ├── 方向=下-左                          // COMPONENT | 43068:259685
    │   ├── Background                     // FRAME | 43068:259608
    │   ├── 提示文字                        // TEXT | 43068:259610
    │   └── Arrow                          // FRAME | 43068:259611
    ├── 方向=下-中                          // COMPONENT | 43068:259711
    │   ├── Background                     // FRAME | 43068:259629
    │   ├── 提示文字                        // TEXT | 43068:259631
    │   └── Arrow                          // FRAME | 43068:259632
    └── 方向=下-右                          // COMPONENT | 43068:259713
        ├── Background                     // FRAME | 43068:259634
        ├── 提示文字                        // TEXT | 43068:259636
        └── Arrow                          // FRAME | 43068:259637
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| Popover | FRAME | `43068:259715` | 组件集容器，包含 8 个方向变体 |
| Background | FRAME | — | 气泡背景层，绝对定位填满容器，带圆角和裁剪 |
| 提示文字 | TEXT | — | 气泡内的提示文本内容 |
| Arrow | FRAME | — | 箭头指示器，指向触发元素，位置因变体不同而异 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `max-width` | `368px` | — |
| `min-height` | `50px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `gap` | `10px` | — |
| `padding` | `15px 14px` | — |
| `position` | `relative` | — |
| `box-shadow` | `0px 10px 20px 0px rgba(0,0,0,0.12)` | `Shadow/shadow-low` |

### 子组件: Background

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `position` | `absolute` | — |
| `inset` | `0` | — |
| `background-color` | `#FFFFFF` | `hyperos-color-surface-highest` |
| `border-radius` | `12px` | `hyperos_theme_radius_small` |
| `overflow` | `clip` | — |

### 子组件: Arrow（上/下方向）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `36px` | — |
| `height` | `10px` | — |
| `position` | `absolute` | — |

### 子组件: Arrow（左/右方向）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `8px` | — |
| `height` | `16px` | — |
| `position` | `absolute` | — |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| 提示文字 | MiSans | 14px | 330 | 100% | 0 | `rgba(0,0,0,0.6)` | `Subtitle/Subtitle 3` |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 气泡背景色 | `#FFFFFF` | `hyperos-color-surface-highest` |
| 提示文字色 | `rgba(0,0,0,0.6)` | `hyperos-color-on-surface-tertiary` |
| 箭头填充色 | `#FFFFFF` | `hyperos-color-surface-highest` |
| 阴影 | `rgba(0,0,0,0.12)` | `Shadow/shadow-low` |

---

## 变体

### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 方向 | `方向` | `上-左` / `上-中` / `上-右` / `左-中` / `右-中` / `下-左` / `下-中` / `下-右` | 控制箭头方向与位置，决定气泡相对于触发元素的弹出方位 |

共计 **1 × 8 = 8 个变体**。

### 变体差异表

> 仅列出各变体之间**有差异**的属性。所有变体的容器样式（尺寸、内边距、背景、阴影、文字）完全一致，唯一差异在于 **Arrow 的尺寸、位置和旋转方式**。

#### 按方向分组 — 上方三个变体（箭头朝上，气泡在触发元素下方）

| 属性 | `上-左` | `上-中` | `上-右` |
|-----|---------|---------|---------|
| Arrow 尺寸 | `36px × 10px` | `36px × 10px` | `36px × 10px` |
| `top` | `-10px` | `-10px` | `-10px` |
| 水平定位 | `left: 14px` | `left: 50%; transform: translateX(-50%)` | `right: 12px` |
| `transform` | `scaleY(-1)` | `scaleY(-1)` | `scaleY(-1)` |

#### 按方向分组 — 下方三个变体（箭头朝下，气泡在触发元素上方）

| 属性 | `下-左` | `下-中` | `下-右` |
|-----|---------|---------|---------|
| Arrow 尺寸 | `36px × 10px` | `36px × 10px` | `36px × 10px` |
| `bottom` | `-10px` | `-10px` | `-10px` |
| 水平定位 | `left: 12px` | `left: calc(50% + 2px); transform: translateX(-50%)` | `right: 12px` |
| `transform` | `scaleY(-1) rotate(180deg)` | `scaleY(-1) rotate(180deg)` | `scaleY(-1) rotate(180deg)` |

#### 按方向分组 — 左右两个变体（箭头水平指向）

| 属性 | `左-中` | `右-中` |
|-----|---------|---------|
| Arrow 尺寸 | `8px × 16px` | `8px × 16px` |
| 垂直定位 | `top: 50%; transform: translateY(-50%)` | `top: 50%; transform: translateY(-50%)` |
| 水平定位 | `left: -8px` | `right: -8px` |
| `transform`（Arrow 内部） | 无旋转 | `scaleY(-1) rotate(180deg)` |

---

## 交互状态

> 以「默认态」为基准，其他状态仅列出**发生变化**的属性。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态） | — |
| `hover` | 鼠标悬停 | Figma 未定义，请由设计团队补充 | — | — |
| `active` | 鼠标按下 / 触摸 | Figma 未定义，请由设计团队补充 | — | — |
| `focused` | 键盘聚焦 | Figma 未定义，请由设计团队补充 | — | — |
| `disabled` | `disabled=true` | Figma 未定义，请由设计团队补充 | — | — |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

```typescript
interface TipsBubbleProps {
  /** 气泡箭头方向，决定气泡相对于触发元素的弹出方位 */
  direction: 'top-left' | 'top-center' | 'top-right' | 'left-center' | 'right-center' | 'bottom-left' | 'bottom-center' | 'bottom-right';
  /** 气泡内的提示文字内容 */
  content: string;
  /** 气泡是否可见 */
  visible?: boolean; // 默认: false
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 方向 | Variant | `direction` | `top-left` | 箭头方向与气泡弹出方位，8 个标准位置 |
| 提示文字 | Text | `content` | `提示文字，提示一些新功能。` | 气泡内显示的提示文本 |

---

## 使用指南

### 何时使用

- **功能引导**：使用气泡提示向用户介绍新功能或操作入口，搭配适当的方向变体指向目标元素
- **操作提示**：在用户首次接触某个交互控件时，通过气泡提示给出简短的操作说明
- **状态反馈**：在需要临时提示用户某项变更或状态更新时使用

### 何时不使用

- **长文本内容**：如果需要展示较多说明内容，应使用 Dialog 或 Drawer 组件代替
- **需要用户交互**：如果提示中包含按钮或操作项，应使用 Popover 组件代替
- **系统级通知**：全局性的消息通知应使用 Toast / Notification 组件代替
- **表单验证**：输入字段的验证错误提示应使用表单内联错误样式代替

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 保持提示文字简短（1-2 行） | 在气泡内放置大段文字 | 气泡宽度有 `max-width: 368px` 限制，过多文字影响阅读体验 |
| 根据触发元素位置选择合适的方向 | 固定使用同一个方向 | 气泡可能被页面边缘裁剪，应根据空间自适应选择方向 |
| 箭头指向触发元素的中心 | 箭头指向空白区域 | 箭头是视觉上连接气泡和触发元素的关键指示 |
| 提供关闭或自动消失机制 | 让气泡永久显示 | 持续存在的气泡会遮挡内容，影响用户操作 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `hyperos-color-surface-highest` | `#FFFFFF` | color | 气泡背景色 |
| `hyperos-color-on-surface-tertiary` | `rgba(0,0,0,0.6)` | color | 提示文字颜色 |
| `hyperos_theme_radius_small` | `12px` | radius | 气泡圆角 |
| `hyperos_font_size_subtitle3` | `14px` | font-size | 提示文字字号 |
| `hyperos_font_weight_subtitle3` | `330` | font-weight | 提示文字字重 |
| `Subtitle/Subtitle 3` | `MiSans Regular / 14px / 330 / lh:100% / ls:0` | typography | 提示文字完整字体样式 |
| `Shadow/shadow-low` | `0px 10px 20px 0px rgba(0,0,0,0.12)` | shadow | 气泡容器阴影 |

---

## 设计注释

> 1. 气泡提示支持 8 个标准位置及自适应位置，实现时应根据触发元素在视口中的位置自动选择最佳方向，避免气泡被裁剪。
> 2. 上/下方向的箭头尺寸为 `36px × 10px`（水平宽、垂直高），左/右方向的箭头尺寸为 `8px × 16px`（水平窄、垂直高），两种箭头形状不同。
> 3. 箭头是通过 SVG 图形实现的，背景色与气泡背景保持一致（`#FFFFFF`），与 `box-shadow` 配合形成连续的视觉效果。
> 4. 气泡的阴影使用 `Shadow/shadow-low` Token，颜色为 `rgba(0,0,0,0.12)`，阴影偏移 Y 轴 `10px`，模糊半径 `20px`，无扩展。
> 5. 所属设计系统：HyperOS UIKit 3.2，设计师：@交互·王靖宇 @视觉·胡佳奇。
