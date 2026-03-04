---
component: DatePicker
description: HyperOS 4 日期选择器组件，提供月盘视图（日历）和滚筒视图（滚轮）两种模式，支持农历显示、配置项和多种日期行数
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=80359-19892
figma_node_id: "80359:19892"
variants: "4 dimensions, 11 variants"
tokens_used: 16
---

# 日期选择器 DatePicker

> HyperOS 4 设计系统中的日期选择器组件，提供月盘视图（Calendar）和滚筒视图（WheelPicker）两种交互模式。月盘视图支持按月浏览日历并点选日期，可选显示农历；滚筒视图通过滚轮列选择年/月/日或时/分。两种模式均可附加配置项（日期与时间显示、重复提醒等），底部统一配置取消/确认按钮。

## 预览

> 截图通过 Figma MCP `get_screenshot` 获取，nodeId: `41719:88341`

![DatePicker 全部变体预览](figma-node://41719:88341)

---

## 组件结构

```
❖ 母组件集合_勿动                                       // FRAME | 80359:19892
├── 表头_Component&Instance                             // INSTANCE | 80359:23704
└── 变体                                                // FRAME | 80359:19914
    ├── DatePicker                                      // FRAME | 80359:105140
    ├── 日期选择器/玻璃材质(OS4禁用)                       // COMPONENT | 80359:105139
    └── DatePicker-Showcase-Content                     // FRAME | 41719:88341
        ├── 模式=月盘视图, 状态=今天选中态, 类型=无配置项, 日期行数=6行   // COMPONENT | 41719:88655
        ├── 模式=月盘视图, 状态=今天选中态, 类型=无配置项, 日期行数=5行   // COMPONENT | 53954:22139
        ├── 模式=月盘视图, 状态=今天选中态, 类型=无配置项, 日期行数=4行   // COMPONENT | 55177:8927
        ├── 模式=滚筒视图, 状态=今天选中态, 类型=无配置项, 日期行数=未定义 // COMPONENT | 41719:88342
        ├── 模式=滚筒视图, 状态=不可选日期, 类型=无配置项, 日期行数=未定义 // COMPONENT | 41719:88422
        ├── 模式=月盘视图, 状态=今天选中态, 类型=有农历, 日期行数=未定义   // COMPONENT | 41719:88770
        ├── 模式=月盘视图, 状态=今天选中态, 类型=无农历, 日期行数=未定义   // COMPONENT | 74814:11120
        ├── 模式=滚筒视图, 状态=时间选中态, 类型=有配置项, 日期行数=未定义 // COMPONENT | 41719:88585
        ├── 模式=月盘视图, 状态=今天选中态, 类型=有配置项, 日期行数=未定义 // COMPONENT | 41719:88896
        ├── 模式=滚筒视图, 状态=不可选日期, 类型=有配置项, 日期行数=未定义 // COMPONENT | 41719:88502
        └── 模式=滚筒视图, 状态=不可选日期, 类型=无农历, 日期行数=未定义   // COMPONENT | 74814:11186
```

### 内部层级（单个变体）

以默认变体「月盘视图, 今天选中态, 无配置项, 6行」为例：

```
DatePicker                                              // COMPONENT | 41719:88655
├── DatePicker-Header                                   // FRAME | 41719:88656
│   ├── DatePicker-Header-TitleContainer                // FRAME | 41719:88657
│   │   └── Title (TEXT: "标题")                         // TEXT | 41719:88658
│   └── DatePicker-Header-Divider                       // FRAME | 41719:88659
│       └── Divider SVG                                 // IMAGE
├── DatePicker-Body                                     // FRAME | 41719:88661
│   ├── DatePicker-Body-MonthSwitcher                   // INSTANCE | 54900:142765
│   │   ├── DatePicker-Body-MonthSwitcher-PrevButton    // FRAME | 54900:142757
│   │   ├── DatePicker-Body-MonthSwitcher-Label         // FRAME | 54900:142759
│   │   │   ├── Label Text (TEXT: "2025/12")            // TEXT | 54900:142760
│   │   │   └── DatePicker-Body-MonthSwitcher-Label-CaretIcon // FRAME | 54900:142761
│   │   └── DatePicker-Body-MonthSwitcher-NextButton    // FRAME | 54900:142762
│   └── DatePicker-Body-Calendar                        // INSTANCE | 54951:145906
│       ├── DatePicker-Body-Calendar-WeekHeader          // FRAME
│       │   └── Mon~Sun (一~日)                          // TEXT × 7
│       ├── DatePicker-Calendar-Week-1                   // FRAME
│       │   └── DateCells × 7                            // FRAME (含 DisabledCell / SelectedCell / DefaultCell)
│       ├── DatePicker-Calendar-Week-2 ~ Week-6          // FRAME × 5
│       │   └── DateCells × 7                            // FRAME
└── DatePicker-Footer                                   // FRAME | 41719:88768
    └── DatePicker-Footer-ActionGroup                   // FRAME | 41719:88769
        ├── DatePicker-Footer-Button-Cancel              // INSTANCE | I41719:88769;5580:1318
        └── DatePicker-Footer-Button-Confirm-Primary     // INSTANCE | I41719:88769;5580:1320
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| DatePicker-Header | FRAME | `41719:88656` | 标题区域，包含标题文字和分割线 |
| DatePicker-Header-TitleContainer | FRAME | `41719:88657` | 标题容器，居中对齐 |
| DatePicker-Header-Divider | FRAME | `41719:88659` | 渐变分割线，高度 20px，SVG 实现 |
| DatePicker-Body | FRAME | `41719:88661` | 主体区域，包含月份切换器 + 日历/滚轮 |
| DatePicker-Body-MonthSwitcher | INSTANCE | `54900:142765` | 月份切换器，含前/后按钮和月份标签 |
| DatePicker-Body-Calendar | INSTANCE | `54951:145906` | 日历面板，含星期行和日期网格 |
| DatePicker-Body-Calendar-WeekHeader | FRAME | 实例内部节点 | 星期行标题（一~日） |
| DatePicker-Footer | FRAME | `41719:88768` | 底部按钮区域 |
| DatePicker-Footer-ActionGroup | FRAME | `41719:88769` | 操作按钮组（取消 + 确认） |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器（DatePicker 整体）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `368px` | — |
| `height` | `auto`（hug） | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `gap` | `16px` | — |
| `padding` | `24px 0` | — |
| `border-radius` | `36px` | `hyperos_theme_radius_big` |
| `background-color` | 未显式定义（继承页面背景 `#FFFFFF`） | `hyperos-color-surface-high` |

### 子组件: DatePicker-Header（标题区域）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `gap` | `6px` | — |
| `align-items` | `flex-start` | — |
| `width` | `100%`（stretch） | — |

#### 标题容器 DatePicker-Header-TitleContainer

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `padding` | `0 166px` | — |
| `width` | `100%`（stretch） | — |

#### 分割线 DatePicker-Header-Divider

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%` | — |
| `height` | `20px` | — |
| 内容 | SVG 渐变线条 | — |

### 子组件: DatePicker-Body-MonthSwitcher（月份切换器）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `368px` | — |
| `height` | `24px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `space-between` | — |
| `padding` | `0 24px` | — |

#### 切换按钮（PrevButton / NextButton）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `20px` | — |
| `height` | `20px` | — |
| 图标字体 | `HyperOS Symbols` | — |
| `font-weight` | `Heavy` | — |
| `font-size` | `9px` | — |
| `color` | `rgba(0,0,0,0.6)` | `hyperos-color-on-surface-tertiary` |

#### 月份标签 DatePicker-Body-MonthSwitcher-Label

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `gap` | `4px` | — |
| `align-items` | `center` | — |
| `font-family` | `MiSans` | — |
| `font-weight` | `Medium` | — |
| `font-size` | `16px` | — |
| `color` | `#000000` | `hyperos-color-on-surface` |
| `text-align` | `center` | — |
| `white-space` | `nowrap` | — |

### 子组件: DatePicker-Body-Calendar（月盘日历面板）

#### 容器

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `368px` | — |
| `height` | `332px`（6 行）/ `auto`（5 行 / 4 行） | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `gap` | `18px` | — |
| `align-items` | `flex-start` | — |

#### 星期行 Calendar-WeekHeader

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `height` | `20px` | — |
| `padding` | `0 14px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `width` | `100%` | — |

#### 星期单元格（一~日）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `flex` | `1 0 0` | — |
| `padding` | `2px 10px` | — |
| `text-align` | `center` | — |
| `font-family` | `MiSans` | — |
| `font-weight` | `Regular` | — |
| `font-size` | `13px` | — |
| `color` | `rgba(0,0,0,0.6)` | `hyperos-color-on-surface-tertiary` |

#### 日期网格行 Calendar-Week-Row

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `padding` | `0 16px` | — |
| `display` | `flex` | — |
| `justify-content` | `space-between` | — |
| `align-items` | `center` | — |
| `width` | `100%` | — |

#### 日期单元格 Calendar-DateCell（外层容器）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `44px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |

#### 日期内容块（35×35px 内部方块）

| 状态 | `background-color` | `border-radius` | `font-size` | `color` | Token |
|-----|-------------------|-----------------|-------------|---------|-------|
| DefaultCell（当月普通日期） | 透明 | — | `18px` | `#000000` | `hyperos-color-on-surface` |
| SelectedCell（选中日期） | `#3482FF` | `8px` | `18px` | `#FFFFFF` | `hyperos-color-primary` / `hyperos-color-on-primary` / `hyperos_theme_radius_tiny` |
| DisabledCell（跨月日期） | 透明 | — | `18px` | `rgba(0,0,0,0.12)` | — |
| EmptyCell（空白占位） | 透明 | — | — | — | — |

日期内容块通用属性：

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `35px` | — |
| `height` | `35px` | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `font-family` | `MiSans` | — |
| `font-weight` | `Regular` | — |
| `text-align` | `center` | — |

### 子组件: DatePicker-Body-WheelPicker（滚筒滚轮选择器）

#### 容器

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `368px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `gap` | `60px` | — |
| `font-family` | `MiSans` | — |
| `font-weight` | `Medium` | — |
| `text-align` | `center` | — |

#### 原子选择列

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `gap` | `18px` | — |
| `padding` | `20px 0` | — |

#### 选择列宽度

| 内容类型 | `width` |
|---------|---------|
| 年（Year） | `56px` |
| 月（Month） | `21px` |
| 日（Day） | `31px` |

#### 滚轮项文字样式

| 项目位置 | `font-size` | `color` | Token |
|---------|-------------|---------|-------|
| 选中项 | `24px` | `#3482FF` | `hyperos-color-primary` |
| 相邻项 | `18px` | `rgba(0,0,0,0.6)` | `hyperos-color-on-surface-tertiary` |
| 远端项（5 行模式） | `14px` | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |
| 列标题（年/月/日） | `18px` | `rgba(0,0,0,0.4)` | `hyperos-color-on-surface-quaternary` |

### 子组件: DatePicker-Footer（底部操作区）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `padding` | `8px 24px 0` | — |
| `overflow` | `clip` | — |
| `width` | `100%` | — |

#### 操作按钮组 DatePicker-Footer-ActionGroup

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `gap` | `12px` | — |
| `width` | `100%` | — |

#### 取消按钮 DatePicker-Footer-Button-Cancel

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `flex` | `1 0 0` | — |
| `max-width` | `336px` | — |
| `padding` | `13.5px 20px` | — |
| `background-color` | `rgba(0,0,0,0.06)` | `hyperos-color-tertiary` |
| `border-radius` | `16px` | `hyperos_theme_radius_common` |
| `font-family` | `MiSans` | — |
| `font-weight` | `Medium` | — |
| `font-size` | `17px` | `Size/Button` |
| `color` | `rgba(0,0,0,0.8)` | `hyperos-color-on-tertiary` |
| `text-align` | `center` | — |
| `text-overflow` | `ellipsis` | — |
| `white-space` | `nowrap` | — |
| `overflow` | `hidden` | — |

#### 确认按钮 DatePicker-Footer-Button-Confirm-Primary

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `flex` | `1 0 0` | — |
| `max-width` | `336px` | — |
| `height` | `50px` | — |
| `padding` | `8px 20px` | — |
| `background-color` | `#3482FF` | `hyperos-color-primary` |
| `border-radius` | `16px` | `hyperos_theme_radius_common` |
| `font-family` | `MiSans` | — |
| `font-weight` | `Medium` | — |
| `font-size` | `17px` | `Size/Button` |
| `color` | `#FFFFFF` | `hyperos-color-on-primary` |
| `text-align` | `center` | — |
| `text-overflow` | `ellipsis` | — |
| `white-space` | `nowrap` | — |
| `overflow` | `hidden` | — |

### 子组件: DatePicker-Header 扩展区域（有配置项 / 有农历时显示）

当 `类型` 为 `有配置项`、`有农历` 或 `无农历` 时，Header 区域会增加额外的配置行。

#### 日期与时间行

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `space-between` | — |
| `padding` | `0 24px` | — |

日期标签（pill 形状）：

| CSS 属性 | 值（选中态） | 值（默认态） | Token |
|---------|-----------|-----------|-------|
| `background-color` | `#3482FF` | `rgba(0,0,0,0.06)` | `hyperos-color-primary` / `hyperos-color-tertiary` |
| `color` | `#FFFFFF` | `#000000` | `hyperos-color-on-primary` / `hyperos-color-on-surface` |
| `border-radius` | `16px` | `16px` | `hyperos_theme_radius_common` |
| `padding` | `4px 12px` | `4px 12px` | — |

#### 农历开关行（有农历变体）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `space-between` | — |
| `padding` | `0 24px` | — |

#### 重复提醒行（有配置项变体）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `space-between` | — |
| `padding` | `0 24px` | — |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| 标题 | MiSans | 18px | Medium (380) | 100% | 0 | `#000000` | `hyperos_font_size_title4` / `hyperos_font_weight_title4` |
| 月份标签 | MiSans | 16px | Medium | 100% | 0 | `#000000` | `hyperos-color-on-surface` |
| 星期标题 | MiSans | 13px | Regular | 100% | 0 | `rgba(0,0,0,0.6)` | `hyperos-color-on-surface-tertiary` |
| 日期数字（默认） | MiSans | 18px | Regular | 100% | 0 | `#000000` | `hyperos-color-on-surface` |
| 日期数字（选中） | MiSans | 18px | Regular | 100% | 0 | `#FFFFFF` | `hyperos-color-on-primary` |
| 日期数字（跨月） | MiSans | 18px | Regular | 100% | 0 | `rgba(0,0,0,0.12)` | — |
| 滚轮选中值 | MiSans | 24px | Medium | 100% | 0 | `#3482FF` | `hyperos-color-primary` |
| 滚轮相邻值 | MiSans | 18px | Medium | 100% | 0 | `rgba(0,0,0,0.6)` | `hyperos-color-on-surface-tertiary` |
| 滚轮远端值 | MiSans | 14px | Medium | 100% | 0 | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |
| 滚轮列标题 | MiSans | 18px | Medium | 100% | 0 | `rgba(0,0,0,0.4)` | `hyperos-color-on-surface-quaternary` |
| 按钮文字 | MiSans | 17px | Medium (380) | 100% | 0 | 见按钮规范 | `Size/Button` / `Weight/Button` |
| 农历文字 | MiSans | 10px | Regular | 100% | 0 | `rgba(0,0,0,0.4)` | — |
| 配置行标签 | MiSans | 16px | Regular | 100% | 0 | `#000000` | `hyperos-color-on-surface` |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 主色 / 选中色 | `#3482FF` | `hyperos-color-primary` |
| 主色上文字 | `#FFFFFF` | `hyperos-color-on-primary` |
| 文字色-主 | `#000000` | `hyperos-color-on-surface` |
| 文字色-三级 | `rgba(0,0,0,0.6)` | `hyperos-color-on-surface-tertiary` |
| 文字色-四级 | `rgba(0,0,0,0.4)` | `hyperos-color-on-surface-quaternary` |
| 文字色-八级 | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |
| 跨月日期色 | `rgba(0,0,0,0.12)` | — |
| 三级按钮背景 | `rgba(0,0,0,0.06)` | `hyperos-color-tertiary` |
| 三级按钮文字 | `rgba(0,0,0,0.8)` | `hyperos-color-on-tertiary` |
| 元素容器色（高） | `rgba(0,0,0,0.1)` | `hyperos-color-surface-container-high` |
| 表面色 | `#FFFFFF` | `hyperos-color-surface-high` |

---

## 变体

### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 模式 | `模式` / `propValue` | `月盘视图` / `滚筒视图` | 选择日历面板或滚轮选择器 |
| 状态 | `状态` / `propValue1` | `今天选中态` / `不可选日期` / `时间选中态` | 控制显示的选中状态 |
| 类型 | `类型` / `propValue2` | `无配置项` / `有配置项` / `有农历` / `无农历` | 控制 Header 扩展区域 |
| 日期行数 | `日期行数` / `propValue3` | `6 行` / `5 行` / `4 行` / `未定义` | 日历面板显示的周数（仅月盘视图生效） |

共计 **11 个变体**（非所有维度组合均存在）。

### 变体差异表

> 仅列出各变体之间**有差异**的属性。未列出的属性与默认变体（月盘视图, 今天选中态, 无配置项, 6行）相同。

#### 按「模式」分组

| 属性 | `月盘视图` | `滚筒视图` |
|-----|----------|----------|
| Body 内容 | MonthSwitcher + Calendar 日历网格 | MonthSwitcher + WheelPicker 滚轮列 |
| Calendar 显示 | 星期行 + 日期网格（4~6 行） | 不显示 |
| WheelPicker 显示 | 不显示 | 年/月/日 三列滚轮 |
| 日历 `height` | `332px`（6行）| — |
| WheelPicker `gap` | — | `60px` |

#### 按「类型」分组

| 属性 | `无配置项` | `有配置项` | `有农历` | `无农历` |
|-----|----------|----------|---------|---------|
| Header 扩展 | 无 | 日期与时间行 + 重复提醒行 | 日期与时间行 + 农历开关行 | 日期与时间行 + 农历开关（关闭态） |
| 日历农历文字 | 不显示 | 不显示 | 显示（每个日期下方） | 不显示 |
| 组件 `height` | 较小 | 较大（增加 ~124px） | 较大（增加 ~124px） | 较大（增加 ~124px） |

#### 按「日期行数」分组（仅月盘视图）

| 属性 | `6 行` | `5 行` | `4 行` |
|-----|--------|--------|--------|
| 日期行数 | 6 行 | 5 行 | 4 行 |
| Calendar `height` | `332px` | 自动适应 | 自动适应 |
| 适用场景 | 月首为周六/周日时 | 大多数月份 | 2 月（28/29 天且首日为周一） |

#### 按「状态」分组

| 属性 | `今天选中态` | `不可选日期` | `时间选中态` |
|-----|------------|------------|------------|
| 适用模式 | 月盘 + 滚筒 | 滚筒 | 滚筒 |
| 选中样式 | 日期蓝色高亮 / 滚轮蓝色选中 | 无选中高亮 | 时间蓝色选中 |
| WheelPicker 列 | 年/月/日 | 年/月/日 | 时/分 |

### 变体详情与截图

#### 月盘视图, 无配置项, 6 行（默认）

> 截图 nodeId: `41719:88655`

标准日历视图，显示 6 行日期网格。适用于月首为周六/周日导致需要 6 行的月份。

#### 月盘视图, 无配置项, 5 行

> 截图 nodeId: `53954:22139`

标准日历视图，显示 5 行日期网格。最常见的月份布局。

#### 月盘视图, 无配置项, 4 行

> 截图 nodeId: `55177:8927`

标准日历视图，显示 4 行日期网格。仅适用于 2 月（28/29 天且月首为周一）。

#### 滚筒视图, 今天选中态

> 截图 nodeId: `41719:88342`

显示年/月/日三列滚轮，选中项为蓝色 24px，相邻项为灰色 18px。

#### 滚筒视图, 不可选日期

> 截图 nodeId: `41719:88422`

滚轮选择器中日期不可选状态，视觉与今天选中态相同但无高亮选中。

#### 月盘视图, 有农历

> 截图 nodeId: `41719:88770`

Header 增加「日期与时间」行和「农历」开关行，日历每个日期下方显示对应农历日期（10px 灰色文字）。

#### 月盘视图, 有配置项

> 截图 nodeId: `41719:88896`

Header 增加「日期与时间」行和「重复提醒」行，日历面板无农历。

#### 滚筒视图, 时间选中态, 有配置项

> 截图 nodeId: `41719:88585`

Header 增加「日期与时间」行，Body 显示时/分两列滚轮替代年/月/日。时间标签呈选中态（蓝色背景）。

---

## 交互状态

> 以「默认态」为基准，其他状态仅列出**发生变化**的属性。

### Calendar 日历面板

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态） | — |
| `selected` | 点击某日期 | `background-color` | `#3482FF` | `hyperos-color-primary` |
| `selected` | 点击某日期 | `color` | `#FFFFFF` | `hyperos-color-on-primary` |
| `selected` | 点击某日期 | `border-radius` | `8px` | `hyperos_theme_radius_tiny` |
| `today` | 当天日期 | Figma 未定义，请由设计团队补充 | — | — |
| `disabled` | 不可选日期 / 跨月日期 | `color` | `rgba(0,0,0,0.12)` | — |
| `hover` | 鼠标悬停 | Figma 未定义，请由设计团队补充 | — | — |
| `active` | 鼠标按下 / 触摸 | Figma 未定义，请由设计团队补充 | — | — |

### WheelPicker 滚轮选择器

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态） | — |
| `scrolling` | 用户滑动滚轮 | 列表项位置 | 根据滚动偏移量平移 | — |
| `selected` | 项目位于中间位置 | `font-size` | `24px` | — |
| `selected` | 项目位于中间位置 | `color` | `#3482FF` | `hyperos-color-primary` |
| `adjacent` | 选中项上下各一项 | `font-size` | `18px` | — |
| `adjacent` | 选中项上下各一项 | `color` | `rgba(0,0,0,0.6)` | `hyperos-color-on-surface-tertiary` |

### MonthSwitcher 月份切换器

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | 单月份标签 + 下拉箭头 | — |
| `expanded` | 点击下拉箭头 | 布局 | 显示年月选择面板 | — |
| `hover` | 鼠标悬停按钮 | Figma 未定义，请由设计团队补充 | — | — |
| `active` | 鼠标按下按钮 | Figma 未定义，请由设计团队补充 | — | — |

### Footer 按钮

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态） | — |
| `hover` | 鼠标悬停 | Figma 未定义，请由设计团队补充 | — | — |
| `active` | 鼠标按下 / 触摸 | Figma 未定义，请由设计团队补充 | — | — |
| `disabled` | `disabled=true` | Figma 未定义，请由设计团队补充 | — | — |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

```typescript
interface DatePickerProps {
  /** 选择器模式 */
  mode: 'calendar' | 'wheel';
  /** 选中状态 */
  state: 'todaySelected' | 'disabled' | 'timeSelected';
  /** 配置类型，控制 Header 扩展区域 */
  type: 'none' | 'withSettings' | 'withLunar' | 'withoutLunar';
  /** 日期行数，仅月盘视图生效 */
  dateRows?: '6' | '5' | '4'; // 默认: 根据当月自动计算
  /** 标题文字 */
  title?: string; // 默认: "标题"
  /** 取消按钮回调 */
  onCancel?: () => void;
  /** 确认按钮回调 */
  onConfirm?: (value: Date) => void;
  /** 日期变化回调 */
  onChange?: (value: Date) => void;
  /** 是否显示农历 */
  showLunar?: boolean; // 默认: false
  /** 当前选中日期 */
  value?: Date;
  /** 不可选日期列表 */
  disabledDates?: Date[];
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 模式 | Variant | `mode` | `月盘视图` → `'calendar'` | 月盘视图 = 日历面板，滚筒视图 = 滚轮选择 |
| 状态 | Variant | `state` | `今天选中态` → `'todaySelected'` | 控制选中态显示 |
| 类型 | Variant | `type` | `无配置项` → `'none'` | 控制 Header 是否显示配置行 |
| 日期行数 | Variant | `dateRows` | `6 行` → `'6'` | 仅月盘视图，应由日历算法自动确定 |

---

## 使用指南

### 何时使用

- **日期选择**：使用「月盘视图」（日历模式），用户可直观地在日历面板中浏览和选择日期
- **快速日期输入**：使用「滚筒视图」（滚轮模式），通过上下滑动快速定位年/月/日
- **日期+时间选择**：使用「有配置项」类型，Header 区域提供日期/时间切换标签
- **带农历日历**：使用「有农历」类型，日期下方显示对应农历日期
- **事件创建**：使用「有配置项」类型，支持设置日期与时间、重复提醒等

### 何时不使用

- **纯时间选择**：仅需选择时分且不涉及日期时，应使用独立的 TimePicker 组件代替
- **日期范围选择**：需要选择起止日期范围时，应使用 DateRangePicker 组件代替
- **少量选项**：仅有几个固定日期选项时，应使用 ActionSheet 或 Radio 组件代替
- **连续数值调节**：应使用 Slider 组件代替

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 根据月份天数自动切换 4/5/6 行布局 | 固定使用 6 行布局 | 避免空行浪费空间 |
| 日历模式配合 MonthSwitcher 使用 | 日历面板无月份切换功能 | 用户需要切换月份浏览 |
| 跨月日期使用 `rgba(0,0,0,0.12)` 弱化显示 | 跨月日期与当月日期使用相同样式 | 区分当月与跨月避免误选 |
| 滚轮选中值使用 `24px` 蓝色强调 | 选中与非选中项视觉差异不足 | 清晰的选中反馈是核心体验 |
| 5 行模式远端值启用 `font-feature-settings: 'tnum', 'lnum'` | 使用非等宽数字 | 等宽数字确保滚动时数位对齐 |
| 「有农历」模式下农历文字使用 10px 灰色 | 农历文字过大或过显眼 | 农历为辅助信息，不应抢占日期数字的视觉焦点 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `hyperos-color-primary` | `#3482FF` | color | 选中日期背景、滚轮选中值、确认按钮背景、日期标签选中态 |
| `hyperos-color-on-primary` | `#FFFFFF` | color | 选中日期文字、确认按钮文字 |
| `hyperos-color-on-surface` | `#000000` | color | 标题文字、默认日期数字、月份标签 |
| `hyperos-color-on-surface-tertiary` | `rgba(0,0,0,0.6)` | color | 星期标题、滚轮相邻值、月份切换按钮图标 |
| `hyperos-color-on-surface-quaternary` | `rgba(0,0,0,0.4)` | color | 滚轮列标题（年/月/日） |
| `hyperos-color-on-surface-octonary` | `rgba(0,0,0,0.3)` | color | 滚轮远端值（5 行模式） |
| `hyperos-color-tertiary` | `rgba(0,0,0,0.06)` | color | 取消按钮背景 |
| `hyperos-color-on-tertiary` | `rgba(0,0,0,0.8)` | color | 取消按钮文字 |
| `hyperos-color-surface-container-high` | `rgba(0,0,0,0.1)` | color | 元素容器色 |
| `hyperos-color-surface-high` | `#FFFFFF` | color | 表面/背景色 |
| `hyperos_theme_radius_big` | `36px` | radius | 组件整体圆角 |
| `hyperos_theme_radius_common` | `16px` | radius | 按钮圆角、日期标签圆角 |
| `hyperos_theme_radius_tiny` | `8px` | radius | 选中日期圆角 |
| `hyperos_font_size_title4` / `Size/Title 4` | `18px` | font-size | 标题字号 |
| `hyperos_font_weight_title4` / `Weight/Title 4` | `380` | font-weight | 标题字重 |
| `hyperos_font_size_button` / `Size/Button` | `17px` | font-size | 按钮文字字号 |

---

## 设计注释

> 1. 组件名称「❖ 母组件集合_勿动」为 Figma 内部管理用途，实际组件名为 DatePicker。
> 2. 存在一个「日期选择器/玻璃材质(OS4禁用)」变体（nodeId: `80359:105139`），该变体使用 `mix-blend-mode: soft-light` 和 `hard-light` 实现毛玻璃效果，包含 `inset box-shadow`，但已标注为 OS4 禁用，不应在 HyperOS 4 中使用。
> 3. 所有原子选择列组件（YearColumn、MonthColumn、DayColumn）在 Figma 组件描述中标注为 `COUINumberPicker`，表明底层实现对应 COUI 框架的 NumberPicker 控件。
> 4. 5 行模式下远端值使用 `font-feature-settings: 'lnum' 1, 'tnum' 1`，启用等宽数字（tabular numerals）和齐线数字（lining numerals），确保滚动时数字对齐。
> 5. MonthSwitcher 使用 `HyperOS Symbols` 字体图标作为左右箭头（`Heavy` 字重，9px），非常规 SVG 图标。
> 6. Header 分割线为 SVG 实现的渐变线条（高 20px），非纯 CSS `border`，资源地址：`http://localhost:3845/assets/9db36c0d5782715de271a0a249d184b855b2c8f4.svg`。
> 7. 日历面板中选中日期的蓝色圆角矩形尺寸为 35×35px，小于日期单元格容器的 44px 宽度，居中显示。
> 8. 按钮组件引用了外部默认按钮组件（nodeId: `75:787`），其设计规范详见 [按钮组件规范](https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=87366-9372)。
> 9. 日期标签的选中态（日期/时间切换）使用蓝色 pill 背景，与整体主色保持一致。
