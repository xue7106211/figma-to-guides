---
component: GraphicSelect
description: 小米 HyperOS4 图形选择控件，通过带预览图的选项卡片让用户在多个功能设置中进行可视化选择
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=82713-133049
figma_node_id: "82713:133049"
variants: "单项组件 5 dimensions (~160+ variants); 布局组件 5 dimensions (24 variants)"
tokens_used: 14
---

# 图形选择 GraphicSelect

> HyperOS4 系统级图形选择控件，用于在系统设置中通过带预览图的选项卡片让用户进行可视化选择（如导航方式、深浅模式、桌面模式、铃声选择等）。选中项以蓝色边框高亮，未选中项无边框。支持单行和宫格两种布局模式，适配 Phone / Fold / Pad 横屏 / Pad 竖屏四种设备尺寸。

## 预览

![图形选择组件全部变体预览 - 单项](http://localhost:3845/figma/screenshot/37717:109834)

![图形选择组件全部变体预览 - 布局](http://localhost:3845/figma/screenshot/37356:114791)

---

## 组件结构

本组件由**两层**构成：**单项选项图**（功能操作选项图）和**布局容器**（.功能操作选项图）。

```
图形选择 Select                                    // FRAME | 82713:133049
├── 表头_Component&Instance                        // INSTANCE | 82713:133050
├── 功能操作选项图（单项组件集）                     // FRAME | 37717:109834
│   ├── [单项] 设备=Phone, 设置项=*, 选项=*, 状态=选中/未选中, 高度=*
│   │   ├── light（图片容器）                       // FRAME
│   │   │   └── 内容                               // FRAME
│   │   │       ├── 背景                           // FRAME (渐变/图片)
│   │   │       └── [内容元素]                      // FRAME / TEXT / INSTANCE
│   │   └── [选项文字标签]                          // TEXT
│   ├── [单项] 设备=Fold, ...
│   ├── [单项] 设备=Pad横屏, ...
│   └── [单项] 设备=Pad竖屏, ...
└── .功能操作选项图（布局容器集）                    // FRAME | 37356:114791
    ├── 适配端=Phone, 布局=单行, 选项数量=2, 是否套卡=off
    │   ├── 功能操作选项图（选项1）                  // INSTANCE
    │   └── 功能操作选项图（选项2）                  // INSTANCE
    ├── 适配端=Phone, 布局=宫格, 选项数量=4, ...
    │   ├── [行1]                                  // FRAME
    │   │   ├── 功能操作选项图（选项1）              // INSTANCE
    │   │   └── 功能操作选项图（选项2）              // INSTANCE
    │   └── [行2]                                  // FRAME
    │       ├── 功能操作选项图（选项3）              // INSTANCE
    │       └── 功能操作选项图（选项4）              // INSTANCE
    └── ...
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| 功能操作选项图（单项集） | FRAME | `37717:109834` | 包含所有单项变体的集合 |
| .功能操作选项图（布局集） | FRAME | `37356:114791` | 包含所有布局变体的集合 |
| light（图片容器） | FRAME | 各变体内部 | 选项卡片的图片区域，选中态有蓝色边框 |
| 内容 | FRAME | 各变体内部 | 预览内容区域，包含背景和示意元素 |
| 背景 | FRAME | 各变体内部 | 预览背景，可能是渐变色或图片 |
| 选项文字标签 | TEXT | 各变体内部 | 卡片下方的选项名称文字 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 单项选项图 — 外层容器

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `flex-start` | — |
| `gap` | `8px` | — |

#### 宽度按设备适配

| 设备 | `width` |
|------|---------|
| Phone（Large / Medium） | `182px` |
| Phone（Small） | `120px` |
| Phone（带图片的铃声/提醒） | `184px` |
| Fold | `185px` ～ `188px` |
| Pad 横屏 | `347px` |
| Pad 竖屏 | `200px` |

### 单项选项图 — 图片容器 light

| CSS 属性 | 值（选中态） | 值（未选中态） | Token |
|---------|------------|-------------|-------|
| `display` | `flex` | `flex` | — |
| `flex-direction` | `column` | `column` | — |
| `align-items` | `center` | `center` | — |
| `justify-content` | `center` | `center` | — |
| `padding` | `6px` | `6px` | — |
| `overflow` | `hidden` | `hidden` | — |
| `border-width` | `3px` | `0` | — |
| `border-style` | `solid` | — | — |
| `border-color` | `#3482FF` | — | `miuix_default_color_primary` |
| `border-radius` | `22px` | `20px` | — |
| `width` | `100%` | `100%` | — |

#### 图片容器高度按「高度」维度

| 高度值 | `height` |
|-------|---------|
| Large | `311px`（Phone）/ `235px`（Fold）/ `255px`（Pad 横屏）/ `151px`（Pad 竖屏） |
| Medium | `182px`（Phone 深浅模式等）/ `211px`（Phone 通知样式等）/ `240px`（铃声选项） |
| Small | 等同 Phone 桌面模式 |
| 自定义 | 按设置项内容自适应 |

### 单项选项图 — 内容区域

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex` | `1 0 0` | — |
| `border-radius` | `16px` | `miuix_theme_radius_common` |
| `width` | `100%` | — |
| `position` | `relative` | — |
| `min-height` | `1px` | — |

### 单项选项图 — 背景

背景有两种模式：

**纯色渐变（系统功能类选项）：**

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `position` | `absolute` | — |
| `inset` | `0` | — |
| `border-radius` | `16px` | `miuix_theme_radius_common` |
| `background` | `linear-gradient(to bottom, #4170FF, #5ABAFF)` | — |

**图片背景（铃声/提醒类选项）：**

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `position` | `absolute` | — |
| `inset` | `0` | — |
| `border-radius` | `16px` | `miuix_theme_radius_common` |
| `overflow` | `hidden` | — |
| `background` | 内嵌图片（object-fit: cover） | — |

### 单项选项图 — 内容元素（线框示意）

系统功能类预览使用半透明毛玻璃元素：

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `background-color` | `rgba(255, 255, 255, 0.25)` | — |
| `backdrop-filter` | `blur(14.979px)` | — |
| `border-radius` | `5px` ～ `7px`（按元素尺寸） | — |

### 单项选项图 — "按钮"类型

铃声设置中的「全部铃声」入口使用特殊的按钮样式：

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `background-color` | `#3482FF` | `miuix_default_color_primary` |
| `border-radius` | `16px` | `miuix_theme_radius_common` |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `gap` | `8px` | — |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| 选项标签（选中） | MiSans | 16px | 500 (Medium) | normal | 0 | `#3482FF` | `miuix_default_color_primary` |
| 选项标签（未选中） | MiSans | 16px | 500 (Medium) | normal | 0 | `rgba(0,0,0,0.8)` | `miuix_default_color_on_surface_secondary` |
| 预览内文字（时间） | MiSans | 24px | 600 (Demibold) | normal | 0 | `#FFFFFF` | — |
| 预览内文字（铃声名） | MiSans | 17px | 500 (Medium) | normal | 0 | `#FFFFFF` | — |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 选中边框 / 选中文字 / 按钮背景 | `#3482FF` | `miuix_default_color_primary` |
| 未选中文字 | `rgba(0,0,0,0.8)` | `miuix_default_color_on_surface_secondary` |
| 预览背景（渐变起点） | `#4170FF` | — |
| 预览背景（渐变终点） | `#5ABAFF` | — |
| 预览内元素 | `rgba(255,255,255,0.25)` | — |
| 容器背景色 | `#FFFFFF` | `miuix_default_color_surface` |
| 文字主色 | `#000000` | `miuix_default_color_on_surface` |

---

## 变体

### 维度定义

#### 单项组件（功能操作选项图）

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 设备 | `设备` | `Phone` / `Fold` / `Pad横屏` / `Pad竖屏` | 控制卡片宽高和内容排版 |
| 设置项 | `设置项` | `最近任务样式` / `系统导航方式` / `深浅模式` / `通知样式设置` / `隐藏屏幕刘海` / `桌面模式` / `全面屏键盘优化` / `安全键盘` / `通知提醒` / `电话铃声` / `闹钟铃声` / `关机设置` | 决定预览图内容 |
| 选项 | `选项` | 33 种选项值（按设置项不同而变化） | 具体的选择项名称 |
| 状态 | `状态` | `选中` / `未选中` / `按钮` | 选中显示蓝色边框，未选中无边框 |
| 高度 | `高度` | `Large` / `Medium` / `Small` / `自定义` | 控制卡片高度 |

#### 布局组件（.功能操作选项图）

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 适配端 | `适配端` | `Phone` / `Fold` / `Pad横屏` / `Pad竖屏` | 控制布局容器宽度 |
| 布局 | `布局` | `单行` / `宫格` | 单行水平排列 / 宫格多行排列 |
| 选项数量 | `选项数量` | `2` / `3` / `4` / `6` | 布局中包含的选项卡片数量 |
| 是否套卡 | `是否套卡` | `on` / `off` | 是否包含外层卡片包裹 |
| 适配方式 | `适配方式` | `端比例适配` / `等高适配` | 端比例按设备屏幕比例缩放 / 等高统一高度 |

### 变体差异表

#### 按设备分组 — 容器宽度差异

| 属性 | `Phone` | `Fold` | `Pad横屏` | `Pad竖屏` |
|-----|---------|--------|----------|----------|
| 布局容器 `width` | `392px` | `411px` | `718px` | `424px` |
| 单项 `width`（默认） | `182px` | `185px` | `347px` | `200px` |

#### 按状态分组 — 选中 vs 未选中差异

| 属性 | `选中` | `未选中` | `按钮` |
|-----|--------|---------|--------|
| 图片容器 `border-width` | `3px` | `0` | `0` |
| 图片容器 `border-color` | `#3482FF` | — | — |
| 图片容器 `border-radius` | `22px` | `20px` | `20px` |
| 标签文字 `color` | `#3482FF` | `rgba(0,0,0,0.8)` | 无标签 |
| 内容背景 | 按设置项渐变/图片 | 同选中态 | 纯色 `#3482FF` |

#### 按高度分组 — Phone 设备高度差异

| 属性 | `Large` | `Medium` | `Small` |
|-----|---------|----------|---------|
| 图片容器 `height` | `311px` ～ `340px` | `182px` ～ `240px` | 按内容自适应 |
| 单项 `width` | `182px` | `182px` ～ `184px` | `120px` |
| 用途 | 系统导航/最近任务 | 深浅模式/铃声等 | 桌面模式 |

#### 按布局分组 — 单行 vs 宫格差异

| 属性 | `单行` | `宫格` |
|-----|--------|--------|
| `flex-direction`（外层） | `row` | `column` |
| `padding`（外层） | `12px 8px`（水平/垂直） | `0` |
| `gap`（外层） | `4px` | `4px` |
| 行内 `gap` | — | `4px` |
| 行内 `padding` | — | `0 12px` |
| 选项排列 | 单行全部水平排列 | 每行 2 个，多行垂直排列 |

### 设备=Phone, 布局=单行, 选项数量=2 详情

![Phone 单行 2 选项布局](http://localhost:3845/figma/screenshot/37356:114792)

### 设备=Phone, 布局=宫格, 选项数量=4 详情

![Phone 宫格 4 选项布局](http://localhost:3845/figma/screenshot/37356:114808)

### 单项：Phone, 深浅模式, 浅色模式, 选中, Medium

![单项选中态](http://localhost:3845/figma/screenshot/37717:109835)

---

## 交互状态

> 以「选中态」为基准，其他状态仅列出**发生变化**的属性。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `选中 (selected)` | 用户点击选项 | — | （基准状态）蓝色边框 + 蓝色文字 | `miuix_default_color_primary` |
| `未选中 (unselected)` | 非当前选中项 | `border-width` | `0`（无边框） | — |
| | | `border-radius` | `20px`（图片容器） | `miuix_theme_radius_medium` |
| | | 标签 `color` | `rgba(0,0,0,0.8)` | `miuix_default_color_on_surface_secondary` |
| `按钮 (button)` | 特定入口（全部铃声） | `background-color` | `#3482FF`（纯色背景） | `miuix_default_color_primary` |
| | | 内容 | 图标 + 文字居中 | — |
| `hover` | Figma 未定义 | — | Figma 未定义，请由设计团队补充 | — |
| `active` | Figma 未定义 | — | Figma 未定义，请由设计团队补充 | — |
| `disabled` | Figma 未定义 | — | Figma 未定义，请由设计团队补充 | — |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

### 单项组件

```typescript
interface GraphicSelectItemProps {
  /** 设备类型，控制卡片尺寸和内容适配 */
  device: 'Phone' | 'Fold' | 'Pad横屏' | 'Pad竖屏';
  /** 设置项类别，决定预览图内容 */
  settingType:
    | '最近任务样式' | '系统导航方式' | '深浅模式' | '通知样式设置'
    | '隐藏屏幕刘海' | '桌面模式' | '全面屏键盘优化' | '安全键盘'
    | '通知提醒' | '电话铃声' | '闹钟铃声' | '关机设置';
  /** 选项名称 */
  option: string;
  /** 选中状态 */
  state: '选中' | '未选中' | '按钮';
  /** 卡片高度模式 */
  height: 'Large' | 'Medium' | 'Small' | '自定义';
}
```

### 布局组件

```typescript
interface GraphicSelectLayoutProps {
  /** 设备类型 */
  device: 'Phone' | 'Fold' | 'Pad横屏' | 'Pad竖屏';
  /** 布局模式 */
  layout: '单行' | '宫格';
  /** 选项数量 */
  optionCount: 2 | 3 | 4 | 6;
  /** 是否有外层卡片包裹 */
  hasCard?: boolean; // 默认: false
  /** 适配方式 */
  adaptMode: '端比例适配' | '等高适配';
}
```

### Figma 属性映射

**单项组件：**

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 设备 | Variant | `device` | `Phone` | 设备适配类型 |
| 设置项 | Variant | `settingType` | `最近任务样式` | 预览内容类型 |
| 选项 | Variant | `option` | `纵向排布` | 选项名称 |
| 状态 | Variant | `state` | `选中` | 选中/未选中/按钮 |
| 高度 | Variant | `height` | `Large` | 卡片高度预设 |

**布局组件：**

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 适配端 | Variant | `device` | `Phone` | 设备适配类型 |
| 布局 | Variant | `layout` | `单行` | 单行/宫格 |
| 选项数量 | Variant | `optionCount` | `2` | 选项卡片数量 |
| 是否套卡 | Boolean | `hasCard` | `off` (false) | 外层卡片包裹 |
| 适配方式 | Variant | `adaptMode` | `端比例适配` | 尺寸适配策略 |

---

## 使用指南

### 何时使用

- **系统功能设置**：如导航方式（全面屏手势 / 经典模式）、最近任务样式、深浅模式切换等，使用「系统功能类」预览图（渐变背景 + 线框示意），高度选择 `Large` 或 `Medium`
- **铃声/提醒选择**：如电话铃声、闹钟铃声、通知提醒等，使用「图片背景类」预览图，高度选择 `Medium`（240px），布局使用 `宫格` 模式
- **键盘布局选择**：如安全键盘、全面屏键盘优化等，使用「线框示意」预览图，高度选择 `自定义`
- **多设备适配**：需要在 Phone / Fold / Pad 横屏 / Pad 竖屏上展示时，使用对应的 `适配端` 变体

### 何时不使用

- **简单开关切换**：应使用 Switch 组件代替
- **纯文本列表选择**：应使用 RadioGroup 或 Actionsheet 组件代替
- **滑动数值选择**：应使用 Slider 组件代替
- **没有可视化预览内容的选项**：不适合使用本组件

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 选项间使用 4px 间距 | 使用过大间距或无间距 | 保持视觉统一和紧凑感 |
| 选中态使用 3px 蓝色边框 | 使用背景色或其他方式标识选中 | 与 HyperOS4 设计语言一致 |
| 预览图内容应真实反映选项效果 | 使用占位图或无关图片 | 帮助用户做出有效的可视化选择 |
| 布局超过 2 个选项时使用宫格模式 | 在单行中放置过多选项 | 避免横向滚动，保证可读性 |
| Pad 设备使用相应适配尺寸 | Phone 尺寸直接在 Pad 上使用 | 充分利用大屏空间 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `miuix_default_color_primary` | `#3482FF` | color | 选中边框、选中文字、按钮背景 |
| `miuix_default_color_on_surface` | `#000000` | color | 主文字色 |
| `miuix_default_color_on_surface_secondary` | `rgba(0,0,0,0.8)` | color | 未选中标签文字 |
| `miuix_default_color_on_surface_quaternary` | `rgba(0,0,0,0.4)` | color | 辅助文字 |
| `miuix_default_color_on_surface_octonary` | `rgba(0,0,0,0.3)` | color | 弱辅助文字 |
| `miuix_default_color_surface` | `#FFFFFF` | color | 容器背景 |
| `miuix_default_color_surface_low` | `#F3F3F3` | color | 低层级表面色 |
| `miuix_theme_radius_big` | `36px` | radius | 大圆角（特殊场景） |
| `miuix_theme_radius_medium` | `20px` | radius | 未选中图片容器圆角 |
| `miuix_theme_radius_common` | `16px` | radius | 内容区域圆角 |
| `miuix_theme_radius_small` | `12px` | radius | 小圆角元素 |
| `radius-3xl` | `20px` | radius | 3XL 级圆角 |
| `spacing-xl` | `16px` | spacing | XL 级间距 |
| `Blur-M` | `40px` | effect | 中等模糊半径 |

---

## 设计注释

> 1. **两层组件架构**：单项选项图定义每个卡片的样式和内容，布局容器控制多个卡片的排列方式。开发时应将两者分别实现为独立组件，布局组件通过 children 或 slot 方式消费单项组件。
> 2. **预览图内容为装饰性**：线框示意图和图片背景仅用于帮助用户理解选项含义，不需要在代码中完全还原 Figma 中的每个装饰元素，可使用静态图片资源替代。
> 3. **选中态边框吃入空间**：选中态的 3px 边框会增加 `border-radius` 从 20px 变为 22px（20px + padding 调整），以保持内容区域视觉上与未选中态一致。
> 4. **毛玻璃效果**：预览内的半透明元素使用 `backdrop-filter: blur(14.979px)` 和 `background: rgba(255,255,255,0.25)` 实现毛玻璃质感。
> 5. **设备适配为同一组件的不同 breakpoint**：实际开发中 `设备` 维度应通过响应式布局实现，而非创建独立组件。
> 6. **「是否套卡」维度**：当 `是否套卡=on` 时，整个选项组被包裹在一个卡片容器中，带有额外的 padding 和背景。
> 7. **该组件包含大量设置项和选项的排列组合**，实际开发时建议抽象为数据驱动的通用组件，通过 props 传入预览图 / 图标 / 文字等内容，而非为每种设置项硬编码变体。
