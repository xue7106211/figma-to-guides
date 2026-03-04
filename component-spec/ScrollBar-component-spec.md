---
component: ScrollBar
description: 滚动内容区域中用于指示当前可视区域位置的竖向滚动条指示器
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=82864-42873
figma_node_id: "82864:42873"
variants: 1 dimension, 2 variants
tokens_used: 3
---

# 滚动条 ScrollBar

> 用于可滚动内容区域中指示当前视口位置的竖向滚动条指示器，包含默认态和激活态两种视觉状态，通过宽度和透明度的变化来反馈用户的触摸交互。

## 预览

![ScrollBar 全部变体预览](component-set-preview)

| 默认态 | 激活态 |
|-------|-------|
| ![ScrollBar 默认态](default-variant) | ![ScrollBar 激活态](active-variant) |

---

## 组件结构

```
滚动条 (Component Set)                   // COMPONENT_SET | 82864:42965
├── Property 1=默认                      // COMPONENT | 9464:3734
│   └── 滚动条                           // RECTANGLE | 9464:3735
└── Property 1=激活                      // COMPONENT | 82864:42964
    └── 滚动条                           // RECTANGLE | 82864:42963
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| 滚动条 (Component Set) | COMPONENT_SET | `82864:42965` | 组件集容器，包含所有变体 |
| Property 1=默认 | COMPONENT | `9464:3734` | 默认态变体 —— 用户未触摸滚动区域时的静默状态 |
| Property 1=激活 | COMPONENT | `82864:42964` | 激活态变体 —— 用户正在滚动时的活跃状态 |
| 滚动条 (内部) | RECTANGLE | `9464:3735` / `82864:42963` | 实际可见的滚动条指示器矩形 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器（外层 Component）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `12px` | — |
| `height` | `180px` | — |
| `display` | `flex` | — |
| `flex-direction` | `row` | — |
| `justify-content` | `center` | — |
| `align-items` | `center` | — |
| `position` | `relative` | — |
| `background-color` | `transparent` | — |
| `padding` | `0` | — |
| `overflow` | `visible` | — |

### 子组件: 滚动条指示器（默认态）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `4px` | — |
| `height` | `100%`（fill） | — |
| `flex-shrink` | `0` | — |
| `border-radius` | `999px` | `miuix_theme_radius_circle` |
| `background-color` | `rgba(0,0,0,0.1)` | `miuix_default_color_outline` |

### 子组件: 滚动条指示器（激活态）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `6px` | — |
| `height` | `100%`（fill） | — |
| `flex-shrink` | `0` | — |
| `border-radius` | `999px` | `miuix_theme_radius_circle` |
| `background-color` | `rgba(0,0,0,0.3)` | `miuix_default_color_on_surface_octonary` |

### 文字样式

该组件不涉及此项。

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 默认态滚动条填充色 | `rgba(0,0,0,0.1)` | `miuix_default_color_outline` |
| 激活态滚动条填充色 | `rgba(0,0,0,0.3)` | `miuix_default_color_on_surface_octonary` |

---

## 变体

### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 状态 | `Property 1` | `默认` / `激活` | 控制滚动条的视觉状态，默认态为静默指示，激活态为用户正在滚动时的高亮反馈 |

共计 **1 × 2 = 2 个变体**。

### 变体差异表

> 仅列出各变体之间**有差异**的属性。未列出的属性与默认变体相同。

#### 按 Property 1（状态）分组

| 属性 | `默认` | `激活` |
|-----|--------|-------|
| 滚动条 `width` | `4px` | `6px` |
| 滚动条 `background-color` | `rgba(0,0,0,0.1)` | `rgba(0,0,0,0.3)` |
| 滚动条 Token | `miuix_default_color_outline` | `miuix_default_color_on_surface_octonary` |

---

## 交互状态

> 以「默认态」为基准，其他状态仅列出**发生变化**的属性。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态：4px 宽，10% 黑色不透明度） | — |
| `active` | 用户触摸并滚动内容区域 | `width` | `4px` → `6px` | — |
| `active` | 用户触摸并滚动内容区域 | `background-color` | `rgba(0,0,0,0.1)` → `rgba(0,0,0,0.3)` | `miuix_default_color_on_surface_octonary` |

> Figma 中未定义 `hover`、`focused`、`disabled` 状态，请由设计团队补充。

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

```typescript
interface ScrollBarProps {
  /** 滚动条当前状态：默认为静默指示，激活为用户正在滚动 */
  state: '默认' | '激活';
  /** 滚动条指示器高度，根据可滚动内容与容器的比例动态计算 */
  height?: number;
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| Property 1 | Variant | `state` | `默认` | 控制滚动条的视觉状态 |

---

## 使用指南

### 何时使用

- **长列表滚动**：当页面内容超出可视区域需要竖向滚动时，使用默认态滚动条作为位置指示
- **用户主动滚动**：当用户触摸并拖动内容时，切换为激活态滚动条，提供更明显的视觉反馈
- **内容浏览辅助**：在设置页、消息列表、联系人列表等需要大量滚动的场景中使用

### 何时不使用

- **横向滚动**：横向滚动场景应使用水平滚动指示器代替
- **分页内容**：如果内容是分页加载的，应使用分页控件（Pagination）代替
- **短内容**：当内容未超出容器高度时，不应显示滚动条

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 距离屏幕右边缘保持 20px 间距 | 将滚动条紧贴屏幕边缘放置 | Figma 设计标注明确要求距离屏幕边缘 20px |
| 滚动条高度根据内容比例动态计算 | 使用固定高度的滚动条 | 滚动条长度应反映可视区域与总内容的比例关系 |
| 用户停止滚动后延迟渐隐回默认态 | 滚动停止后立即切换状态 | 渐变过渡提供更自然的交互体验 |
| 在深色模式下使用对应的反色 Token | 在深色模式中使用固定的黑色值 | Token 系统会自动适配深色模式 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `miuix_default_color_outline` | `rgba(0,0,0,0.1)` / `#0000001a` | color | 默认态滚动条填充色 |
| `miuix_default_color_on_surface_octonary` | `rgba(0,0,0,0.3)` / `#0000004d` | color | 激活态滚动条填充色 |
| `miuix_theme_radius_circle` | `999px` | radius | 滚动条圆角（全圆角胶囊形） |

---

## 设计注释

> 1. 距离屏幕边缘 20px —— 滚动条应定位于可滚动容器的右侧，与屏幕右边缘保持 20px 的间距。
> 2. 滚动条容器宽度为 12px，但实际可见的指示器宽度仅为 4px（默认态）或 6px（激活态），其余空间为透明的触摸热区。
> 3. 激活态相比默认态，指示器宽度从 4px 增加到 6px（+50%），不透明度从 10% 增加到 30%（×3），通过双重视觉变化强化滚动反馈。
