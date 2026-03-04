---
component: NavigationBarPad
description: Pad 端顶部导航栏组件，由左侧图标区、中间内容区和右侧操作区三部分组成，支持多种内容变体和材质风格
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=83334-32651
figma_node_id: "83334:32651"
variants: "9 sub-component sets, ~40 variants total"
tokens_used: 25
---

# Pad标题栏 NavigationBarPad

> Pad 端顶部导航栏组件，采用左-中-右三段式布局，左侧放置返回/关闭等导航图标，中间放置标题或 Tab 切换导航，右侧放置操作图标或搜索框，支持多种材质风格（玻璃/磨砂/纯色）和深浅色模式。

## 预览

![NavigationBarPad 全部变体预览](http://localhost:3845/assets/screenshot-83334-32651.png)

![pad顶栏 组装态预览](http://localhost:3845/assets/screenshot-80765-11993.png)

---

## 组件结构

```
Navigation Bar pad标题栏                      // FRAME | 83334:32651
├── pad顶栏                                   // INSTANCE | 80765:11993
│   ├── 左侧                                  // INSTANCE | 80747:11190
│   │   ├── pad 图标 (back)                   // INSTANCE | chevron_backward
│   │   ├── pad 图标 (close)                  // INSTANCE | close
│   │   └── pad 图标 (edit)                   // INSTANCE | edit
│   ├── 中间                                  // INSTANCE | 80765:11975
│   │   ├── 中间 平面&浮起                     // INSTANCE | 80765:11918
│   │   │   └── 中间选择背景                   // INSTANCE | container_list bg
│   │   └── tab                               // FRAME | 80765:11756
│   │       ├── Sidebar (icon)                // FRAME | 80765:11757
│   │       ├── 中间导航状态 (选中)             // INSTANCE | 81628:142770
│   │       └── 中间导航状态 (未选中)           // INSTANCE | 81628:143431
│   └── 右侧图标组                            // INSTANCE | 91164:122169
│       ├── pad 图标 (edit)                   // INSTANCE | edit
│       ├── pad 图标 (search)                 // INSTANCE | search
│       └── pad 图标 (more)                   // INSTANCE | more
├── 左侧 (原子组件集)                         // COMPONENT_SET | 80747:11169
│   ├── 类型选择=3个图标                       // COMPONENT | 80747:11167
│   ├── 类型选择=返回+标题                     // COMPONENT | 85173:53104
│   ├── 类型选择=2个图标                       // COMPONENT | 91481:99956
│   ├── 类型选择=1个图标                       // COMPONENT | 91481:99973
│   └── 类型选择=无图标                        // COMPONENT | 91164:119820
├── 中间 (原子组件集)                          // COMPONENT_SET | 80765:11927
│   ├── Property 1=中间导航                    // COMPONENT | 80765:11924
│   ├── Property 1=单行标题                    // COMPONENT | 80765:11925
│   ├── Property 1=双行标题                    // COMPONENT | 80765:11926
│   └── Property 1=无内容                      // COMPONENT | 91164:123654
├── 右侧图标组 (原子组件集)                    // COMPONENT_SET | 91164:121965
│   ├── 右侧状态=3个及以上图标                  // COMPONENT | 91164:121964
│   ├── 右侧状态=带搜索框                      // COMPONENT | 91164:123248
│   ├── 右侧状态=2个图标                       // COMPONENT | 91481:99024
│   ├── 右侧状态=1个图标                       // COMPONENT | 91481:99878
│   └── 右侧状态=无图标                        // COMPONENT | 91164:121963
├── 中间 平面&浮起 (原子组件集)                 // COMPONENT_SET | 80747:11280
│   ├── Property 1=浮起                        // COMPONENT | 80747:11279
│   └── Property 1=平面                        // COMPONENT | 80765:10047
├── 中间选择条材质 (原子组件集)                  // COMPONENT_SET | 80747:11263
│   ├── 材质=玻璃材质, 深色模式=no              // COMPONENT | 80747:11262
│   ├── 材质=混色模糊, 深色模式=no              // COMPONENT | 80747:11261
│   ├── 材质=纯色面板, 深色模式=no              // COMPONENT | 80747:11260
│   ├── 材质=玻璃材质, 深色模式=yes             // COMPONENT | 91164:110895
│   ├── 材质=混色模糊, 深色模式=yes             // COMPONENT | 91164:110896
│   └── 材质=纯色面板, 深色模式=yes             // COMPONENT | 91164:110897
├── 中间选择背景 (原子组件集)                   // COMPONENT_SET | 80759:8903
│   ├── 背景=白背景                            // COMPONENT | 80759:8902
│   └── 背景=灰背景                            // COMPONENT | 80759:8901
├── icon背景材质 (原子组件集)                   // COMPONENT_SET | 80747:10968
│   ├── 材质类型=玻璃材质, 深色模式=no           // COMPONENT | 80747:10969
│   ├── 材质类型=混色模糊, 深色模式=no           // COMPONENT | 80747:10971
│   ├── 材质类型=纯色面板, 深色模式=no           // COMPONENT | 80747:10973
│   ├── 材质类型=玻璃材质, 深色模式=yes          // COMPONENT | 80747:10981
│   ├── 材质类型=混色模糊, 深色模式=yes          // COMPONENT | 80747:10983
│   └── 材质类型=纯色面板, 深色模式=yes          // COMPONENT | 80747:10986
├── pad 图标 (原子组件集)                       // COMPONENT_SET | 80747:11007
│   ├── 平面&浮起=平面                          // COMPONENT | 80747:11006
│   └── 平面&浮起=浮起                          // COMPONENT | 80747:11005
└── 中间导航状态 (原子组件集)                    // COMPONENT_SET | 81628:142772
    ├── Property 1=选中                         // COMPONENT | 81628:142770
    └── Property 1=未选中                       // COMPONENT | 81628:142771
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| pad顶栏 | INSTANCE | `80765:11993` | 组装完成的导航栏实例，展示默认配置 |
| 左侧 | COMPONENT_SET | `80747:11169` | 左侧导航图标原子组件集，5 个变体 |
| 中间 | COMPONENT_SET | `80765:11927` | 中间内容区原子组件集，4 个变体 |
| 右侧图标组 | COMPONENT_SET | `91164:121965` | 右侧操作图标原子组件集，5 个变体 |
| 中间 平面&浮起 | COMPONENT_SET | `80747:11280` | 中间选择条的容器风格，2 个变体 |
| 中间选择条材质 | COMPONENT_SET | `80747:11263` | 中间选择条材质效果，6 个变体（3材质×2模式） |
| 中间选择背景 | COMPONENT_SET | `80759:8903` | 中间选择区域背景，2 个变体 |
| icon背景材质 | COMPONENT_SET | `80747:10968` | 图标悬浮态背景材质，6 个变体（3材质×2模式） |
| pad 图标 | COMPONENT_SET | `80747:11007` | 单个图标按钮原子组件，2 个变体 |
| 中间导航状态 | COMPONENT_SET | `81628:142772` | Tab 导航项状态，2 个变体 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器（pad顶栏）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `space-between` | — |
| `padding` | `2px 20px` | — |
| `height` | `56px` | — |
| `width` | `100%`（fill） | — |
| `position` | `relative` | — |

### 子组件: 左侧图标区

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `position` | `absolute` | — |
| `left` | `12px` | — |
| `top` | `50%` | — |
| `transform` | `translateY(-50%)` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `gap` | `10px`（3个图标/2个图标/1个图标） / `12px`（返回+标题） | — |

### 子组件: 中间内容区

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `position` | `absolute` | — |
| `left` | `50%` | — |
| `top` | `50%` | — |
| `transform` | `translate(-50%, -50%)` | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `gap` | `28px`（中间导航模式） | — |

### 子组件: 右侧操作区

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `position` | `absolute` | — |
| `right` | `12px` | — |
| `top` | `50%` | — |
| `transform` | `translateY(-50%)` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `flex-end` | — |
| `gap` | `8px` | `spacing-md` |

### 子组件: pad 图标按钮

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `44px` | — |
| `height` | `44px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `padding` | `0 8px` | — |
| `border-radius` | `102.604px`（圆形） | — |

### 子组件: 图标

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `28px` | — |
| `height` | `28px` | — |
| `font-family` | `HyperOS Symbols VF` / `HyperOS Symbols UI` | — |
| `font-weight` | `330` | — |
| `font-size` | `21px` | — |
| `color` | `#000000` | `hyperos-color-on-surface` |

### 子组件: Tab 导航容器（中间导航模式）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `204px` | — |
| `height` | `44px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `padding` | `4px` | — |
| `border-radius` | `102.604px` | — |
| `background-color` | `#FFFFFF`（白背景/浮起时由材质层提供） | `元素色/container_list` |

### 子组件: Tab 导航项

| CSS 属性 | 值（选中态） | 值（未选中态） | Token |
|---------|------------|-------------|-------|
| `height` | `36px` | `36px` | — |
| `padding` | `8px 20px` | `8px 20px` | — |
| `border-radius` | `100px` | `100px` | — |
| `background-color` | `rgba(0,0,0,0.06)` | `transparent` | `hyperos-color-surface-container-low` |

### 子组件: 搜索框（右侧带搜索框模式）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `176px` | — |
| `height` | `44px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `gap` | `8px` | `spacing-md` |
| `padding` | `0 12px` | — |
| `border-radius` | `999px` | `hyperos_theme_radius_circle` |
| `background-color` | `rgba(0,0,0,0.05)` | `新增色彩变量/container_nav` |
| `overflow` | `hidden` | — |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| 标题（单行/双行） | MiSans | 18px | 380 | 100% | 0 | `#000000` | `Title/Title 4`，`hyperos_font_size_title4` |
| 副标题（双行模式） | MiSans | 13px | 400 | 100% | 0 | `rgba(0,0,0,0.6)` | `hyperos-color-on-surface-tertiary` |
| Tab 导航文字 | MiSans | 16px | 430（Medium） | 20px | 0 | `#000000` | `hyperos-color-on-surface` |
| 搜索框占位符 | MiSans | 17px | 430（Medium） | 100% | 0 | `rgba(0,0,0,0.3)` | `Headline/Headline 1`，`hyperos-color-on-surface-octonary` |
| 搜索框图标 | HyperOS Symbols VF | 18px | 430（Medium） | 100% | 0 | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 图标色-默认 | `#000000` | `hyperos-color-on-surface` |
| 标题文字色 | `#000000` | `hyperos-color-on-surface` |
| 副标题文字色 | `rgba(0,0,0,0.6)` | `hyperos-color-on-surface-tertiary` |
| 搜索框占位符色 | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |
| Tab 选中背景 | `rgba(0,0,0,0.06)` | `hyperos-color-surface-container-low` |
| Tab 容器背景（白背景） | `#FFFFFF` | `元素色/container_list` |
| 搜索框背景 | `rgba(0,0,0,0.05)` | `新增色彩变量/container_nav` |
| 浮起图标背景（纯色/亮色） | `#FFFFFF` | `hyperos-color-surface-high` |
| 浮起图标背景（纯色/深色） | `#242424` | `Base/Popup_Dark` / `white/color-white-solid-30` |

---

## 变体

### 维度定义

该组件由多个原子组件集组合而成，各原子组件集的变体维度如下：

#### 左侧（导航图标区）

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型选择 | `类型选择` | `3个图标` / `返回+标题` / `2个图标` / `1个图标` / `无图标` | 左侧导航图标组合方式 |

#### 中间（内容区）

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 内容类型 | `Property 1` | `中间导航` / `单行标题` / `双行标题` / `无内容` | 中间区域展示内容 |

#### 右侧（操作区）

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 右侧状态 | `右侧状态` | `3个及以上图标` / `带搜索框` / `2个图标` / `1个图标` / `无图标` | 右侧操作图标组合方式 |

#### 容器风格

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 浮起风格 | `Property 1` / `平面&浮起` | `浮起` / `平面` | 中间选择条和图标的容器样式 |
| 材质类型 | `材质` / `材质类型` | `玻璃材质` / `混色模糊` / `纯色面板` | 浮起态时的材质效果 |
| 深色模式 | `深色模式` | `yes` / `no` | 是否为深色模式 |
| 背景风格 | `背景` | `白背景` / `灰背景` | 平面态时的背景风格 |

### 变体差异表

#### 按左侧「类型选择」分组

> 以 `3个图标` 为基准变体。

![左侧原子组件变体](http://localhost:3845/assets/screenshot-80747-11169.png)

| 属性 | `3个图标` | `返回+标题` | `2个图标` | `1个图标` | `无图标` |
|-----|---------|-----------|---------|---------|--------|
| 显示图标 | back + close + edit | back + 文字标题 | back + more | back | 无 |
| `gap` | `10px` | `12px` | `10px` | `0` | — |
| 子元素数 | 3 个 pad 图标 | 1 个 pad 图标 + 1 个文字 | 2 个 pad 图标 | 1 个 pad 图标 | — |
| 尺寸 | `auto × 44px` | `auto × 44px` | `auto × 44px` | `44 × 44px` | `52 × 34px` |

#### 按中间「内容类型」分组

> 以 `中间导航` 为基准变体。

![中间原子组件变体](http://localhost:3845/assets/screenshot-80765-11927.png)

| 属性 | `中间导航` | `单行标题` | `双行标题` | `无内容` |
|-----|---------|---------|---------|--------|
| 显示内容 | Tab 切换导航 | 单行标题文字 | 标题 + 副标题 | 无 |
| `width` | `204px` | `auto` | `98px` | `0` |
| `height` | `auto` | `24px` | `41px` | `54px` |
| 子元素 | 背景 + Tab 容器 | TEXT "小标题" | TEXT "小标题" + TEXT 副标题 | — |

#### 按右侧「右侧状态」分组

> 以 `3个及以上图标` 为基准变体。

![右侧原子组件变体](http://localhost:3845/assets/screenshot-91164-121965.png)

| 属性 | `3个及以上图标` | `带搜索框` | `2个图标` | `1个图标` | `无图标` |
|-----|-------------|---------|---------|---------|--------|
| 显示元素 | edit + search + more | 搜索框 + edit + search + more | search + more | more | 无 |
| `gap` | `8px` | `8px` | `8px` | `0` | — |
| 子元素数 | 3 个 pad 图标 | 1 个搜索框 + 3 个 pad 图标 | 2 个 pad 图标 | 1 个 pad 图标 | — |
| 尺寸 | `auto × 44px` | `auto × 44px` | `auto × 44px` | `44 × 44px` | `44 × 44px` |

#### 按「浮起风格」分组

> 以 `平面` 为基准变体。

![中间 平面&浮起](http://localhost:3845/assets/screenshot-80747-11280.png)

| 属性 | `平面` | `浮起` |
|-----|------|------|
| 选择条容器 | `中间选择背景` (纯色) | `中间选择条材质` (材质效果) |
| 图标按钮 | 无背景，直接显示图标 | 带 `icon背景材质` 的圆形容器 |

#### 材质详情

![中间选择条材质](http://localhost:3845/assets/screenshot-80747-11263.png)

##### 玻璃材质（亮色）`Pured/Pured_Thin_Glass_Light`

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `border` | `0.8px solid rgba(252,252,252,0.2)` | `Stroke/Glass_Stroke_Small_Light` |
| `border-radius` | `1000px` | — |
| `box-shadow` | `0px 0px 40px 0px rgba(0,0,0,0.06), 0px 24px 60px 0px rgba(0,0,0,0.08)` | — |
| 内层1 | `background: rgba(0,0,0,0.02)` | — |
| 内层2 | `background: rgba(255,255,255,0.6); mix-blend-mode: soft-light` | — |
| 内层3 | `background: rgba(255,255,255,0.4); mix-blend-mode: hard-light` | — |
| `box-shadow`（内阴影） | `inset 0px 2px 2px 0px #9d9d9d` | — |
| `backdrop-filter` | `blur(10px)` | — |

##### 混色模糊（亮色）`Colored/Colored_Regular_Light`

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `border` | `0.8px solid rgba(252,252,252,0.2)` | — |
| `border-radius` | `1000px` | — |
| `box-shadow` | `0px 0px 40px 0px rgba(0,0,0,0.06), 0px 24px 60px 0px rgba(0,0,0,0.08)` | — |
| 内层1 | `background: rgba(166,166,166,0.52); mix-blend-mode: overlay` | — |
| 内层2 | `background: rgba(255,255,255,0.11); mix-blend-mode: plus-lighter; backdrop-filter: blur(10px)` | — |
| `box-shadow`（内阴影） | `inset 0px 2px 2px 0px #9d9d9d` | — |

##### 纯色面板（亮色）`Base/Popup_Light`

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `background-color` | `#FFFFFF` | `hyperos-color-surface-high` |
| `border-radius` | `1000px` | — |
| `box-shadow` | `0px 0px 20px 0px rgba(0,0,0,0.02), 0px 12px 40px 0px rgba(0,0,0,0.04)` | `Shadow/Shadow_Low` |

##### 玻璃材质（深色）`Pured/Pured_Thin_Glass_Dark`

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `border` | `0.8px solid #262626` | `Stroke/Glass_Stroke_Small_Dark` |
| 内层1 | `background: rgba(0,0,0,0.1)` | — |
| 内层2 | `background: rgba(86,86,86,0.4); mix-blend-mode: luminosity` | — |
| 内层3 | `background: rgba(63,63,63,0.6); mix-blend-mode: overlay` | — |

##### 混色模糊（深色）`Pured/Pured_Extra_Thick_Dark`

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `border` | `0.8px solid #262626` | — |
| 内层1 | `background: rgba(25,25,25,0.8); mix-blend-mode: luminosity` | — |
| 内层2 | `background: rgba(49,49,49,0.33); mix-blend-mode: plus-lighter; backdrop-filter: blur(10px)` | — |

##### 纯色面板（深色）`Base/Popup_Dark`

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `background-color` | `#242424` | `Base/Popup_Dark` / `white/color-white-solid-30` |
| `box-shadow` | `0px 0px 20px 0px rgba(0,0,0,0.02), 0px 12px 40px 0px rgba(0,0,0,0.04)` | `Shadow/Shadow_Low` |

#### 图标背景材质

![icon背景材质变体](http://localhost:3845/assets/screenshot-80747-10968.png)

图标背景材质与中间选择条材质使用相同的材质系统，区别仅在尺寸：

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `44px` | — |
| `height` | `44px` | — |
| `border-radius` | `1000px` | — |
| `padding` | `10px 12px` | — |

#### Pad 图标风格

![pad 图标变体](http://localhost:3845/assets/screenshot-80747-11007.png)

| 属性 | `平面` | `浮起` |
|-----|------|------|
| 容器 | 仅圆角容器，无背景 | 带 icon背景材质 的容器 |
| `padding` | `0 8px` | `10px 12px` |
| `border-radius` | `102.604px` | `1000px` |
| 背景效果 | 无 | 根据材质类型和深色模式变化 |

#### 中间选择背景风格

![中间选择背景变体](http://localhost:3845/assets/screenshot-80759-8903.png)

| 属性 | `白背景` | `灰背景` |
|-----|--------|--------|
| `background-color` | `#FFFFFF` | `#FFFFFF` |
| `border-radius` | `102.604px` | `999px` |
| `box-shadow` | `0px 6px 30px 0px rgba(0,0,0,0.1)` | 无 |
| `width` | `204px` | `204px` |
| `height` | `44px` | `44px` |

#### 中间导航状态

![中间导航状态](http://localhost:3845/assets/screenshot-81628-142772.png)

| 属性 | `选中` | `未选中` |
|-----|------|--------|
| `background-color` | `rgba(0,0,0,0.06)` | `transparent` |
| `border-radius` | `100px` | `100px` |
| `padding` | `8px 20px` | `8px 20px` |
| `height` | `36px` | `36px` |

---

## 交互状态

> 以「默认态」为基准，其他状态仅列出**发生变化**的属性。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态） | — |
| `hover` | 鼠标悬停（pad 图标按钮） | Figma 未定义，请由设计团队补充 | — | — |
| `active` | 鼠标按下 / 触摸（pad 图标按钮） | Figma 未定义，请由设计团队补充 | — | — |
| `focused` | 键盘聚焦 | Figma 未定义，请由设计团队补充 | — | — |
| `disabled` | 功能不可用 | Figma 未定义，请由设计团队补充 | — | — |
| `tab-selected` | Tab 导航项被选中 | `background-color` | `rgba(0,0,0,0.06)` | `hyperos-color-surface-container-low` |
| `tab-unselected` | Tab 导航项未选中 | `background-color` | `transparent` | — |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

```typescript
interface NavigationBarPadProps {
  /** 左侧导航图标组合方式 */
  leftType: '3icons' | 'backWithTitle' | '2icons' | '1icon' | 'none';
  /** 中间内容区展示类型 */
  centerType: 'tabNavigation' | 'singleTitle' | 'doubleTitle' | 'none';
  /** 右侧操作图标组合方式 */
  rightType: '3plusIcons' | 'withSearchBar' | '2icons' | '1icon' | 'none';
  /** 容器浮起风格（影响中间选择条和图标按钮） */
  floatingStyle?: 'flat' | 'floating'; // 默认: 'flat'
  /** 材质类型（仅 floatingStyle='floating' 时生效） */
  materialType?: 'glass' | 'coloredBlur' | 'solid'; // 默认: 'glass'
  /** 选择背景类型（仅 floatingStyle='flat' 时生效） */
  backgroundType?: 'white' | 'gray'; // 默认: 'white'
  /** 是否为深色模式 */
  darkMode?: boolean; // 默认: false
  /** 左侧返回+标题模式下的标题文字 */
  leftTitle?: string; // 默认: '小标题'
  /** 中间单行/双行标题文字 */
  centerTitle?: string; // 默认: '小标题'
  /** 中间双行标题的副标题 */
  centerSubtitle?: string; // 默认: ''
  /** Tab 导航项列表（中间导航模式） */
  tabItems?: Array<{ label: string; selected?: boolean }>;
  /** 搜索框占位符文字（右侧带搜索框模式） */
  searchPlaceholder?: string; // 默认: '搜索提示'
  /** 左侧图标按钮组，通过 Instance Swap 自定义 */
  leftIcons?: ReactNode[];
  /** 右侧图标按钮组，通过 Instance Swap 自定义 */
  rightIcons?: ReactNode[];
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 类型选择 | Variant | `leftType` | `3个图标` | 左侧导航图标组合 |
| Property 1（中间） | Variant | `centerType` | `中间导航` | 中间内容区类型 |
| 右侧状态 | Variant | `rightType` | `3个及以上图标` | 右侧操作图标组合 |
| Property 1（平面&浮起） | Variant | `floatingStyle` | `平面` | 容器浮起风格 |
| 材质 / 材质类型 | Variant | `materialType` | `玻璃材质` | 浮起态材质效果 |
| 背景 | Variant | `backgroundType` | `白背景` | 平面态背景风格 |
| 深色模式 | Variant (Boolean) | `darkMode` | `no` | 深浅色模式 |
| Property 1（导航状态） | Variant | Tab `selected` | `选中` | Tab 导航项选中状态 |

---

## 使用指南

### 何时使用

- **多功能页面导航**：当 Pad 端页面需要顶部导航栏时，使用「中间导航」模式配合 Tab 切换
- **详情/子页面返回**：从子页面返回时使用「返回+标题」或「1个图标」的左侧变体
- **内容管理页面**：编辑、搜索、更多操作较多时，使用右侧「3个及以上图标」或「带搜索框」变体
- **沉浸式场景**：在图片浏览等沉浸式场景中，使用「浮起」风格 + 玻璃材质，图标和选择条悬浮于内容之上
- **简洁页面**：仅需返回功能时，使用左侧「1个图标」+ 中间「无内容」+ 右侧「无图标」

### 何时不使用

- **手机端导航**：手机端应使用对应的 Phone NavigationBar 组件
- **底部导航**：底部 Tab 切换应使用 BottomNavigationBar 组件
- **全屏沉浸内容**：视频播放等全屏场景中不应显示导航栏

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 左侧保留至少一个返回/关闭按钮 | 左侧和右侧同时为「无图标」 | 用户需要导航退出路径 |
| 浮起风格用于半透明/图片背景 | 平面风格叠加在图片上 | 平面风格无背景，图标在图片上不可见 |
| Tab 导航项控制在 2-3 项 | Tab 导航项超过 4 项 | 中间区域宽度有限（204px），过多会溢出 |
| 搜索框模式与操作图标搭配使用 | 仅展示搜索框无其他操作 | 右侧区域设计为图标+搜索框的组合 |
| 深色模式下使用对应的深色材质 | 亮色材质在深色背景上 | 材质颜色和混合模式针对特定模式优化 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `hyperos-color-on-surface` | `#000000` | color | 图标颜色、标题文字色 |
| `hyperos-color-on-surface-tertiary` | `rgba(0,0,0,0.6)` | color | 副标题文字色 |
| `hyperos-color-on-surface-octonary` | `rgba(0,0,0,0.3)` | color | 搜索框占位符、搜索图标色 |
| `hyperos-color-surface-container-low` | `rgba(0,0,0,0.06)` | color | Tab 导航项选中背景 |
| `hyperos-color-surface-high` | `#FFFFFF` | color | 纯色面板背景（亮色） |
| `元素色/container_list` | `#FFFFFF` | color | Tab 导航容器背景 |
| `新增色彩变量/container_nav` | `rgba(0,0,0,0.05)` | color | 搜索框背景 |
| `Base/Popup_Light` | `#FFFFFF` | color | 纯色面板（亮色） |
| `Base/Popup_Dark` | `#242424` | color | 纯色面板（深色） |
| `white/color-white-solid-30` | `#242424` | color | 浮起图标背景（深色纯色） |
| `Pured/Pured_Thin_Glass_Light` | `#000000, #FFFFFF, #FFFFFF` | material | 玻璃材质内层颜色（亮色） |
| `Pured/Pured_Thin_Glass_Dark` | `#000000, #565656, #3F3F3F` | material | 玻璃材质内层颜色（深色） |
| `Pured/Pured_Extra_Thick_Dark` | `#191919, #313131` | material | 混色模糊内层颜色（深色） |
| `Colored/Colored_Regular_Light` | `#A6A6A6, #FFFFFF` | material | 混色模糊内层颜色（亮色） |
| `Stroke/Glass_Stroke_Small_Light` | `rgba(252,252,252,0.2)` | border | 玻璃材质描边（亮色） |
| `Stroke/Glass_Stroke_Small_Dark` | `#262626` | border | 玻璃材质描边（深色） |
| `Shadow/Shadow_Low` | `0px 12px 40px rgba(0,0,0,0.04), 0px 0px 20px rgba(0,0,0,0.02)` | shadow | 纯色面板阴影 |
| `GlassShadow/GlassEffect_Thin_ShadowOn` | 多层阴影 + 内阴影 + glass blur | effect | 玻璃材质阴影效果 |
| `FrostShadow/FrostEffect_Thin_ShadowOn` | 多层阴影 + 内阴影 + background blur | effect | 混色模糊阴影效果 |
| `Miscellaneous/Floating Tab - Pill Shadow` | `rgba(0,0,0,0.08)` | shadow | 白背景 Tab 容器阴影 |
| `spacing-xl` | `16px` | spacing | 间距 |
| `spacing-md` | `8px` | spacing | 右侧图标间距、搜索框内间距 |
| `hyperos_theme_radius_circle` | `999px` | radius | 搜索框圆角 |
| `radius-3xl` | `20px` | radius | 大圆角 |
| `hyperos_font_size_title4` | `18px` | font-size | 标题字号 |
| `hyperos_font_weight_title4` | `380` | font-weight | 标题字重 |
| `hyperos_font_size_Headline1` | `17px` | font-size | 搜索框占位符字号 |
| `hyperos_font_weight_Headline1` | `380` | font-weight | 搜索框占位符字重 |
| `Title/Title 4` | `MiSans Medium, 18px/100%, weight 380` | typography | 标题文字样式 |
| `Headline/Headline 1` | `MiSans Medium, 17px/100%, weight 380` | typography | 搜索提示文字样式 |
| `GridWidth/1N` | `24px` | spacing | 栅格基准宽度 |
| `cos-space/xxs` | `6px` | spacing | 超小间距 |
| `var(--color-icon)` | `rgba(0,0,0,0.9)` | color | 图标色变量 |

---

## 设计注释

> 1. 该组件为 **Pad 端专用**导航栏，区别于手机端的 NavigationBar 组件，主要差异在于更宽的布局和更多的操作空间。
> 2. 左侧、中间、右侧三个区域均采用 **absolute 定位**，左侧 `left: 12px`，右侧 `right: 12px`，中间水平居中，三者不会互相挤压。
> 3. 「浮起」风格使用了复杂的多层混合模式（`soft-light`、`hard-light`、`overlay`、`luminosity`、`plus-lighter`）来实现玻璃和磨砂效果，实现时需注意浏览器兼容性。
> 4. 图标使用 **HyperOS Symbols VF** / **HyperOS Symbols UI** 图标字体，字号 `21px`，字重 `330`。
> 5. 所有圆形容器使用 `border-radius: 102.604px` 或 `1000px` 来实现完美圆角。
> 6. 该组件标记为"母组件集合_系统团队维护"，业务使用请优先复制场景实例。
