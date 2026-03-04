---
component: NavigationBar
description: 小米 HyperOS 系统标题栏组件，用于页面顶部展示标题、返回按钮和操作图标，支持多种标题类型和交互状态
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=80637-9785
figma_node_id: "80637:9785"
variants: "4 dimensions, 36 variants"
tokens_used: 18
---

# 标题栏 NavigationBar

> 系统级导航标题栏组件，位于页面顶部，包含返回按钮、标题文字和右侧操作图标。支持大标题、中标题、小标题等多种类型，以及平面放置和上滑浮起两种交互状态，同时适配亮色/深色模式。

## 预览

![NavigationBar 全部变体预览](http://localhost:3845/assets/navigation-bar-all-variants.png)

---

## 组件结构

```
标题栏 Navigation Bar                              // FRAME | 1890:3345
├── 大标题, 默认态, 无辅助标题, 亮色模式             // COMPONENT | 1890:3486
│   ├── .标题栏/顶部功能栏                          // FRAME | 1890:3487
│   │   ├── 左 (平面icon集合)                       // INSTANCE | 91243:101906
│   │   │   └── 1个 (图标板子)                      // FRAME
│   │   │       └── chevron_backward                // INSTANCE (返回图标)
│   │   └── 右 (平面icon集合)                       // INSTANCE | 91243:93502
│   │       ├── 图标板子（平面）- edit               // INSTANCE
│   │       ├── 图标板子（平面）- search             // INSTANCE
│   │       └── 图标板子（平面）- more               // INSTANCE
│   └── .标题栏/标题/上滑前/单行                     // FRAME | 1890:3495
│       └── 大标题 (TEXT)                           // TEXT | 1890:3496
├── 大标题, 默认态, 有辅助标题, 亮色模式             // COMPONENT | 1890:3439
│   ├── .标题栏/顶部功能栏                          // FRAME
│   └── .标题栏/标题/上滑前/多行                     // FRAME
│       ├── 大标题 (TEXT)                           // TEXT
│       └── 辅助标题 (TEXT)                         // TEXT
├── 中标题（Q18）, 默认态, 无辅助标题, 亮色模式      // COMPONENT | 78321:24804
│   ├── 中标题 (TEXT)                               // TEXT
│   └── 右 (图标集合)                               // INSTANCE
├── 中标题二级页, 默认态, 无辅助标题, 亮色模式       // COMPONENT | 80090:28306
│   ├── 左 (返回按钮)                               // INSTANCE
│   ├── 中标题 (TEXT)                               // TEXT
│   └── 右 (图标集合)                               // INSTANCE
├── 小标题, 默认态, 无辅助标题, 亮色模式             // COMPONENT | 1890:3390
│   ├── 左 (返回按钮)                               // INSTANCE
│   ├── 小标题 (TEXT, 居中绝对定位)                  // TEXT
│   └── 右 (图标集合)                               // INSTANCE
└── ... (深色模式 / 浮起态 / 有辅助标题 变体)
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| .标题栏/顶部功能栏 | FRAME | `1890:3487` | 顶部图标操作区域，包含返回按钮和右侧操作图标 |
| .标题栏/标题/上滑前/单行 | FRAME | `1890:3495` | 单行大标题区域 |
| .标题栏/标题/上滑前/多行 | FRAME | `1890:3448` | 多行标题区域（含辅助标题） |
| 平面icon集合 | COMPONENT_SET | `91243:93459` | 平面状态下的图标集合（0个/1个/2个/3个/文字版本） |
| 浮起icon集合 | COMPONENT_SET | `91243:103943` | 浮起状态下的图标集合（玻璃材质） |
| 图标板子（平面） | COMPONENT_SET | `78326:18152` | 平面状态的单个图标按钮，支持多种交互状态 |
| 图标板子（浮起） | COMPONENT_SET | `78351:11738` | 浮起状态的单个图标按钮（玻璃材质），支持多种交互状态 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器（NavigationBar 根节点）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `392px` | — |
| `height` | `auto`（hug） | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `flex-start` | — |
| `backdrop-filter` | `blur(66px)` | `模糊数值/Default` |
| `background-color` | 透明（由页面背景决定） | — |

### 子组件: 顶部功能栏（大标题/小标题类型）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%`（fill） | — |
| `height` | `auto`（hug） | — |
| `display` | `flex` | — |
| `flex-direction` | `row` | — |
| `align-items` | `center` | — |
| `justify-content` | `space-between` | — |
| `padding` | `6px 12px` | `padding/padding_sm` = `12px` |

### 子组件: 顶部功能栏（中标题 Q18 类型）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%`（fill） | — |
| `display` | `flex` | — |
| `flex-direction` | `row` | — |
| `align-items` | `center` | — |
| `gap` | `8px` | — |
| `padding` | `6px 12px 6px 28px` | `padding/padding_lg` = `28px`, `padding/padding_sm` = `12px` |

### 子组件: 顶部功能栏（中标题二级页类型）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%`（fill） | — |
| `display` | `flex` | — |
| `flex-direction` | `row` | — |
| `align-items` | `center` | — |
| `gap` | `12px` | — |
| `padding` | `6px 12px` | `padding/padding_sm` = `12px` |

### 子组件: 标题区域（单行 - 大标题）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%`（fill） | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `flex-start` | — |
| `padding` | `8px 28px 10px 28px` | `padding/padding_lg` = `28px` |

### 子组件: 标题区域（多行 - 大标题含辅助标题）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%`（fill） | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `flex-start` | — |
| `padding` | `8px 28px 14px 28px` | `padding/padding_lg` = `28px` |
| `backdrop-filter` | `blur(29.08px)` | — |

### 子组件: 图标板子（平面）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `44px` | — |
| `height` | `44px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `padding` | `0 8px` | — |
| `border-radius` | `1000px` | — |

### 子组件: 图标板子（浮起 - 玻璃材质）

| CSS 属性 | 值（亮色模式） | 值（深色模式） | Token |
|---------|-------------|-------------|-------|
| `width` | `44px` | `44px` | — |
| `height` | `44px` | `44px` | — |
| `padding` | `10px 12px` | `10px 12px` | — |
| `border-radius` | `1000px` | `1000px` | — |
| `border` | `0.8px solid #F9F9F9` | `0.8px solid #262626` | — |
| `box-shadow` | `0px 0px 40px 0px rgba(0,0,0,0.06), 0px 24px 60px 0px rgba(0,0,0,0.08)` | 同左 | `Shadow/Shadow_Regular` |
| `box-shadow` (inset) | `inset 0px 2px 2px 0px #9D9D9D` | 同左 | `FrostShadow/FrostEffect_Thin_ShadowOn` |
| 背景层 1 | `rgba(0,0,0,0.02)` | `rgba(0,0,0,0.1)` | `Pured/Pured_Thin_Glass_Light` / `Dark` |
| 背景层 2 | `rgba(255,255,255,0.6)` + `mix-blend-mode: soft-light` | `rgba(86,86,86,0.4)` + `mix-blend-mode: luminosity` | — |
| 背景层 3 | `rgba(255,255,255,0.4)` + `mix-blend-mode: hard-light` + `backdrop-filter: blur(10px)` | `rgba(63,63,63,0.6)` + `mix-blend-mode: overlay` + `backdrop-filter: blur(10px)` | — |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color`（亮色） | `color`（深色） | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|----------------|----------------|-----------|
| 大标题 | MiSans | 32px | 330 | 100% | 0 | `#000000` | `rgba(255,255,255,0.95)` | `Title/Title 1` |
| 中标题（Q18） | MiSans | 20px | 380 | 100% | 0 | `#000000` | `rgba(255,255,255,0.95)` | — |
| 中标题二级页 | MiSans | 26px | 380 | 100% | 0 | `#000000` | `rgba(255,255,255,0.95)` | — |
| 小标题 | MiSans | 18px | 380 | 100% | 0 | `#000000` | `rgba(255,255,255,0.95)` | `Title/Title 4` |
| 辅助标题 | MiSans | 14px | 380 | 100% | 0 | `rgba(0,0,0,0.6)` | `rgba(255,255,255,0.5)` | `Subtitle/Subtitle` |
| 辅助标题（小标题下） | MiSans | 13px | 380 | 100% | 0 | `rgba(0,0,0,0.6)` | `rgba(255,255,255,0.5)` | — |
| 图标符号 | HyperOS Symbols VF | 21px | 330 | normal | 0 | `#000000` | `rgba(255,255,255,0.95)` | — |
| 返回图标符号 | HyperOS Symbols UI | 21px | 330 | normal | 0 | `#000000` | `rgba(255,255,255,0.95)` | — |

### 颜色一览

| 语义用途 | 值（亮色模式） | 值（深色模式） | Token |
|---------|-------------|-------------|-------|
| 文字色-主 | `#000000` | `rgba(255,255,255,0.95)` | `hyperos-color-on-surface` |
| 文字色-次（辅助标题） | `rgba(0,0,0,0.6)` | `rgba(255,255,255,0.5)` | `hyperos-color-on-surface-tertiary` |
| 文字色-禁用 | `rgba(0,0,0,0.3)` | `rgba(255,255,255,0.3)` | `hyperos-color-on-surface-octonary` |
| 图标/按钮容器背景（平面） | `rgba(0,0,0,0.05)` | `rgba(255,255,255,0.12)` | `新增色彩变量/container_nav` |
| 激活色（筛选反馈） | `#3482FF` | `#4788FF` | `hyperos-color-primary` |
| 浮起边框色 | `#F9F9F9` | `#262626` | — |
| 玻璃材质阴影 | `0px 24px 60px rgba(0,0,0,0.08)` | 同左 | `Shadow/Shadow_Regular` |

---

## 变体

### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 标题类型 | `标题类型` | `大标题` / `中标题（Q18）` / `中标题二级页` / `小标题` / `小标题可点击` | 控制标题的显示样式和布局模式 |
| 交互状态 | `交互状态` | `默认态（平面放置）` / `浮起态（上滑浮起）` | 默认态为平面图标，浮起态为玻璃材质图标 |
| 辅助标题 | `辅助标题` | `yes` / `no` | 是否显示辅助副标题文字 |
| 颜色模式 | `颜色模式` | `亮色模式` / `深色模式` | 适配系统主题 |

共计 **5 × 2 × 2 × 2 = 40 个理论组合**，实际约 **36 个有效变体**（小标题可点击仅部分组合）。

### 变体差异表

> 仅列出各变体之间**有差异**的属性。未列出的属性与默认变体（大标题/默认态/无辅助标题/亮色模式）相同。

#### 按标题类型分组

| 属性 | `大标题` | `中标题（Q18）` | `中标题二级页` | `小标题` |
|-----|---------|---------------|-------------|---------|
| 整体高度 | `116px`（无副标题）/ `139px`（有副标题） | `56px` | `56px`（无副标题）/ `64px`（有副标题） | `56px` |
| 容器布局 | 顶部功能栏 + 标题区域（上下两部分） | 单行 flex 行内布局 | 单行 flex 行内布局 + 返回按钮 | 单行 flex 行内布局 + 标题居中绝对定位 |
| 容器 `padding` | 顶部功能栏 `6px 12px`，标题区 `8px 28px 10px 28px` | `6px 28px 6px 12px` | `6px 12px` | `6px 12px` |
| 标题 `font-size` | `32px` | `20px` | `26px` | `18px` |
| 标题 `font-weight` | `330` | `380` | `380` | `380` |
| 标题对齐 | 左对齐 | 左对齐 | 左对齐 | 居中（绝对定位） |
| 返回按钮 | 有（顶部功能栏内） | 无 | 有（行内） | 有（行内） |
| 右侧图标数量 | 最多 3 个 | 最多 2 个 | 最多 1 个 | 最多 1 个 |

#### 按交互状态分组

| 属性 | `默认态（平面放置）` | `浮起态（上滑浮起）` |
|-----|-------------------|-------------------|
| 图标按钮样式 | 平面样式，无背景/阴影 | 玻璃材质，含多层背景混合、边框、阴影 |
| 图标按钮 `padding` | `0 8px` | `10px 12px` |
| 图标按钮 `border` | 无 | `0.8px solid`（亮 `#F9F9F9` / 暗 `#262626`） |
| 图标按钮 `box-shadow` | 无 | `0px 0px 40px rgba(0,0,0,0.06), 0px 24px 60px rgba(0,0,0,0.08)` + `inset 0px 2px 2px #9D9D9D` |
| 图标按钮背景 | 透明 | 玻璃材质（三层混合） |

#### 按颜色模式分组

| 属性 | `亮色模式` | `深色模式` |
|-----|----------|----------|
| 标题文字色 | `#000000` | `rgba(255,255,255,0.95)` |
| 辅助标题色 | `rgba(0,0,0,0.6)` | `rgba(255,255,255,0.5)` |
| 图标色 | `#000000` | `rgba(255,255,255,0.95)` |
| 玻璃材质 背景层 1 | `rgba(0,0,0,0.02)` | `rgba(0,0,0,0.1)` |
| 玻璃材质 背景层 2 | `rgba(255,255,255,0.6)` soft-light | `rgba(86,86,86,0.4)` luminosity |
| 玻璃材质 背景层 3 | `rgba(255,255,255,0.4)` hard-light | `rgba(63,63,63,0.6)` overlay |
| 浮起边框色 | `#F9F9F9` | `#262626` |

---

## 交互状态

> 以下为图标板子（图标按钮）的交互状态。以「默认态」为基准，其他状态仅列出**发生变化**的属性。

### 图标板子（平面）交互状态

| 状态 | 触发条件 | 变化的属性 | 变化值（亮色模式） | 变化值（深色模式） | Token |
|-----|---------|-----------|----------------|----------------|-------|
| `默认` | — | — | （基准状态，无背景） | （基准状态，无背景） | — |
| `悬停` | 鼠标悬停 | `background` | `rgba(0,0,0,0.04) + rgba(0,0,0,0.05)` 叠加 | `rgba(255,255,255,0.08) + rgba(255,255,255,0.12)` 叠加 | — |
| `按下` | 鼠标按下 / 触摸 | `background` | `rgba(0,0,0,0.1) + rgba(0,0,0,0.05)` 叠加 | `rgba(255,255,255,0.14) + rgba(255,255,255,0.12)` 叠加 | — |
| `禁用` | disabled | `background-color` | `rgba(0,0,0,0.05)` | `rgba(255,255,255,0.12)` | `新增色彩变量/container_nav` |
| `禁用` | disabled | 图标 `color` | `rgba(0,0,0,0.3)` | `rgba(255,255,255,0.3)` | `hyperos-color-on-surface-octonary` |
| `筛选反馈` | 筛选操作激活 | 图标替换 | 图标变为筛选指示器（三条横线递减），颜色 `#3482FF` | 同左但颜色 `#4788FF` | `hyperos-color-primary` |
| `按下+悬停` | 组合状态 | `background` | `rgba(0,0,0,0.04) + rgba(0,0,0,0.12) + rgba(0,0,0,0.05)` 叠加 | `rgba(255,255,255,0.08) + rgba(255,255,255,0.14) + rgba(255,255,255,0.12)` 叠加 | — |

### 系统通用交互反馈色汇总

| 状态 | 亮色模式（light） | 深色模式（dark） |
|-----|-----------------|-----------------|
| 常态 normal | 0% | 0% |
| 悬停 hover | 4% | 8% |
| 按下 touch | 10% | 14% |
| 选中 select | 6% | 12% |
| 禁用 disable | 原色的 30% | 原色的 30% |
| 悬停+按下 hover+touch | 4%+10% | 8%+14% |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

```typescript
interface NavigationBarProps {
  /** 标题类型，控制标题的显示样式和布局模式 */
  titleType: '大标题' | '中标题（Q18）' | '中标题二级页' | '小标题' | '小标题可点击';
  /** 交互状态，默认态为平面图标样式，浮起态为玻璃材质图标 */
  interactionState: '默认态（平面放置）' | '浮起态（上滑浮起）';
  /** 是否显示辅助副标题 */
  showSubtitle?: boolean; // 默认: false
  /** 颜色模式，适配系统主题 */
  colorMode: '亮色模式' | '深色模式';
  /** 标题文字内容 */
  title?: string; // 默认: 对应类型的默认文字
  /** 辅助标题文字内容 */
  subtitle?: string; // 默认: "106952836183947"
  /** 左侧图标/返回按钮 */
  leftIcon?: ReactNode; // 默认: chevron_backward
  /** 右侧操作图标区域 */
  rightIcons?: ReactNode; // 默认: edit + search + more（大标题时最多3个）
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 标题类型 | Variant | `titleType` | `大标题` | 控制标题样式和布局 |
| 交互状态 | Variant | `interactionState` | `默认态（平面放置）` | 平面或浮起 |
| 辅助标题 | Boolean | `showSubtitle` | `false` | 是否显示副标题 |
| 颜色模式 | Variant | `colorMode` | `亮色模式` | 亮色/深色 |

---

## 使用指南

### 何时使用

- **一级页面顶部**：使用「大标题」类型，适用于设置、应用列表等一级入口页面
- **二级页面顶部**：使用「中标题二级页」类型，带有返回按钮，适用于从一级页面进入的详情页
- **功能列表页**：使用「中标题（Q18）」类型，适用于带有搜索等操作的中间层级页面
- **弹窗/浮层标题**：使用「小标题」类型，标题居中显示，适用于底部弹窗或模态对话框的标题
- **页面滚动浮起**：使用「浮起态」交互状态，当页面内容上滑时切换为玻璃材质风格的悬浮标题栏

### 何时不使用

- **全屏沉浸式页面**：不需要标题栏的全屏内容（如相机、视频播放），不应使用 NavigationBar
- **Tab 导航**：底部 Tab 导航栏应使用 TabBar 组件代替
- **仅需返回按钮**：如果只需要返回功能不需要标题，应使用独立的 BackButton 组件

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 根据页面层级选择合适的标题类型 | 所有页面统一使用大标题 | 不同层级的页面需要不同的信息层次 |
| 浮起态仅在页面滚动时自动切换 | 默认就使用浮起态样式 | 浮起态表示页面有可滚动内容，静态页面应使用默认态 |
| 右侧图标数量与标题类型匹配 | 小标题类型放置 3 个右侧图标 | 空间有限，小标题最多 1 个右侧操作，大标题最多 3 个 |
| 辅助标题显示关键辅助信息 | 辅助标题放置过长的文字 | 辅助标题应简洁，超长文字会被截断 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `hyperos-color-on-surface` | `#000000`（亮）/ `rgba(255,255,255,0.95)`（暗） | color | 标题文字色、图标色 |
| `hyperos-color-on-surface-tertiary` | `rgba(0,0,0,0.6)`（亮）/ `rgba(255,255,255,0.5)`（暗） | color | 辅助标题文字色 |
| `hyperos-color-on-surface-octonary` | `rgba(0,0,0,0.3)`（亮）/ `rgba(255,255,255,0.3)`（暗） | color | 禁用状态图标色 |
| `hyperos-color-primary` | `#3482FF`（亮）/ `#4788FF`（暗） | color | 筛选反馈激活色 |
| `新增色彩变量/container_nav` | `rgba(0,0,0,0.05)`（亮）/ `rgba(255,255,255,0.12)`（暗） | color | 图标按钮禁用背景 |
| `padding/padding_sm` | `12px` | spacing | 功能栏水平内边距 |
| `padding/padding_lg` | `28px` | spacing | 标题区域水平内边距、中标题 Q18 左内边距 |
| `hyperos_font_size_title1` | `32px` | font-size | 大标题字号 |
| `hyperos_font_weight_title1` | `330` | font-weight | 大标题字重 |
| `hyperos_font_size_title4` | `18px` | font-size | 小标题字号 |
| `hyperos_font_weight_title4` | `380` | font-weight | 小标题字重 |
| `hyperos_font_size_subtitle` | `14px` | font-size | 辅助标题字号 |
| `hyperos_font_weight_subtitle` | `380` | font-weight | 辅助标题字重 |
| `Title/Title 1` | `MiSans, 32px, 330, 100%, 0` | typography | 大标题完整排版样式 |
| `Title/Title 4` | `MiSans, 18px, 380, 100%, 0` | typography | 小标题完整排版样式 |
| `Subtitle/Subtitle` | `MiSans, 14px, 380, 100%, 0` | typography | 辅助标题完整排版样式 |
| `模糊数值/Default` | `blur(66px)` | effect | 整体容器背景模糊 |
| `Shadow/Shadow_Regular` | `0px 24px 60px rgba(0,0,0,0.08), 0px 0px 40px rgba(0,0,0,0.06)` | effect | 浮起图标按钮阴影 |
| `FrostShadow/FrostEffect_Thin_ShadowOn` | 多层阴影+模糊复合效果 | effect | 浮起图标玻璃材质效果 |
| `Pured/Pured_Thin_Glass_Light` | `#000000, #FFFFFF, #FFFFFF` | material | 亮色玻璃材质背景色组 |
| `Pured/Pured_Thin_Glass_Dark` | `#000000, #565656, #3F3F3F` | material | 深色玻璃材质背景色组 |

---

## 设计注释

> 1. 组件提供了默认状态与浮层状态的切换展示。但由于部分原始组件并不包含浮层样式，因此当切换为浮层状态时，会自动回退为默认样式，这是正常表现。
> 2. 「小标题可点击」类型在 Figma 中标记为 `hidden`，属于保留变体，实际使用时请确认设计团队是否需要此变体。
> 3. 浮起态的玻璃材质（Glassmorphism）采用三层背景混合叠加实现，需要注意浏览器兼容性（特别是 `mix-blend-mode` 和 `backdrop-filter` 的支持）。
> 4. OS4 版本中玻璃材质（`GlassShadow`）标记为禁用，改用 `FrostShadow` 霜冻效果替代。
> 5. 图标使用 HyperOS 自定义符号字体（`HyperOS Symbols VF` 和 `HyperOS Symbols UI`），实现时需确保字体资源加载。
