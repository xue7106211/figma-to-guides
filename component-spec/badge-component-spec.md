---
component: Badge
description: HyperOS 新事件提示组件，用于在 UI 元素上附加数字计数、圆点指示或彩色状态标记
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=90794-66364
figma_node_id: "90794:66364"
variants: "3 component sets: Badge/number (6 variants: 2 sizes × 3 types), Badge/Dot (3 sizes), Badge/Color (4 colors)"
tokens_used: 8
---

# 新事件提示 Badge

> HyperOS 系统级徽标组件，用于在图标、列表项或其他 UI 元素上附加新事件提示。包含三种子类型：**数字徽标**（显示未读数量）、**圆点徽标**（表示有新内容）和**彩色圆点**（表示状态颜色）。支持多种尺寸以适应不同上下文。

## 预览

![新事件提示 Badge 全部变体预览](figma-screenshot-90794-66364.png)

---

## 组件结构

```
新事件提示 Badge                                    // SECTION | 90794:66364
├── Badge/number                                   // COMPONENT_SET | 37258:166676
│   ├── Size=Medium, Type=number                   // COMPONENT | 37184:165259 | 24×24
│   │   └── 数字文字 (居中)                         // TEXT
│   ├── Size=Medium, Type=2number                  // COMPONENT | 37184:165260 | 30×24
│   │   └── 数字文字                               // TEXT
│   ├── Size=Medium, Type=More number              // COMPONENT | 37184:165284 | 39×24
│   │   └── 数字文字 "99+"                          // TEXT
│   ├── Size=Small, Type=number                    // COMPONENT | 37225:165566 | 16×16
│   │   └── 数字文字 (居中)                         // TEXT
│   ├── Size=Small, Type=2number                   // COMPONENT | 37225:166635 | 21×16
│   │   └── 数字文字                               // TEXT
│   └── Size=Small, Type=More number               // COMPONENT | 37225:166643 | 31×16
│       └── 数字文字 "99+"                          // TEXT
├── Badge/Dot                                      // COMPONENT_SET | 37258:166674
│   ├── Property 1=Large                           // COMPONENT | 37184:165258 | 12×12
│   ├── Property 1=Medium                          // COMPONENT | 37258:166673 | 8×8
│   └── Property 1=Small                           // COMPONENT | 37225:165558 | 6×6
└── Badge/Color                                    // COMPONENT_SET | 37258:166782
    ├── Property 1=Red                             // COMPONENT | 37258:166781 | 6×6
    ├── Property 1=Yellow                          // COMPONENT | 37258:166780 | 6×6
    ├── Property 1=Blue                            // COMPONENT | 37258:166779 | 6×6
    └── Property 1=Green                           // COMPONENT | 37258:166778 | 6×6
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| Badge/number | COMPONENT_SET | `37258:166676` | 数字计数徽标，2 种尺寸 × 3 种数字类型 |
| Badge/Dot | COMPONENT_SET | `37258:166674` | 圆点指示徽标，3 种尺寸 |
| Badge/Color | COMPONENT_SET | `37258:166782` | 彩色状态圆点，4 种颜色 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 子组件: Badge/number — Medium 尺寸

| Type | CSS 属性 | 值 | Token |
|------|---------|---|-------|
| **通用** | `height` | `24px` | — |
| | `min-height` / `max-height` | `24px` | — |
| | `background-color` | `#FA382E` | `hyperos-color-error` |
| | `border-radius` | `999px` | `hyperos_theme_radius_circle` |
| | `overflow` | `clip` | — |
| | `color` | `#FFFFFF` | — |
| | `font-family` | MiSans | — |
| | `font-weight` | Demibold (450) | `hyperos_font_weight_subtitle2` |
| | `font-size` | `14px` | `hyperos_font_size_subtitle2` |
| | `text-align` | `center` | — |
| | `line-height` | `normal` | — |
| **number** (1 位数) | `width` | `24px` | — |
| | 文字定位 | 绝对居中 (`translate -50%`) | — |
| **2number** (2 位数) | `width` | 自适应（`flex`） | — |
| | `padding-left` / `padding-right` | `7px` | — |
| | `display` | `flex` | — |
| | `align-items` | `center` | — |
| **More number** (99+) | `width` | 自适应（`flex`） | — |
| | `padding-left` / `padding-right` | `6px` | — |
| | `display` | `flex` | — |
| | `align-items` | `center` | — |

### 子组件: Badge/number — Small 尺寸

| Type | CSS 属性 | 值 | Token |
|------|---------|---|-------|
| **通用** | `height` | `16px` | — |
| | `min-height` / `max-height` | `16px` | — |
| | `background-color` | `#FA382E` | `hyperos-color-error` |
| | `border-radius` | `999px` | `hyperos_theme_radius_circle` |
| | `overflow` | `clip` | — |
| | `color` | `#FFFFFF` | — |
| | `font-family` | MiSans | — |
| | `font-weight` | Medium | — |
| | `font-size` | `12px` | — |
| | `text-align` | `center` | — |
| | `line-height` | `12px` | — |
| **number** (1 位数) | `width` | `16px` | — |
| | 文字定位 | 绝对居中 (`translate -50%`) | — |
| **2number** (2 位数) | `width` | 自适应（`flex`） | — |
| | `padding-left` / `padding-right` | `4px` | — |
| | `display` | `flex` | — |
| | `align-items` | `center` | — |
| | `justify-content` | `center` | — |
| **More number** (99+) | `width` | 自适应（`flex`） | — |
| | `padding-left` / `padding-right` | `4px` | — |
| | `display` | `flex` | — |
| | `align-items` | `center` | — |

### 子组件: Badge/Dot

| CSS 属性 | Large | Medium | Small | Token |
|---------|-------|--------|-------|-------|
| `width` | `12px` | `8px` | `6px` | — |
| `height` | `12px` | `8px` | `6px` | — |
| `background-color` | `#FA382E` | `#FA382E` | `#FA382E` | `hyperos-color-error` |
| `border-radius` | `60px` | `60px` | `60px` | — |
| `overflow` | `clip` | `clip` | `clip` | — |

### 子组件: Badge/Color

| CSS 属性 | Red | Yellow | Blue | Green | Token |
|---------|-----|--------|------|-------|-------|
| `width` | `6px` | `6px` | `6px` | `6px` | — |
| `height` | `6px` | `6px` | `6px` | `6px` | — |
| `background-color` | `#FA382E` | `#FF9F05` | `#3482FF` | `#36D167` | 见下方 |
| `border-radius` | `60px` | `60px` | `60px` | `60px` | — |

颜色 Token 映射：

| 颜色 | 值 | Token |
|-----|---|-------|
| Red | `#FA382E` | `hyperos-color-error` |
| Yellow | `#FF9F05` | `hyperos-color-caution` |
| Blue | `#3482FF` | `hyperos-color-primary` |
| Green | `#36D167` | — |

### 尺寸速查表

| 子组件 | 变体 | 宽度 | 高度 |
|-------|------|------|------|
| Badge/number Medium | 1 位数 | `24px`（正圆） | `24px` |
| Badge/number Medium | 2 位数 | `30px`（胶囊） | `24px` |
| Badge/number Medium | 99+ | `39px`（胶囊） | `24px` |
| Badge/number Small | 1 位数 | `16px`（正圆） | `16px` |
| Badge/number Small | 2 位数 | `21px`（胶囊） | `16px` |
| Badge/number Small | 99+ | `31px`（胶囊） | `16px` |
| Badge/Dot | Large | `12px` | `12px` |
| Badge/Dot | Medium | `8px` | `8px` |
| Badge/Dot | Small | `6px` | `6px` |
| Badge/Color | 所有颜色 | `6px` | `6px` |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-------|
| Medium 数字 | MiSans | 14px | Demibold (450) | normal | 0 | `#FFFFFF` | `Subtitle/Subtitle 2` |
| Small 数字 | MiSans | 12px | Medium | 12px | 0 | `#FFFFFF` | — |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 数字/圆点徽标背景 | `#FA382E` | `hyperos-color-error` |
| 数字文字色 | `#FFFFFF` | — |
| 彩色圆点-红色 | `#FA382E` | `hyperos-color-error` |
| 彩色圆点-黄色 | `#FF9F05` | `hyperos-color-caution` |
| 彩色圆点-蓝色 | `#3482FF` | `hyperos-color-primary` |
| 彩色圆点-绿色 | `#36D167` | — |

---

## 变体

### 维度定义

#### Badge/number

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| Size | `Size` | `Medium` / `Small` | 徽标尺寸 |
| Type | `Type` | `number` / `2number` / `More number` | 数字位数类型 |

共计 **6 个变体**（2 尺寸 × 3 类型）。

#### Badge/Dot

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| Property 1 | `Property 1` | `Large` / `Medium` / `Small` | 圆点尺寸 |

共计 **3 个变体**。

#### Badge/Color

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| Property 1 | `Property 1` | `Red` / `Yellow` / `Blue` / `Green` | 圆点颜色 |

共计 **4 个变体**。

### 变体差异表

#### Badge/number 按尺寸分组

| 属性 | Medium | Small |
|-----|--------|-------|
| 容器高度 | `24px` | `16px` |
| 1 位数宽度 | `24px` | `16px` |
| 2 位数宽度 | `30px` | `21px` |
| 99+ 宽度 | `39px` | `31px` |
| font-size | `14px` | `12px` |
| font-weight | Demibold (450) | Medium |
| line-height | normal | `12px` |
| 2 位数 padding-x | `7px` | `4px` |
| 99+ padding-x | `6px` | `4px` |

#### Badge/number 按 Type 分组

| 属性 | number (1 位) | 2number (2 位) | More number (99+) |
|-----|-------------|---------------|-------------------|
| 形状 | 正圆 | 胶囊 | 胶囊 |
| 宽度 | 固定 = 高度 | 自适应 | 自适应 |
| 布局 | 绝对居中 | flex 水平居中 | flex 水平居中 |
| padding-x (Medium) | 0 | `7px` | `6px` |
| padding-x (Small) | 0 | `4px` | `4px` |

---

## 交互状态

> Badge 是纯展示型组件，不具备独立的交互状态。其显隐和数值变化由父组件驱动。

| 状态 | 说明 |
|-----|------|
| 默认 | 显示当前计数或圆点指示 |
| 隐藏 | 当计数为 0 或无新事件时不渲染 |
| 数值更新 | 数字变化时直接更新文字内容，Type 可能随之切换 |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

### Badge/number

```typescript
interface BadgeNumberProps {
  /** 尺寸 */
  size: 'Medium' | 'Small';
  /** 数字类型：1 位数 / 2 位数 / 超过 99 */
  type: 'number' | '2number' | 'More number';
  /** 显示的数字或文字（如 "3"、"18"、"99+"） */
  value: string;
}
```

### Badge/Dot

```typescript
interface BadgeDotProps {
  /** 圆点尺寸 */
  size: 'Large' | 'Medium' | 'Small';
}
```

### Badge/Color

```typescript
interface BadgeColorProps {
  /** 圆点颜色 */
  color: 'Red' | 'Yellow' | 'Blue' | 'Green';
}
```

| Figma 属性名 | 类型 | 对应组件 | 对应 Prop | 默认值 | 说明 |
|-------------|------|---------|----------|-------|------|
| Size | Variant | Badge/number | `size` | `Medium` | 徽标尺寸 |
| Type | Variant | Badge/number | `type` | `number` | 数字位数类型 |
| Property 1 | Variant | Badge/Dot | `size` | `Large` | 圆点尺寸 |
| Property 1 | Variant | Badge/Color | `color` | `Red` | 圆点颜色 |

---

## 使用指南

### 何时使用

- **未读计数**: 在应用图标、消息入口、列表项右侧显示未读消息数量，使用 Badge/number
- **新内容指示**: 标记有新内容但不需要具体数量时，使用 Badge/Dot
- **状态颜色标记**: 表示设备在线/离线、连接状态等使用不同颜色的 Badge/Color
- **数量超限**: 超过 99 条时统一显示 "99+"，使用 `Type=More number`

### 何时不使用

- **标签分类**: 表示内容分类或标签应使用 Tag 组件
- **状态说明文字**: 需要文字描述的状态应使用文字标签而非纯色圆点
- **交互按钮**: Badge 不可点击，需要交互时应在父元素上添加点击事件
- **装饰元素**: 不要将 Badge 用于纯装饰目的

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 数字超过 99 时使用 "99+" 形式 | 显示 "128" 等超大数字 | 胶囊宽度过大会破坏布局 |
| 使用 Small 尺寸配合小图标或紧凑列表 | 在大图标上使用 Small 徽标 | 尺寸比例不协调 |
| Badge/Dot 仅用于"有/无"二元指示 | 用 Dot 表示具体数量 | 圆点无法传达数量信息 |
| Badge/Color 用于一致的状态颜色系统 | 随意使用颜色 | 颜色需与系统语义一致（红=错误, 黄=警告, 蓝=强调, 绿=成功） |
| 将 Badge 定位在父元素右上角 | 将 Badge 放在父元素正中央 | 用户习惯在右上角寻找徽标信息 |
| 计数为 0 时移除 Badge | 显示 "0" 的徽标 | 无新事件时不应分散注意力 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `hyperos-color-error` | `#FA382E` | color | 数字徽标背景、圆点背景、红色状态 |
| `hyperos-color-primary` | `#3482FF` | color | 蓝色状态圆点 |
| `hyperos-color-caution` | `#FF9F05` | color | 黄色状态圆点 |
| `hyperos_theme_radius_circle` | `999px` | radius | 数字徽标全圆角 |
| `hyperos_font_size_subtitle2` | `14px` | font-size | Medium 数字字号 |
| `hyperos_font_weight_subtitle2` | `450` | font-weight | Medium 数字字重 |
| `Subtitle/Subtitle 2` | `MiSans, Demibold, 14px, 450, lh:100%, ls:0` | typography | Medium 数字完整文字样式 |
| `hyperos-color-on-surface` | `#000000` | color | 基础文字色（Badge 内不使用，但在上下文中参考） |

---

## 设计注释

> 1. **正圆 vs 胶囊**: 单位数字（number 类型）使用固定宽高的正圆形状；多位数字（2number / More number）使用固定高度 + 水平 padding 的胶囊形状，宽度随内容自适应。
> 2. **border-radius 差异**: Badge/Dot 使用 `60px`（固定值），Badge/number 使用 `999px`（`hyperos_theme_radius_circle` Token）。两者视觉效果相同（均为全圆角），但实现引用不同。
> 3. **文字样式差异**: Medium 使用 `Subtitle/Subtitle 2` 样式（Demibold 450, 14px），Small 使用独立的 MiSans Medium 12px 样式（非 Token 化），Small 的 line-height 明确设置为 `12px` 以确保垂直居中。
> 4. **Green 颜色无 Token**: 绿色圆点 `#36D167` 在当前组件中未关联语义 Token，虽然系统色板中存在 `系统色-light/green-light-primary-default`，但组件直接使用硬编码值。
> 5. **Badge/Color 内部实现**: Red 颜色复用了 Badge/Dot Small 组件实例，其他颜色直接使用 `<div>` 实现。实现时应统一处理，无需区分内部实现差异。
> 6. **数字徽标的 padding-x**: Medium 的 2number 使用 `7px`，More number 使用 `6px`；Small 统一使用 `4px`。这一差异是为了在不同数字宽度下保持视觉平衡。
> 7. **定位方式**: Badge 组件自身不包含绝对定位属性，需要在使用处通过 `position: absolute` 将其定位在父元素右上角。
