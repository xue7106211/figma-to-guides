---
component: BottomNavigation
description: 小米 HyperOS4 底部导航栏组件，包含 Tab 栏、FAB 浮动按钮和渐变遮罩
figma_source: https://www.figma.com/design/eA5elewu0o86Fw1fqdOsNu/Xiaomi-Hyper-OS4-UI-Kit--Copy-?node-id=82817-4257
figma_node_id: "82817:4257"
variants: "多维度组合：3 种尺寸规格 × 2 种明暗模式 × 2-5 个 Tab 数量 × 3 种材质 × 3 种 Fab 功能 × 3 种遮罩场景"
tokens_used: 15
---

# 底部导航栏 BottomNavigation

> HyperOS4 系统级底部导航组件，由底部 Tab 栏、FAB 浮动操作按钮和渐变遮罩三部分组成，支持标准、Mini、横版三种尺寸规格以及亮色/暗色两种模式。

## 预览

![底部导航栏全部变体预览](http://localhost:3845/figma/screenshot/82817:4257)

---

## 组件结构

```
底部导航栏 Bottom navigation OS4         // FRAME | 82817:4257
├── 底部栏                               // FRAME | 80431:26739
│   ├── 遮罩                             // INSTANCE（渐变背景层，absolute）
│   ├── 底Tab材质                        // INSTANCE（Tab 栏容器含材质效果）
│   │   └── 底Tab                        // INSTANCE（Tab 项排列）
│   │       ├── tab组件 (选中)            // INSTANCE | 52117:25113
│   │       ├── tab组件 (未选中)          // INSTANCE | 52117:25212
│   │       └── ...更多 tab组件
│   └── Fab                              // INSTANCE（可选浮动按钮）
├── 底部栏_mini                          // FRAME | 82345:20575
├── 底部栏_横版本                        // FRAME | 82345:21373
├── tab组件                              // COMPONENT_SET | 52117:25213
├── .tab组件_mini                        // COMPONENT_SET | 82202:2397
├── .tab组件_横版本                      // COMPONENT_SET | 82218:10640
├── 底Tab                                // COMPONENT_SET | 28892:1150
├── 底Tab_mini                           // COMPONENT_SET | 82218:10032
├── 底Tab_横版本                         // COMPONENT_SET | 82277:3937
├── Fab                                  // COMPONENT_SET | 78092:6597
├── Fab_mini&横版本                      // COMPONENT_SET | 82345:21077
├── 遮罩                                 // COMPONENT_SET | 78093:8831
├── 遮罩_mini&横版本                     // COMPONENT_SET | 82345:20693
├── 底Tab材质                            // COMPONENT_SET | 78282:10976
├── 底Tab材质_mini                       // COMPONENT_SET | 82218:10385
├── 底Tab材质_横版本                     // COMPONENT_SET | 82277:4412
├── Fab材质板子                          // COMPONENT_SET | 82345:12971
└── 玻璃材质变体 (OS4 已禁用)            // SYMBOL（多个）
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| 底部栏 | FRAME | `80431:26739` | 标准尺寸完整底部栏（含遮罩 + Tab栏 + Fab） |
| 底部栏_mini | FRAME | `82345:20575` | Mini 尺寸底部栏 |
| 底部栏_横版本 | FRAME | `82345:21373` | 横屏/平板尺寸底部栏 |
| tab组件 | COMPONENT_SET | `52117:25213` | 单个 Tab 项（标准尺寸） |
| .tab组件_mini | COMPONENT_SET | `82202:2397` | 单个 Tab 项（Mini 尺寸） |
| .tab组件_横版本 | COMPONENT_SET | `82218:10640` | 单个 Tab 项（横版尺寸） |
| 底Tab | COMPONENT_SET | `28892:1150` | Tab 栏排列（标准尺寸） |
| 底Tab_mini | COMPONENT_SET | `82218:10032` | Tab 栏排列（Mini 尺寸） |
| 底Tab_横版本 | COMPONENT_SET | `82277:3937` | Tab 栏排列（横版尺寸） |
| Fab | COMPONENT_SET | `78092:6597` | 浮动操作按钮（标准 56px） |
| Fab_mini&横版本 | COMPONENT_SET | `82345:21077` | 浮动操作按钮（Mini/横版 44px） |
| 遮罩 | COMPONENT_SET | `78093:8831` | 底部渐变遮罩（标准 100px 高） |
| 遮罩_mini&横版本 | COMPONENT_SET | `82345:20693` | 底部渐变遮罩（Mini/横版 88px 高） |
| 底Tab材质 | COMPONENT_SET | `78282:10976` | Tab 栏材质容器（标准尺寸） |
| 底Tab材质_mini | COMPONENT_SET | `82218:10385` | Tab 栏材质容器（Mini 尺寸） |
| 底Tab材质_横版本 | COMPONENT_SET | `82277:4412` | Tab 栏材质容器（横版尺寸） |
| Fab材质板子 | COMPONENT_SET | `82345:12971` | Fab 材质效果容器 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 子组件: tab组件（单个 Tab 项）

![Tab 组件预览](http://localhost:3845/figma/screenshot/52117:25213)

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `66px`（独立态）/ 在栏内自适应 | — |
| `height` | `50px`（标准）/ `38px`（Mini / 横版） | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `border-radius` | `36px` | `miuix_theme_radius_big` |

#### 选中态（Light）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `background-color` | `rgba(0,0,0,0.08)` | `miuix_default_color_surface_container_medium` |

#### 选中态（Dark）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `background-color` | `rgba(159,159,159,0.2)` 叠加层 | — |
| `mix-blend-mode` | `color-dodge` | — |

#### 未选中态

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `background-color` | `transparent` | — |

#### 图标

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `28px` | — |
| `height` | `28px` | — |
| `font-family` | `HyperOS_Symbols_VF` | — |
| `font-size` | `21px` | — |
| `color`（Light） | `#000000` | `miuix_default_color_on_surface` |
| `color`（Dark） | `rgba(255,255,255,0.95)` | `miuix_default_color_on_surface` |

#### 文字标签

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `font-family` | `MiSans` | — |
| `font-weight` | `500`（Medium） | — |
| `font-size` | `11px` | `miuix_font_size_footnote2` |
| `line-height` | `normal` | — |
| `text-align` | `center` | — |
| `width` | `46px` | — |
| `height` | `16px` | — |
| `overflow` | `hidden` | — |
| `text-overflow` | `ellipsis` | — |
| `white-space` | `nowrap` | — |
| `color`（Light） | `#000000` | `miuix_default_color_on_surface` |
| `color`（Dark） | `rgba(255,255,255,0.95)` | `miuix_default_color_on_surface` |

---

### 子组件: 底Tab（Tab 栏排列）

![底 Tab 预览](http://localhost:3845/figma/screenshot/28892:1150)

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `padding` | `3px 13px 3px 3px` | — |
| `border-radius` | `28px` | — |

#### Tab 项宽度（标准尺寸）

| Tab 数量 | 单个 Tab 宽度 |
|----------|-------------|
| 5 个 | `75.6px` |
| 4 个 | `92px` |
| 3 个 | `88px` |
| 2 个 | `88px` |

#### Tab 项间距

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `margin-right` | `-10px`（重叠排列） | — |

---

### 子组件: 底Tab材质（Tab 栏容器材质）

![底 Tab 材质预览](http://localhost:3845/figma/screenshot/78282:10976)

#### 混色模糊材质（Frosted Blur）— Light

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `border-radius` | `28px` | — |
| `border` | `0.8px solid #F9F9F9` | `Stroke/Glass_Stroke_Middle_Light` |
| `box-shadow` | `0px 0px 40px 0px rgba(0,0,0,0.06), 0px 24px 60px 0px rgba(0,0,0,0.08)` | `Shadow/Shadow_Regular` |
| 内层阴影 | `inset 0px 2px 2px 0px #9D9D9D` | `FrostShadow/FrostEffect_Thin_ShadowOn` |

材质叠加层（由底到顶）：

| 层级 | `background-color` | `mix-blend-mode` | `backdrop-filter` |
|-----|--------------------|-----------------|--------------------|
| 1 | `rgba(0,0,0,0.02)` | `normal` | — |
| 2 | `rgba(255,255,255,0.6)` | `soft-light` | — |
| 3 | `rgba(255,255,255,0.4)` | `hard-light` | `blur(10px)` |

#### 混色模糊材质（Frosted Blur）— Dark

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `border` | `0.8px solid #333333` | `Stroke/Glass_Stroke_Middle_Dark` |
| `box-shadow` | 同 Light | `Shadow/Shadow_Regular` |
| 内层阴影 | `inset 0px 2px 2px 0px #9D9D9D` | `FrostShadow/FrostEffect_Thin_ShadowOn` |

材质叠加层（由底到顶）：

| 层级 | `background-color` | `mix-blend-mode` | `backdrop-filter` |
|-----|--------------------|-----------------|--------------------|
| 1 | `rgba(0,0,0,0.1)` | `normal` | — |
| 2 | `rgba(86,86,86,0.4)` | `luminosity` | — |
| 3 | `rgba(63,63,63,0.6)` | `overlay` | `blur(10px)` |

#### 纯色面板材质（Solid Panel）— Light

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `background-color` | `#FFFFFF` | `miuix_default_color_surface_high` / `Base/Popup_Light` |
| `border-radius` | `28px` | — |
| `box-shadow` | `0px 0px 40px 0px rgba(0,0,0,0.06), 0px 24px 60px 0px rgba(0,0,0,0.08)` | `Shadow/Shadow_Regular` |

#### 纯色面板材质（Solid Panel）— Dark

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `background-color` | `#242424` | `white/color-white-solid-30` / `Base/Popup_Dark` |
| `border-radius` | `28px` | — |
| `box-shadow` | 同 Light | `Shadow/Shadow_Regular` |

> **注意**：玻璃材质（Glass）在 OS4 中已禁用，不应使用。

---

### 子组件: Fab（浮动操作按钮）

![Fab 预览](http://localhost:3845/figma/screenshot/78092:6597)

| CSS 属性 | 值（标准） | 值（Mini/横版） | Token |
|---------|----------|--------------|-------|
| `width` | `56px` | `44px` | — |
| `height` | `56px` | `44px` | — |
| `border-radius` | `28px` | `22px` | — |
| `padding` | `3px` | `3px` | — |
| `border` | `1px solid rgba(252,252,252,0.2)` | 同左 | `Stroke/Glass_Stroke_Small_Light` |
| `box-shadow` | `0px 0px 40px 0px rgba(0,0,0,0.06), 0px 24px 60px 0px rgba(0,0,0,0.08)` | 同左 | `Shadow/Shadow_Regular` |
| 内层阴影 | `inset 0px 2px 2px 0px #9D9D9D` | 同左 | — |

#### Fab 功能变体渐变色

| 功能 | `background-image` | 图标 |
|-----|--------------------|----|
| 拨号 | `linear-gradient(12deg, rgba(102,242,125,0.9) 11.7%, rgba(73,225,98,0.9) 65.5%)` | 键盘图标（SVG） |
| 笔记 | `linear-gradient(12deg, rgba(255,220,145,0.9) 11.7%, rgba(255,193,49,0.9) 65.5%)` | add 图标（HyperOS_Symbols_VF） |
| 搜索 | 磨砂玻璃效果（`Pured/Pured_Extra_Thick_Light`） | search 图标（HyperOS_Symbols_VF） |

#### Fab 搜索功能材质

| 层级 | `background-color` | `mix-blend-mode` | `backdrop-filter` |
|-----|--------------------|-----------------|--------------------|
| 1 | `rgba(255,255,255,0.4)` | `plus-lighter` | — |
| 2 | `rgba(245,245,245,0.6)` | `normal` | `blur(10px)` |

Fab 图标通用尺寸：`28px × 28px`

---

### 子组件: 遮罩（底部渐变遮罩）

![遮罩预览](http://localhost:3845/figma/screenshot/78093:8831)

| CSS 属性 | 值（标准） | 值（Mini/横版） |
|---------|----------|--------------|
| `width` | `392px` | `392px` / `539px`（横版） |
| `height` | `100px` | `88px` |
| `display` | `flex` | `flex` |
| `justify-content` | `center` | `center` |
| `padding` | `3px` | `3px` |

#### 渐变色定义

| 使用场景 | 深色模式 | `background-image` |
|---------|---------|-------------------|
| 灰色背景 | no | `linear-gradient(to bottom, rgba(243,243,243,0), rgba(243,243,243,0.8) 50%, rgba(243,243,243,0.96))` |
| 灰色背景 | yes | `linear-gradient(to bottom, rgba(0,0,0,0), rgba(0,0,0,0.8) 50%, rgba(0,0,0,0.96))` |
| 白色背景 | no | `linear-gradient(to bottom, rgba(255,255,255,0), rgba(255,255,255,0.8) 50%, rgba(255,255,255,0.96))` |
| 白色背景 | yes | `linear-gradient(to bottom, rgba(0,0,0,0), rgba(0,0,0,0.8) 50%, rgba(0,0,0,0.96))` |
| 图片背景 | no/yes | `linear-gradient(to bottom, rgba(0,0,0,0), rgba(0,0,0,0.29) 75.2%)` |

---

### 子组件: 底部栏（完整组合）

![底部栏预览](http://localhost:3845/figma/screenshot/80431:26739)

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `gap` | `10px` | — |
| `padding-top` | `20px` | — |
| `padding-bottom` | `24px` | — |
| `padding-left` | `24px` | — |
| `padding-right` | `24px` | — |
| `position` | `relative` | — |

底部栏将遮罩作为绝对定位的背景层（`position: absolute; inset: 0`），Tab 栏和 Fab 为内容层。

---

## 变体

### 维度定义

#### 尺寸规格（贯穿所有子组件）

| 规格名称 | 适用场景 | Tab 栏高度 | Fab 尺寸 | 遮罩高度 |
|---------|---------|----------|---------|---------|
| 标准 | 竖屏手机 | `56px` | `56px` | `100px` |
| Mini | 紧凑模式 | `44px` | `44px` | `88px` |
| 横版本 | 横屏/平板 | `44px` | `44px` | `88px` |

#### tab组件

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 模式 | `模式` | `Light` / `Dark` | 亮暗色模式 |
| 状态 | `状态` | `选中` / `未选中` | 选中高亮状态 |

共计 **2 × 2 = 4 个变体**。

#### 底Tab

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 暗色模式 | `dark` | `yes` / `no` | 亮暗色模式 |
| Tab 数量 | `数量` | `2` / `3` / `4` / `5` | Tab 项数量 |

共计 **2 × 4 = 8 个变体**（每种尺寸规格各 8 个）。

#### 底Tab材质

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 材质 | `材质` | `混色模糊` / `纯色面板` | 背景材质效果 |
| 暗色模式 | `dark` | `yes` / `no` | 亮暗色模式 |

共计 **2 × 2 = 4 个变体**（每种尺寸规格各 4 个）。OS4 已禁用玻璃材质。

#### Fab

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 功能 | `功能` | `拨号` / `笔记` / `搜索` | Fab 图标和颜色 |

共计 **3 个变体**（标准和 Mini/横版各 3 个）。

#### Fab材质板子

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 材质 | `Property 1` | `模糊混色` / `纯色面板` | 背景材质效果 |
| 名称 | `名称` | `拨号` / `添加` / `搜索` | 功能类型 |
| 深色模式 | `深色模式` | `light` / `dark` | 亮暗色模式 |

共计 **2 × 3 × 2 = 12 个变体**。OS4 已禁用玻璃材质。

#### 遮罩

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 使用场景 | `使用场景` | `灰色背景` / `白色背景` / `图片背景` | 页面底色适配 |
| 深色模式 | `深色模式` | `yes` / `no` | 亮暗色模式 |

共计 **3 × 2 = 6 个变体**（标准和 Mini/横版各 6 个）。

#### 底部栏（完整组合）

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 是否打开Fab | `是否打开Fab` | `yes` / `no` | 是否显示 Fab 按钮 |
| 是否分开展示 | `是否分开展示` | `yes` / `no` | Tab 栏与 Fab 是否分离排列 |

标准/Mini 底部栏共 **3 个变体**（Fab=no 时无分开选项）；横版底部栏共 **2 个变体**（无分开展示维度）。

### 变体差异表

#### 按尺寸规格分组

| 属性 | 标准 | Mini | 横版本 |
|-----|------|------|-------|
| Tab 栏 `height` | `56px` | `44px` | `44px` |
| Tab 项 `height` | `50px` | `38px` | `38px` |
| Fab `size` | `56px` | `44px` | `44px` |
| 遮罩 `height` | `100px` | `88px` | `88px` |
| 横版 Tab 项 | 纵向图标+文字 | 纵向图标+文字 | 横向图标+文字（`105×38px`） |
| 横版 Tab 栏 `width` | `344px`（5tab） | `344px`（5tab） | `491px`（5tab） |

#### 底部栏按 Fab 状态分组

| 属性 | Fab=no | Fab=yes, 分开=no | Fab=yes, 分开=yes |
|-----|--------|-----------------|------------------|
| 布局 | Tab 栏居中 | Tab 栏 + Fab 同容器, `justify-between` | Tab 栏 + Fab 分离排列, `justify-between` |
| Tab 数量 | 通常 4-5 个 | 通常 3 个 | 通常 3 个 |
| 底部栏 `height` | `auto`（hug） | `100px` | `100px` |
| Fab 位置 | 不存在 | 与 Tab 栏同行右侧 | 与 Tab 栏分离右侧 |

---

## 交互状态

> 以「默认态」为基准，其他状态仅列出**发生变化**的属性。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态） | — |
| `selected` | 点击 Tab 项 | `background-color` | Light: `rgba(0,0,0,0.08)` / Dark: `rgba(159,159,159,0.2)` 叠加 | `miuix_default_color_surface_container_medium` |
| `unselected` | 非当前 Tab | `background-color` | `transparent` | — |
| `fab-pressed` | Figma 未定义，请由设计团队补充 | — | — | — |
| `disabled` | Figma 未定义，请由设计团队补充 | — | — | — |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

```typescript
interface TabItemProps {
  /** 亮暗色模式 */
  mode: 'Light' | 'Dark';
  /** 选中状态 */
  state: '选中' | '未选中';
  /** Tab 标签文字 */
  label?: string; // 默认: "选中项" / "未选中"
  /** Tab 图标 */
  icon?: ReactNode;
}

interface TabBarProps {
  /** 亮暗色模式 */
  dark: boolean; // 默认: false
  /** Tab 项数量 */
  count: '2' | '3' | '4' | '5'; // 默认: "5"
}

interface TabBarMaterialProps {
  /** 材质类型 */
  material: '混色模糊' | '纯色面板'; // 默认: "混色模糊"
  /** 亮暗色模式 */
  dark: boolean; // 默认: false
}

interface FabProps {
  /** 功能类型，决定图标和渐变色 */
  function: '拨号' | '笔记' | '搜索'; // 默认: "拨号"
}

interface FabMaterialProps {
  /** 材质类型 */
  material: '模糊混色' | '纯色面板'; // 默认: "模糊混色"
  /** 功能名称 */
  name: '拨号' | '添加' | '搜索';
  /** 深色模式 */
  darkMode: 'light' | 'dark'; // 默认: "light"
}

interface MaskProps {
  /** 使用场景（底色适配） */
  scene: '灰色背景' | '白色背景' | '图片背景'; // 默认: "灰色背景"
  /** 深色模式 */
  darkMode: boolean; // 默认: false
}

interface BottomNavigationProps {
  /** 是否显示 Fab */
  showFab: boolean; // 默认: false
  /** Tab 栏与 Fab 是否分开展示（仅 showFab=true 时有效） */
  separated: boolean; // 默认: false
  /** 尺寸规格 */
  size: 'standard' | 'mini' | 'landscape';
}
```

### Figma 属性映射表

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 模式 | Variant | `mode` | `Light` | Tab 项亮暗色 |
| 状态 | Variant | `state` | `选中` | Tab 项选中状态 |
| dark | Variant | `dark` | `no` | Tab 栏亮暗色 |
| 数量 | Variant | `count` | `5` | Tab 项数量 |
| 材质 | Variant | `material` | `混色模糊` | Tab 栏材质 |
| 功能 | Variant | `function` | `拨号` | Fab 功能类型 |
| 使用场景 | Variant | `scene` | `灰色背景` | 遮罩底色适配 |
| 深色模式 | Variant | `darkMode` | `no` | 遮罩暗色模式 |
| 是否打开Fab | Variant | `showFab` | `no` | 底部栏 Fab 开关 |
| 是否分开展示 | Variant | `separated` | `no` | Tab 栏与 Fab 分离 |

---

## 使用指南

### 何时使用

- **标准底部导航**：竖屏手机场景，使用「标准」尺寸规格，Tab 数量 3-5 个
- **紧凑底部导航**：需要节省纵向空间时，使用「Mini」尺寸规格
- **横屏/平板场景**：使用「横版本」尺寸规格，Tab 项改为图标+文字横向排列
- **需要快捷操作入口**：使用「Fab=yes」变体，将核心操作按钮（拨号、笔记、搜索等）置于底部栏右侧
- **需要适配不同背景色**：根据页面底色选择对应的遮罩变体（灰色/白色/图片背景）

### 何时不使用

- **仅有 1 个导航项**：应使用返回按钮或无底部导航
- **超过 5 个导航项**：应使用抽屉导航（Drawer）或更多菜单（More Menu）代替
- **临时浮层中**：应使用 Sheet 或 Dialog 内的操作按钮代替
- **内容区需要全屏展示**：应使用手势导航代替

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 使用 `混色模糊` 材质作为默认方案 | 使用玻璃材质 | OS4 已禁用玻璃材质 |
| 圆角使用**平滑圆角**（squircle） | 使用普通 CSS `border-radius` 圆角 | Figma 标注明确要求平滑圆角 |
| 根据页面底色选择对应遮罩变体 | 所有场景使用同一遮罩 | 错误的遮罩会导致底部过渡不自然 |
| Tab 项重叠排列（`margin-right: -10px`） | Tab 项之间留间距 | 设计规范要求 Tab 项紧密排列 |
| Fab 图标尺寸保持 `28px` | 缩放 Fab 图标 | 与系统图标栅格对齐 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `miuix_default_color_on_surface` | Light: `#000000` / Dark: `rgba(255,255,255,0.95)` | color | Tab 图标色、Tab 文字色 |
| `miuix_default_color_surface_container_medium` | Light: `rgba(0,0,0,0.08)` / Dark: `rgba(255,255,255,0.14)` | color | Tab 选中态背景 |
| `miuix_default_color_surface_high` | `#FFFFFF` | color | 纯色面板 Tab 栏背景（Light） |
| `miuix_theme_radius_big` | `36px` | radius | Tab 项圆角 |
| `miuix_theme_radius_medium` | `20px` | radius | 备用圆角 |
| `miuix_font_size_footnote2` | `11px` | font-size | Tab 标签字号 |
| `miuix_font_size_footnote3` | `11px` | font-size | 辅助文字字号 |
| `spacing-xl` | `16px` | spacing | 通用间距 |
| `radius-3xl` | `20px` | radius | 卡片圆角 |
| `white/color-white-solid-30` | `#242424` | color | 纯色面板 Tab 栏背景（Dark） |
| `✦/_icon/icon-default` | `rgba(0,0,0,0.9)` | color | 默认图标色 |
| `文字图标色/on_surface_button_disable` | `#FFFFFF` | color | Fab 笔记图标色 |
| `Base/Popup_Light` | `#FFFFFF` | color | 弹出面板背景（Light） |
| `Base/Popup_Dark` | `#242424` | color | 弹出面板背景（Dark） |
| `Shadow/Shadow_Regular` | `0px 0px 40px rgba(0,0,0,0.06), 0px 24px 60px rgba(0,0,0,0.08)` | effect | Tab 栏和 Fab 阴影 |
| `Shadow/Shadow_Low` | `0px 0px 20px rgba(0,0,0,0.02), 0px 12px 40px rgba(0,0,0,0.04)` | effect | 低层级阴影 |
| `FrostShadow/FrostEffect_Thin_ShadowOn` | 含 `DROP_SHADOW` + `INNER_SHADOW` + `BACKGROUND_BLUR(20)` | effect | 混色模糊材质综合效果 |
| `Pured/Pured_Thin_Glass_Light` | `#000000, #FFFFFF, #FFFFFF` | material | 混色模糊材质叠加层（Light） |
| `Pured/Pured_Thin_Glass_Dark` | `#000000, #565656, #3F3F3F` | material | 混色模糊材质叠加层（Dark） |
| `Pured/Pured_Extra_Thick_Light` | `#FFFFFF, #F5F5F5` | material | Fab 搜索功能磨砂材质（Light） |
| `Pured/Pured_Extra_Thick_Dark` | `#191919, #313131` | material | Fab 搜索功能磨砂材质（Dark） |
| `Stroke/Glass_Stroke_Middle_Light` | 浅色描边 | stroke | 混色模糊材质边框（Light） |
| `Stroke/Glass_Stroke_Middle_Dark` | 深色描边 | stroke | 混色模糊材质边框（Dark） |
| `Stroke/Glass_Stroke_Small_Light` | 浅色描边 | stroke | Fab 边框（Light） |
| `Stroke/Glass_Stroke_Small_Dark` | 深色描边 | stroke | Fab 边框（Dark） |
| `Glass Color/Light/绿色` | 绿色渐变 | gradient | Fab 拨号功能渐变色 |

---

## 设计注释

> 1. **圆角是平滑圆角**：所有圆角（Tab 项 36px、Tab 栏 28px、Fab 28px）均应使用平滑圆角（squircle / continuous corners），而非标准 CSS `border-radius`。
> 2. **OS4 禁用玻璃材质**：虽然 Figma 文件中保留了玻璃材质（Glass）变体，但 OS4 已明确禁用该材质，实现时应仅使用「混色模糊」和「纯色面板」两种材质。
> 3. **Tab 项重叠排列**：Tab 项之间使用 `margin-right: -10px` 实现重叠效果，选中项通过背景色区分，无需额外间距。
> 4. **三种尺寸规格**：标准、Mini、横版三套组件各自独立，横版的 Tab 项采用图标+文字横向排列（`105×38px`），与标准/Mini 的纵向排列不同。
> 5. **遮罩层为绝对定位**：遮罩（渐变背景）使用 `position: absolute; inset: 0` 覆盖整个底部栏，内容层（Tab 栏 + Fab）在其上方。
> 6. **Fab 颜色编码**：拨号=绿色渐变、笔记=黄色渐变、搜索=磨砂灰白，颜色与功能强绑定。
> 7. **字体依赖**：图标使用 `HyperOS_Symbols_VF` 字体（符号字体），文字使用 `MiSans Medium`。
