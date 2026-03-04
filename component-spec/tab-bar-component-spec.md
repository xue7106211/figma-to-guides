---
component: TabBar
description: 小米 HyperOS 4 标签页导航组件，支持多种形态（平面/浮起）、深色模式、多种背景环境和材质效果
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=99625-580
figma_node_id: "99625:580"
variants: "4 dimensions, 14 variants (标签页); 5 dimensions, 14 variants (选项); 4 dimensions, 24 variants (材质板子)"
tokens_used: 22
---

# 标签页 TabBar

> 用于在同一层级的多个内容视图之间切换的导航组件，支持平面和浮起两种形态，适配亮色/深色模式，并提供文字背景、彩色背景、图片背景等多种使用场景。

## 预览

![TabBar 组件全部变体预览](http://localhost:3845/figma-screenshot-99625-580)

---

## 组件结构

```
❖ 母组件集合_勿动                                    // FRAME | 99625:580
├── 标签页/phone端                                   // COMPONENT_SET (展示区) | 36597:12853
│   ├── 深色模式=亮色模式, 背景环境=文字背景-灰, ...     // COMPONENT | 36597:12854
│   │   └── 自适应内容                                // FRAME
│   │       ├── .选项 (选中)                          // INSTANCE | 状态=选中
│   │       ├── .选项 (未选中)                        // INSTANCE | 状态=未选中
│   │       ├── .选项 (未选中)                        // INSTANCE
│   │       ├── .选项 (未选中)                        // INSTANCE
│   │       └── .选项 (未选中)                        // INSTANCE
│   └── ... (共 14 个变体)
├── .选项                                            // COMPONENT_SET | 42501:25654
│   ├── 状态=选中, 深色模式=light, 形态=平面, ...       // COMPONENT | 42501:25689
│   │   └── 文字 "选中项"                             // TEXT
│   ├── 状态=未选中, 深色模式=light, 形态=平面, ...     // COMPONENT | 42501:25665
│   │   └── 文字 "未选中"                             // TEXT
│   ├── 状态=选中, 形态=浮起, ...                      // COMPONENT
│   │   ├── 材质板子                                  // FRAME (材质效果层)
│   │   └── 文字 "选中项"                             // TEXT
│   └── ... (共 14 个变体)
├── 材质板子                                          // COMPONENT_SET | 85119:73566
│   ├── 材质=玻璃材质, 深色模式=light, 状态=选中项, ...  // COMPONENT | 85119:73564
│   ├── 材质=混色模糊, ...                             // COMPONENT | 85119:73565
│   ├── 材质=纯色面板, ...                             // COMPONENT | 85119:73558
│   └── ... (共 24 个变体)
├── 选中项 (图标内容)                                  // FRAME | 94047:142729
│   └── 内容=图标                                     // INSTANCE | 94047:142726
├── 选中项/文字                                       // INSTANCE | 94047:142728
└── 未选中                                            // FRAME | 94047:142847
    ├── 内容=文字                                     // INSTANCE | 94047:142850
    └── 内容=图标                                     // INSTANCE | 94047:142852
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| 标签页/phone端 | COMPONENT_SET | `36597:12853` | 标签页主组件，包含所有形态和模式变体 |
| .选项 | COMPONENT_SET | `42501:25654` | 单个标签选项，支持选中/未选中状态 |
| 材质板子 | COMPONENT_SET | `85119:73566` | 浮起形态下的材质效果层，支持玻璃/模糊/纯色 |
| 选中项 (图标) | FRAME | `94047:142729` | 选中状态下显示图标的内容变体 |
| 选中项/文字 | INSTANCE | `94047:142728` | 选中状态下显示文字的内容变体 |
| 未选中 | FRAME | `94047:142847` | 未选中状态下的选项，支持文字和图标两种内容 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器（标签页/phone端）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `392px` | — |
| `height` | `auto`（hug） | — |
| `display` | `flex` | — |
| `flex-direction` | `row`（默认）/ `column`（部分变体） | — |
| `align-items` | `center`（等宽填充）/ `flex-start`（自适应） | — |
| `justify-content` | `center`（部分变体） | — |
| `padding-left` | `12px` | `hyperos_theme_container_margin_base_horizontal` |
| `padding-right` | `12px` | `hyperos_theme_container_margin_base_horizontal` |
| `padding-top` | `0` | — |
| `padding-bottom` | `0` | — |

### 子组件: 自适应内容容器

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `row` | — |
| `align-items` | `center` | — |
| `gap` | `12px` | — |
| `height` | `40px` | — |
| `width` | `100%` / `368px` | — |

### 子组件: 等宽填充容器

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `row` | — |
| `align-items` | `center` | — |
| `gap` | `12px` | — |
| `height` | `40px` | — |
| `flex` | `1 0 0` | — |

### 子组件: .选项（单个标签项）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `min-height` | `40px` | — |
| `height` | `40px`（浮起）/ `auto`（平面） | — |
| `padding-left` | `16px` | `spacing-xl` |
| `padding-right` | `16px` | `spacing-xl` |
| `border-radius` | `20px` | `hyperos_theme_radius_medium` |
| `gap` | `10px` | — |
| `overflow` | `hidden`（平面选中）/ `visible`（其他） | — |

#### .选项 — 平面形态 · 选中态（亮色/灰背景）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `background-color` | `#FFFFFF` | `文字图标色/on_surface_button_disable` |
| `border-radius` | `20px` | `hyperos_theme_radius_medium` |

#### .选项 — 平面形态 · 选中态（亮色/白背景）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `background-color` | `#FFFFFF` | `文字图标色/on_surface_button_disable` |
| `border-radius` | `20px` | `hyperos_theme_radius_medium` |
| `box-shadow` | `0px 4px 26px 0px rgba(0,0,0,0.05), 0px 0px 18px 0px rgba(0,0,0,0.04)` | — |
| `overflow` | `hidden` | — |

#### .选项 — 平面形态 · 选中态（深色）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `background-color` | `rgba(255,255,255,0.3)` | `文字图标色/on_surface_button_disable` |
| `border-radius` | `20px 20px 20px 20px` | `hyperos_theme_radius_medium` |

#### .选项 — 平面形态 · 未选中态（亮色/灰背景）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `background-color` | `rgba(0,0,0,0.05)` | `新增色彩变量/container_nav` |
| `border-radius` | `20px` | `hyperos_theme_radius_medium` |
| `overflow` | `hidden` | — |

#### .选项 — 平面形态 · 未选中态（亮色/白背景）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `background-color` | `rgba(0,0,0,0.05)` | `新增色彩变量/container_nav` |
| `border-radius` | `20px` | `hyperos_theme_radius_medium` |
| `overflow` | `hidden` | — |

#### .选项 — 平面形态 · 未选中态（深色）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `background-color` | `rgba(255,255,255,0.12)`（mix-blend-mode: plus-lighter 叠加层） | `新增色彩变量/container_nav` |
| `border-radius` | `20px` | `hyperos_theme_radius_medium` |

#### .选项 — 浮起形态 · 选中态（亮色/文字背景）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `border-radius` | `1000px`（胶囊形） | — |
| `border` | `0.8px solid rgba(252,252,252,0.2)` | `Stroke/Glass_Stroke_Small_Light` |
| `box-shadow` | `0px 0px 40px 0px rgba(0,0,0,0.06), 0px 24px 60px 0px rgba(0,0,0,0.08)` | `FrostShadow/FrostEffect_Thin_ShadowOn` |
| `backdrop-filter` | `blur(10px)` | — |

材质效果层叠加（从底到顶）：
1. `background: rgba(255,255,255,0.4)` + `mix-blend-mode: plus-lighter`
2. `background: rgba(245,245,245,0.6)` + `backdrop-filter: blur(10px)`
3. `box-shadow: inset 0px 2px 2px 0px #9D9D9D`（内阴影）

#### .选项 — 浮起形态 · 选中态（深色/文字背景）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `border-radius` | `1000px`（胶囊形） | — |
| `border` | `1px solid #262626` | — |
| `box-shadow` | `0px 0px 40px 0px rgba(0,0,0,0.06), 0px 24px 60px 0px rgba(0,0,0,0.08)` | `FrostShadow/FrostEffect_Thin_ShadowOn` |
| `backdrop-filter` | `blur(10px)` | — |

材质效果层叠加（从底到顶）：
1. `background: rgba(25,25,25,0.8)` + `mix-blend-mode: luminosity`
2. `background: rgba(49,49,49,0.33)` + `mix-blend-mode: plus-lighter` + `backdrop-filter: blur(10px)`
3. `box-shadow: inset 0px 2px 2px 0px #9D9D9D`（内阴影）

#### .选项 — 浮起形态 · 未选中态（亮色/文字背景）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `border-radius` | `24px` | `hyperos_theme_radius_demi_big` |
| `border` | `0.8px solid #FCFCFC` | — |
| `box-shadow` | `0px 12px 21px 0px rgba(0,0,0,0.05), 0px 5px 40px 0px rgba(0,0,0,0.11)` | — |

材质效果层叠加（从底到顶）：
1. `background: rgba(116,116,116,0.9)` + `mix-blend-mode: overlay`
2. `background: rgba(142,142,142,0.16)` + `backdrop-filter: blur(5px)`
3. `box-shadow: inset 0px 1px 3px 0px #9D9D9D`（内阴影）

#### .选项 — 浮起形态 · 未选中态（亮色/图片背景）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `border-radius` | `24px` | `hyperos_theme_radius_demi_big` |
| `border` | `0.8px solid rgba(252,252,252,0.7)` | — |
| `box-shadow` | `0px 0px 40px 0px rgba(0,0,0,0.06), 0px 24px 60px 0px rgba(0,0,0,0.08)` | — |

材质效果层叠加（从底到顶）：
1. `background: rgba(255,255,255,0.4)` + `mix-blend-mode: plus-lighter`
2. `background: rgba(97,97,97,0.26)` + `backdrop-filter: blur(10px)`
3. `box-shadow: inset 0px 2px 2px 0px #9D9D9D`（内阴影）

#### .选项 — 浮起形态 · 未选中态（深色/文字背景）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `border-radius` | `20px` | `hyperos_theme_radius_medium` |
| `border` | `0.8px solid rgba(38,38,38,0.5)` | — |
| `box-shadow` | `0px 0px 40px 0px rgba(0,0,0,0.06), 0px 24px 60px 0px rgba(0,0,0,0.08)` | — |

材质效果层叠加（从底到顶）：
1. `background: rgba(25,25,25,0.8)` + `mix-blend-mode: luminosity`
2. `background: rgba(49,49,49,0.33)` + `mix-blend-mode: plus-lighter`
3. `background: rgba(149,149,149,0.16)` + `backdrop-filter: blur(10px)`
4. `box-shadow: inset 0px 2px 2px 0px #9D9D9D`（内阴影）

#### .选项 — 浮起形态 · 未选中态（深色/图片背景）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `border-radius` | `20px` | `hyperos_theme_radius_medium` |
| `border` | `0.8px solid rgba(38,38,38,0.6)` | — |
| `box-shadow` | `0px 0px 40px 0px rgba(0,0,0,0.06), 0px 24px 60px 0px rgba(0,0,0,0.08)` | — |

材质效果层叠加（从底到顶）：
1. `background: rgba(0,0,0,0.19)` + `mix-blend-mode: luminosity`
2. `background: rgba(0,0,0,0.4)` + `mix-blend-mode: overlay` + `backdrop-filter: blur(10px)`
3. `box-shadow: inset 0px 2px 2px 0px #9D9D9D`（内阴影）

### 子组件: 材质板子（浮起形态的材质效果层）

材质板子是浮起形态下选项的背景效果层，通过多层叠加实现毛玻璃/模糊/纯色效果。

#### 玻璃材质 · 亮色 · 选中

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `height` | `40px` | — |
| `width` | `70px` | — |
| `border-radius` | `1000px` | — |
| `border` | `0.8px solid rgba(252,252,252,0.2)` | `Stroke/Glass_Stroke_Small_Light` |
| `box-shadow` | `0px 0px 40px 0px rgba(0,0,0,0.06), 0px 24px 60px 0px rgba(0,0,0,0.08)` | `FrostShadow/FrostEffect_Thin_ShadowOn` |

叠加层：
1. `background: rgba(0,0,0,0.02)`
2. `background: rgba(255,255,255,0.6)` + `mix-blend-mode: soft-light`
3. `background: rgba(255,255,255,0.4)` + `mix-blend-mode: hard-light`
4. `box-shadow: inset 0px 2px 2px 0px #9D9D9D`

#### 混色模糊 · 亮色 · 选中

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `border-radius` | `1000px` | — |
| `border` | `0.8px solid rgba(252,252,252,0.2)` | `Stroke/Glass_Stroke_Small_Light` |
| `box-shadow` | `0px 0px 40px 0px rgba(0,0,0,0.06), 0px 24px 60px 0px rgba(0,0,0,0.08)` | `FrostShadow/FrostEffect_Thin_ShadowOn` |

叠加层：
1. `background: rgba(255,255,255,0.4)` + `mix-blend-mode: plus-lighter`
2. `background: rgba(245,245,245,0.6)` + `backdrop-filter: blur(10px)`
3. `box-shadow: inset 0px 2px 2px 0px #9D9D9D`

#### 纯色面板 · 亮色 · 选中

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `border-radius` | `1000px` | — |
| `background-color` | `#FFFFFF` | `hyperos-color-surface-high` |
| `box-shadow` | `0px 0px 20px 0px rgba(0,0,0,0.02), 0px 12px 40px 0px rgba(0,0,0,0.04)` | `Shadow/Shadow_Low` |

#### 纯色面板 · 深色 · 选中

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `border-radius` | `1000px` | — |
| `background-color` | `#242424` | `white/color-white-solid-30` |
| `box-shadow` | `0px 0px 20px 0px rgba(0,0,0,0.02), 0px 12px 40px 0px rgba(0,0,0,0.04)` | `Shadow/Shadow_Low` |

#### 未选中（所有材质一致）· 亮色

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `border-radius` | `24px` | `hyperos_theme_radius_demi_big` |
| `border` | `0.8px solid #FCFCFC`（文字浮起）/ `0.8px solid rgba(252,252,252,0.7)`（彩色浮起） | — |

#### 未选中（所有材质一致）· 深色

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `border-radius` | `20px` | `hyperos_theme_radius_medium` |
| `border` | `0.8px solid rgba(38,38,38,0.5)`（文字浮起）/ `0.8px solid rgba(38,38,38,0.6)`（彩色浮起） | — |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| 选中项文字（亮色） | MiSans | 14px | 450 (Demibold) | 100% | 0 | `#000000` | `Subtitle/Subtitle 2` |
| 选中项文字（深色） | MiSans | 14px | 450 (Demibold) | 100% | 0 | `rgba(255,255,255,0.95)` | `Subtitle/Subtitle 2` |
| 未选中文字（亮色） | MiSans | 14px | 330 (Regular) | 100% | 0 | `rgba(0,0,0,0.6)` | `Subtitle/Subtitle 3` |
| 未选中文字（深色） | MiSans | 14px | 330 (Regular) | 100% | 0 | `rgba(255,255,255,0.5)` | `Subtitle/Subtitle 3` |

### 颜色一览

| 语义用途 | 亮色值 | 深色值 | Token |
|---------|-------|-------|-------|
| 选中项背景（平面） | `#FFFFFF` | `rgba(255,255,255,0.3)` | `文字图标色/on_surface_button_disable` |
| 未选中项背景（平面） | `rgba(0,0,0,0.05)` | `rgba(255,255,255,0.12)` | `新增色彩变量/container_nav` |
| 选中项文字色 | `#000000` | `rgba(255,255,255,0.95)` | `hyperos-color-on-surface` |
| 未选中项文字色 | `rgba(0,0,0,0.6)` | `rgba(255,255,255,0.5)` | `hyperos-color-on-surface-tertiary` |
| 纯色面板选中背景 | `#FFFFFF` | `#242424` | `hyperos-color-surface-high` / `white/color-white-solid-30` |
| 主题色 | `#3482FF` | `#3482FF` | `hyperos-color-primary` |
| 面板背景色 | `#FFFFFF` | `#242424` | `Base/Popup_Light` / `Base/Popup_Dark` |

---

## 变体

### 维度定义

#### 标签页/phone端（主组件）

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 深色模式 | `深色模式` | `亮色模式` / `深色模式` | 控制整体配色方案 |
| 背景环境 | `背景环境` | `文字背景-灰` / `文字背景-白` / `文字背景` / `彩色背景` | 使用场景的背景类型 |
| 标签规则 | `标签规则` | `自适应内容` / `等宽填充容器` | 标签项宽度策略 |
| 形态 | `形态` | `平面` / `浮起` | 标签项的视觉形态 |

共计 **14 个有效变体**（并非所有组合都存在）。

#### .选项（子组件）

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 状态 | `状态` | `选中` / `未选中` | 标签项的选中状态 |
| 深色模式 | `深色模式` | `light` / `dark` | 配色方案 |
| 形态 | `形态` | `平面` / `浮起` | 视觉形态 |
| 类型 | `类型` | `文字背景` / `图片背景` | 所处背景的类型 |
| 背景颜色 | `背景颜色` | `灰背景` / `白背景` | 平面形态下的背景颜色 |

共计 **14 个有效变体**。

#### 材质板子（子组件）

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 材质 | `材质` | `玻璃材质` / `混色模糊` / `纯色面板` | 选中态的材质效果 |
| 深色模式 | `深色模式` | `light` / `dark` | 配色方案 |
| 状态 | `状态` | `选中项` / `未选中` | 选中状态 |
| 类型 | `类型` | `文字浮起` / `彩色浮起` | 所处背景类型 |

共计 **3 × 2 × 2 × 2 = 24 个变体**。

### 变体差异表

#### 按形态分组（标签页主组件）

> 以「亮色模式 + 文字背景-灰 + 自适应内容 + 平面」为基准变体。

| 属性 | `平面` | `浮起` |
|-----|--------|--------|
| 选中项 `background` | 纯色（白色/半透明） | 材质叠加层（毛玻璃效果） |
| 选中项 `border-radius` | `20px` | `1000px`（胶囊） |
| 选中项 `border` | 无 | `0.8px solid`（半透明边框） |
| 选中项 `box-shadow` | 无 / 低阴影 | `FrostShadow` 效果 |
| 选中项 `backdrop-filter` | 无 | `blur(5px~10px)` |
| 未选中项 `border-radius` | `20px` | `20px~24px` |
| 未选中项 `background` | 半透明灰 | 材质叠加层 |

#### 按深色模式分组（.选项）

| 属性 | `light` | `dark` |
|-----|---------|--------|
| 选中项文字 `color` | `#000000` | `rgba(255,255,255,0.95)` |
| 未选中文字 `color` | `rgba(0,0,0,0.6)` | `rgba(255,255,255,0.5)` |
| 选中项 `background`（平面） | `#FFFFFF` | `rgba(255,255,255,0.3)` |
| 未选中 `background`（平面） | `rgba(0,0,0,0.05)` | `rgba(255,255,255,0.12)` |
| 浮起 `border-color` | `rgba(252,252,252,0.2)` | `#262626` |
| 未选中浮起 `border-radius` | `24px` | `20px` |

#### 按背景环境分组

| 属性 | `文字背景-灰` | `文字背景-白` | `文字背景` | `彩色背景` |
|-----|-------------|-------------|-----------|-----------|
| 可用形态 | 平面 | 平面 | 浮起 | 浮起 |
| 选中态阴影（平面） | 无 | 有低阴影 | — | — |

#### 按标签规则分组

| 属性 | `自适应内容` | `等宽填充容器` |
|-----|------------|-------------|
| 标签项宽度 | `auto`（由内容撑开） | `flex: 1 0 0`（等分容器） |
| 容器 `flex-direction` | `column`（部分）/ `row` | `row` |

### 变体截图

#### 标签页变体总览（.选项）

![选项变体总览](http://localhost:3845/figma-screenshot-42501-25654)

#### 材质板子变体总览

![材质板子变体总览](http://localhost:3845/figma-screenshot-85119-73566)

#### 默认变体截图（亮色/灰背景/自适应/平面）

![默认变体截图](http://localhost:3845/figma-screenshot-36597-12854)

---

## 交互状态

> 以「默认态（未选中）」为基准，其他状态仅列出**发生变化**的属性。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default`（未选中） | — | — | （基准状态） | — |
| `selected`（选中） | 用户点击 / 触摸 | `background-color`（平面） | `#FFFFFF`（亮）/ `rgba(255,255,255,0.3)`（暗） | `文字图标色/on_surface_button_disable` |
| | | `font-weight` | `450`（Demibold） | `hyperos_font_weight_subtitle2` |
| | | `color` | `#000000`（亮）/ `rgba(255,255,255,0.95)`（暗） | `hyperos-color-on-surface` |
| | | `border-radius`（浮起） | `1000px` | — |
| `hover` | 鼠标悬停 | Figma 未定义，请由设计团队补充 | — | — |
| `active` | 鼠标按下 / 触摸 | Figma 未定义，请由设计团队补充 | — | — |
| `focused` | 键盘聚焦 | Figma 未定义，请由设计团队补充 | — | — |
| `disabled` | 禁用 | Figma 未定义，请由设计团队补充 | — | — |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

### 标签页/phone端

```typescript
interface TabBarProps {
  /** 深色模式切换 */
  darkMode: '亮色模式' | '深色模式';
  /** 使用场景的背景类型；文字背景-灰和文字背景-白仅用于平面形态，文字背景和彩色背景仅用于浮起形态 */
  backgroundEnv: '文字背景-灰' | '文字背景-白' | '文字背景' | '彩色背景';
  /** 标签项宽度策略 */
  tabRule: '自适应内容' | '等宽填充容器';
  /** 标签项的视觉形态 */
  form: '平面' | '浮起';
}
```

### .选项

```typescript
interface TabItemProps {
  /** 选中状态 */
  state: '选中' | '未选中';
  /** 深色模式 */
  darkMode: 'light' | 'dark';
  /** 视觉形态 */
  form: '平面' | '浮起';
  /** 所处背景类型（浮起形态使用） */
  bgType: '文字背景' | '图片背景';
  /** 背景颜色（平面形态使用） */
  bgColor: '灰背景' | '白背景';
  /** 标签项内容，支持文字或图标 */
  content?: ReactNode;
}
```

### 材质板子

```typescript
interface MaterialPanelProps {
  /** 材质类型 */
  material: '玻璃材质' | '混色模糊' | '纯色面板';
  /** 深色模式 */
  darkMode: 'light' | 'dark';
  /** 选中状态 */
  state: '选中项' | '未选中';
  /** 所处背景类型 */
  bgType: '文字浮起' | '彩色浮起';
}
```

### API 属性映射表

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 深色模式 | Variant | `darkMode` | `亮色模式` / `light` | 深色/亮色模式切换 |
| 背景环境 | Variant | `backgroundEnv` | `文字背景-灰` | 使用场景的背景类型 |
| 标签规则 | Variant | `tabRule` | `自适应内容` | 标签项宽度策略 |
| 形态 | Variant | `form` | `平面` | 视觉形态 |
| 状态 | Variant | `state` | `选中` | 选中/未选中 |
| 类型 | Variant | `bgType` | `文字背景` | 背景类型 |
| 背景颜色 | Variant | `bgColor` | `灰背景` | 平面形态背景色 |
| 材质 | Variant | `material` | `玻璃材质` | 材质效果类型 |
| 内容 | Instance Swap | `content` | 文字 | 标签项内容 |

---

## 使用指南

### 何时使用

- **页面级标签切换**：在同一层级的多个内容视图间切换时，使用「自适应内容 + 平面」类型
- **等分标签导航**：标签数量固定且需要均分宽度时，使用「等宽填充容器」类型
- **沉浸式场景**：在图片或彩色背景上使用标签时，使用「浮起」形态，材质效果可增强可读性
- **深色主题**：系统深色模式下自动切换「深色模式」变体
- **彩色/图片背景**：在非纯色背景上使用时，选择「浮起 + 彩色背景/图片背景」组合

### 何时不使用

- **底部导航**：应使用 BottomNavigationBar 代替
- **仅两个选项切换**：应使用 SegmentedControl 代替
- **内容筛选**：应使用 FilterChip 或 DropdownMenu 代替
- **层级导航**：需要显示层级关系时，应使用 Breadcrumb 代替

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 标签数量控制在 2-5 个 | 超过 5 个标签 | 过多标签会导致文字截断，影响可读性 |
| 在灰色/白色背景上使用平面形态 | 在图片背景上使用平面形态 | 平面形态无材质效果，在复杂背景上可读性差 |
| 在图片/彩色背景上使用浮起形态 | 在纯色背景上使用浮起形态 | 浮起形态的毛玻璃效果在纯色背景上无意义 |
| 保持所有标签文字长度相近 | 标签文字长度差异过大 | 等宽填充时会导致布局不均衡 |
| 选中态使用更重的字重（Demibold 450） | 选中和未选中使用相同字重 | 字重变化是区分选中状态的关键视觉线索 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `hyperos-color-on-surface` | `#000000`（亮）/ `rgba(255,255,255,0.95)`（暗） | color | 选中项文字色 |
| `hyperos-color-on-surface-tertiary` | `rgba(0,0,0,0.6)`（亮）/ `rgba(255,255,255,0.5)`（暗） | color | 未选中项文字色 |
| `hyperos-color-primary` | `#3482FF` | color | 主题色 |
| `hyperos-color-surface-high` | `#FFFFFF` | color | 纯色面板选中背景（亮色） |
| `hyperos_color_surface` | `#FFFFFF` | color | 表面色 |
| `hyperos_color_surface_low` | `#F3F3F3` | color | 低层级表面色 |
| `文字图标色/on_surface_button_disable` | `#FFFFFF`（亮）/ `rgba(255,255,255,0.3)`（暗） | color | 平面选中项背景 |
| `新增色彩变量/container_nav` | `rgba(0,0,0,0.05)`（亮）/ `rgba(255,255,255,0.12)`（暗） | color | 平面未选中项背景 |
| `文字图标色/on_Surface_empty_state` | `rgba(0,0,0,0.2)` | color | 空状态文字色 |
| `white/color-white-solid-30` | `#242424` | color | 纯色面板选中背景（深色） |
| `Base/Popup_Light` | `#FFFFFF` | color | 弹出面板背景（亮色） |
| `Base/Popup_Dark` | `#242424` | color | 弹出面板背景（深色） |
| `全系统色板/Violet` | `#B74AF7` | color | 系统紫色 |
| `hyperos_font_size_subtitle2` | `14px` | font-size | 选中项字号 |
| `hyperos_font_weight_subtitle2` | `450` | font-weight | 选中项字重 |
| `hyperos_font_size_subtitle3` | `14px` | font-size | 未选中项字号 |
| `hyperos_font_weight_subtitle3` | `330` | font-weight | 未选中项字重 |
| `hyperos_theme_radius_medium` | `20px` | radius | 标签项圆角（平面 + 深色浮起未选中） |
| `hyperos_theme_radius_demi_big` | `24px` | radius | 亮色浮起未选中项圆角 |
| `hyperos_theme_radius_big` | `36px` | radius | 大圆角 |
| `radius-3xl` | `20px` | radius | 通用大圆角 |
| `spacing-xl` | `16px` | spacing | 标签项内边距 |
| `hyperos_theme_container_margin_base_horizontal` | `12px` | spacing | 容器水平边距 |
| `Subtitle/Subtitle 2` | `MiSans Demibold 14px/100% weight:450` | typography | 选中项文字样式 |
| `Subtitle/Subtitle 3` | `MiSans Regular 14px/100% weight:330` | typography | 未选中项文字样式 |
| `Pured/Pured_Extra_Thick_Light` | `#FFFFFF, #F5F5F5` | material | 纯色厚材质（亮色） |
| `Pured/Pured_Extra_Thick_Dark` | `#191919, #313131` | material | 纯色厚材质（深色） |
| `Pured/Pured_Thin_Glass_Light` | `#000000, #FFFFFF, #FFFFFF` | material | 薄玻璃材质（亮色） |
| `Pured/Pured_Thin_Glass_Dark` | `#000000, #565656, #3F3F3F` | material | 薄玻璃材质（深色） |
| `Stroke/Glass_Stroke_Small_Light` | 细描边（亮色） | stroke | 玻璃效果描边 |
| `Stroke/Glass_Stroke_Small_Dark` | 细描边（深色） | stroke | 玻璃效果描边 |
| `FrostShadow/FrostEffect_Thin_ShadowOn` | 多层阴影 + 内阴影 + 模糊 | effect | 毛玻璃阴影效果 |
| `Shadow/Shadow_Low` | `0px 12px 40px rgba(0,0,0,0.04), 0px 0px 20px rgba(0,0,0,0.02)` | effect | 低阴影效果 |

---

## 设计注释

> 1. **背景环境与形态的对应关系**：`文字背景-灰` 和 `文字背景-白` 仅搭配 `平面` 形态使用；`文字背景` 和 `彩色背景` 仅搭配 `浮起` 形态使用。
> 2. **材质板子说明**：浮起形态下，选中项和未选中项的材质板子在三种材质（玻璃材质、混色模糊、纯色面板）下，彩色浮起和文字浮起三种材质效果一致（来自 Figma 标注）。
> 3. **未选中项材质一致性**：未选中状态下，所有材质类型的效果一致（来自 Figma 标注"未选中所有材质一致"）。
> 4. **选项内容类型**：每个标签项支持文字和图标两种内容形式，选中项显示高亮样式，未选中项显示次级样式。
> 5. **Constraints 说明**（来自 Figma 标注）：材质板子使用 Left+Right constraints，默认 Fixed 模式；若选择 hug，constraints 会被改为 center；文字选 hug，整体选 hug。
> 6. **标签项宽度策略**：`自适应内容` 模式下标签项宽度由内容撑开，各项宽度可能不同；`等宽填充容器` 模式下所有标签项等分容器宽度。
