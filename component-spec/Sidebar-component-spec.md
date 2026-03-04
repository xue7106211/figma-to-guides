---
component: Sidebar
description: 侧边导航栏，用于平板/折叠屏等大屏设备中提供一级/二级导航，支持三种显示尺寸和三种面板材质
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=83981-33380
figma_node_id: "83981:33380"
variants: "2 dimensions (显示模式 × 材质), 9 combinations"
tokens_used: 12
---

# 侧边导航栏 Sidebar

> 用于平板、折叠屏等大屏设备的侧边栏导航组件，提供三种尺寸形态（LC 全展开、NLC 窄栏、Mini 图标栏）和三种面板材质（玻璃、模糊混色、纯色），支持分组菜单、数字尾标、新建操作等丰富的菜单内容类型。

## 预览

### 三种尺寸形态

![侧边导航栏 三种尺寸形态](http://localhost:3845/figma/screenshot/51136:184615)

### 三种面板材质

![侧边导航栏 三种面板材质](http://localhost:3845/figma/screenshot/80443:18827)

### 侧边栏（NLC 形态 / 玻璃材质）

![侧边栏 NLC 形态](http://localhost:3845/figma/screenshot/80474:9379)

### Mini 导航形态

![侧边栏 Mini 形态](http://localhost:3845/figma/screenshot/80730:6839)

### 菜单内容原子

![菜单内容原子](http://localhost:3845/figma/screenshot/52274:40009)

### 导航组件原子

![导航组件原子](http://localhost:3845/figma/screenshot/52274:40366)

### 应用图标

![应用图标集](http://localhost:3845/figma/screenshot/83257:138308)

---

## 组件结构

```
侧边导航栏 Sidebar                            // FRAME | 83981:33380
├── 导航栏尺寸/形态                             // FRAME | 51136:184615
│   ├── 显示：LC 导航=on                       // COMPONENT | 83143:4425
│   ├── 显示：NLC 导航=on                      // COMPONENT | 44810:11762
│   └── 显示：Mini 导航=on                     // COMPONENT | 80730:6839
├── 板子材质层                                  // FRAME | 80443:18827
│   ├── 材质选择=玻璃材质                       // COMPONENT | 80443:18828
│   ├── 材质选择=模糊混色                       // COMPONENT | 83215:3256
│   └── 材质选择=纯色面板                       // COMPONENT | 83215:3376
├── 菜单内容_原子                               // FRAME | 52274:40009
│   ├── 内容类型=默认内容                       // COMPONENT | 83257:137817
│   ├── 内容类型=默认内容 - 选中态              // COMPONENT | 83257:137805
│   ├── 内容类型=分组标题                       // COMPONENT | 83185:10364
│   ├── 内容类型=包含数字尾标                    // COMPONENT | 83185:10421
│   ├── 内容类型=新建文件夹                     // COMPONENT | 83185:10441
│   └── 内容类型=分割线                         // COMPONENT | 83185:10347
├── 导航组件_原子                               // FRAME | 52274:40366
│   ├── 导航类型=标题栏1                        // COMPONENT | 52274:40069
│   ├── 导航类型=标题栏2                        // COMPONENT | 83215:13928
│   ├── 导航类型=标题栏3                        // COMPONENT | 83215:13929
│   └── 导航类型=导航类型4                      // COMPONENT | 83215:13945
├── 侧边栏（NLC 实例）                          // COMPONENT | 80474:9379
│   └── 板子材质层                              // FRAME | 83215:13110
│       ├── 导航栏尺寸/形态                     // FRAME
│       │   ├── 导航组件_原子                   // FRAME
│       │   │   ├── 顶部功能栏                  // FRAME
│       │   │   └── 标题栏                      // FRAME
│       │   └── 内容区域                        // FRAME
│       │       └── 菜单内容列表                // FRAME
│       └── 面板效果层                          // overlay
├── 图标                                        // FRAME | 83257:138308
└── 应用专属图标集                              // FRAME | 106427:23323
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| 导航栏尺寸/形态 | FRAME | `51136:184615` | 展示三种导航尺寸形态的组件集 |
| 板子材质层 | FRAME | `80443:18827` | 展示三种面板材质效果的组件集 |
| 菜单内容_原子 | FRAME | `52274:40009` | 菜单项的 6 种内容类型原子组件 |
| 导航组件_原子 | FRAME | `52274:40366` | 标题栏和功能栏的 4 种原子组件 |
| 侧边栏 | COMPONENT | `80474:9379` | 主组件实例（NLC + 玻璃材质） |
| 图标 | FRAME | `83257:138308` | 文件管理等应用专用彩色图标集 |
| 应用专属图标集 | FRAME | `106427:23323` | 相册、文件管理、笔记、时钟、电话、计算器、日历等应用的导航图标 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器（侧边栏外层）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `flex-start` | — |
| `justify-content` | `center` | — |
| `padding-top` | `6px` | — |
| `padding-right` | `0` | — |
| `padding-bottom` | `12px` | — |
| `padding-left` | `12px` | — |

### 面板层（板子材质层）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `border-radius` | `24px` | — |
| `border` | `1px solid #F9F9F9` | `Stroke/Stroke_Regular_Light` |
| `overflow` | `hidden` | — |

### 子组件: 导航栏尺寸/形态 — LC 导航（全展开）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `width` | `413px` | — |
| `min-width` | `413px` | — |
| `height` | `800px` | — |
| `padding` | `6px 12px` | — |
| `gap` | `10px` | — |

### 子组件: 导航栏尺寸/形态 — NLC 导航（窄栏）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `width` | `260px` | — |
| `height` | `800px` | — |
| `padding` | `6px 12px` | — |
| `gap` | `10px` | — |

### 子组件: 导航栏尺寸/形态 — Mini 导航（图标栏）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `width` | `82px` | — |
| `height` | `800px` | — |
| `padding` | `6px 0` | — |

### 子组件: 导航组件_原子 — 顶部功能栏

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `flex-start` | — |
| `width` | `100%`（继承父级宽度） | — |
| `backdrop-filter` | `blur(33px)` | `模糊数值/Default`（部分） |
| `padding` | `6px 12px` | — |
| `overflow` | `clip` | — |

### 子组件: 导航组件_原子 — 右侧图标按钮

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `height` | `44px` | — |
| `gap` | `8px` | — |
| `align-items` | `center` | — |
| `justify-content` | `flex-end` | — |

### 子组件: 导航组件_原子 — 图标按钮（平面）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `width` | `44px` | — |
| `height` | `44px` | — |
| `padding` | `0 8px` | — |
| `border-radius` | `1000px` | — |

### 子组件: 导航组件_原子 — 标题栏

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `padding-top` | `4px` | — |
| `padding-right` | `24px` | — |
| `padding-bottom` | `10px` | — |
| `padding-left` | `12px` | — |

### 子组件: 内容区域

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `flex` | `1 0 0` | — |
| `width` | `100%`（LC: `389px` / NLC: `236px`） | — |
| `overflow` | `clip` | — |
| `gap` | `4px` | — |

### 子组件: 菜单内容_原子 — 默认内容

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `gap` | `12px` | — |
| `width` | `236px`（NLC） / `389px`（LC） | — |
| `padding` | `8px 12px` | — |
| `border-radius` | `100px` | — |

### 子组件: 菜单内容_原子 — 选中态

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `background-color` | `rgba(0,0,0,0.06)` | `miuix_default_color_surface_container_low` |
| `border-radius` | `100px` | — |

### 子组件: 菜单内容_原子 — 分割线

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `height` | `20px` | — |
| `align-items` | `flex-start` | — |
| `justify-content` | `center` | — |
| `padding` | `0 20px` | — |

### 子组件: 分割线线条

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%` | — |
| `height` | `0.5px` | — |
| `background-color` | `rgba(0,0,0,0.1)` | `miuix_default_color_outline` |

### 子组件: 图标

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `28px` | — |
| `height` | `28px` | — |
| `font-family` | `HyperOS Symbols UI` | — |
| `font-size` | `21px` | — |
| `color` | `#000000` | `miuix_default_color_on_surface` |

### 子组件: Mini 导航 — 图标容器

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `width` | `66px` | — |
| `padding` | `8px 12px` | — |
| `border-radius` | `100px` | — |

### 子组件: Mini 导航 — 图标容器（选中态）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `background-color` | `rgba(0,0,0,0.06)` | `miuix_default_color_surface_container_low` |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| 大标题 | MiSans | 32px | 330 | 100% | 0 | `#000000` | `miuix_font_size_title1` / `miuix_font_weight_title1` |
| 菜单文字 | MiSans Medium | 16px | 500 | 100% | 0 | `#000000` | `miuix_default_color_on_surface` |
| 分组标题 | MiSans | 14px | 400 | 100% | 0 | `rgba(0,0,0,0.6)` | `miuix_default_color_on_surface_tertiary` |
| 数字尾标 | MiSans | 12px | 400 | 100% | 0 | `rgba(0,0,0,0.6)` | `miuix_default_color_on_surface_tertiary` |
| 新建文件夹 | MiSans Medium | 16px | 500 | 100% | 0 | `#FFBB0F` | `全系统色板/Yellow` |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 文字色-主 | `#000000` | `miuix_default_color_on_surface` |
| 文字色-次 | `rgba(0,0,0,0.6)` | `miuix_default_color_on_surface_tertiary` |
| 菜单选中背景 | `rgba(0,0,0,0.06)` | `miuix_default_color_surface_container_low` |
| 导航容器背景 | `rgba(0,0,0,0.05)` | `miuix_default_color_container_nav` |
| 面板表面色 | `#FFFFFF` | `miuix_default_color_surface` |
| 分割线颜色 | `rgba(0,0,0,0.1)` | `miuix_default_color_outline` |
| 强调色（新建） | `#FFBB0F` | `全系统色板/Yellow` |
| 面板边框色 | `#F9F9F9` | — |

---

## 变体

### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 显示模式 | `显示：LC 导航` / `显示：NLC导航` / `显示：Mini 导航` | `LC` / `NLC` / `Mini` | 控制导航栏的宽度和内容展示方式，三者互斥 |
| 面板材质 | `材质选择` | `玻璃材质` / `模糊混色` / `纯色面板` | 控制面板的视觉材质效果 |

共计 **3 × 3 = 9 种组合**。

### 变体差异表

#### 按显示模式分组

> 以 NLC（窄栏）为基准。

| 属性 | `NLC`（基准） | `LC`（全展开） | `Mini`（图标栏） |
|-----|------------|-------------|--------------|
| `width` | `260px` | `413px` | `82px` |
| `min-width` | — | `413px` | — |
| `padding` | `6px 12px` | `6px 12px` | `6px 0` |
| 菜单项宽度 | `236px` | `389px` | `66px` |
| 标题栏 | 显示（单行标题） | 显示（单行标题） | 隐藏 |
| 大标题 | 显示 | 显示 | 隐藏 |
| 菜单图标 | 显示 | 显示 | 显示 |
| 菜单文字 | 显示 | 显示 | 隐藏 |
| 数字尾标 | 显示 | 显示 | 隐藏 |
| 顶部功能栏 | 返回按钮 | 返回按钮 | 侧栏展开按钮 |
| Mini 图标间距 | — | — | `gap: 12px` |

#### 按面板材质分组

> 以玻璃材质为基准。

| 属性 | `玻璃材质`（基准） | `模糊混色` | `纯色面板` |
|-----|--------------|---------|---------|
| 背景效果层 1 | `rgba(0,0,0,0.02)` | `rgba(255,255,255,0.6)` | `#FFFFFF` |
| 背景效果层 2 | `rgba(255,255,255,0.6)` soft-light | `rgba(255,255,255,0.6)` | — |
| 背景效果层 3 | `rgba(255,255,255,0.6)` hard-light | `rgba(255,255,255,0.6)` | — |
| `backdrop-filter` | `blur(40px)` (glass) | `blur(60px)` | 无 |
| `box-shadow` | `0px 0px 40px rgba(0,0,0,0.06), 0px 24px 60px rgba(0,0,0,0.08)` | `0px 0px 40px rgba(0,0,0,0.06), 0px 24px 60px rgba(0,0,0,0.08)` | `0px 12px 40px rgba(0,0,0,0.04), 0px 0px 20px rgba(0,0,0,0.02)` |
| 内阴影 | `inset 0px 2px 2px #9D9D9D` | `inset 0px 2px 2px #9D9D9D` | 无 |
| 适用 Token | `Pured/Pured_Regular_Glass_Light` | `Frost/Pured_Extra_Thin_Light` | `Base/Popup_Light` |
| 阴影 Token | `GlassShadow/GlassEffect_Regular_ShadowOn` | `FrostShadow/FrostEffect_Regular_ShadowOn` | `Shadow/Shadow_Low` |

#### 菜单内容类型

> 菜单内容_原子共有 6 种类型。

| 内容类型 | 结构 | 特殊样式 | nodeId |
|---------|------|---------|--------|
| 默认内容 | 图标 + 文字 | `border-radius: 100px` | `83257:137817` |
| 默认内容 - 选中态 | 图标 + 文字 | `background: rgba(0,0,0,0.06)`, `border-radius: 100px` | `83257:137805` |
| 分组标题 | 文字 + 展开箭头 | 文字 `14px` `rgba(0,0,0,0.6)`，箭头 `20×20` | `83185:10364` |
| 包含数字尾标 | 图标 + 文字 + 数字 | 数字 `12px` `rgba(0,0,0,0.6)` 右对齐 | `83185:10421` |
| 新建文件夹 | 图标 + 文字 | 图标和文字均为 `#FFBB0F` | `83185:10441` |
| 分割线 | 水平线 | `0.5px` 高 `rgba(0,0,0,0.1)`, 两侧 `padding: 20px` | `83185:10347` |

---

## 交互状态

> 以「默认态」为基准，其他状态仅列出**发生变化**的属性。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态） | — |
| `selected` | 用户选中菜单项 | `background-color` | `rgba(0,0,0,0.06)` | `miuix_default_color_surface_container_low` |
| `hover` | 鼠标悬停菜单项 | `background-color` | Figma 未定义，请由设计团队补充 | — |
| `active` | 鼠标按下 / 触摸 | `background-color` | Figma 未定义，请由设计团队补充 | — |
| `focused` | 键盘聚焦 | `outline` | Figma 未定义，请由设计团队补充 | — |
| `disabled` | `disabled=true` | `opacity` | Figma 未定义，请由设计团队补充 | — |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

### 侧边栏主组件

```typescript
interface SidebarProps {
  /** 控制导航栏显示模式，三者互斥 */
  displayMode: 'lc' | 'nlc' | 'mini';
  /** 面板材质效果 */
  material: 'glass' | 'frost' | 'solid';
  /** 大标题文字 */
  title?: string; // 默认: "大标题"
  /** 菜单项列表 */
  items: SidebarMenuItem[];
  /** 当前选中的菜单项 ID */
  activeItemId?: string;
  /** 顶部操作栏自定义图标 */
  headerActions?: ReactNode;
  /** 菜单项点击回调 */
  onItemClick?: (itemId: string) => void;
  /** 返回/侧栏按钮点击回调 */
  onBackClick?: () => void;
}
```

### 菜单内容原子

```typescript
interface SidebarMenuItemProps {
  /** 菜单内容类型 */
  contentType: 'default' | 'selected' | 'groupTitle' | 'withBadge' | 'createFolder' | 'divider';
  /** 菜单文字 */
  label?: string;
  /** 前置图标 */
  icon?: ReactNode;
  /** 数字尾标（仅 withBadge 类型） */
  badgeCount?: number;
  /** 是否展开（仅 groupTitle 类型） */
  expanded?: boolean;
}
```

### 导航栏尺寸变体

```typescript
interface SidebarSizeVariantProps {
  /** 是否显示 LC 全展开导航 */
  lc?: boolean; // 默认: false
  /** 是否显示 NLC 窄栏导航 */
  nlc?: boolean; // 默认: true
  /** 是否显示 Mini 图标导航 */
  mini?: boolean; // 默认: false
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 显示：LC 导航 | Boolean | `lc` | `false` | 全展开模式，宽 413px |
| 显示：NLC导航 | Boolean | `nlc` | `true` | 窄栏模式，宽 260px |
| 显示：Mini 导航 | Boolean | `mini` | `false` | 图标模式，宽 82px |
| 材质选择 | Variant | `material` | `glass` | 面板材质 |
| 内容类型 | Variant | `contentType` | `默认内容` | 菜单项内容类型 |
| 导航类型 | Variant | `navType` | `标题栏1` | 标题栏/功能栏类型 |
| 名称 (图标) | Variant | `iconName` | — | 图标名称 |
| app (图标) | Variant | `iconApp` | — | 图标所属应用 |

---

## 使用指南

### 何时使用

- **平板/折叠屏主导航**：使用「LC 导航」或「NLC 导航」形态，在大屏设备中提供应用的一级分类导航
- **窄侧边栏导航**：使用「NLC 导航」形态，适用于内容区域需要更多空间的场景
- **最小化导航**：使用「Mini 导航」形态，在空间极其有限时仅展示图标入口
- **毛玻璃视觉效果**：使用「玻璃材质」或「模糊混色」材质，在需要背景透视效果的场景下使用
- **朴素简洁风格**：使用「纯色面板」材质，在不需要模糊效果的场景下使用

### 何时不使用

- **手机端底部导航**：应使用 BottomNavigation（底部导航栏）代替
- **页面内二级 Tab 切换**：应使用 TabBar 代替
- **临时操作面板**：应使用 Drawer（抽屉）或 ActionSheet 代替
- **仅含 2-3 个入口**：应使用 SegmentedControl（分段控制器）代替

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 三种尺寸模式互斥使用，同一时刻只显示一种 | 同时显示多种尺寸模式 | 设计上三种模式代表不同的空间策略，同时显示会造成布局混乱 |
| Mini 模式仅保留最核心的导航图标（通常 3-5 个） | Mini 模式放置过多图标 | Mini 模式空间有限，图标过多影响辨识度 |
| 选中态使用系统 Token `surface_container_low` 背景色 | 自定义选中态背景色 | 保持与 HyperOS 设计系统的一致性 |
| 分组标题配合展开/收起箭头使用 | 分组标题没有交互反馈 | 用户需要明确的视觉提示来理解可折叠行为 |
| 新建文件夹操作使用黄色强调色 `#FFBB0F` | 新建操作使用默认黑色 | 强调色区分操作项和普通导航项 |
| 面板材质根据系统主题和背景选择 | 在纯色背景上使用玻璃/模糊材质 | 毛玻璃效果需要有背景内容才能体现透视感 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `miuix_default_color_on_surface` | `#000000` | color | 主文字色、图标色 |
| `miuix_default_color_on_surface_tertiary` | `rgba(0,0,0,0.6)` | color | 分组标题色、数字尾标色 |
| `miuix_default_color_surface_container_low` | `rgba(0,0,0,0.06)` | color | 菜单项选中背景 |
| `miuix_default_color_container_nav` | `rgba(0,0,0,0.05)` | color | 导航容器背景 |
| `miuix_default_color_surface` | `#FFFFFF` | color | 面板表面色（纯色面板） |
| `miuix_default_color_outline` | `rgba(0,0,0,0.1)` | color | 分割线颜色 |
| `全系统色板/Yellow` | `#FFBB0F` | color | 新建文件夹图标/文字色 |
| `miuix_font_size_title1` | `32px` | font-size | 大标题字号 |
| `miuix_font_weight_title1` | `330` | font-weight | 大标题字重 |
| `Pured/Pured_Regular_Glass_Light` | `#000000, #FFFFFF, #FFFFFF` | material | 玻璃材质背景层 |
| `Frost/Pured_Extra_Thin_Light` | `#FFFFFF, #FFFFFF, #FFFFFF` | material | 模糊混色背景层 |
| `Base/Popup_Light` | `#FFFFFF` | material | 纯色面板背景 |
| `GlassShadow/GlassEffect_Regular_ShadowOn` | `drop-shadow + inner-shadow + glass` | effect | 玻璃材质阴影效果 |
| `FrostShadow/FrostEffect_Regular_ShadowOn` | `drop-shadow + inner-shadow + blur` | effect | 模糊混色阴影效果 |
| `Shadow/Shadow_Low` | `drop-shadow` | effect | 纯色面板阴影效果 |
| `Stroke/Stroke_Regular_Light` | border style | stroke | 面板描边 |
| `模糊数值/Default` | `blur(66px)` | effect | 默认背景模糊值 |

---

## 设计注释

> 1. 三种导航尺寸（LC/NLC/Mini）为互斥的布尔属性组合，在 Figma 中通过 `显示：LC 导航`、`显示：NLC导航`、`显示：Mini 导航` 三个布尔属性控制，同一时刻仅一个为 `on`。
> 2. 面板材质层独立于导航尺寸形态，可自由组合；面板内阴影 `inset 0px 2px 2px #9D9D9D` 仅在玻璃和模糊混色材质中出现。
> 3. Mini 导航中顶部功能栏变为「侧栏展开」按钮，点击后应切换为 LC 或 NLC 模式。
> 4. 菜单内容区域的 `backdrop-filter: blur(33px)` 作用于导航组件原子层级，用于内容滚动时的模糊过渡效果。
> 5. 图标使用 HyperOS Symbols UI 图标字体（`21px`），应用专属图标为 `28×28` 的彩色 SVG/PNG 资源。
> 6. 菜单项高亮使用 `border-radius: 100px`（胶囊形），与 HyperOS 4 的整体设计语言一致。
> 7. 应用专属图标集覆盖：相册、文件管理、笔记、时钟、电话、计算器、日历等系统应用，每个应用包含多个子页面导航图标（如电话 → 通话/联系人/营业厅/拨号键盘）。
