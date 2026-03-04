---
component: PopupMenus
description: 小米 HyperOS4 近手菜单组件，用于在当前上下文中快速展示一组可选操作项
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=82824-11352
figma_node_id: "82824:11352"
variants: "2 component sets — .近手菜单: 2 dimensions (类型×行数), 6 variants; .近手菜单列表: 3 dimensions (位置×前置图标×状态), 10 variants"
tokens_used: 12
---

# 近手菜单 PopupMenus

> HyperOS4 系统级近手菜单（Popup Menus）组件，用于在触发点附近弹出一组可选操作项。支持单行与双行列表项，可选配前置图标和勾选标记。包含标准菜单、最大宽度菜单和自定义菜单三种类型，适配不同内容长度和功能复杂度的场景。

## 预览

![近手菜单组件全部变体预览](http://localhost:3845/figma/screenshot/82824:11352)

---

## 组件结构

本组件由两个核心组件集构成：`.近手菜单`（菜单容器）和 `.近手菜单列表`（列表项）。

```
近手菜单 Popup Menus                              // FRAME | 82824:11352
├── .近手菜单                                      // COMPONENT_SET | 28784:27390
│   ├── 类型=近手菜单, 行数=单行                     // COMPONENT | 28784:27149
│   │   ├── .近手菜单列表 × N                       // INSTANCE | 列表项实例
│   │   └── ...
│   ├── 类型=近手菜单, 行数=双行                     // COMPONENT | 28784:27146
│   ├── 类型=最大宽度-近手菜单, 行数=单行             // COMPONENT | 28784:27455
│   ├── 类型=最大宽度-近手菜单, 行数=双行             // COMPONENT | 28784:27147
│   ├── 类型=自定义菜单, 行数=单行                    // COMPONENT | 80794:4749
│   │   ├── .近手菜单列表 × N                       // INSTANCE | 常规列表项
│   │   ├── .MenuItem（分割线）                     // FRAME | 分隔线区域
│   │   └── .近手菜单列表/顶层/无/默认（底部操作项）   // INSTANCE | 自定义操作入口
│   └── 类型=自定义菜单, 行数=双行                    // COMPONENT | 80794:5551
│
└── .近手菜单列表                                    // COMPONENT_SET | 28784:25420
    ├── 位置=中间层, 前置图标=无, 状态=默认            // COMPONENT | 28784:25565
    │   ├── Content（内容区）                        // FRAME
    │   │   ├── Title（主标题）                      // TEXT
    │   │   └── Subtitle（副标题，可选）              // TEXT
    │   └── .TrailingIcon（尾部勾选图标）              // INSTANCE
    ├── 位置=中间层, 前置图标=无, 状态=选中            // COMPONENT | 28784:25485
    ├── 位置=中间层, 前置图标=无, 状态=悬停            // COMPONENT | 82354:14218
    ├── 位置=中间层, 前置图标=无, 状态=按压            // COMPONENT | 82354:14268
    ├── 位置=中间层, 前置图标=无, 状态=禁用            // COMPONENT | 82354:14300
    ├── 位置=中间层, 前置图标=有, 状态=默认            // COMPONENT | 28784:25569
    ├── 位置=中间层, 前置图标=有, 状态=选中            // COMPONENT | 28784:25489
    ├── 位置=中间层, 前置图标=有, 状态=悬停            // COMPONENT | 82354:14223
    ├── 位置=中间层, 前置图标=有, 状态=按压            // COMPONENT | 82354:14273
    └── 位置=中间层, 前置图标=有, 状态=禁用            // COMPONENT | 82354:14305
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| .近手菜单 | COMPONENT_SET | `28784:27390` | 菜单容器组件集，包含 6 个变体 |
| .近手菜单列表 | COMPONENT_SET | `28784:25420` | 菜单列表项组件集，包含 10 个变体 |
| Content（内容区） | FRAME | — | 列表项的文本内容区域，flex 纵向布局 |
| Title（主标题） | TEXT | — | 列表项主文本，Body 1 样式 |
| Subtitle（副标题） | TEXT | — | 列表项副文本，Body 2 样式，双行模式可见 |
| .TrailingIcon | INSTANCE | — | 尾部勾选标记图标，选中时显示 |
| Leading Icon | INSTANCE | — | 前置图标（HyperOS Symbols 字体图标），`前置图标=有` 时存在 |
| .MenuItem（分割线） | FRAME | — | 自定义菜单中的分隔线区域 |
| Divider-Line | SVG | — | 分隔线 SVG 资源 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器: .近手菜单

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `flex-start` | — |
| `padding` | `8px` | — |
| `border-radius` | `24px` | `miuix_theme_radius_demi_big` |
| `background-color` | `#FFFFFF` | `miuix_default_color_surface_highest` |
| `overflow` | `hidden` | — |

#### 容器宽度（按类型变体）

| 类型 | 容器宽度 | 列表项宽度 | `max-width` |
|-----|---------|-----------|-------------|
| 近手菜单 | `200px`（hug） | `184px` | `288px` |
| 最大宽度-近手菜单 | `288px`（hug） | `272px` | `288px` |
| 自定义菜单 | `200px`（hug） | `184px` | `288px` |

### 子组件: .近手菜单列表（列表项）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `max-width` | `288px` | — |
| `min-height` | `44px` | — |
| `padding` | `10px 12px` | — |
| `border-radius` | `14px` | — |
| `gap` | `10px` | — |
| `width` | `184px`（近手菜单 / 自定义菜单）或 `272px`（最大宽度-近手菜单） | — |

#### 双行变体列表项 padding 差异

| 类型 | `padding` |
|-----|-----------|
| 近手菜单（双行） | `11px 12px` |
| 最大宽度-近手菜单（双行） | `11px 12px` |
| 自定义菜单（双行） | `11px 12px` |

### 子组件: Content（内容区）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `flex-start` | — |
| `justify-content` | `center` | — |
| `flex` | `1 0 0` | — |
| `min-width` | `1px` | — |
| `min-height` | `1px` | — |

### 子组件: Leading Icon（前置图标）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `24px` | — |
| `height` | `24px` | — |
| `flex-shrink` | `0` | — |
| `font-family` | `HyperOS_Symbols_VF` | — |
| `font-size` | `18px` | — |

### 子组件: .TrailingIcon（尾部勾选图标）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `24px` | — |
| `height` | `24px` | — |
| `flex-shrink` | `0` | — |
| `opacity` | `0`（未选中）/ `1`（选中） | — |

#### Checkmark 图标内部结构

| CSS 属性 | 值 | Token |
|---------|----|-------|
| Checkmark-Container `width` | `24px` | — |
| Checkmark-Container `height` | `24px` | — |
| Checkmark-Shape `width` | `20px` | — |
| Checkmark-Shape `height` | `20px` | — |
| Checkmark-Shape `offset` | `left: 2px; top: 2px` | — |

### 子组件: .MenuItem（分割线，仅自定义菜单）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `padding` | `8px 14px` | — |
| `width` | `184px` | — |

#### 自定义菜单底部操作项

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `gap` | `8px` | — |
| `padding` | `11px 14px`（单行）/ `11px 16px`（双行） | — |
| `border-radius` | `16px 16px 0 0` | `miuix_theme_radius_common` |
| `width` | `184px` | — |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| 主标题（默认） | MiSans | 16px | 330 | 100% | 0 | `#000000` | `Body/Body 1` |
| 主标题（选中） | MiSans | 16px | 330 | 100% | 0 | `#3482FF` | `Body/Body 1` + `miuix_default_color_primary` |
| 主标题（禁用） | MiSans | 16px | 330 | 100% | 0 | `rgba(0,0,0,0.3)` | `Body/Body 1` + `miuix_default_color_on_surface_octonary` |
| 副标题（默认） | MiSans | 14px | 330 | 100% | 0 | `rgba(0,0,0,0.6)` | `Body/Body 2` + `miuix_default_color_on_surface_tertiary` |
| 副标题（选中/禁用） | MiSans | 14px | 330 | 100% | 0 | 继承主标题色 | `Body/Body 2` |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 菜单背景色 | `#FFFFFF` | `miuix_default_color_surface_highest` |
| 文字色-主（默认） | `#000000` | `miuix_default_color_on_surface` |
| 文字色-次（副标题） | `rgba(0,0,0,0.6)` | `miuix_default_color_on_surface_tertiary` |
| 文字色-禁用 | `rgba(0,0,0,0.3)` | `miuix_default_color_on_surface_octonary` |
| 选中色（文字+图标） | `#3482FF` | `miuix_default_color_primary` |
| 列表项悬停背景 | `rgba(0,0,0,0.04)` | — |
| 列表项按压背景 | `rgba(0,0,0,0.1)` | — |
| 分割线颜色 | `rgba(0,0,0,0.1)` | `miuix_default_color_surface_container_high` |

---

## 变体

### 组件集 1: .近手菜单（菜单容器）

#### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `类型` | `近手菜单` / `最大宽度-近手菜单` / `自定义菜单` | 控制菜单宽度和结构 |
| 行数 | `行数` | `单行` / `双行` | 控制列表项是否显示副标题 |

共计 **3 × 2 = 6 个变体**。

#### 变体差异表

> 以「类型=近手菜单, 行数=单行」为基准。

##### 按类型分组

| 属性 | `近手菜单` | `最大宽度-近手菜单` | `自定义菜单` |
|-----|-----------|------------------|------------|
| 列表项 `width` | `184px` | `272px` | `184px` |
| 容器 `max-width` | 未设置 | `288px` | 未设置 |
| 分割线 | 无 | 无 | 有（底部操作项前） |
| 底部操作项 | 无 | 无 | 有（"自定义"入口） |

##### 按行数分组

| 属性 | `单行` | `双行` |
|-----|-------|-------|
| 副标题（Subtitle） | 隐藏 | 显示 |
| 列表项 `padding` | `10px 12px` | `11px 12px` |

#### 类型=自定义菜单 详情

自定义菜单在标准列表项下方增加了：

1. **分割线**：`.MenuItem` 容器内包含 `Divider-Line` SVG
2. **底部操作项**：独立样式的列表项，顶部圆角 `16px`，文本为"自定义"
3. 底部操作项的 `gap` 为 `8px`（区别于标准列表项的 `10px`），`padding` 水平方向为 `14px`（单行）或 `16px`（双行）

### 组件集 2: .近手菜单列表（列表项）

#### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 位置 | `位置` | `中间层` | 列表项在菜单中的位置 |
| 前置图标 | `前置图标` | `有` / `无` | 是否显示前置图标 |
| 状态 | `状态` | `默认` / `选中` / `悬停` / `按压` / `禁用` | 交互状态 |

共计 **1 × 2 × 5 = 10 个变体**。

#### 变体差异表

##### 按前置图标分组

| 属性 | `无` | `有` |
|-----|------|------|
| Leading Icon | 不存在 | 显示 24×24 图标 |
| Content 布局 | `flex-direction: column` | `flex-direction: row`（图标与文本水平排列） |

##### 按状态分组（前置图标=无）

| 属性 | `默认` | `选中` | `悬停` | `按压` | `禁用` |
|-----|--------|-------|--------|-------|--------|
| `background-color` | 透明 | 透明 | `rgba(0,0,0,0.04)` | `rgba(0,0,0,0.1)` | 透明 |
| 主标题 `color` | `#000000` | `#3482FF` | `#000000` | `#000000` | `rgba(0,0,0,0.3)` |
| 副标题 `color` | `rgba(0,0,0,0.6)` | 继承主标题色 | `rgba(0,0,0,0.6)` | `rgba(0,0,0,0.6)` | 继承主标题色 |
| .TrailingIcon `opacity` | `0` | `1` | `0` | `0` | `0` |
| 勾选图标 `color` | — | `#3482FF` | — | — | — |
| `gap` | `10px` | `10px` | `10px` | `10px` | `8px` |

##### 按状态分组（前置图标=有）

| 属性 | `默认` | `选中` | `悬停` | `按压` | `禁用` |
|-----|--------|-------|--------|-------|--------|
| `background-color` | 透明 | 透明 | `rgba(0,0,0,0.04)` | `rgba(0,0,0,0.1)` | 透明 |
| 主标题 `color` | `#000000` | `#3482FF` | `#000000` | `#000000` | `rgba(0,0,0,0.3)` |
| 前置图标 `color` | `#000000` | `#3482FF` | `#000000` | `#000000` | `rgba(0,0,0,0.3)` |
| .TrailingIcon `opacity` | `0` | `1` | `0` | `0` | `0` |
| `gap` | `10px` | `10px` | `10px` | `10px` | `8px` |

---

## 交互状态

> 以「默认态」为基准，其他状态仅列出**发生变化**的属性。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态） | — |
| `hover` | 鼠标悬停列表项 | `background-color` | `rgba(0,0,0,0.04)` | — |
| `active` | 鼠标按下 / 触摸 | `background-color` | `rgba(0,0,0,0.1)` | — |
| `selected` | 当前项被选中 | 主标题 `color` | `#3482FF` | `miuix_default_color_primary` |
| `selected` | 当前项被选中 | 前置图标 `color` | `#3482FF` | `miuix_default_color_primary` |
| `selected` | 当前项被选中 | .TrailingIcon `opacity` | `1` | — |
| `disabled` | `disabled=true` | 主标题 `color` | `rgba(0,0,0,0.3)` | `miuix_default_color_on_surface_octonary` |
| `disabled` | `disabled=true` | 前置图标 `color` | `rgba(0,0,0,0.3)` | `miuix_default_color_on_surface_octonary` |
| `disabled` | `disabled=true` | `gap` | `8px` | — |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

### PopupMenus（菜单容器）

```typescript
interface PopupMenusProps {
  /** 菜单类型，控制宽度和结构 */
  type: '近手菜单' | '最大宽度-近手菜单' | '自定义菜单';
  /** 列表项行数模式 */
  rows: '单行' | '双行';
  /** 菜单项列表 */
  items: PopupMenuItemProps[];
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 类型 | Variant | `type` | `近手菜单` | 控制菜单宽度和结构 |
| 行数 | Variant | `rows` | `单行` | 控制列表项行数 |

### PopupMenuItem（菜单列表项）

```typescript
interface PopupMenuItemProps {
  /** 列表项位置 */
  position: '中间层';
  /** 是否显示前置图标 */
  leadingIcon?: ReactNode;
  /** 交互状态 */
  state: '默认' | '选中' | '悬停' | '按压' | '禁用';
  /** 是否显示副标题（双行模式） */
  showSubtitle?: boolean;
  /** 主标题文本 */
  title: string;
  /** 副标题文本 */
  subtitle?: string;
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 位置 | Variant | `position` | `中间层` | 列表项位置类型 |
| 前置图标 | Variant | `leadingIcon` | `无` | 是否显示前置图标 |
| 状态 | Variant | `state` | `默认` | 交互状态 |
| propValue | Boolean | `showSubtitle` | `true` | 是否显示副标题 |

---

## 使用指南

### 何时使用

- **快速选择场景**：使用「近手菜单」类型，当用户需要从少量选项（≤8项）中快速选择时，如邮件账户切换、排序方式选择
- **长文本选项场景**：使用「最大宽度-近手菜单」类型，当选项文本较长需要更多显示空间时，如邮箱地址选择
- **需要自定义入口场景**：使用「自定义菜单」类型，当选项列表末尾需要提供额外的自定义操作入口时，如重复频率选择（永不、明天、每周... + 自定义）
- **需要副标题补充信息**：使用「双行」模式，当选项需要额外描述信息时，如账户名 + 邮箱地址
- **需要图标辅助识别**：配合「前置图标=有」，当选项需要通过图标增强辨识度时

### 何时不使用

- **操作项超过 8 个**：应使用 ActionSheet（操作面板）或独立页面代替
- **需要复杂表单输入**：应使用 Dialog（对话框）或 BottomSheet 代替
- **纯导航场景**：应使用 Sidebar（侧边导航栏）或 BottomNavigation（底部导航栏）代替
- **需要多选**：当前组件仅支持单选（单个勾选标记），多选场景应使用 Checkbox 列表代替

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 选项文本保持简洁，优先使用「近手菜单」类型 | 所有场景都使用「最大宽度-近手菜单」 | 过宽的菜单影响近手操作的便捷性 |
| 选中项通过蓝色文字 + 勾选图标双重标识 | 仅依赖颜色区分选中状态 | 确保色觉障碍用户也能识别选中态 |
| 保持菜单项数量 ≤ 8 个 | 在近手菜单中放置过多选项 | 菜单过长影响操作效率和可视性 |
| 禁用项保留在列表中并置灰显示 | 直接隐藏不可用的选项 | 用户需要知道该选项存在但当前不可用 |
| 自定义菜单中的分割线用于区分常规选项与自定义入口 | 在标准菜单中添加分割线 | 保持标准菜单的简洁性 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `miuix_default_color_surface_highest` | `#FFFFFF` | color | 菜单容器背景色 |
| `miuix_default_color_on_surface` | `#000000` | color | 默认态文字色 |
| `miuix_default_color_on_surface_tertiary` | `rgba(0,0,0,0.6)` | color | 副标题文字色 |
| `miuix_default_color_on_surface_octonary` | `rgba(0,0,0,0.3)` | color | 禁用态文字色、图标色 |
| `miuix_default_color_primary` | `#3482FF` | color | 选中态文字色、图标色、勾选标记 |
| `miuix_default_color_surface_container_high` | `rgba(0,0,0,0.1)` | color | 分割线颜色 |
| `miuix_theme_radius_demi_big` | `24px` | radius | 菜单容器圆角 |
| `miuix_theme_radius_common` | `16px` | radius | 自定义菜单底部操作项顶部圆角 |
| `miuix_theme_radius_medium` | `20px` | radius | 预留圆角 Token |
| `miuix_font_size_body1` | `16px` | font-size | 主标题字号 |
| `miuix_font_weight_body1` | `330` | font-weight | 主标题字重 |
| `miuix_font_size_body2` | `14px` | font-size | 副标题字号 |
| `miuix_font_weight_body2` | `330` | font-weight | 副标题字重 |

---

## 设计注释

> 1. 菜单容器整体采用 `border-radius: 24px` 的大圆角设计，与 HyperOS4 的圆润视觉语言一致。
> 2. 列表项采用 `border-radius: 14px` 的内圆角，悬停和按压时的背景色变化限定在各列表项区域内。
> 3. 存在两个隐藏的"玻璃"材质变体（`近手菜单组件/Light/玻璃（OS4禁用）` 和 `近手菜单组件/Dark/玻璃（OS4禁用）`），均标注为 OS4 禁用状态，当前版本不使用。
> 4. 前置图标使用 `HyperOS_Symbols_VF` 可变字体（Variable Font），图标尺寸为 18px，容器为 24×24px。
> 5. 勾选标记（Checkmark）在未选中状态下通过 `opacity: 0` 隐藏，而非从 DOM 中移除，以保持列表项宽度一致。
> 6. 自定义菜单的分割线通过 SVG 资源渲染，非纯 CSS `border`。
> 7. 「位置」维度当前仅有「中间层」一个值，未来可能扩展为顶层/底层以支持不同圆角样式。
