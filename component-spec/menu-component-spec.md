---
component: Menu
description: HyperOS 系统级菜单组件，包含下拉菜单、选择菜单、分组菜单、二级菜单和水平操作栏等多种形态
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=82824-19605
figma_node_id: "82824:19605"
variants: "3 component sets: DropdownMenu (10 types), MenuItem (5 types × 4 states), HorizontalMenu (3 quantities), TrailingIcon (3 types)"
tokens_used: 18
---

# 菜单 Menu

> HyperOS 系统级上下文菜单组件，用于在用户触发操作后弹出一组可选项。支持普通列表、选择、分组、二级导航等多种菜单形态，以及水平操作栏（HorizontalMenu）模式。采用毛玻璃（Glass）视觉风格，配合圆角卡片和阴影层级体现 HyperOS 设计语言。

## 预览

![Menu 组件全部变体预览](figma-screenshot-82824-19605.png)

---

## 组件结构

```
Menu-Component-Spec                               // FRAME | 82824:19605
├── Header-ComponentInstance                       // INSTANCE | 82824:19606
├── Menu (预览区)                                  // FRAME | 78297:8566
├── .DropdownMenu                                  // FRAME (COMPONENT_SET) | 28784:29717
│   ├── 类型=下拉菜单                              // COMPONENT | 28784:29564
│   │   ├── MenuItem-Row-1~8                       // INSTANCE | ...
│   │   │   ├── MenuItem-Content-Row               // FRAME
│   │   │   │   ├── Leading-Icon                   // INSTANCE (24×24)
│   │   │   │   └── Text                           // TEXT
│   ├── 类型=最大宽度-下拉菜单                      // COMPONENT | 28784:29560
│   ├── 类型=分组菜单                              // COMPONENT | 28784:29561
│   │   ├── MenuItem-Row-1~7                       // INSTANCE
│   │   └── Divider-Row                            // INSTANCE
│   ├── 类型=最大宽度-分离菜单                      // COMPONENT | 28784:29557
│   ├── 类型=选择菜单                              // COMPONENT | 28784:29555
│   │   ├── SelectionItem-Row-1~6                  // INSTANCE
│   │   ├── Divider-Row                            // INSTANCE
│   │   └── SelectionItem-Row-7 (选中态)           // INSTANCE
│   │       ├── Leading-Icon-Selected              // INSTANCE (primary color)
│   │       ├── Text (primary color)               // TEXT
│   │       └── Trailing-Checkmark                 // INSTANCE
│   ├── 类型=进二级菜单                            // COMPONENT | 28784:31039
│   │   ├── SubMenuItem-Row-1~4                    // INSTANCE
│   │   ├── Divider-Row                            // INSTANCE
│   │   └── SubMenuItem-Row-5~6 (带箭头)           // INSTANCE
│   │       ├── Leading-Icon                       // INSTANCE
│   │       ├── Text                               // TEXT
│   │       └── Trailing-Arrow                     // INSTANCE (.TrailingIcon)
│   ├── 类型=最大宽度-选择菜单                      // COMPONENT | 28784:29554
│   ├── 类型=二级菜单                              // COMPONENT | 45580:19514
│   ├── 类型=分组菜单-多选                          // COMPONENT | 80596:9866
│   └── 类型=下拉菜单混合分组                       // COMPONENT | 80679:55754
├── .HorizontalMenu                                // FRAME (COMPONENT_SET) | 28784:31009
│   ├── 数量=3个                                   // COMPONENT | 28784:29995
│   │   ├── ActionItem-1                           // FRAME
│   │   │   ├── Icon                               // TEXT (symbol font)
│   │   │   └── Label                              // TEXT
│   │   ├── ActionItem-2                           // FRAME
│   │   └── ActionItem-3                           // FRAME
│   ├── 数量=2个                                   // COMPONENT | 28784:29994
│   └── 数量=1个                                   // COMPONENT | 28784:29993
├── .MenuItem                                      // FRAME (COMPONENT_SET) | 9631:27553
│   ├── 类型=下拉菜单普通列表, 状态=默认            // COMPONENT | 9631:27264
│   ├── 类型=下拉菜单普通列表, 状态=悬停            // COMPONENT | 82354:4022
│   ├── 类型=下拉菜单普通列表, 状态=按压            // COMPONENT | 82354:4064
│   ├── 类型=下拉菜单普通列表, 状态=禁用            // COMPONENT | 82354:4106
│   ├── 类型=下拉菜单选择, 状态=默认                // COMPONENT | 9631:27262
│   ├── 类型=下拉菜单选择, 状态=悬停                // COMPONENT | 82354:4017
│   ├── 类型=下拉菜单选择, 状态=按压                // COMPONENT | 82354:4059
│   ├── 类型=下拉菜单选择, 状态=禁用                // COMPONENT | 82354:4101
│   ├── 类型=下拉菜单进二级, 状态=默认              // COMPONENT | 9631:27267
│   ├── 类型=下拉菜单进二级, 状态=悬停              // COMPONENT | 82354:4012
│   ├── 类型=下拉菜单进二级, 状态=按压              // COMPONENT | 82354:4054
│   ├── 类型=下拉菜单进二级, 状态=禁用              // COMPONENT | 82354:4096
│   ├── 类型=分割线, 状态=默认                      // COMPONENT | 9631:27269
│   └── 类型=分组标题, 状态=默认                    // COMPONENT | 86366:76499
└── .TrailingIcon                                  // FRAME (COMPONENT_SET) | 13821:2346
    ├── 类型=二级                                  // COMPONENT | 13821:2340
    ├── 类型=选中                                  // COMPONENT | 43336:55002
    └── 类型=收起                                  // COMPONENT | 43336:55000
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| .DropdownMenu | COMPONENT_SET | `28784:29717` | 下拉菜单容器，包含 10 种类型变体 |
| .MenuItem | COMPONENT_SET | `9631:27553` | 菜单项原子组件，5 种类型 × 最多 4 种状态 |
| .HorizontalMenu | COMPONENT_SET | `28784:31009` | 水平操作栏，按数量分为 1/2/3 个变体 |
| .TrailingIcon | COMPONENT_SET | `13821:2346` | 尾部图标，3 种类型：箭头/勾选/收起 |
| MenuItem-Content-Row | FRAME | 多个实例 | MenuItem 内容行，包含图标 + 文字 |
| Divider-Row | INSTANCE | 多个实例 | 分割线行 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器: DropdownMenu

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `200px`（默认）/ `288px`（最大宽度变体） | — |
| `min-width` | `200px` | — |
| `max-width` | `288px` | — |
| `height` | `auto`（hug） | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `flex-start` | — |
| `padding` | `8px` | `padding/padding_xs` |
| `background` | 毛玻璃效果（见下方玻璃样式） | `Pured/Pured_Regular_Glass_Light` |
| `border-radius` | `16px` | `hyperos_theme_radius_common` |
| `box-shadow` | `0px 24px 60px rgba(0,0,0,0.08), 0px 0px 40px rgba(0,0,0,0.06)` | `Shadow/Shadow_Regular` |
| `backdrop-filter` | `blur(60px)` | `FrostShadow/FrostEffect_Regular_ShadowOn` |
| `overflow` | `hidden` | — |

#### 玻璃效果详情（Light 模式）

| 效果类型 | 参数 | Token |
|---------|------|-------|
| `DROP_SHADOW` | `color: #00000014, offset: (0, 24), blur: 60, spread: 0` | `FrostShadow/FrostEffect_Regular_ShadowOn` |
| `DROP_SHADOW` | `color: #0000000F, offset: (0, 0), blur: 40, spread: 0` | `FrostShadow/FrostEffect_Regular_ShadowOn` |
| `INNER_SHADOW` | `color: #9D9D9D, offset: (0, 2), blur: 2, spread: 0` | `FrostShadow/FrostEffect_Regular_ShadowOn` |
| `BACKGROUND_BLUR` | `blur: 60` | `FrostShadow/FrostEffect_Regular_ShadowOn` |

### 子组件: MenuItem（默认态 — 下拉菜单普通列表）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%`（fill container） | — |
| `height` | `44px` | — |
| `min-height` | `44px` | — |
| `max-width` | `288px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `gap` | `8px` | `padding/padding_xs` |
| `padding` | `12px` | `padding/padding_sm` |
| `border-radius` | `16px` | `hyperos_theme_radius_common` |
| `background-color` | `transparent` | — |

### 子组件: MenuItem-Content-Row

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex` | `1 0 0` | — |
| `align-items` | `center` | — |
| `gap` | `8px` | `padding/padding_xs` |

### 子组件: Leading-Icon

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `24px` | — |
| `height` | `24px` | — |
| `flex-shrink` | `0` | — |
| `font-family` | `HyperOS Symbols VF` | — |
| `font-size` | `18px` | — |
| `color` | `#000000` | `hyperos-color-on-surface` |

### 子组件: Divider-Row

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%`（fill container） | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `padding` | `8px 12px` | — |

#### Divider-Line

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `flex` | `1 0 0` | — |
| `height` | `0.72px` | — |
| `background-color` | `rgba(0,0,0,0.06)` | — |

### 子组件: HorizontalMenu 容器

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `200px`（3 项）/ `136px`（2 项）/ `74px`（1 项） | — |
| `height` | `56px` | — |
| `display` | `flex` | — |
| `align-items` | `flex-start` | — |
| `padding` | `0 6px` | — |
| `background-color` | `#FFFFFF` | `hyperos-color-surface-highest` |
| `border-radius` | `24px` | `hyperos_theme_radius_demi_big` |
| `box-shadow` | `0px 0px 40px rgba(0,0,0,0.06), 0px 24px 60px rgba(0,0,0,0.08)` | `Shadow/Shadow_Regular` |

### 子组件: HorizontalMenu ActionItem

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex` | `1 0 0` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `padding` | `8px 2px` | — |

### 子组件: TrailingIcon

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `24px` | — |
| `height` | `24px` | — |
| `flex-shrink` | `0` | — |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| MenuItem 文字 | MiSans | 16px | 330 | 100% | 0 | `#000000` | `Body/Body 1` |
| HorizontalMenu 图标 | HyperOS Symbols UI | 18px | Regular | normal | 0 | `#000000` | — |
| HorizontalMenu 标签 | MiSans | 11px | Medium | 16px | 0 | `#000000` | `hyperos_font_size_footnote3` |
| TrailingIcon 箭头 | HyperOS Symbols UI | 15px | Regular / Medium | normal | 0 | `rgba(0,0,0,0.4)` | — |
| 选中态文字 | MiSans | 16px | 330 | 100% | 0 | `#3482FF` | `Body/Body 1` + `hyperos-color-primary` |
| 禁用态文字 | MiSans | 16px | 330 | 100% | 0 | `rgba(0,0,0,0.3)` | `Body/Body 1` + `on_Surface_right_icon` |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 菜单背景色（Light） | 毛玻璃 `#FFFFFF` 基底 | `Pured/Pured_Regular_Glass_Light` |
| 菜单背景色（Dark） | 毛玻璃 `#060606` 基底 | `Pured/Pured_Regular_Glass_Dark` |
| 水平菜单背景色 | `#FFFFFF` | `hyperos-color-surface-highest` |
| 文字色-主 | `#000000` | `hyperos-color-on-surface` |
| 文字色-次 | `rgba(0,0,0,0.6)` | `hyperos-color-on-surface-tertiary` |
| 文字色-辅 | `rgba(0,0,0,0.4)` | `hyperos-color-on-surface-quaternary` |
| 文字色-禁用 | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |
| 选中/激活色 | `#3482FF` | `hyperos-color-primary` |
| 悬停背景 | `rgba(0,0,0,0.04)` | — |
| 按压背景 | `rgba(0,0,0,0.1)` | `hyperos-color-surface-container-high` |
| 图标色-默认 | `#000000` (89% opacity) | `var(--color-icon)` |

---

## 变体

### 维度定义

#### DropdownMenu 变体（维度：类型）

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `类型` | `下拉菜单` / `最大宽度-下拉菜单` / `分组菜单` / `最大宽度-分离菜单` / `选择菜单` / `最大宽度-选择菜单` / `进二级菜单` / `二级菜单` / `分组菜单-多选` / `下拉菜单混合分组` | 控制菜单类型和内容组合 |

共计 **10 个变体**。

#### MenuItem 变体（维度：类型 × 状态）

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `类型` | `下拉菜单普通列表` / `下拉菜单选择` / `下拉菜单进二级` / `分割线` / `分组标题` | 菜单项类型 |
| 状态 | `状态` | `默认` / `悬停` / `按压` / `禁用` | 交互状态 |

共计 **5 × 4 = 14 个变体**（分割线和分组标题仅有默认态）。

#### HorizontalMenu 变体（维度：数量）

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 数量 | `数量` | `1个` / `2个` / `3个` | 操作项数量 |

共计 **3 个变体**。

#### TrailingIcon 变体（维度：类型）

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `propValue` | `二级` / `选中` / `收起` | 尾部图标类型 |

共计 **3 个变体**。

### 变体差异表

#### DropdownMenu 按「类型」分组

> 以「类型=下拉菜单」(200×368) 为基准，仅列出差异属性。

| 属性 | `下拉菜单` | `最大宽度-下拉菜单` | `分组菜单` | `选择菜单` | `进二级菜单` |
|-----|-----------|-------------------|-----------|-----------|-------------|
| `width` | `200px` | `288px` | `200px` | `200px` | `200px` |
| `height` | `368px` | `324px` | `388px` | `296px` | `296px` |
| 内含分割线 | 否 | 否 | 是 | 是 | 是 |
| 含选中态项 | 否 | 否 | 否 | 是（带 Checkmark） | 否 |
| 含二级箭头 | 否 | 否 | 否 | 否 | 是（Trailing-Arrow） |
| 列表项数 | 8 | 8 | 7+分割线 | 6+分割线+选中项 | 4+分割线+2 导航项 |

#### HorizontalMenu 按「数量」分组

| 属性 | `3个` | `2个` | `1个` |
|-----|-------|-------|-------|
| `width` | `200px` | `136px` | `74px` |
| `height` | `56px` | `56px` | `56px` |
| ActionItem 数量 | 3 | 2 | 1 |

#### TrailingIcon 按「类型」分组

| 属性 | `二级` | `选中` | `收起` |
|-----|--------|-------|-------|
| 图标类型 | 右箭头 (chevron) | 勾选 (checkmark) | 下箭头旋转-90° |
| `font-family` | HyperOS Symbols UI | — (使用图片资源) | HyperOS Symbols UI |
| `font-size` | `15px` | — | `15px` |
| `color` | `rgba(0,0,0,0.4)` | `#3482FF` | `rgba(0,0,0,0.4)` |
| `transform` | — | — | `rotate(-90deg)` |

---

## 交互状态

> 以「默认态」为基准，其他状态仅列出**发生变化**的属性。

### MenuItem — 下拉菜单普通列表

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态） | — |
| `hover` | 鼠标悬停 | `background-color` | `rgba(0,0,0,0.04)` | — |
| `active` | 鼠标按下 / 触摸 | `background-color` | `rgba(0,0,0,0.1)` | `hyperos-color-surface-container-high` |
| `disabled` | `disabled=true` | `color`（文字） | `rgba(0,0,0,0.3)` | `on_Surface_right_icon` |
| `disabled` | `disabled=true` | `color`（图标） | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |
| `disabled` | `disabled=true` | `border-radius` | `14px`（从 16px 变化） | — |

### MenuItem — 下拉菜单选择

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态，同普通列表） | — |
| `selected` | 选中 | `color`（文字） | `#3482FF` | `hyperos-color-primary` |
| `selected` | 选中 | `color`（图标） | `#3482FF` | `hyperos-color-primary` |
| `selected` | 选中 | 尾部图标 | 显示 Checkmark | — |
| `hover` | 鼠标悬停 | `background-color` | `rgba(0,0,0,0.04)` | — |
| `active` | 鼠标按下 | `background-color` | `rgba(0,0,0,0.1)` | `hyperos-color-surface-container-high` |
| `disabled` | `disabled=true` | `color` | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |

### MenuItem — 下拉菜单进二级

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态，带 Trailing-Arrow） | — |
| `hover` | 鼠标悬停 | `background-color` | `rgba(0,0,0,0.04)` | — |
| `active` | 鼠标按下 | `background-color` | `rgba(0,0,0,0.1)` | `hyperos-color-surface-container-high` |
| `disabled` | `disabled=true` | `color` | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

### DropdownMenu

```typescript
interface DropdownMenuProps {
  /** 菜单类型 */
  type: '下拉菜单' | '最大宽度-下拉菜单' | '分组菜单' | '最大宽度-分离菜单' | '选择菜单' | '最大宽度-选择菜单' | '进二级菜单' | '二级菜单' | '分组菜单-多选' | '下拉菜单混合分组';
}
```

### MenuItem

```typescript
interface MenuItemProps {
  /** 菜单项类型 */
  type: '下拉菜单普通列表' | '下拉菜单选择' | '下拉菜单进二级' | '分割线' | '分组标题';
  /** 交互状态 */
  state: '默认' | '悬停' | '按压' | '禁用';
  /** 是否显示前置图标 */
  showIcon?: boolean; // 默认: true
}
```

### HorizontalMenu

```typescript
interface HorizontalMenuProps {
  /** 操作项数量 */
  count: '1个' | '2个' | '3个';
}
```

### TrailingIcon

```typescript
interface TrailingIconProps {
  /** 图标类型 */
  propValue: '二级' | '选中' | '收起'; // 默认: '二级'
}
```

| Figma 属性名 | 类型 | 对应组件 | 对应 Prop | 默认值 | 说明 |
|-------------|------|---------|----------|-------|------|
| 类型 | Variant | DropdownMenu | `type` | `下拉菜单` | 菜单类型 |
| 类型 | Variant | MenuItem | `type` | `下拉菜单普通列表` | 菜单项类型 |
| 状态 | Variant | MenuItem | `state` | `默认` | 交互状态 |
| 数量 | Variant | HorizontalMenu | `count` | `3个` | 操作项数量 |
| propValue | Variant | TrailingIcon | `propValue` | `二级` | 尾部图标类型 |
| showIcon | Boolean | MenuItem | `showIcon` | `true` | 是否显示前置图标 |

---

## 使用指南

### 何时使用

- **上下文操作**：用户长按或右键触发时，使用「下拉菜单」展示可执行操作列表
- **单选切换**：切换排序方式、视图模式等需要单选确认的场景，使用「选择菜单」
- **分类操作**：操作较多需要分组时，使用「分组菜单」通过分割线区隔不同类别
- **多级导航**：操作项有子选项时，使用「进二级菜单」引导用户进入下一层
- **快捷操作栏**：在长按气泡等场景中，使用「HorizontalMenu」提供 1~3 个高频操作按钮
- **多选操作**：需要同时选中多项的场景，使用「分组菜单-多选」

### 何时不使用

- **超过 8 个选项的长列表**：应使用 ActionSheet（操作面板）或 BottomSheet 代替
- **需要复杂表单输入**：应使用 Dialog 或独立页面代替
- **导航场景**：应使用 NavigationBar 或 TabBar 代替
- **通知或提示**：应使用 Toast 或 Snackbar 代替

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 菜单项文字简洁，控制在一行内 | 使用过长的菜单项描述文字 | 菜单宽度有限（200~288px），过长文字会被截断 |
| 使用分割线逻辑分组相关操作 | 所有操作平铺不分组 | 分组有助于用户快速定位目标操作 |
| 破坏性操作（如删除）放在最后并使用危险色 | 破坏性操作放在菜单首位 | 防止用户误操作 |
| 选中态使用 Primary 色标识当前选项 | 不提供当前选中的视觉反馈 | 用户需要明确知道当前选中项 |
| HorizontalMenu 限制在 3 个以内操作 | 在 HorizontalMenu 放置超过 3 个操作 | 水平空间有限，操作过多影响可点击性 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `hyperos-color-on-surface` | `#000000` | color | 菜单项文字色、图标色 |
| `hyperos-color-primary` | `#3482FF` | color | 选中态文字、选中态图标 |
| `hyperos-color-surface-highest` | `#FFFFFF` | color | HorizontalMenu 背景色 |
| `hyperos_color_surface` | `#FFFFFF` | color | 基础面板颜色 |
| `hyperos-color-surface-container-high` | `rgba(0,0,0,0.1)` | color | 按压态背景 |
| `hyperos-color-on-surface-tertiary` | `rgba(0,0,0,0.6)` | color | 次级文字色 |
| `hyperos-color-on-surface-quaternary` | `rgba(0,0,0,0.4)` | color | TrailingIcon 箭头色 |
| `hyperos-color-on-surface-octonary` | `rgba(0,0,0,0.3)` | color | 禁用态图标色 |
| `文字图标色/on_Surface_right_icon` | `rgba(0,0,0,0.3)` | color | 禁用态文字色 |
| `var(--color-icon)` | `rgba(0,0,0,0.89)` | color | 图标默认色 |
| `padding/padding_xs` | `8px` | spacing | DropdownMenu 内边距、内容行 gap |
| `padding/padding_sm` | `12px` | spacing | MenuItem 内边距 |
| `spacing-xl` | `16px` | spacing | 通用间距 |
| `hyperos_theme_radius_common` | `16px` | radius | DropdownMenu 圆角、MenuItem 圆角 |
| `hyperos_theme_radius_demi_big` | `24px` | radius | HorizontalMenu 圆角 |
| `hyperos_theme_radius_medium` | `20px` | radius | — |
| `radius-3xl` | `20px` | radius | — |
| `hyperos_theme_radius_big` | `36px` | radius | — |
| `hyperos_font_size_body1` | `16px` | font-size | MenuItem 文字字号 |
| `hyperos_font_weight_body1` | `330` | font-weight | MenuItem 文字字重 |
| `hyperos_font_size_footnote3` | `11px` | font-size | HorizontalMenu 标签字号 |
| `Body/Body 1` | `MiSans, Regular, 16px, 330, lh:100%, ls:0` | typography | MenuItem 文字完整样式 |
| `Pured/Pured_Regular_Glass_Light` | `#000000, #FFFFFF, #FFFFFF` | effect | Light 模式毛玻璃 |
| `Pured/Pured_Regular_Glass_Dark` | `#000000, #6C6C6C, #060606` | effect | Dark 模式毛玻璃 |
| `Shadow/Shadow_Regular` | `0px 24px 60px #00000014, 0px 0px 40px #0000000F` | shadow | DropdownMenu、HorizontalMenu 阴影 |
| `Shadow/Shadow_High` | `0px 36px 80px #00000014, 0px 0px 60px #0000000F` | shadow | 高层级阴影（二级菜单等） |
| `FrostShadow/FrostEffect_Regular_ShadowOn` | DROP_SHADOW + INNER_SHADOW + BLUR(60) | effect | 毛玻璃完整效果 |

---

## 设计注释

> 1. 菜单组件采用 HyperOS 标志性的**毛玻璃（Frosted Glass）**视觉风格，需要配合 `backdrop-filter: blur()` 和多层阴影实现。
> 2. Light 和 Dark 模式分别使用不同的毛玻璃 Token（`Pured_Regular_Glass_Light` vs `Pured_Regular_Glass_Dark`），颜色映射完全不同。
> 3. 菜单宽度默认 `200px`，当内容需要更多空间时可使用「最大宽度」变体扩展至 `288px`。
> 4. MenuItem 的 `border-radius` 在禁用态从 `16px` 变为 `14px`，这可能是设计稿中的精度差异，建议与设计团队确认。
> 5. HorizontalMenu 通常与 DropdownMenu 配合使用，出现在长按气泡的上方，作为快捷操作区域。
> 6. 图标使用 HyperOS 自有符号字体（`HyperOS Symbols VF` 和 `HyperOS Symbols UI`），非标准 icon 库。
> 7. 存在两个隐藏变体：`Menu 菜单/Light/玻璃（禁用）` 和 `Menu 菜单/Dark/玻璃（禁用）`，在 Figma 中标记为 `hidden`，可能用于特殊场景或已废弃。
