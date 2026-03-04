---
component: SegmentedControls
description: 分段按钮，用于在同一层级中切换不同视图或筛选项，支持 2-5 个分段选项
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=105830-9444
figma_node_id: "105830:9444"
variants: "3 dimensions, 24 variants"
tokens_used: 14
---

# 分段按钮 SegmentedControls

> HyperOS 4 设计系统中的分段按钮组件，用于在同一层级中切换不同视图或筛选内容。支持 2~5 个分段选项，适配亮色/深色模式以及灰色、白色、彩色三种背景环境，彩色背景下使用毛玻璃材质。

## 预览

### Phone 端全部变体

![SegmentedControls Phone 全部变体预览](https://www.figma.com/api/mcp/asset/105830-9508)

### Pad 端变体（以灰色背景为例）

![SegmentedControls Pad 变体预览](https://www.figma.com/api/mcp/asset/105830-10052)

### 原子组件（选项 + 底板 + 材质）

![SegmentedControls 原子组件](https://www.figma.com/api/mcp/asset/105830-9981)

![SegmentedControls 材质板子](https://www.figma.com/api/mcp/asset/105830-10083)

---

## 组件结构

```
母组件集合_勿动                                 // FRAME | 105830:9444
├── SegmentedControls 分段按钮                   // COMPONENT_SET | 105830:9508
│   ├── 颜色模式=亮色模式, 个数=2, 背景环境=灰色背景  // COMPONENT | 105830:9509
│   │   ├── SegmentedControl-Body               // FRAME
│   │   │   ├── Segment-TrackBase               // FRAME (底板)
│   │   │   └── Segment-Group                   // FRAME
│   │   │       ├── Segment-Selected            // FRAME (选中项)
│   │   │       │   └── Container               // FRAME
│   │   │       │       └── 选中项 (TEXT)
│   │   │       └── .选项 (未选项)               // INSTANCE
│   │   │           └── Container               // FRAME
│   │   │               └── 未选中 (TEXT)
│   │   └── ...
│   ├── 颜色模式=亮色模式, 个数=3, 背景环境=灰色背景  // COMPONENT | 105830:9515
│   ├── ... (共 24 个变体)
│   └── 颜色模式=深色模式, 个数=5, 背景环境=彩色背景  // COMPONENT | 105830:9650
├── .选项                                       // COMPONENT_SET | 105830:9981
│   ├── 筛选项=选中项, 状态=平面, 深色模式=light, 背景颜色模式=灰背景
│   ├── 筛选项=未选项, 状态=平面, 深色模式=light, 背景颜色模式=灰背景
│   ├── 筛选项=底板, 状态=平面, 深色模式=light, 背景颜色模式=灰背景
│   └── ... (共 15 个变体)
├── 材质板子                                     // COMPONENT_SET | 105830:10083
│   ├── 材质=混色模糊, 深色模式=no
│   ├── 材质=混色模糊, 深色模式=yes
│   ├── 材质=纯色面板, 深色模式=no
│   └── 材质=纯色面板, 深色模式=yes
└── 以灰色背景为例子 (Pad 端)                     // FRAME | 105830:10052
    ├── Property 1=2                             // COMPONENT | 105830:10053
    ├── Property 1=3                             // COMPONENT | 105830:10059
    ├── Property 1=4                             // COMPONENT | 105830:10066
    └── Property 1=5                             // COMPONENT | 105830:10074
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| SegmentedControls 分段按钮 | COMPONENT_SET | `105830:9508` | Phone 端主组件集，含 24 个变体 |
| SegmentedControl-Body | FRAME | — | 轨道主体区域，包含底板和分段组 |
| Segment-TrackBase | FRAME | — | 底板背景层，承载纯色或毛玻璃材质 |
| Segment-Group | FRAME | — | 分段按钮组，水平排列所有选项 |
| Segment-Selected | FRAME | — | 选中态分段项 |
| .选项 | COMPONENT_SET | `105830:9981` | 原子选项组件，含选中/未选/底板变体 |
| 材质板子 | COMPONENT_SET | `105830:10083` | 毛玻璃 / 纯色材质面板 |
| 以灰色背景为例子 (Pad) | FRAME | `105830:10052` | Pad 端变体展示 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器（Phone 端）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `392px` | — |
| `height` | `40px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `padding` | `0 12px` | — |

### 容器（Pad 端）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `1137px` | — |
| `height` | `40px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `padding` | `0 12px` | — |

### 子组件: SegmentedControl-Body（轨道主体）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `flex` | `1 0 0` | — |
| `height` | `40px` | — |
| `position` | `relative` | — |
| `overflow` | `clip`（非彩色背景变体） / `visible`（彩色背景变体） | — |

### 子组件: Segment-TrackBase（底板）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `position` | `absolute` | — |
| `inset` | `0` | — |
| `height` | `40px` | — |
| `border-radius` | `20px` | `hyperos_theme_radius_medium` |

底板样式按变体差异见下方「变体」章节。

### 子组件: Segment-Group（分段组）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `position` | `absolute` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `top` | `4px` | — |
| `left` | `4px` | — |
| `right` | `4px` | — |
| `bottom` | `4px`（深色彩色背景）/ `auto`（其他） | — |

### 子组件: Segment-Selected（选中项）

| CSS 属性 | 值（默认：亮色 + 灰色/白色背景） | Token |
|---------|----|-------|
| `flex` | `1 0 0` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `overflow` | `clip` | — |
| `background-color` | `rgba(0,0,0,0.05)` | `新增色彩变量/container_nav` |
| `border-radius` | `16px` | `hyperos_theme_radius_common` |
| `padding` | `6px 24px` | — |

### 子组件: 未选项

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `flex` | `1 0 0` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `overflow` | `clip` | — |
| `background-color` | `transparent` | — |
| `border-radius` | `10px` | — |
| `padding` | `6px 24px` | — |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| 选中项（亮色） | MiSans | 14px | 380 (Medium) | 100% | 0 | `#000000` | `Subtitle/Subtitle` |
| 选中项（深色+灰背景） | MiSans | 14px | 380 (Medium) | 100% | 0 | `rgba(255,255,255,0.95)` | `Subtitle/Subtitle` |
| 选中项（深色+白/彩背景） | MiSans | 14px | 450 (Demibold) | 100% | 0 | `rgba(255,255,255,0.95)` | `Subtitle/Subtitle 2` |
| 未选中（亮色） | MiSans | 14px | 380 (Medium) | 100% | 0 | `#000000` | `Subtitle/Subtitle` |
| 未选中（深色+灰背景） | MiSans | 14px | 380 (Medium) | 100% | 0 | `rgba(255,255,255,0.95)` | `Subtitle/Subtitle` |
| 未选中（深色+白/彩背景） | MiSans | 14px | 330 (Regular) | 100% | 0 | `rgba(255,255,255,0.5)` | `Subtitle/Subtitle 3` |

### 颜色一览

| 语义用途 | 值（亮色模式） | 值（深色模式） | Token |
|---------|-------------|-------------|-------|
| 底板背景色（灰背景） | `#FFFFFF` | `rgba(255,255,255,0.14)` | `元素色/container_list` |
| 底板背景色（白背景） | `#FFFFFF` | `rgba(255,255,255,0.14)` | `文字图标色/on_Surface_button_disable` / `元素色/container_list` |
| 底板边框色（白背景-亮色） | `rgba(0,0,0,0.05)` | — | `新增色彩变量/container_nav` |
| 选中项背景色 | `rgba(0,0,0,0.05)` | `rgba(255,255,255,0.12)` | `新增色彩变量/container_nav` |
| 选中项文字色 | `#000000` | `rgba(255,255,255,0.95)` | `hyperos-color-on-surface` |
| 未选中文字色 | `#000000` | `rgba(255,255,255,0.95)` / `rgba(255,255,255,0.5)` | `hyperos-color-on-surface` / `hyperos-color-on-surface-tertiary` |

---

## 变体

### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 颜色模式 | `颜色模式` | `亮色模式` / `深色模式` | 控制整体色彩方案 |
| 段数 | `个数` | `2` / `3` / `4` / `5` | 分段按钮中选项的数量 |
| 背景环境 | `背景环境` | `灰色背景` / `白色背景` / `彩色背景` | 组件所处的页面背景环境，影响底板材质和颜色对比 |

共计 **2 × 4 × 3 = 24 个变体**。

### 变体差异表

> 仅列出各变体之间**有差异**的属性。未列出的属性与默认变体（亮色模式 + 灰色背景）相同。

#### 按「背景环境」×「颜色模式」分组 — 底板（Segment-TrackBase）

| 属性 | 亮色+灰背景 | 亮色+白背景 | 亮色+彩背景 | 深色+灰背景 | 深色+白背景 | 深色+彩背景 |
|-----|-----------|-----------|-----------|-----------|-----------|-----------|
| `background-color` | `#FFFFFF` | `#FFFFFF` | 毛玻璃(Light) | `rgba(255,255,255,0.14)` | `rgba(255,255,255,0.14)` | 毛玻璃(Dark) |
| `border` | — | `1px solid rgba(0,0,0,0.05)` | `0.8px solid rgba(252,252,252,0.2)` | — | — | `0.8px solid #262626` |
| `border-radius` | `20px` | `20px` | `20px` | `20px` | `20px` | `20px` |
| 材质类型 | 纯色面板 | 纯色面板(带描边) | FrostEffect (背景模糊) | 纯色面板 | 纯色面板 | GlassEffect (叠层混合) |
| `overflow` (Body) | `clip` | `clip` | `visible` | `clip` | `clip` | `visible` |

#### 按「背景环境」×「颜色模式」分组 — 选中项（Segment-Selected）

| 属性 | 亮色+灰/白背景 | 亮色+彩背景 | 深色+灰/白/彩背景 |
|-----|-------------|-----------|-----------------|
| `background-color` | `rgba(0,0,0,0.05)` | `rgba(0,0,0,0.05)` | `rgba(255,255,255,0.12)` |
| `height` | `auto` | `32px` | `32px` |
| `padding` | `6px 24px` | `4px 26px` | `4px 26px` |
| `border-radius` | `16px`（全角） | `16px 16px 16px 16px`（右上角跟随 Token） | `16px 16px 16px 16px`（右上角跟随 Token） |
| 选中文字 `font-weight` | 380 (Medium) | 380 (Medium) | 380 (Medium)（灰） / 450 (Demibold)（白/彩） |

#### 按「背景环境」×「颜色模式」分组 — 未选中文字

| 属性 | 亮色（全部背景） | 深色+灰背景 | 深色+白/彩背景 |
|-----|--------------|-----------|-------------|
| `font-weight` | 380 (Medium) | 380 (Medium) | 330 (Regular) |
| `color` | `#000000` | `rgba(255,255,255,0.95)` | `rgba(255,255,255,0.5)` |
| Token | `hyperos-color-on-surface` | `hyperos-color-on-surface` | `hyperos-color-on-surface-tertiary` |

#### 深色彩色背景 — 选中项附加效果

深色+彩色背景的选中项有一层半透明叠层：

| CSS 属性 | 值 |
|---------|----|
| `background-color` | `rgba(177,177,177,0.19)` |
| `mix-blend-mode` | `plus-lighter` |
| `border-radius` | `16px 16px 16px var(--hyperos_theme_radius_common, 16px)` |

### 毛玻璃材质详细规范

#### FrostEffect（亮色模式 + 彩色背景）

底板由三层叠加 + 描边 + 阴影组成：

| 层 | CSS 属性 | 值 |
|----|---------|---|
| 层1 | `background-color` | `rgba(0,0,0,0.02)` |
| 层2 | `background-color` | `rgba(255,255,255,0.6)` |
| 层2 | `mix-blend-mode` | `soft-light` |
| 层3 | `background-color` | `rgba(255,255,255,0.4)` |
| 层3 | `mix-blend-mode` | `hard-light` |
| 层3 | `backdrop-filter` | `blur(10px)` |
| 描边 | `border` | `0.8px solid rgba(252,252,252,0.2)` |
| 外阴影1 | `box-shadow` | `0px 0px 40px 0px rgba(0,0,0,0.06)` |
| 外阴影2 | `box-shadow` | `0px 24px 60px 0px rgba(0,0,0,0.08)` |
| 内阴影 | `box-shadow` | `inset 0px 2px 2px 0px #9D9D9D` |

Token: `FrostShadow/FrostEffect_Thin_ShadowOn`、`Pured/Pured_Thin_Glass_Light`、`Stroke/Glass_Stroke_Small_Light`

#### GlassEffect（深色模式 + 彩色背景）

底板由三层叠加 + 描边 + 阴影组成：

| 层 | CSS 属性 | 值 |
|----|---------|---|
| 层1 | `background-color` | `rgba(0,0,0,0.1)` |
| 层2 | `background-color` | `rgba(86,86,86,0.4)` |
| 层2 | `mix-blend-mode` | `luminosity` |
| 层3 | `background-color` | `rgba(63,63,63,0.6)` |
| 层3 | `mix-blend-mode` | `overlay` |
| 描边 | `border` | `0.8px solid #262626` |
| 外阴影1 | `box-shadow` | `0px 0px 40px 0px rgba(0,0,0,0.06)` |
| 外阴影2 | `box-shadow` | `0px 24px 60px 0px rgba(0,0,0,0.08)` |
| 内阴影 | `box-shadow` | `inset 0px 2px 2px 0px #9D9D9D` |

Token: `GlassShadow (OS4禁用）/GlassEffect_Thin_ShadowOn`、`Pured/Pured_Thin_Glass_Dark`、`Stroke/Glass_Stroke_Small_Dark`

---

## 交互状态

> 以「默认态」为基准，其他状态仅列出**发生变化**的属性。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态） | — |
| `selected` | 用户点击某一分段 | 选中项 `background-color` | `rgba(0,0,0,0.05)` / `rgba(255,255,255,0.12)` | `新增色彩变量/container_nav` |
| `selected` | 用户点击某一分段 | 选中文字 `font-weight` | 380~450（按变体） | `hyperos_font_weight_subtitle` / `hyperos_font_weight_subtitle2` |
| `disabled` | Figma 未定义 | — | Figma 未定义，请由设计团队补充 | — |
| `hover` | Figma 未定义 | — | Figma 未定义，请由设计团队补充 | — |
| `pressed` | Figma 未定义 | — | Figma 未定义，请由设计团队补充 | — |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

### Phone 端 SegmentedControls

```typescript
interface SegmentedControlsProps {
  /** 颜色模式，对应亮色/深色主题 */
  colorMode: '亮色模式' | '深色模式';
  /** 分段选项数量 */
  segmentCount: '2' | '3' | '4' | '5';
  /** 背景环境，影响底板材质和颜色 */
  backgroundEnv: '灰色背景' | '白色背景' | '彩色背景';
}
```

### 原子组件: 选项 (.选项)

```typescript
interface SegmentOptionProps {
  /** 选项类型：选中项 / 未选项 / 底板 */
  filterItem: '选中项' | '未选项' | '底板';
  /** 样式状态：平面（纯色背景）/ 浮起（毛玻璃背景） */
  style: '平面' | '浮起';
  /** 深色模式开关 */
  darkMode: 'light' | 'dark';
  /** 背景颜色模式 */
  bgColorMode: '灰背景' | '白背景' | '彩色背景';
}
```

### 材质板子

```typescript
interface MaterialPanelProps {
  /** 材质类型 */
  material: '混色模糊' | '纯色面板';
  /** 是否为深色模式 */
  darkMode: boolean; // 默认: false
}
```

### Pad 端

```typescript
interface SegmentedControlsPadProps {
  /** 分段选项数量（Pad 端以灰色背景为例） */
  segmentCount: '2' | '3' | '4' | '5';
}
```

### Figma 属性映射

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 颜色模式 | Variant | `colorMode` | `亮色模式` | 控制亮色/深色主题 |
| 个数 | Variant | `segmentCount` | `2` | 分段按钮中选项数量 |
| 背景环境 | Variant | `backgroundEnv` | `灰色背景` | 组件所处背景环境 |
| 筛选项 | Variant (选项) | `filterItem` | `选中项` | 选项类型 |
| 状态 | Variant (选项) | `style` | `平面` | 平面/浮起样式 |
| 深色模式 | Variant (选项/材质) | `darkMode` | `light` / `false` | 深色模式开关 |
| 背景颜色模式 | Variant (选项) | `bgColorMode` | `灰背景` | 选项的背景颜色模式 |
| 材质 | Variant (材质) | `material` | `混色模糊` | 毛玻璃/纯色面板 |

---

## 使用指南

### 何时使用

- **视图切换**：在同一页面内切换不同的内容视图（如「日/周/月」切换），使用 2~3 段分段按钮
- **筛选分类**：对内容进行快速分类筛选（如「全部/图片/视频/文档」），使用 3~5 段分段按钮
- **灰色背景页面**：大部分设置页面使用灰色背景变体
- **白色背景页面**：内容详情页等白色背景场景使用白色背景变体（带细描边区分层级）
- **彩色/渐变背景**：桌面小组件、锁屏等彩色背景场景使用毛玻璃材质变体

### 何时不使用

- **标签页导航**：如果需要在不同页面间切换且伴随页面跳转，应使用 TabBar 代替
- **单选按钮组**：如果选项之间是互斥的表单输入，应使用 RadioGroup 代替
- **操作按钮**：如果点击后触发操作而非切换视图，应使用 Button 代替
- **超过 5 个选项**：选项过多时，应使用 ScrollableTabBar 或 Dropdown 代替

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 每个分段使用简短文字（2~4 字） | 使用过长的标签文字 | 分段宽度等分，长文字会被截断 |
| 确保分段数量在 2~5 之间 | 使用 1 个或超过 5 个分段 | Figma 设计仅提供 2~5 段变体，超出范围无设计规范支撑 |
| 根据页面背景正确选择变体 | 在灰色背景上使用白色背景变体 | 会导致底板与页面背景混融，无法区分组件边界 |
| 在深色模式彩色背景使用 GlassEffect | 在深色模式使用 FrostEffect 亮色材质 | 亮色毛玻璃在深色环境下对比度不足 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `hyperos_theme_radius_medium` | `20px` | radius | 底板圆角 |
| `hyperos_theme_radius_common` | `16px` | radius | 选中项圆角 |
| `元素色/container_list` | `#FFFFFF`（亮色）/ `rgba(255,255,255,0.14)`（深色） | color | 底板背景色（灰/白背景） |
| `新增色彩变量/container_nav` | `rgba(0,0,0,0.05)`（亮色）/ `rgba(255,255,255,0.12)`（深色） | color | 选中项背景色、白背景底板描边色 |
| `文字图标色/on_Surface_button_disable` | `#FFFFFF` | color | 亮色白背景底板背景色 |
| `hyperos-color-on-surface` | `#000000`（亮色）/ `rgba(255,255,255,0.95)`（深色） | color | 选中/未选中文字色 |
| `hyperos-color-on-surface-tertiary` | `rgba(255,255,255,0.5)` | color | 深色模式下白/彩背景未选中文字色 |
| `hyperos_font_size_subtitle` | `14px` | font-size | 选中项文字字号 (Subtitle) |
| `hyperos_font_weight_subtitle` | `380` | font-weight | 选中项文字字重 (Medium) |
| `hyperos_font_size_subtitle2` | `14px` | font-size | 选中项文字字号 (Subtitle 2) |
| `hyperos_font_weight_subtitle2` | `450` | font-weight | 深色白/彩背景选中项字重 (Demibold) |
| `hyperos_font_size_subtitle3` | `14px` | font-size | 未选中文字字号 (Subtitle 3) |
| `hyperos_font_weight_subtitle3` | `330` | font-weight | 深色白/彩背景未选中文字字重 (Regular) |
| `Subtitle/Subtitle` | `MiSans Medium 14px / 100% / 0` | typography | 选中项文字样式（亮色全部、深色灰背景） |
| `Subtitle/Subtitle 2` | `MiSans Demibold 14px / 100% / 0` | typography | 选中项文字样式（深色白/彩背景） |
| `Subtitle/Subtitle 3` | `MiSans Regular 14px / 100% / 0` | typography | 未选中文字样式（深色白/彩背景） |
| `Pured/Pured_Thin_Glass_Light` | `#000000, #FFFFFF, #FFFFFF` | material | 亮色毛玻璃材质叠层颜色 |
| `Pured/Pured_Thin_Glass_Dark` | `#000000, #565656, #3F3F3F` | material | 深色毛玻璃材质叠层颜色 |
| `FrostShadow/FrostEffect_Thin_ShadowOn` | 见毛玻璃详细规范 | effect | 亮色毛玻璃阴影 + 模糊效果 |
| `GlassShadow (OS4禁用）/GlassEffect_Thin_ShadowOn` | 见毛玻璃详细规范 | effect | 深色毛玻璃阴影 + 玻璃效果 |

---

## 设计注释

> 1. Pad 端仅展示了灰色背景示例，宽度为 1137px，其他属性与 Phone 端一致。白色和彩色背景的 Pad 端规范请由设计团队补充。
> 2. 彩色背景变体使用毛玻璃材质（FrostEffect / GlassEffect），需要多层叠加实现，注意 `mix-blend-mode` 和 `backdrop-filter` 的浏览器兼容性。
> 3. 「材质板子」组件有「纯色面板」变体，用于非彩色背景场景，其背景色直接使用 `元素色/container_list` Token。
> 4. 交互状态（hover、pressed、disabled）在 Figma 中未定义，需要设计团队补充。
> 5. 选中项在深色+白色/彩色背景下使用更重的字重 (Demibold 450)，而未选中项使用更轻的字重 (Regular 330) 和更低透明度的文字色，以增强视觉对比。
> 6. 所有变体中，选中项与未选中项均使用等分宽度（`flex: 1 0 0`），文字超长时会触发 `text-overflow: ellipsis` 截断。
