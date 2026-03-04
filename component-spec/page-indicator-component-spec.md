---
component: PageIndicator
description: 用于指示当前所在页面位置的点状指示器组件，支持大小两种尺寸，具备溢出渐变缩小效果
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=42927-152694
figma_node_id: "42927:152694"
variants: "3 dimensions, 81 variants"
tokens_used: 3
---

# 页面指示器 PageIndicator

> 用于分页场景中指示当前页面位置的圆点指示器组件。通过高亮圆点标识当前页面，支持大小两种尺寸，当页面数量超过最大可见数时，远端圆点会渐变缩小以暗示更多页面的存在。

## 预览

![页面指示器全部变体预览](figma-screenshot:38787:56871)

### 小尺寸预览

![页面指示器 小尺寸 数量=2 选中=1](figma-screenshot:38787:56872)

### 大尺寸预览

![页面指示器 大尺寸 数量=2 选中=1](figma-screenshot:38800:60133)

### 溢出预览（小尺寸 6+）

![页面指示器 小尺寸 数量=6+ 选中=1](figma-screenshot:38788:58940)

---

## 组件结构

```
页面指示器                                    // COMPONENT_SET | 38787:56871
├── 尺寸=小尺寸, 数量=2, 选中=1              // COMPONENT | 38787:56872
│   ├── .3个材质切换/玻璃材质/亮色模式        // FRAME | 81348:1395 (条件渲染)
│   │   ├── glass-layer-base                  // FRAME (bg rgba(0,0,0,0.02))
│   │   ├── glass-layer-soft-light            // FRAME (bg rgba(255,255,255,0.6) mix-blend-mode: soft-light)
│   │   ├── glass-layer-hard-light            // FRAME (bg rgba(255,255,255,0.4) mix-blend-mode: hard-light)
│   │   └── glass-inner-shadow                // FRAME (inner shadow)
│   ├── Dot-Active                            // FRAME | 38788:58637 (选中圆点)
│   └── Dot-Inactive                          // FRAME | 38788:58638 (未选中圆点)
├── 尺寸=小尺寸, 数量=6+, 选中=1             // COMPONENT | 38788:58940
│   ├── .3个材质切换/玻璃材质/亮色模式        // FRAME (条件渲染)
│   ├── Dot-Active                            // FRAME (选中圆点 5px)
│   ├── Dot-Inactive ×4                       // FRAME (未选中圆点 5px)
│   ├── Dot-Shrink-Medium                     // FRAME+子节点 (缩小圆点 4px)
│   └── Dot-Shrink-Small                      // FRAME+子节点 (最小圆点 2px)
├── 尺寸=大尺寸, 数量=2, 选中=1              // COMPONENT | 38800:60133
│   └── ... (结构同小尺寸，尺寸不同)
├── 尺寸=大尺寸, 数量=9+, 选中=1             // COMPONENT | 38800:60210
│   ├── .3个材质切换/玻璃材质/亮色模式        // FRAME (条件渲染)
│   ├── Dot-Active                            // FRAME (选中圆点 7px)
│   ├── Dot-Inactive ×7                       // FRAME (未选中圆点 7px)
│   ├── Dot-Shrink-Medium                     // FRAME+子节点 (缩小圆点 6px)
│   └── Dot-Shrink-Small                      // FRAME+子节点 (最小圆点 4px)
└── ... (其余变体)
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| .3个材质切换/玻璃材质/亮色模式 | FRAME | `81348:1395` | 可选的玻璃材质背景层，通过 Boolean 属性控制显隐 |
| Dot-Active | FRAME | `38788:58637` | 选中状态的圆点，使用深色填充 |
| Dot-Inactive | FRAME | `38788:58638` | 未选中状态的圆点，使用浅色填充 |
| Dot-Shrink-Medium | FRAME | `38800:62692` | 溢出时的中等缩小圆点容器，内含缩小的子圆点 |
| Dot-Shrink-Small | FRAME | `38800:62695` | 溢出时的最小缩小圆点容器，内含最小的子圆点 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器（小尺寸）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `row` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `gap` | `8px` | — |
| `height` | `21px` | — |
| `width` | `auto`（hug） | — |
| `padding-top` | `8px` | — |
| `padding-right` | `10px` | — |
| `padding-bottom` | `8px` | — |
| `padding-left` | `10px` | — |
| `border-radius` | `999px` | `hyperos_theme_radius_circle` |
| `background-color` | `transparent` | — |
| `overflow` | `visible` | — |

### 容器（大尺寸）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `row` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `gap` | `10px` | — |
| `height` | `30px` | — |
| `width` | `auto`（hug） | — |
| `padding-top` | `8px` | — |
| `padding-right` | `12px` | — |
| `padding-bottom` | `8px` | — |
| `padding-left` | `12px` | — |
| `border-radius` | `999px` | `hyperos_theme_radius_circle` |
| `background-color` | `transparent` | — |
| `overflow` | `visible` | — |

### 子组件: 圆点（小尺寸）

| CSS 属性 | 值（选中） | 值（未选中） | Token |
|---------|----------|------------|-------|
| `width` | `5px` | `5px` | — |
| `height` | `5px` | `5px` | — |
| `border-radius` | `999px` | `999px` | `hyperos_theme_radius_circle` |
| `background-color` | `rgba(0,0,0,0.8)` | `rgba(0,0,0,0.3)` | 选中: `hyperos-color-on-surface-secondary` / 未选中: `hyperos-color-on-surface-octonary` |
| `flex-shrink` | `0` | `0` | — |

### 子组件: 圆点（大尺寸）

| CSS 属性 | 值（选中） | 值（未选中） | Token |
|---------|----------|------------|-------|
| `width` | `7px` | `7px` | — |
| `height` | `7px` | `7px` | — |
| `border-radius` | `999px` | `999px` | `hyperos_theme_radius_circle` |
| `background-color` | `rgba(0,0,0,0.8)` | `rgba(0,0,0,0.3)` | 选中: `hyperos-color-on-surface-secondary` / 未选中: `hyperos-color-on-surface-octonary` |
| `flex-shrink` | `0` | `0` | — |

### 子组件: 溢出缩小圆点

当页面数量超过最大可见数时（小尺寸 >6，大尺寸 >9），远端圆点使用外层容器包裹并逐级缩小。

#### 小尺寸溢出圆点

| 缩小级别 | 外层容器尺寸 | 内部圆点尺寸 | `border-radius` | `background-color` | Token |
|---------|------------|------------|----------------|--------------------|----|
| 正常 | — | `5px` | `999px` | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |
| 中等缩小 | `5px` | `4px` | `50px` | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |
| 最大缩小 | `5px` | `2px` | `50px` | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |

#### 大尺寸溢出圆点

| 缩小级别 | 外层容器尺寸 | 内部圆点尺寸 | `border-radius` | `background-color` | Token |
|---------|------------|------------|----------------|--------------------|----|
| 正常 | — | `7px` | `999px` | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |
| 中等缩小 | `7px`（含 `1px` padding） | `6px` | `50px` | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |
| 最大缩小 | `7px`（含 `1px` padding） | `4px` | `50px` | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |

### 子组件: 玻璃材质背景

当 `propValue`（玻璃材质）开启时，容器上叠加以下效果层：

| CSS 属性 | 值 | 说明 |
|---------|----|------|
| `position` | `absolute` | 覆盖整个容器 |
| `inset` | `0` | 填满容器 |
| `border` | `0.8px solid rgba(252,252,252,0.2)` | 玻璃边框 |
| `border-radius` | `28px` | 玻璃圆角 |
| `box-shadow` | `0px 0px 40px 0px rgba(0,0,0,0.06), 0px 24px 60px 0px rgba(0,0,0,0.08)` | 外部阴影 |
| `box-shadow`（内阴影） | `inset 0px 2px 2px 0px #9d9d9d` | 内部阴影 |
| `pointer-events` | `none` | 不影响交互 |

#### 玻璃效果图层叠加

| 图层顺序 | `background-color` | `mix-blend-mode` | 说明 |
|---------|--------------------|-----------------|----|
| 1（底层） | `rgba(0,0,0,0.02)` | `normal` | 基础着色层 |
| 2（中层） | `rgba(255,255,255,0.6)` | `soft-light` | 柔光层 |
| 3（顶层） | `rgba(255,255,255,0.4)` | `hard-light` | 强光层 |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 选中圆点填充色 | `rgba(0,0,0,0.8)` | `hyperos-color-on-surface-secondary` |
| 未选中圆点填充色 | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |
| 玻璃边框色 | `rgba(252,252,252,0.2)` | — |
| 玻璃基础层 | `rgba(0,0,0,0.02)` | — |
| 玻璃柔光层 | `rgba(255,255,255,0.6)` | — |
| 玻璃强光层 | `rgba(255,255,255,0.4)` | — |
| 玻璃内阴影 | `#9d9d9d` | — |

---

## 变体

### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 尺寸 | `尺寸` | `小尺寸` / `大尺寸` | 控制圆点大小和间距 |
| 数量 | `数量` | `2` / `3` / `4` / `5` / `6` / `6+` / `7` / `8` / `9` / `9+` | 页面总数（小尺寸最大 `6+`，大尺寸最大 `9+`） |
| 选中 | `选中` | `1` ~ `N`（N 为对应数量值） | 当前选中的页面序号 |

- 小尺寸变体数量范围：`2` ~ `6+`，共 **27 个变体**
- 大尺寸变体数量范围：`2` ~ `9+`，共 **54 个变体**
- 合计 **81 个变体**

### 变体差异表

> 仅列出两种尺寸之间**有差异**的属性。

#### 按尺寸分组

| 属性 | `小尺寸` | `大尺寸` |
|-----|---------|---------|
| `height` | `21px` | `30px` |
| `gap` | `8px` | `10px` |
| `padding` | `8px 10px` | `8px 12px` |
| 圆点 `size` | `5px` | `7px` |
| 最大可见数量 | `6`（超过使用 `6+`） | `9`（超过使用 `9+`） |

#### 按数量分组 — 溢出行为

当数量为 `6+`（小尺寸）或 `9+`（大尺寸）时，容器最多显示固定数量的圆点，超出部分通过渐变缩小暗示：

##### 小尺寸 6+ 溢出规则

| 选中位置 | 圆点序列（从左到右） |
|---------|------------------|
| `选中=1`（靠左） | `●` `○` `○` `○` `○` `◎`(4px) `·`(2px) |
| `选中=4`（居中） | `·`(2px) `◎`(4px) `○` `○` `●` `○` `○` |
| `选中=6`（靠右） | `·`(2px) `◎`(4px) `○` `○` `○` `●` `○` |

> `●` = 选中 5px, `○` = 未选中 5px, `◎` = 缩小 4px, `·` = 最小 2px

##### 大尺寸 9+ 溢出规则

| 选中位置 | 圆点序列（从左到右） |
|---------|------------------|
| `选中=1`（靠左） | `●` `○` `○` `○` `○` `○` `○` `○` `◎`(6px) `·`(4px) |
| `选中=9`（靠右） | `·`(4px) `◎`(6px) `○` `○` `○` `○` `○` `○` `●` `○` |

> `●` = 选中 7px, `○` = 未选中 7px, `◎` = 缩小 6px, `·` = 最小 4px

---

## 交互状态

> 页面指示器本身是展示型组件，不直接响应用户交互。状态变化由外部容器（如 ViewPager / ScrollView）驱动。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态） | — |
| `page-change` | 外部页面切换 | 圆点 `background-color` | 选中圆点切换为 `rgba(0,0,0,0.8)`，原选中变为 `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-secondary` / `hyperos-color-on-surface-octonary` |
| `overflow-scroll` | 页面数 > 最大可见数时滑动 | 远端圆点 `size` | 渐变缩小：全尺寸 → 中等 → 最小 | — |
| `glass-enabled` | `propValue=true` | 叠加玻璃材质背景 | 见「玻璃材质背景」section | — |

> Figma 中未定义 hover / active / focused / disabled 状态。该组件为纯展示型，交互状态由父容器控制，请由设计团队补充过渡动画规范。

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

```typescript
interface PageIndicatorProps {
  /** 尺寸，控制圆点大小和容器间距 */
  size: 'small' | 'large';
  /** 页面总数量 */
  count: number;
  /** 当前选中的页面索引（从 1 开始） */
  activeIndex: number;
  /** 是否显示玻璃材质背景 */
  glass?: boolean; // 默认: false
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 尺寸 | Variant | `size` | `small` | `小尺寸` → `'small'`，`大尺寸` → `'large'` |
| 数量 | Variant | `count` | `2` | 页面总数，实现时为 `number` 类型，超过阈值时自动启用溢出缩小 |
| 选中 | Variant | `activeIndex` | `1` | 当前选中的页面序号 |
| propValue | Boolean | `glass` | `false` | 是否叠加玻璃材质背景效果 |

---

## 使用指南

### 何时使用

- **轮播图 / Banner**：使用「小尺寸」配合少量页面（2~6），展示当前轮播位置
- **引导页 / Onboarding**：使用「大尺寸」配合固定页面数，突出页面进度感
- **内容分页浏览**：当页面数量不确定或较多（>6）时，使用 `6+` 或 `9+` 溢出模式
- **天气 / 桌面小组件**：在毛玻璃背景上使用时，启用 `glass=true`

### 何时不使用

- **步骤进度**：应使用 Stepper 组件代替，页面指示器不表达先后顺序和完成状态
- **Tab 导航**：应使用 TabBar 或 SegmentedControl 代替，页面指示器不支持直接点击切换
- **无限滚动列表**：应使用滚动条或加载指示器代替，页面指示器适用于有限离散页面

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 在分页内容底部居中放置 | 放置在内容侧边或上方 | 符合平台惯例，用户视线自然下移 |
| 页面数 ≤6 时使用小尺寸 | 页面数 >6 时仍使用小尺寸非溢出模式 | 小尺寸最多支持 6 个圆点，超出应使用 `6+` |
| 在深色/图片背景上启用 glass 效果 | 在纯白背景上启用 glass 效果 | 玻璃材质在深色/复杂背景上才有视觉效果 |
| 圆点切换时添加过渡动画 | 无动画直接切换 | 平滑过渡能传递页面滑动的方向感 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `hyperos_theme_radius_circle` | `999px` | radius | 容器圆角、圆点圆角 |
| `hyperos-color-on-surface-secondary` | `rgba(0,0,0,0.8)` | color | 选中圆点填充色 |
| `hyperos-color-on-surface-octonary` | `rgba(0,0,0,0.3)` | color | 未选中圆点填充色 |

---

## 设计注释

> 1. 该组件属于 HyperOS 4 设计系统的「页面指示器 Page controls」分类。
> 2. 小尺寸最大可见圆点数为 **6**，超过 6 个页面时使用 `6+` 溢出模式（固定显示 7 个位置，含 2 个渐缩圆点）。
> 3. 大尺寸最大可见圆点数为 **9**，超过 9 个页面时使用 `9+` 溢出模式（固定显示 10 个位置，含 2 个渐缩圆点）。
> 4. 溢出模式下，远离选中位置的圆点分两级缩小：中等缩小（小尺寸 4px / 大尺寸 6px）→ 最大缩小（小尺寸 2px / 大尺寸 4px）。
> 5. 溢出缩小圆点使用外层容器保持占位尺寸不变（等于正常圆点尺寸），内部圆点居中缩小，这样可以保证整体容器宽度不随选中位置变化而跳动。
> 6. 玻璃材质背景（`propValue`）采用三层叠加实现毛玻璃效果，适用于在图片或深色背景上使用该指示器的场景（如天气小组件）。
> 7. 在同一页面区域中还存在关联组件「天气指示器」（nodeId: `81320:23977`），它将页面指示器与位置图标组合使用，用于天气类小组件的底部导航。
> 8. Figma 中未定义页面切换时的过渡动画规范，实现时建议添加圆点颜色和尺寸的平滑过渡效果，请由设计团队补充动画曲线和时长。
