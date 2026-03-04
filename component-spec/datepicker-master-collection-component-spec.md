---
component: DatePickerMasterCollection
description: HyperOS 4 日期选择器母组件集合展示帧，包含表头、滚轮选择器、月盘、月份切换器及原子选择器子组件
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=80745-353319&t=YpAk0BW0qD86pKHa-11
figma_node_id: "80745:353319"
variants: "展示帧，含多组子组件变体"
tokens_used: 16
---

# 日期选择器母组件集合 DatePickerMasterCollection

> Xiaomi HyperOS 4 设计系统中「日期选择器」相关的母组件集合展示帧。本节点为文档/展示用 FRAME，内含表头、滚轮选择器（WheelPicker）多种类型、月盘（5 行/6 行）、月份切换器（展开/收起）及原子选择器（年/月/日、上午/下午）等子组件，用于设计规范展示与开发对照。

## 预览

> 预览可通过 Figma MCP `get_screenshot` 获取，nodeId: `80745:353319`

![DatePicker 母组件集合预览](figma-node://80745:353319)

---

## 组件结构

```
❖ 母组件集合_勿动                                    // FRAME | 80745:353319
├── 表头_Component&Instance                            // INSTANCE | 80745:353320
├── DatePicker-Body-WheelPicker                        // FRAME | 54951:143108
│   ├── DatePicker-Body-WheelPicker-Columns            // SYMBOL | 54951:143054
│   ├── 类型=类型14, 行数=5 行                          // SYMBOL | 99369:1643
│   ├── 类型=上午, 行数=3 行                             // SYMBOL | 54951:143125
│   ├── 类型=类型13, 行数=5 行                          // SYMBOL | 99369:1647
│   ├── 类型=下午, 行数=3 行                             // SYMBOL | 54951:143172
│   ├── 类型=类型12, 行数=5 行                          // SYMBOL | 99369:1651
│   ├── 类型=年月, 行数=3 行                             // SYMBOL | 54951:143083
│   ├── 类型=类型11, 行数=5 行                          // SYMBOL | 99369:1655
│   ├── 类型=时分, 行数=3 行                             // SYMBOL | 54951:144569
│   ├── 类型=类型10, 行数=5 行                          // SYMBOL | 99369:1658
│   ├── 类型=数量, 行数=3 行                             // SYMBOL | 54951:143107
│   ├── 类型=类型9, 行数=5 行                           // SYMBOL | 99369:1661
│   ├── 类型=日期+时分, 行数=3 行                        // SYMBOL | 54951:143084
│   └── 类型=类型8, 行数=5 行                           // SYMBOL | 99369:1663
├── 月盘                                               // FRAME | 54951:145585
│   ├── Property 1=5行                                 // SYMBOL | 54900:142912
│   └── Property 1=6行                                 // SYMBOL | 54951:145584
├── DatePicker-Body-MonthSwitcher                      // FRAME | 54900:142785
│   ├── DatePicker-Body-MonthSwitcher-Container        // SYMBOL | 54900:142765
│   └── Property 1=展开                                // SYMBOL | 54900:142784
└── _原子组件_选择器                                    // FRAME | 54951:143033
    ├── DatePicker-Body-WheelPicker-YearColumn         // SYMBOL | 54900:141574
    ├── 内容=内容8, 行数=5 行                           // SYMBOL | 99369:8467
    ├── DatePicker-Body-WheelPicker-MonthColumn        // SYMBOL | 54900:141578
    ├── 内容=月份, 行数=5 行                            // SYMBOL | 99369:8472
    ├── DatePicker-Body-WheelPicker-DayColumn          // SYMBOL | 54951:143021
    ├── 内容=日, 行数=5 行                             // SYMBOL | 99369:8477
    ├── 内容=上午, 行数=小于 3 行专用                    // SYMBOL | 54900:141586
    └── 内容=下午, 行数=小于 3 行专用                    // SYMBOL | 54900:141590
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| 表头_Component&Instance | INSTANCE | `80745:353320` | 页面表头，含品牌与标题区 |
| DatePicker-Body-WheelPicker | FRAME | `54951:143108` | 滚轮选择器展示区，含多种类型（年月、年月日、日期+时分、时分、上午/下午、数量等） |
| 月盘 | FRAME | `54951:145585` | 月盘（日历）展示，含 5 行/6 行两种变体 |
| DatePicker-Body-MonthSwitcher | FRAME | `54900:142785` | 月份切换器展示，含默认与「展开」态 |
| _原子组件_选择器 | FRAME | `54951:143033` | 原子级滚轮列（年/月/日/上午/下午）展示 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器（母组件集合 FRAME）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `3014px` | — |
| `height` | `1698px` | — |
| `display` | 未定义 | — |
| `flex-direction` | — | — |
| `align-items` | — | — |
| `overflow` | 未定义 | — |

> 本节点为展示用画布，尺寸为内部子组件排布后的整体包围框。

### 子组件: 表头_Component&Instance

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `3014px` | — |
| `height` | `350px` | — |
| 说明 | 表头为 Instance，具体样式见设计稿 | — |

### 子组件: DatePicker-Body-WheelPicker（滚轮区容器）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `2912px` | — |
| `height` | `549px` | — |
| 说明 | 内含多组 368×198 / 368×240 的滚轮选择器符号 | — |

### 子组件: 滚轮列（COUINumberPicker 原子）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` / `stretch` | — |
| `gap` | `18px`（列内） | — |
| `padding` | `20px` 上下 | — |
| 列宽（年） | `56px` | — |
| 列宽（月） | `21px` | — |
| 列宽（日） | `31px` | — |
| 列宽（上午/下午） | `80px` | — |

### 子组件: 滚轮列文字

| 文字角色 | `font-size` | `color` | Token |
|---------|-------------|---------|-------|
| 列标题（年/月/日等） | `18px` | `rgba(0,0,0,0.4)` | `hyperos-color-on-surface-quaternary` |
| 未选中项 | `18px` | `rgba(0,0,0,0.6)` | `hyperos-color-on-surface-tertiary` |
| 选中项 | `24px` | `#3482FF` | `hyperos-color-primary` |
| 次要/上下项 | `14px` | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |

### 子组件: DatePicker-Body-MonthSwitcher（月份切换器）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `368px` | — |
| `height` | `24px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `space-between` | — |
| `padding` | `0 24px` | — |
| 标签字号 | `16px` | — |
| 标签颜色 | `#000000` | `hyperos-color-on-surface` |
| 图标颜色 | `rgba(0,0,0,0.6)` | `hyperos-color-on-surface-tertiary` |
| 按钮点击区域 | `20px × 20px` | — |

### 子组件: 月盘（日历）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| 单列宽度 | `368px` | — |
| 星期行高度 | `20px` | — |
| 星期行内边距 | `14px` 水平 | — |
| 星期文字 | `12px`，`rgba(0,0,0,0.6)` | `hyperos-color-on-surface-tertiary` |
| 日期行内边距 | `16px` 水平 | — |
| 日期格占位 | `44px × 44px` | — |
| 日期格内容区 | `35px × 35px` | — |
| 日期数字 | `18px`，`#000000` | `hyperos-color-on-surface` |
| 农历/辅助文字 | `10px`，`rgba(0,0,0,0.4)` | — |
| 选中格背景 | `#3482FF`，圆角 `8px` | `hyperos-color-primary`，`hyperos_theme_radius_tiny` |
| 选中格文字 | `18px`，`#FFFFFF` | `hyperos-color-on-primary` |
| 不可选日期 | `18px`，`rgba(0,0,0,0.12)` | — |
| 月盘 5 行 / 6 行 | `gap` 行间 `17px` | — |

### 文字样式汇总

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|---------|-----------|
| 标题/主标题 | MiSans | 18px | 380 | 100% | `#000000` | Title/Title 4 |
| 选中项（滚轮） | MiSans | 24px | 未定义 | normal | `#3482FF` | `hyperos-color-primary` |
| 月份标签 | MiSans Medium | 16px | 未定义 | 0 | `#000000` | `hyperos-color-on-surface` |
| 正文/未选中 | MiSans | 18px | 未定义 | normal | `rgba(0,0,0,0.6)` | `hyperos-color-on-surface-tertiary` |
| 次要/辅助 | MiSans | 14px | 未定义 | normal | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |
| 星期标题 | MiSans Regular | 12px | 未定义 | normal | `rgba(0,0,0,0.6)` | `hyperos-color-on-surface-tertiary` |
| 农历/辅助 | MiSans Regular | 10px | 未定义 | normal | `rgba(0,0,0,0.4)` | — |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 背景色 | `#FFFFFF` | `hyperos_color_surface` / `hyperos-color-surface` |
| 主色/选中 | `#3482FF` | `hyperos-color-primary` |
| 主色上文 | `#FFFFFF` | `hyperos-color-on-primary` |
| 主文字 | `#000000` | `hyperos-color-on-surface` |
| 次要文字 | `rgba(0,0,0,0.6)` / `#00000099` | `hyperos-color-on-surface-tertiary` |
| 四级文字 | `rgba(0,0,0,0.4)` / `#00000066` | `hyperos-color-on-surface-quaternary` |
| 八级/辅助 | `rgba(0,0,0,0.3)` / `#0000004d` | `hyperos-color-on-surface-octonary` |
| 禁用/弱化 | `rgba(0,0,0,0.12)` | — |
| 图标 | `#000000e5` | `var(--color-icon)` |

### 圆角与间距

| 用途 | 值 | Token |
|------|---|-------|
| 小圆角（选中格、小控件） | `8px` | `hyperos_theme_radius_tiny` |
| 中圆角 | `20px` | `hyperos_theme_radius_medium` / `radius-3xl` |
| 大圆角 | `36px` | `hyperos_theme_radius_big` |
| 滚轮列间距 | `18px` / `12px` / `8px` / `4px` | — |
| 月份切换器内边距 | `0 24px` | — |
| 月盘星期行 | `14px` 水平 | — |
| 月盘日期行 | `16px` 水平 | — |

---

## 变体

### 维度定义（本展示帧内涉及的子组件变体）

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 滚轮类型 | 类型 | 年月、日期+时分、时分、上午/下午、数量、类型8~14 等 | 滚轮列组合方式 |
| 行数 | 行数 | 3 行、5 行、小于 3 行专用 | 滚轮可见行数 |
| 月盘行数 | Property 1 | 5行、6行 | 日历显示 5 行或 6 行周 |
| 月份切换器 | Property 1 | 默认、展开 | 是否展示为展开态（双月份标签+箭头） |
| 内容 | 内容 | 内容8、月份、日、上午、下午 | 原子列内容类型 |

### 变体差异摘要

- **滚轮列**：列宽随内容类型变化（年 56px、月 21px、日 31px、上午/下午 80px）；选中项 24px + 主色，未选中 18px + 次要色。
- **月盘**：5 行与 6 行仅行数不同，6 行时含上月/下月占位格（DisabledCell），日期格 44×44、内容区 35×35，选中用主色+小圆角。
- **月份切换器**：展开态显示两处「2025/12」及箭头图标，布局为左右箭头+中间标签；收起态为单行 24px 高。

---

## 交互状态

> 以「默认态」为基准，其他状态仅列出**发生变化**的属性。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态） | — |
| 选中（滚轮） | 当前选中项 | `font-size`、`color` | `24px`、`#3482FF` | `hyperos-color-primary` |
| 选中（月盘格） | 当前选中日期 | `background-color`、`color`、`border-radius` | `#3482FF`、`#FFFFFF`、`8px` | `hyperos-color-primary`、`hyperos_theme_radius_tiny` |
| 不可选（月盘） | 非当月日期 | `color` | `rgba(0,0,0,0.12)` | — |
| 月份切换器-展开 | 展开态 | 布局双标签+箭头 | 见设计稿 | — |

Figma 中 hover/active/focus 等态未在本展示帧内单独定义，实现时可由设计团队补充。

---

## 组件 API

> 本节点为展示用 FRAME，无单一组件 API。以下为子组件原子（滚轮列、月份切换器）的 Props 归纳，供实现参考。

### 滚轮列（COUINumberPicker）

```typescript
interface WheelPickerColumnProps {
  /** 内容类型：年 / 月 / 日 / 上午 / 下午 等 */
  content?: '内容8' | '月份' | '日' | '上午' | '下午';
  /** 行数：5 行 或 小于 3 行专用 */
  rows?: '5 行' | '小于 3 行专用';
  /** 当前选中值（受控） */
  value?: string | number;
}
```

### 月份切换器

```typescript
interface DatePickerMonthSwitcherProps {
  /** 展开态：显示双月份标签 */
  property1?: '默认' | '展开';
  /** 当前年月，如 "2025/12" */
  label?: string;
}
```

### 月盘（日历）

```typescript
interface DatePickerCalendarProps {
  /** 5 行或 6 行周 */
  property1?: '5行' | '6行';
  /** 当前选中日期 */
  value?: Date;
  /** 是否显示农历等辅助信息 */
  showLunar?: boolean;
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 内容 | Variant | `content` | — | 滚轮列内容类型 |
| 行数 | Variant | `rows` | `5 行` | 滚轮可见行数 |
| Property 1（月盘） | Variant | `property1` | `5行` | 5 行 / 6 行 |
| Property 1（月份切换器） | Variant | `property1` | 默认 | 展开 / 收起 |

---

## 使用指南

### 何时使用

- 本节点为**设计规范展示帧**，用于查阅 DatePicker 相关子组件（滚轮、月盘、月份切换器、原子列）的尺寸、颜色与排版。
- 业务实现时应使用具体组件（如 DatePicker、WheelPicker、Calendar），并复制「场景实例」以保证与母组件一致。

### 何时不使用

- 不要将本 FRAME 作为可复用组件直接嵌入产品页面。
- 需要完整日期选择器能力时，应使用 DatePicker 组件（见 `datepicker-component-spec.md`），而非仅引用本展示帧。

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 按子组件（滚轮列、月盘、月份切换器）分别实现并复用 | 从本帧整帧导出为单一组件 | 本帧为展示用，非单一交互组件 |
| 使用文档中的 Token 与尺寸实现滚轮/月盘 | 自定颜色或字号 | 保证与 HyperOS 4 设计系统一致 |
| 滚轮选中项使用 24px + 主色 | 与未选中项同字号同色 | 选中态需明显区分 |
| 月盘选中格使用 8px 圆角 + 主色背景 | 使用直角或其它圆角 | 与设计系统 radius 规范一致 |

---

## 设计 Token 映射

> 该展示帧及子组件使用的设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `hyperos-color-primary` | `#3482FF` | color | 滚轮选中项、月盘选中格背景、主按钮等 |
| `hyperos-color-on-primary` | `#FFFFFF` | color | 选中格文字、主按钮文字 |
| `hyperos-color-on-surface` | `#000000` | color | 主文字、月份标签、日期数字 |
| `hyperos-color-on-surface-tertiary` | `#00000099` / `rgba(0,0,0,0.6)` | color | 未选中滚轮项、星期标题 |
| `hyperos-color-on-surface-quaternary` | `#00000066` / `rgba(0,0,0,0.4)` | color | 列标题、农历等 |
| `hyperos-color-on-surface-octonary` | `#0000004d` / `rgba(0,0,0,0.3)` | color | 次要辅助文字 |
| `hyperos_color_surface` / `hyperos-color-surface` | `#FFFFFF` | color | 背景 |
| `hyperos_theme_radius_tiny` | `8px` | radius | 选中日期格、小控件圆角 |
| `hyperos_theme_radius_medium` | `20px` | radius | 中等圆角 |
| `hyperos_theme_radius_big` | `36px` | radius | 大圆角（如弹层） |
| `hyperos_font_size_title4` | `18` | font-size | 标题/主文案 |
| `hyperos_font_weight_title4` | `380` | font-weight | 标题字重 |
| `Title/Title 4` | MiSans, 18px, weight 380, lineHeight 100% | typography | 标题样式 |
| `var(--color-icon)` | `#000000e5` | color | 图标色 |
| `spacing-xl` | `16` | spacing | 间距参考 |
| `radius-3xl` | `20` | radius | 与 medium 对应 |

---

## 设计注释

- 由设计系统团队维护的 Components 组件合集，业务使用请复制场景实例，效果与母组件一致。
- 组件使用中若发现问题可飞书联系 @设计系统小组。
- 滚轮列原子（年/月/日/上午/下午）在 Figma 中标注为 COUINumberPicker，实现时需保证列宽、字号、颜色与本文档一致。
- 月盘 6 行时首尾周可能包含上月/下月的灰色日期格（DisabledCell），需单独样式与不可选交互。
