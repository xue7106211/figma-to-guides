---
component: IndexBar
description: 小米 HyperOS4 索引控件，用于在长列表右侧提供字母索引快速定位功能
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=82864-42825
figma_node_id: "75:3322"
variants: "1 dimension (模式), 4 variants"
tokens_used: 6
---

# 索引控件 IndexBar

> HyperOS4 系统级字母索引控件，置于长列表（如通讯录、音乐列表）右侧，用于快速跳转到指定字母分区。支持默认全字母模式和分屏缩略模式，手指触摸滑动时弹出泡泡指示器（大索引）显示当前字母。

## 预览

![索引控件全部变体预览](http://localhost:3845/figma/screenshot/75:3322)

---

## 组件结构

```
索引控件                                   // COMPONENT_SET | 75:3322
├── 模式=默认                              // COMPONENT | 82881:46572
│   └── 索引条                             // FRAME | 82881:46576
│       ├── 收藏（心形图标）                // FRAME | 82881:46577
│       │   └── 󰀻（图标字符）              // TEXT | 82881:46578
│       ├── A                              // TEXT | 82881:46579
│       ├── B                              // TEXT | 82881:46580
│       ├── ...（C-L）
│       ├── M（选中态，高亮色）             // TEXT | 82881:46591
│       ├── ...（N-Z）
│       └── #                              // TEXT | 82881:46605
├── 模式=默认-定位                          // COMPONENT | 75:3347
│   ├── 大索引（泡泡指示器）                // FRAME | 75:3348
│   │   ├── 泡泡（SVG 气泡形状）           // VECTOR | 75:3349
│   │   └── M（当前字母）                  // TEXT | 75:3350
│   └── 索引条                             // FRAME | 75:3351
│       ├── 收藏（心形图标）                // FRAME | 49649:76254
│       ├── A ~ Z + #                      // TEXT (多个)
│       └── M（选中态，高亮色）             // TEXT | 75:3365
├── 模式=分屏-默认                          // COMPONENT | 82881:47507
│   └── 索引条                             // FRAME | 82881:47508
│       ├── 收藏（心形图标）                // FRAME | 82881:47509
│       ├── A                              // TEXT | 82881:47511
│       ├── •（圆点分隔符）                 // FRAME | 82881:47512
│       ├── G                              // TEXT | 82881:47515
│       ├── •（圆点分隔符）                 // FRAME | 82881:47516
│       ├── N                              // TEXT | 82881:47519
│       ├── •（圆点分隔符）                 // FRAME | 82881:47520
│       ├── T                              // TEXT | 82881:47523
│       ├── •（圆点分隔符）                 // FRAME | 82881:47524
│       ├── Z                              // TEXT | 82881:47527
│       └── #                              // TEXT | 82881:47528
└── 模式=分屏-定位                          // COMPONENT | 75:3323
    ├── 索引条（同分屏-默认）               // FRAME | 75:3324
    └── 大索引（泡泡指示器）                // FRAME | 75:3344
        ├── 泡泡（SVG 气泡形状）           // VECTOR | 75:3345
        └── M（当前字母）                  // TEXT | 75:3346
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| 索引条 | FRAME | `82881:46576` / `75:3351` / `82881:47508` / `75:3324` | 胶囊形索引条容器，包含字母和图标 |
| 收藏 | FRAME | `82881:46577` / `49649:76254` / `82881:47509` / `49649:76562` | 顶部心形收藏图标 |
| 大索引 | FRAME | `75:3348` / `75:3344` | 泡泡指示器容器，含 SVG 气泡和字母 |
| 泡泡 | VECTOR | `75:3349` / `75:3345` | SVG 气泡形状（水滴形指向右侧） |
| 圆点分隔符 | FRAME | `82881:47512` 等 | 分屏模式下字母间的圆点分隔 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器（各变体整体尺寸）

| 变体 | `width` | `height` | `position` |
|-----|---------|----------|-----------|
| 默认 | `49px` | `519px` | `relative` |
| 默认-定位 | `119px` | `522px` | `relative` |
| 分屏-默认 | `53px` | `213px` | `relative` |
| 分屏-定位 | `119px` | `213px` | `relative` |

### 子组件: 索引条

![索引条预览 — 默认模式](http://localhost:3845/figma/screenshot/82881:46572)

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `position` | `absolute` | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `gap` | `6px` | — |
| `padding` | `12px 6px`（默认模式）/ `12px 7px`（分屏模式） | — |
| `background-color` | `rgba(0,0,0,0.04)` | `miuix_default_color_surface_container` |
| `border-radius` | `999px` | `miuix_theme_radius_circle` |
| `overflow` | `clip` | — |

#### 索引条定位（各变体）

| 变体 | `top` | `left` | 其他定位 |
|-----|-------|--------|---------|
| 默认 | `0` | `12px` | — |
| 默认-定位 | `0` | `82px` | — |
| 分屏-默认 | `50%` | `30.19%` | `right: 30.19%; transform: translateY(-50%)` |
| 分屏-定位 | `50%` | `68.91%` | `right: 13.45%; transform: translateY(-50%)` |

### 子组件: 收藏图标

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `9px` | — |
| `height` | `9px` | — |
| `font-family` | `HyperOS_Symbols_VF` | — |
| `font-weight` | `Regular` | — |
| `font-size` | `7px` | — |
| `color` | `#FA382E` | `miuix_default_color_error` |

### 子组件: 大索引（泡泡指示器）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `82px` | — |
| `height` | `62px` | — |
| `position` | `absolute` | — |

泡泡形状为 SVG 矢量图形（水滴形/气泡形，尖端指向右侧索引条方向）。

资源 URL：`http://localhost:3845/assets/b62a46eb3a20f44a06c4732868868d3f2c1c7164.svg`

#### 泡泡内定位（默认-定位模式）

| CSS 属性 | 值 |
|---------|---|
| 大索引容器 `left` | `0` |
| 大索引容器 `top` | `217px`（与当前选中字母对齐） |

#### 泡泡内定位（分屏-定位模式）

| CSS 属性 | 值 |
|---------|---|
| 大索引容器 `inset` | `35.45% 31.09% 35.45% 0`（垂直居中于索引条） |

#### 泡泡内字母

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `font-family` | `MiSans` | — |
| `font-weight` | `500`（Medium） | — |
| `font-size` | `29px` | — |
| `line-height` | `normal` | — |
| `color` | `#3482FF` | `miuix_default_color_primary` |
| `text-align` | `center` | — |
| `position` | `absolute` | — |
| `left` | `30px` | — |
| `top` | `12px` | — |
| `transform` | `translateX(-50%)` | — |

### 子组件: 圆点分隔符（仅分屏模式）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `4px` | — |
| `height` | `4px` | — |
| `border-radius` | `28px` | — |
| `background-color` | `rgba(0,0,0,0.4)` | `miuix_default_color_on_surface_quaternary` |

圆点外层容器（用于垂直间距对齐）：

| CSS 属性 | 值 |
|---------|---|
| `width` | `6px` |
| `height` | `12px` |
| `display` | `inline-grid` |
| 圆点相对于容器 | `margin-left: 1px; margin-top: 4px` |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| 字母项（默认） | MiSans | 9px | 500（Medium） | normal | 0 | `rgba(0,0,0,0.4)` | `miuix_default_color_on_surface_quaternary` |
| 字母项（选中） | MiSans | 9px | 500（Medium） | normal | 0 | `#3482FF` | `miuix_default_color_primary` |
| 泡泡字母 | MiSans | 29px | 500（Medium） | normal | 0 | `#3482FF` | `miuix_default_color_primary` |
| 收藏图标 | HyperOS_Symbols_VF | 7px | Regular | normal | 0 | `#FA382E` | `miuix_default_color_error` |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 索引条背景色 | `rgba(0,0,0,0.04)` | `miuix_default_color_surface_container` |
| 字母默认色 | `rgba(0,0,0,0.4)` | `miuix_default_color_on_surface_quaternary` |
| 字母选中色 / 泡泡字母色 | `#3482FF` | `miuix_default_color_primary` |
| 收藏图标色 | `#FA382E` | `miuix_default_color_error` |
| 圆点分隔符色 | `rgba(0,0,0,0.4)` | `miuix_default_color_on_surface_quaternary` |

---

## 变体

### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 模式 | `模式` | `默认` / `默认-定位` / `分屏-默认` / `分屏-定位` | 控制索引条的显示模式和定位指示器 |

共计 **4 个变体**。

### 变体差异表

> 仅列出各变体之间**有差异**的属性。未列出的属性与默认变体相同。

#### 按模式分组

| 属性 | `默认` | `默认-定位` | `分屏-默认` | `分屏-定位` |
|-----|--------|-----------|-----------|-----------|
| 整体 `width` | `49px` | `119px` | `53px` | `119px` |
| 整体 `height` | `519px` | `522px` | `213px` | `213px` |
| 字母列表 | 收藏 + A~Z + # (28项) | 收藏 + A~Z + # (28项) | 收藏 + A•G•N•T•Z•# (6字母+5圆点) | 收藏 + A•G•N•T•Z•# (6字母+5圆点) |
| 索引条 `padding` | `12px 6px` | `12px 6px` | `12px 7px` | `12px 7px` |
| 索引条定位 | `left: 12px; top: 0` | `left: 82px; top: 0` | 垂直居中 `left: 30.19%` | 垂直居中 `left: 68.91%` |
| 大索引（泡泡） | 不显示 | 显示，`left: 0; top: 217px` | 不显示 | 显示，`inset: 35.45% 31.09% 35.45% 0` |

#### 默认 详情

![默认模式](http://localhost:3845/figma/screenshot/82881:46572)

完整字母索引条，显示收藏图标 + A 至 Z + # 共 28 个项目。索引条左侧留 12px 间距。无泡泡指示器。

#### 默认-定位 详情

![默认-定位模式](http://localhost:3845/figma/screenshot/75:3347)

完整字母索引条 + 泡泡指示器。泡泡位于索引条左侧，显示当前定位的字母（示例中为 M，以主题色显示）。索引条中当前字母同步高亮为主题色。

#### 分屏-默认 详情

![分屏-默认模式](http://localhost:3845/figma/screenshot/82881:47507)

缩略字母索引条，仅显示 A、G、N、T、Z、# 六个代表性字母，字母之间以圆点分隔。适用于分屏或空间受限场景。索引条垂直居中于容器。

#### 分屏-定位 详情

![分屏-定位模式](http://localhost:3845/figma/screenshot/75:3323)

缩略字母索引条 + 泡泡指示器。泡泡居于索引条左侧居中位置，显示当前定位的字母。

---

## 交互状态

> 以「默认态」为基准，其他状态仅列出**发生变化**的属性。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态，索引条可见，无泡泡） | — |
| `touching` | 手指触摸索引条 | 模式切换 | 从「默认」→「默认-定位」或从「分屏-默认」→「分屏-定位」，显示泡泡指示器 | — |
| `scrolling` | 手指在索引条上滑动 | 泡泡 `top` 位置 + 泡泡内字母 | 泡泡跟随手指位置，字母更新为当前指向的索引字母 | — |
| `selected-letter` | 手指指向某个字母 | 字母 `color` | `#3482FF`（从默认色变为主题色） | `miuix_default_color_primary` |
| `released` | 手指抬起 | 模式切换 | 从「定位」→「默认/分屏-默认」，泡泡指示器消失 | — |
| `hover` | Figma 未定义，请由设计团队补充 | — | — | — |
| `disabled` | Figma 未定义，请由设计团队补充 | — | — | — |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

```typescript
interface IndexBarProps {
  /** 显示模式：默认（全字母）、默认-定位（全字母+泡泡）、分屏-默认（缩略）、分屏-定位（缩略+泡泡） */
  mode: '默认' | '默认-定位' | '分屏-默认' | '分屏-定位';
  /** 索引字母列表，默认 A-Z + # */
  letters?: string[];
  /** 当前选中/定位的字母 */
  activeLetter?: string;
  /** 是否显示收藏图标 */
  showFavorite?: boolean; // 默认: true
  /** 字母点击/滑动回调 */
  onLetterChange?: (letter: string) => void;
}
```

### Figma 属性映射表

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 模式 | Variant | `mode` | `默认` | 控制索引条的显示模式和定位指示器 |

---

## 使用指南

### 何时使用

- **通讯录 / 联系人列表**：使用「默认」模式，手指触摸时切换至「默认-定位」模式，快速跳转至目标字母分区
- **分屏模式**：屏幕空间受限时，使用「分屏-默认」/「分屏-定位」模式，以缩略字母 + 圆点分隔的方式节省纵向空间
- **音乐 / 应用列表**：任何按字母排序的长列表场景

### 何时不使用

- **列表项数量较少（< 20 项）**：无需索引，应使用普通滚动
- **非字母排序的列表**：应使用搜索栏（SearchBar）或筛选器（Filter）代替
- **横向列表**：应使用分页指示器（PageIndicator）代替

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 索引条距离屏幕右侧边缘 `40px` | 索引条紧贴屏幕边缘 | Figma 标注明确要求 40px 边距，保证触摸区域舒适 |
| 泡泡指示器仅在触摸时出现 | 泡泡指示器常驻显示 | 指示器为临时反馈，不应干扰内容区域 |
| 分屏模式使用 6 个代表字母 + 圆点分隔 | 分屏模式仍显示全部 26 个字母 | 空间受限时需要缩略以保持可读性 |
| 选中字母使用主题色 `#3482FF` 高亮 | 选中字母使用加粗或放大来区分 | 设计规范通过颜色而非尺寸来标识当前位置 |
| 收藏图标始终位于索引条顶部 | 将收藏图标混排在字母中间 | 收藏是特殊分区，应独立于字母排序 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `miuix_default_color_surface_container` | `rgba(0,0,0,0.04)` | color | 索引条背景色 |
| `miuix_default_color_on_surface_quaternary` | `rgba(0,0,0,0.4)` | color | 字母默认色、圆点分隔符色 |
| `miuix_default_color_primary` | `#3482FF` | color | 选中字母色、泡泡内字母色 |
| `miuix_default_color_error` | `#FA382E` | color | 收藏心形图标色 |
| `miuix_theme_radius_circle` | `999px` | radius | 索引条胶囊形圆角 |
| `miuix_theme_radius_medium` | `20px` | radius | 备用圆角（未在当前组件直接使用） |

---

## 设计注释

> 1. **距离屏幕边缘 40px**：Figma 组件描述明确标注，索引控件应距离屏幕右侧边缘 40px 放置，该间距不包含在组件自身尺寸内，由使用方通过布局控制。
> 2. **泡泡形状为 SVG 矢量图形**：大索引的泡泡（气泡/水滴形）是一个 82×62px 的 SVG 资源，尖端指向右侧索引条方向，内部居中显示当前字母。
> 3. **分屏模式的字母选取规则**：分屏缩略模式固定显示 A、G、N、T、Z、# 六个字母，按字母表均匀分布选取，字母之间以 4px 圆点分隔。
> 4. **选中态仅改变颜色**：当前定位的字母仅通过颜色变化（从 `rgba(0,0,0,0.4)` 变为 `#3482FF`）标识，字号和字重保持不变。
> 5. **字体依赖**：字母文字使用 `MiSans Medium`（500），收藏图标使用 `HyperOS_Symbols_VF Regular` 符号字体。
> 6. **索引条为绝对定位**：索引条在组件内使用 `position: absolute`，不同变体的定位方式不同（默认模式靠上对齐，分屏模式垂直居中）。
