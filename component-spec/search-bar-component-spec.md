---
component: SearchBar
description: HyperOS 4 搜索栏组件，提供平面与浮起两种视觉风格，支持默认、激活、输入中、按压等多种交互状态
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=98770-58056
figma_node_id: "98770:58056"
variants: "搜索框: 2 dimensions (状态×平面&浮起), 13 variants; 材质板子: 2 dimensions (材质×深色模式), 4 variants; 搜索标签: 1 dimension, 2 variants; pad搜索框: 2 dimensions (状态×平面&浮起), 8 variants"
tokens_used: 27
---

# 搜索栏 SearchBar

> HyperOS 4 设计系统中的搜索栏组件集合，包含手机端搜索框、Pad 端搜索框、搜索框材质和搜索标签四个子组件。搜索框支持平面（Flat）和浮起（Raised / 玻璃材质）两种视觉风格，涵盖默认、激活未输入、激活输入中、按压、直搜建议等多种交互状态。

## 预览

![搜索栏 SearchBar 全部变体预览](http://localhost:3845/screenshots/98770:58056)

---

## 组件结构

```
搜索栏_Search bar                              // FRAME | 98770:58056
├── 搜索框                                     // FRAME (组件展示区) | 1890:7003
│   ├── 状态=默认态, 平面&浮起=平面              // COMPONENT | 1890:7004
│   │   └── 搜索框背景                          // FRAME | 1890:7005
│   │       ├── SearchIcon                     // TEXT (icon font) | 47506:4266
│   │       └── PlaceholderText                // TEXT | 1890:7007
│   ├── 状态=默认态, 平面&浮起=浮起              // COMPONENT | 80636:7022
│   │   └── GlassMaterial + 搜索框背景          // FRAME + INSTANCE
│   ├── 状态=激活-未输入, 平面&浮起=平面          // COMPONENT | 69750:33723
│   │   ├── 搜索框背景                          // FRAME
│   │   │   ├── SearchIcon                     // INSTANCE
│   │   │   └── 文字和光标                      // FRAME (光标 + 占位文字)
│   │   └── 关闭                               // FRAME (关闭按钮)
│   ├── 状态=激活-输入中, 平面&浮起=平面          // COMPONENT | 1890:7020
│   │   ├── 搜索框背景                          // FRAME
│   │   │   ├── SearchIcon                     // INSTANCE
│   │   │   ├── 文字和光标                      // FRAME (输入文字 + 光标)
│   │   │   └── 一键清除                        // INSTANCE (清除按钮)
│   │   └── 关闭                               // FRAME (关闭按钮)
│   ├── 状态=按压态, 平面&浮起=平面              // COMPONENT | 1890:7012
│   │   └── 搜索框背景                          // FRAME (深色背景渐变)
│   ├── 状态=sug词-直搜, 平面&浮起=平面          // COMPONENT | 80687:4662
│   │   ├── 返回按钮                            // FRAME
│   │   ├── 搜索框背景                          // FRAME
│   │   └── 搜索按钮                            // FRAME
│   ├── 状态=激活-输入中2, 平面&浮起=平面         // COMPONENT | 88706:23088
│   │   ├── 搜索框背景                          // FRAME
│   │   └── 关闭(文字按钮)                      // FRAME
│   └── [浮起变体镜像以上各状态]
├── 材质板子                                    // FRAME | 80636:7500
│   ├── 材质=混色模糊, 深色模式=light            // COMPONENT | 80636:7503
│   ├── 材质=混色模糊, 深色模式=dark             // COMPONENT | 88706:16242
│   ├── 材质=纯色面板, 深色模式=light            // COMPONENT | 80636:7505
│   └── 材质=纯色面板, 深色模式=dark             // COMPONENT | 88706:16243
├── 搜索标签                                    // FRAME | 7334:9620
│   ├── 底色=灰底白卡                           // COMPONENT | 1890:9699
│   └── 底色=白底灰卡                           // COMPONENT | 1890:9698
└── pad 搜索框                                  // FRAME | 81907:21340
    ├── 状态=默认_最小宽度, 平面&浮起=平面        // COMPONENT | 81907:21339
    ├── 状态=默认, 平面&浮起=平面                // COMPONENT | 81907:21336
    ├── 状态=激活-未输入, 平面&浮起=平面          // COMPONENT | 81907:21337
    ├── 状态=激活-输入中, 平面&浮起=平面          // COMPONENT | 81907:21338
    └── [浮起变体镜像以上各状态]
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| 搜索框 | FRAME | `1890:7003` | 手机端搜索框组件集，含 13 个变体 |
| 材质板子 | FRAME | `80636:7500` | 搜索框背景材质选项，含 4 个变体 |
| 搜索标签 | FRAME | `7334:9620` | 搜索标签 / 热词标签，含 2 个变体 |
| pad 搜索框 | FRAME | `81907:21340` | Pad 端搜索框组件集，含 8 个变体 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 一、搜索框（手机端）

#### 容器

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `392px` | — |
| `height` | `auto`（hug） | — |
| `display` | `flex` | — |
| `flex-direction` | `column`（默认态）/ `row`（激活态） | — |
| `align-items` | `flex-start`（默认态）/ `center`（激活态） | — |
| `gap` | `0`（默认态）/ `10px`（激活态） | — |
| `padding-top` | `4px` | — |
| `padding-right` | `12px` | `padding/padding_sm` |
| `padding-bottom` | `8px` | — |
| `padding-left` | `12px` | `padding/padding_sm` |

#### 子组件: 搜索框背景（平面 / Flat）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%`（fill） | — |
| `height` | `44px` | — |
| `display` | `flex` | — |
| `flex-direction` | `row` | — |
| `align-items` | `center` | — |
| `gap` | `8px` | `spacing-md` |
| `padding` | `10.5px 12px` | — |
| `background-color` | `rgba(0,0,0,0.05)` | `新增色彩变量/container_nav` |
| `border-radius` | `999px` | `hyperos_theme_radius_circle` |
| `overflow` | `hidden` | — |

#### 子组件: 搜索框背景（浮起 / Raised — 玻璃材质）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `368px` | — |
| `height` | `44px` | — |
| `border-radius` | `28px` | — |
| `border` | `1px solid rgba(252,252,252,0.2)` | `Stroke/Glass_Stroke_Small_Light` |
| `box-shadow` | `0px 0px 40px 0px rgba(0,0,0,0.06), 0px 24px 60px 0px rgba(0,0,0,0.08), inset 0px 2px 2px 0px #9D9D9D` | `FrostShadow/FrostEffect_Thin_ShadowOn` |
| `backdrop-filter` | `blur(10px)` | — |
| 玻璃层 1 | `background: rgba(0,0,0,0.02)` | — |
| 玻璃层 2 | `background: rgba(255,255,255,0.6); mix-blend-mode: soft-light` | — |
| 玻璃层 3 | `background: rgba(255,255,255,0.4); mix-blend-mode: hard-light; backdrop-filter: blur(10px)` | `Pured/Pured_Thin_Glass_Light` |

#### 子组件: 搜索图标

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `font-family` | `HyperOS_Symbols_VF` | — |
| `font-size` | `18px`（默认态）/ `15.43px`（激活态图标实例） | — |
| `font-weight` | `430` | — |
| `color` | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |

#### 子组件: 光标

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `2.181px` | — |
| `height` | `20px` | — |
| `background-color` | `#3482FF` | `hyperos-color-on-secondary` |
| `border-radius` | `3.635px` | — |

#### 子组件: 一键清除按钮

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `20px` | — |
| `height` | `20px` | — |
| `position` | `absolute` | — |
| `right` | `14px` | — |
| `top` | `50%` | — |
| `transform` | `translateY(-50%)` | — |

#### 子组件: 关闭按钮（图标型）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `44px` | — |
| `height` | `44px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `padding` | `8px` | — |
| `background-color` | `rgba(0,0,0,0.05)` | `新增色彩变量/container_nav` |
| `border-radius` | `22px` | — |
| 图标 `font-family` | `HyperOS_Symbols_VF` | — |
| 图标 `font-size` | `21px` | — |
| 图标 `font-weight` | `330` | — |
| 图标 `color` | `#000000` | `hyperos-color-on-surface` |

#### 子组件: 关闭/搜索按钮（文字型）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `54px` | — |
| `height` | `44px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `padding` | `8px` | — |
| `background-color` | `rgba(0,0,0,0.05)` | `新增色彩变量/container_nav` |
| `border-radius` | `22px` | — |
| `font-family` | `MiSans` | — |
| `font-size` | `17px` | `hyperos_font_size_Headline1` |
| `font-weight` | `380` | `hyperos_font_weight_Headline1` |
| `color` | `#000000` | `hyperos-color-on-surface` |
| `text-align` | `center` | — |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| 占位文字 | MiSans | 17px | 380 | 100% | 0 | `rgba(0,0,0,0.3)` | `Headline/Headline 1` |
| 输入文字 | MiSans | 17px | 380 | 100% | 0 | `#000000` | `Headline/Headline 1` |
| 搜索图标 | HyperOS_Symbols_VF | 18px | 430 | normal | 0 | `rgba(0,0,0,0.3)` | — |
| 关闭/搜索按钮文字 | MiSans | 17px | 380 | normal | 0 | `#000000` | `Headline/Headline 1` |
| 搜索标签文字 | MiSans | 14px | 330 | 21.025px | 0 | `#000000` | `Subtitle/Subtitle 3` |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 搜索框背景（平面） | `rgba(0,0,0,0.05)` | `新增色彩变量/container_nav` |
| 搜索框背景（浮起-玻璃层） | 多层叠加（见上方） | `Pured/Pured_Thin_Glass_Light` |
| 按压态背景 | `linear-gradient rgba(0,0,0,0.12) + rgba(0,0,0,0.06)` | — |
| 占位文字色 | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |
| 输入文字色 | `#000000` | `hyperos-color-on-surface` |
| 光标色 | `#3482FF` | `hyperos-color-on-secondary` |
| 按钮背景色 | `rgba(0,0,0,0.05)` | `新增色彩变量/container_nav` |
| 纯色面板背景 | `#FFFFFF` | `hyperos-color-surface-high` |
| 搜索标签背景 | `#FFFFFF` | `元素色/container_list` |

---

## 变体

### 二、搜索框（手机端）变体

#### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 状态 | `状态` | `默认态` / `按压态` / `激活-未输入` / `激活-输入中` / `激活-输入中2` / `sug词-直搜` | 控制搜索框的交互状态 |
| 表面样式 | `平面&浮起` | `平面` / `浮起` | 平面为纯色背景，浮起为玻璃材质效果 |

共计 **6 × 2 = 12 个变体**（另有 1 个隐藏的旧版 sug词-直搜 变体，总计 13 个）。

#### 搜索框变体预览

![搜索框全部变体](http://localhost:3845/screenshots/1890:7003)

#### 变体差异表

> 仅列出各变体之间**有差异**的属性。未列出的属性与默认变体（状态=默认态, 平面&浮起=平面）相同。

##### 按状态分组

| 属性 | `默认态` | `按压态` | `激活-未输入` | `激活-输入中` | `激活-输入中2` | `sug词-直搜` |
|-----|---------|---------|-------------|-------------|-------------|------------|
| 容器 `flex-direction` | `column` | `column` | `row` | `row` | `row` | `row` |
| 容器 `align-items` | `flex-start` | `flex-start` | `center` | `center` | `center` | `center` |
| 容器 `gap` | `0` | `0` | `10px` | `10px` | `10px` | `10px` |
| 搜索框背景 `width` | `100%` (fill) | `100%` (fill) | `flex: 1` | `flex: 1` | `flex: 1` | `flex: 1` |
| 搜索框背景 `background` | `rgba(0,0,0,0.05)` | 渐变叠加 `rgba(0,0,0,0.12) + rgba(0,0,0,0.06)` | `rgba(0,0,0,0.05)` | `rgba(0,0,0,0.05)` | `rgba(0,0,0,0.05)` | `rgba(0,0,0,0.05)` |
| 搜索框背景 `overflow` | `hidden` | `hidden` | 无 | 无 | 无 | 无 |
| 搜索图标尺寸 | 字体 18px | 24×24px 实例 | 24×24px 实例 | 24×24px 实例 | 24×24px 实例 | 无 |
| 文字显示 | 占位文字 | 占位文字 | 光标 + 占位文字 | 输入文字 + 光标 | 输入文字 + 光标 | 光标 + 占位文字 |
| 文字颜色 | `rgba(0,0,0,0.3)` | `rgba(0,0,0,0.3)` | `rgba(0,0,0,0.3)` | `#000000` | `#000000` | `rgba(0,0,0,0.3)` |
| 一键清除按钮 | 隐藏 | 隐藏 | 隐藏 | 显示 | 显示 | 隐藏 |
| 关闭按钮 | 无 | 无 | ✕ 图标按钮 | ✕ 图标按钮 | "关闭" 文字按钮 | 无 |
| 返回按钮 | 无 | 无 | 无 | 无 | 无 | ← 图标按钮 |
| 搜索按钮 | 无 | 无 | 无 | 无 | 无 | "搜索" 文字按钮 |

##### 按表面样式分组

| 属性 | `平面` | `浮起` |
|-----|-------|-------|
| 搜索框背景 `background-color` | `rgba(0,0,0,0.05)` | 玻璃材质叠加层 |
| 搜索框背景 `border` | 无 | `1px solid rgba(252,252,252,0.2)` |
| 搜索框背景 `border-radius` | `999px` | `28px` |
| 搜索框背景 `box-shadow` | 无 | `0px 0px 40px rgba(0,0,0,0.06), 0px 24px 60px rgba(0,0,0,0.08), inset 0px 2px 2px #9D9D9D` |
| 搜索框背景 `backdrop-filter` | 无 | `blur(10px)` |
| `mix-blend-mode` 层 | 无 | `soft-light` + `hard-light` 双层叠加 |

### 三、材质板子变体

#### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 材质 | `材质` | `混色模糊` / `纯色面板` | 搜索框背景材质类型 |
| 深色模式 | `深色模式` | `light` / `dark` | 适配浅色/深色模式 |

共计 **2 × 2 = 4 个变体**。

![材质板子变体预览](http://localhost:3845/screenshots/80636:7500)

#### 变体差异表

| 属性 | 混色模糊 light | 混色模糊 dark | 纯色面板 light | 纯色面板 dark |
|-----|--------------|-------------|--------------|-------------|
| `background` | 玻璃三层叠加 | 玻璃三层叠加（深色） | `#FFFFFF` | `#242424` |
| `box-shadow` | FrostShadow | FrostShadow | Shadow_Low | Shadow_Low |
| `border` | `1px solid rgba(252,252,252,0.2)` | `1px solid rgba(252,252,252,0.2)` | 无 | 无 |
| `backdrop-filter` | `blur(10px)` | `blur(10px)` | 无 | 无 |
| `mix-blend-mode` 层 | 有 | 有 | 无 | 无 |
| Token | `Pured/Pured_Thin_Glass_Light` | `Pured/Pured_Thin_Glass_Dark` | `Base/Popup_Light` | `Base/Popup_Dark` |

### 四、搜索标签变体

#### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 底色 | `底色` | `灰底白卡` / `白底灰卡` | 控制标签与背景的色彩层级关系 |

共计 **2 个变体**。

![搜索标签变体预览](http://localhost:3845/screenshots/7334:9620)

#### 搜索标签容器

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `height` | `40px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `padding` | `9px 22px` | — |
| `border-radius` | `20px` | `hyperos_theme_radius_medium` |
| `background-color` | `#FFFFFF` | `元素色/container_list` |
| `overflow` | `hidden` | — |

### 五、Pad 搜索框变体

#### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 状态 | `状态` | `默认_最小宽度` / `默认` / `激活-未输入` / `激活-输入中` | Pad 端搜索框交互状态 |
| 表面样式 | `平面&浮起` | `平面` / `浮起` | 同手机端两种视觉风格 |

共计 **4 × 2 = 8 个变体**。

![Pad 搜索框变体预览](http://localhost:3845/screenshots/81907:21340)

#### 变体差异表

| 属性 | `默认_最小宽度` | `默认` | `激活-未输入` | `激活-输入中` |
|-----|--------------|-------|-------------|-------------|
| 搜索框 `width` | `176px` | `264px` | `264px` | `264px` |
| 搜索框 `height` | `44px` | `44px` | `44px` | `44px` |
| 文字显示 | 占位文字 | 占位文字 | 光标 + 占位文字 | 输入文字 + 光标 |
| 一键清除按钮 | 隐藏 | 隐藏 | 隐藏 | 显示 |
| 关闭按钮 | 无 | 无 | 无 | 无 |

---

## 交互状态

> 以「默认态 + 平面」为基准，其他状态仅列出**发生变化**的属性。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `默认态` | — | — | （基准状态） | — |
| `按压态` | 手指按下搜索框 | `background` | `linear-gradient(rgba(0,0,0,0.12)), linear-gradient(rgba(0,0,0,0.06))` 叠加 | — |
| `按压态` | 手指按下搜索框 | `padding` | `12px`（四周） | — |
| `按压态` | 手指按下搜索框 | 搜索图标 | 从字体图标变为 24×24 实例 | — |
| `激活-未输入` | 点击搜索框后、尚未输入 | 容器 `flex-direction` | `row` | — |
| `激活-未输入` | 点击搜索框后、尚未输入 | 容器 `gap` | `10px` | — |
| `激活-未输入` | 点击搜索框后、尚未输入 | 光标 | 显示，颜色 `#3482FF` | `hyperos-color-on-secondary` |
| `激活-未输入` | 点击搜索框后、尚未输入 | 关闭按钮（✕ 图标） | 显示 | — |
| `激活-输入中` | 用户正在输入文字 | 输入文字 `color` | `#000000` | `hyperos-color-on-surface` |
| `激活-输入中` | 用户正在输入文字 | 一键清除按钮 | 显示（20×20px） | — |
| `激活-输入中` | 用户正在输入文字 | 关闭按钮（✕ 图标） | 显示 | — |
| `激活-输入中2` | 用户输入文字（变体 2） | 关闭按钮 | 改为 "关闭" 文字按钮（54×44px） | — |
| `sug词-直搜` | 出现搜索建议，可直接搜索 | 容器布局 | 返回按钮 + 搜索框 + 搜索按钮 三段式 | — |
| `sug词-直搜` | 出现搜索建议 | 返回按钮（← 图标） | 44×44px 圆形按钮 | — |
| `sug词-直搜` | 出现搜索建议 | "搜索" 文字按钮 | 54×44px | — |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

### 搜索框（手机端）

```typescript
interface SearchBarProps {
  /** 搜索框交互状态 */
  state: '默认态' | '按压态' | '激活-未输入' | '激活-输入中' | '激活-输入中2' | 'sug词-直搜';
  /** 表面样式：平面为纯色背景，浮起为玻璃材质 */
  surface: '平面' | '浮起';
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 状态 | Variant | `state` | `默认态` | 控制搜索框的交互状态 |
| 平面&浮起 | Variant | `surface` | `平面` | 平面为纯色背景，浮起为玻璃材质 |

### 材质板子

```typescript
interface SearchBarMaterialProps {
  /** 材质类型 */
  material: '混色模糊' | '纯色面板';
  /** 深色模式适配 */
  colorScheme: 'light' | 'dark';
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 材质 | Variant | `material` | `混色模糊` | 背景材质类型 |
| 深色模式 | Variant | `colorScheme` | `light` | 浅色/深色模式 |

### 搜索标签

```typescript
interface SearchTagProps {
  /** 底色方案，控制标签与背景的色彩层级 */
  background: '灰底白卡' | '白底灰卡';
  /** 标签文字内容 */
  label: string; // 默认: "标签"
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 底色 | Variant | `background` | `灰底白卡` | 标签底色方案 |

### Pad 搜索框

```typescript
interface PadSearchBarProps {
  /** 搜索框交互状态 */
  state: '默认_最小宽度' | '默认' | '激活-未输入' | '激活-输入中';
  /** 表面样式 */
  surface: '平面' | '浮起';
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 状态 | Variant | `state` | `默认_最小宽度` | Pad 端搜索框状态 |
| 平面&浮起 | Variant | `surface` | `平面` | 表面样式 |

---

## 使用指南

### 何时使用

- **全局搜索入口**：在应用首页或设置页顶部放置搜索框，使用「默认态 + 平面」作为初始状态
- **浮起搜索**：在需要与背景内容产生层次分离时（如地图、图片上方覆盖搜索框），使用「浮起」变体
- **Pad 端**：在平板设备上使用 Pad 搜索框变体，支持最小宽度（176px）以适应不同布局
- **搜索建议直搜**：当搜索出现热门建议词时，使用「sug词-直搜」状态展示返回+搜索框+搜索按钮三段式布局

### 何时不使用

- **筛选/过滤场景**：应使用 Filter / Chip 组件代替
- **简单文本输入**：应使用 TextField / Input 组件代替
- **命令/语音搜索**：请由设计团队补充

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 搜索框始终保持 44px 高度 | 自定义搜索框高度 | 符合 HyperOS 触控最小点击区域规范 |
| 浮起模式使用「混色模糊」材质 | 在浮起模式使用纯色背景 | 玻璃材质是浮起模式的核心视觉语言 |
| 激活态显示关闭按钮以退出搜索 | 仅依赖系统返回键退出搜索 | 提供明确的退出搜索操作路径 |
| Pad 端根据容器宽度选择最小宽度或默认宽度 | 固定使用手机端 392px 宽度 | Pad 端搜索框应响应式适配 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `新增色彩变量/container_nav` | `rgba(0,0,0,0.05)` | color | 搜索框背景（平面）、按钮背景 |
| `hyperos_theme_radius_circle` | `999px` | radius | 搜索框背景圆角（平面） |
| `hyperos-color-on-surface-octonary` | `rgba(0,0,0,0.3)` | color | 占位文字色、搜索图标色 |
| `hyperos-color-on-surface` | `#000000` | color | 输入文字色、按钮文字/图标色 |
| `hyperos-color-on-secondary` | `#3482FF` | color | 光标色 |
| `hyperos-color-on-surface-secondary` | `rgba(0,0,0,0.8)` | color | 次级文字色 |
| `hyperos-color-surface-high` | `#FFFFFF` | color | 纯色面板背景（light） |
| `hyperos-color-surface-container-low` | `rgba(0,0,0,0.06)` | color | 表面容器低层色 |
| `hyperos-color-surface-container-medium` | `rgba(0,0,0,0.08)` | color | 表面容器中层色 |
| `hyperos_color_surface_low` | `#F3F3F3` | color | 低层表面色 |
| `hyperos_theme_radius_medium` | `20px` | radius | 搜索标签圆角 |
| `hyperos_theme_radius_demi_big` | `24px` | radius | 中大圆角 |
| `hyperos_theme_radius_big` | `36px` | radius | 大圆角 |
| `hyperos_font_size_Headline1` | `17px` | font-size | 搜索框文字字号 |
| `hyperos_font_weight_Headline1` | `380` | font-weight | 搜索框文字字重 |
| `hyperos_font_size_subtitle3` | `14px` | font-size | 搜索标签字号 |
| `hyperos_font_weight_subtitle3` | `330` | font-weight | 搜索标签字重 |
| `padding/padding_sm` | `12px` | spacing | 容器水平内边距 |
| `spacing-xl` | `16px` | spacing | 大间距 |
| `spacing-md` | `8px` | spacing | 搜索框内元素间距 |
| `cos-space/xxs` | `6px` | spacing | 超小间距 |
| `元素色/container_list` | `#FFFFFF` | color | 搜索标签背景 |
| `Pured/Pured_Thin_Glass_Light` | 玻璃三层叠加 | material | 浮起搜索框背景（light） |
| `Pured/Pured_Thin_Glass_Dark` | 玻璃三层叠加（深色） | material | 浮起搜索框背景（dark） |
| `Base/Popup_Light` | `#FFFFFF` | color | 纯色面板（light） |
| `Base/Popup_Dark` | `#242424` | color | 纯色面板（dark） |
| `Shadow/Shadow_Low` | `0px 12px 40px rgba(0,0,0,0.04), 0px 0px 20px rgba(0,0,0,0.02)` | shadow | 纯色面板阴影 |
| `FrostShadow/FrostEffect_Thin_ShadowOn` | `0px 24px 60px rgba(0,0,0,0.08), 0px 0px 40px rgba(0,0,0,0.06), inset 0px 2px 2px #9D9D9D + blur(20px)` | shadow+blur | 玻璃材质阴影 |
| `white/color-white-solid-30` | `#242424` | color | 深色模式白色基色 |
| `var(--color-icon)` | `rgba(0,0,0,0.9)` | color | 图标默认色 |

---

## 设计注释

> 1. 搜索框组件区分手机端（392px 固定宽度）和 Pad 端（可变宽度，最小 176px），请根据设备类型选择正确的组件。
> 2. 浮起（Raised）模式的玻璃材质由三层叠加实现：底色层 + soft-light 混合层 + hard-light 模糊层，需注意浏览器对 `mix-blend-mode` 和 `backdrop-filter` 的兼容性。
> 3. OS4 已禁用旧版玻璃材质效果（`GlassShadow (OS4禁用）`），浮起模式统一使用 `FrostShadow/FrostEffect_Thin_ShadowOn` 霜冻阴影效果。
> 4. 搜索框的「激活-输入中」和「激活-输入中2」两个状态的区别在于关闭按钮的样式：前者使用 ✕ 图标按钮，后者使用 "关闭" 文字按钮，具体使用场景请由设计团队补充。
> 5. 搜索标签（Search Tag）描述为"按钮文字"，可用于搜索热词推荐入口。
