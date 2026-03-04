---
component: Divider
description: 用于在列表或卡片内容之间提供视觉分隔的水平分割线组件，支持两种高度模式
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=88712-10542
figma_node_id: "88712:10513"
variants: "1 dimension, 2 variants"
tokens_used: 4
---

# 分割器 Divider

> 用于在列表项、卡片内容或分组之间提供视觉分隔的水平线组件。支持两种模式：「0.7 高度」用于套卡列表内嵌分割（带左右内缩），「32 高度」用于列表组之间的分段分隔（更大的留白区域）。

## 预览

![Divider 全部变体预览](figma-screenshot:88712:10513)

### 0.7 高度变体预览

![Divider 0.7 高度](figma-screenshot:88712:10512)

### 32 高度变体预览

![Divider 32 高度](figma-screenshot:88712:10511)

---

## 组件结构

```
Divider 分割器                                // COMPONENT_SET | 88712:10513
├── 类型选择=0.7 高度                         // COMPONENT | 88712:10512
│   └── 套卡列表/ 分割线                      // INSTANCE | 88712:10502
│       └── Container                         // FRAME | I88712:10502;88691:9285
│           └── Divider                       // FRAME | I88712:10502;82355:7762
└── 类型选择=32 高度                          // COMPONENT | 88712:10511
    └── 列表组/分割线                         // INSTANCE | 88712:10507
        └── Rectangle                         // FRAME | I88712:10507;82227:1036
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| 套卡列表/ 分割线 | INSTANCE | `88712:10502` | 0.7 高度变体的分割线实例，包含 Container 和 Divider |
| Container | FRAME | `I88712:10502;88691:9285` | 分割线的内层容器，提供左右 16px 内缩 |
| Divider | FRAME | `I88712:10502;82355:7762` | 0.7px 高度的实际分割线元素 |
| 列表组/分割线 | INSTANCE | `88712:10507` | 32 高度变体的分割线实例，包含 Rectangle |
| Rectangle | FRAME | `I88712:10507;82227:1036` | 0.74px 高度的实际分割线元素 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器（通用）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `392px` | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `flex-start` | — |
| `overflow` | `visible` | — |

### 变体: 0.7 高度

#### 外层包裹（套卡列表/ 分割线）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%`（fill） | — |
| `height` | `auto`（hug） | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `flex-start` | — |
| `padding-left` | `12px` | `padding/padding_sm` |
| `padding-right` | `12px` | `padding/padding_sm` |
| `padding-top` | `0` | — |
| `padding-bottom` | `0` | — |

#### 子组件: Container

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%`（fill） | — |
| `height` | `auto`（hug） | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `flex-start` | — |
| `padding-left` | `16px` | — |
| `padding-right` | `16px` | — |
| `background-color` | `#FFFFFF` | `元素色/container_list` |

#### 子组件: Divider（分割线本体）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%`（fill） | — |
| `height` | `0.7px` | — |
| `background-color` | `rgba(0,0,0,0.1)` | `hyperos-color-surface-container-high` |

### 变体: 32 高度

#### 外层包裹（列表组/分割线）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%`（fill） | — |
| `height` | `32px` | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `padding-left` | `28px` | `padding/padding_lg` |
| `padding-right` | `28px` | `padding/padding_lg` |
| `padding-top` | `0` | — |
| `padding-bottom` | `0` | — |

#### 子组件: Rectangle（分割线本体）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%`（fill） | — |
| `height` | `0.74px` | — |
| `background-color` | `rgba(0,0,0,0.1)` | `hyperos-color-surface-container-high` |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 分割线颜色 | `rgba(0,0,0,0.1)` | `hyperos-color-surface-container-high` |
| 内层容器背景（0.7 高度） | `#FFFFFF` | `元素色/container_list` |

---

## 变体

### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型选择 | `类型选择` | `0.7 高度` / `32 高度` | 控制分割线的视觉模式和上下留白 |

共计 **1 × 2 = 2 个变体**。

### 变体差异表

> 仅列出两种类型之间**有差异**的属性。未列出的属性与默认变体相同。

#### 按类型选择分组

| 属性 | `0.7 高度`（默认） | `32 高度` |
|-----|------------------|----------|
| 容器 `height` | `auto`（hug，≈0.7px） | `auto`（hug，外层 32px 固定高度） |
| 外层 `height` | `auto`（hug） | `32px` |
| 外层 `align-items` | `flex-start` | `center` |
| 外层 `justify-content` | 未定义 | `center` |
| 外层 `padding-left` / `padding-right` | `12px`（`padding/padding_sm`） | `28px`（`padding/padding_lg`） |
| 内层结构 | 两层嵌套（外层 + Container + Divider） | 单层嵌套（外层 + Rectangle） |
| 内层额外 `padding` | Container 左右各 `16px` | 无 |
| 内层 `background-color` | `#FFFFFF`（`元素色/container_list`） | 无 |
| 分割线 `height` | `0.7px` | `0.74px` |

#### 0.7 高度 详情

适用于**套卡列表内部**的行间分隔。分割线不会铺满整行，而是通过外层 12px + 内层 16px 的双层内缩（合计 28px），在视觉上与列表文本内容左对齐。内层 Container 带有白色背景，确保分割线在卡片上下文中正确渲染。

总缩进：左右各 `12px + 16px = 28px`。

#### 32 高度 详情

适用于**列表组之间**的分段分隔。外层固定 32px 高度提供了上下留白，分割线居中于该空间内。通过更大的左右内边距（28px）与列表组的整体布局对齐。无额外背景色。

---

## 交互状态

> 分割线是纯展示型组件，不具备交互状态。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态） | — |

> Figma 中未定义 hover / active / focused / disabled 状态。该组件为纯装饰元素，无需交互状态，请由设计团队确认是否需要在暗色模式下调整分割线颜色。

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

```typescript
interface DividerProps {
  /** 分割线类型，控制高度和内边距模式 */
  variant: 'inline' | 'section';
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 类型选择 | Variant | `variant` | `'inline'` | `0.7 高度` → `'inline'`（套卡列表内嵌分割），`32 高度` → `'section'`（列表组间分段分割） |

---

## 使用指南

### 何时使用

- **列表内行间分隔**：使用「inline / 0.7 高度」类型，在同一卡片/列表容器内的相邻行之间添加细微分隔线
- **列表组间分段**：使用「section / 32 高度」类型，在不同的列表分组之间提供明显的段落间隔

### 何时不使用

- **内容区块分隔**：应使用间距（spacing）或卡片容器代替，分割线不适用于大块内容的视觉分隔
- **装饰性分割**：如需带颜色或渐变的装饰性横线，应使用自定义样式代替
- **可交互边界**：如需可拖拽的分割面板，应使用 SplitPane / ResizablePanel 组件代替

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 在列表项之间使用 `inline` 类型 | 在列表项之间使用 `section` 类型 | `section` 类型 32px 的高度会造成过大的视觉间隔，打断列表的连续感 |
| 在不同列表分组之间使用 `section` 类型 | 在同一组的每个列表项之间使用 `section` 类型 | 过度使用 `section` 分割会让界面显得碎片化 |
| 让分割线颜色跟随系统 Token | 自定义分割线颜色 | 使用 `hyperos-color-surface-container-high` Token 可确保暗色模式适配 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `hyperos-color-surface-container-high` | `rgba(0,0,0,0.1)` | color | 分割线颜色（两种变体共用） |
| `元素色/container_list` | `#FFFFFF` | color | 0.7 高度变体的内层容器背景 |
| `padding/padding_sm` | `12px` | spacing | 0.7 高度变体外层左右内边距 |
| `padding/padding_lg` | `28px` | spacing | 32 高度变体外层左右内边距 |

---

## 设计注释

> 1. 该组件属于 HyperOS 4 设计系统的「Divider 分割器」分类，由系统团队维护。
> 2. 两种变体的分割线实际高度略有不同：`0.7 高度` 变体为 `0.7px`，`32 高度` 变体为 `0.74px`。实现时建议统一为 `1px`（使用 `transform: scaleY(0.5)` 实现物理 0.5px），或根据设备像素比动态调整。
> 3. `0.7 高度` 变体采用两层嵌套结构（外层 12px 缩进 + 内层 16px 缩进），总内缩 28px，与列表文字内容左对齐。实现时可简化为单层结构配合 `margin-left: 28px`。
> 4. `32 高度` 变体的 32px 高度包含了上下留白空间，分割线居中。实现时可通过 `padding-top` + `padding-bottom` 或 `margin` 实现等效效果。
> 5. 分割线颜色使用 `hyperos-color-surface-container-high` Token（`rgba(0,0,0,0.1)`），在暗色模式下预期由 Token 系统自动切换为适配暗色背景的值（如 `rgba(255,255,255,0.1)`），请由设计团队确认暗色模式值。
