---
component: Switch
description: 小米 HyperOS4 开关控件，用于在两种互斥状态（开启/关闭）之间进行切换
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=82713-132370
figma_node_id: "12643:23242"
variants: "1 dimension (状态), 4 variants"
tokens_used: 6
---

# 开关 Switch

> HyperOS4 系统级开关控件，用于在两种互斥状态之间即时切换（如开启/关闭某项功能）。拨动后即刻生效，无需额外确认操作。支持开启、未开启两种基础状态，以及各自对应的不可用（disabled）状态。

## 预览

![开关组件全部变体预览](http://localhost:3845/figma/screenshot/12643:23242)

---

## 组件结构

```
开关                                        // COMPONENT_SET | 12643:23242
├── 状态=开启                               // COMPONENT | 12643:23243
│   ├── Rectangle（轨道）                   // RECTANGLE | 12643:23244
│   └── Oval（滑块）                        // FRAME > IMG | 12643:23245
├── 状态=开启不可用                          // COMPONENT | 12643:23249
│   ├── Rectangle（轨道）                   // RECTANGLE | 12643:23250
│   └── Oval（滑块）                        // FRAME > IMG | 12643:23251
├── 状态=未开启                              // COMPONENT | 12643:23246
│   ├── Rectangle（轨道）                   // RECTANGLE | 12643:23247
│   └── Oval（滑块）                        // FRAME > IMG | 12643:23248
└── 状态=未开启不可用                         // COMPONENT | 12643:23252
    ├── Rectangle（轨道）                   // RECTANGLE | 12643:23253
    └── Oval（滑块）                        // FRAME > IMG | 12643:23254
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| Rectangle（轨道） | RECTANGLE | `12643:23244` 等 | 开关的背景轨道，承载颜色状态变化 |
| Oval（滑块） | FRAME | `12643:23245` 等 | 圆形滑块（Thumb），通过位置偏移表达开/关状态，包含阴影效果（SVG 资源） |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器（各变体共享）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `49px` | — |
| `height` | `32px`（hug） | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `padding` | `2px 0` | — |
| `position` | `relative` | — |
| `overflow` | `visible` | — |

### 子组件: Rectangle（轨道）

| CSS 属性 | 值（默认：开启态） | Token |
|---------|----|-------|
| `width` | `49px` | — |
| `height` | `28px` | — |
| `border-radius` | `999px` | `miuix_theme_radius_circle` |
| `background-color` | `#3482FF` | `miuix_default_color_primary` |
| `flex-shrink` | `0` | — |
| `opacity` | `1` | — |
| `border` | 无 | — |
| `box-shadow` | 无 | — |

### 子组件: Oval（滑块）

| CSS 属性 | 值（默认：开启态） | Token |
|---------|----|-------|
| `width` | `20px` | — |
| `height` | `20px` | — |
| `position` | `absolute` | — |
| `top` | `50%` | — |
| `transform` | `translateY(-50%)` | — |
| `left` | `25px` | — |
| `border-radius` | `50%`（圆形） | — |
| `background-color` | `#FFFFFF`（含投影，以 SVG 资源渲染） | `miuix_default_color_on_primary` |

### 文字样式

该组件不涉及此项。

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 轨道背景-开启 | `#3482FF` | `miuix_default_color_primary` |
| 轨道背景-开启不可用 | `#3482FF` + `opacity: 0.3` | `全系统色板/Blue` |
| 轨道背景-未开启 | `rgba(0,0,0,0.10)` | `miuix_default_color_surface_container_high` |
| 轨道背景-未开启不可用 | `rgba(0,0,0,0.04)` | `miuix_default_color_surface_container` |
| 滑块填充 | `#FFFFFF` | `miuix_default_color_on_primary` |

---

## 变体

### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 状态 | `状态` | `开启` / `开启不可用` / `未开启` / `未开启不可用` | 控制开关的视觉状态与可用性 |

共计 **1 × 4 = 4 个变体**。

### 变体差异表

> 仅列出各变体之间**有差异**的属性。未列出的属性与默认变体（状态=开启）相同。

#### 按状态分组

| 属性 | `开启` | `开启不可用` | `未开启` | `未开启不可用` |
|-----|-------|------------|---------|--------------|
| 轨道 `background-color` | `#3482FF` | `#3482FF` | `rgba(0,0,0,0.10)` | `rgba(0,0,0,0.04)` |
| 轨道 `background-color` Token | `miuix_default_color_primary` | `全系统色板/Blue` | `miuix_default_color_surface_container_high` | `miuix_default_color_surface_container` |
| 轨道 `opacity` | `1` | `0.3` | `1` | `1` |
| 滑块 `left` | `25px` | `25px`（等效 `right: 4px`） | `4px` | `4px` |
| 滑块外观 | 白色圆形 + 投影 | 白色圆形 + 轻投影（降低对比度） | 灰白色圆形 + 轻投影 | 浅灰色圆形（极低对比度） |

#### 状态=开启 详情

![开关 开启态](http://localhost:3845/figma/screenshot/12643:23243)

- 轨道为品牌蓝色（`#3482FF`），滑块位于右侧（`left: 25px`）
- 滑块为白色圆形，带有轻微投影以增强层次感

#### 状态=开启不可用 详情

![开关 开启不可用态](http://localhost:3845/figma/screenshot/12643:23249)

- 轨道同为蓝色（`#3482FF`），但整体 `opacity: 0.3`，呈浅蓝色效果
- 滑块保持在右侧（`right: 4px`，等效 `left: 25px`）
- 滑块投影减弱，整体视觉弱化，传达不可操作语义

#### 状态=未开启 详情

![开关 未开启态](http://localhost:3845/figma/screenshot/12643:23246)

- 轨道为半透明黑色叠加（`rgba(0,0,0,0.10)`），在浅色背景下呈灰色
- 滑块位于左侧（`left: 4px`）
- 滑块为灰白色调，带轻微投影

#### 状态=未开启不可用 详情

![开关 未开启不可用态](http://localhost:3845/figma/screenshot/12643:23252)

- 轨道为极浅半透明黑色（`rgba(0,0,0,0.04)`），几乎不可见
- 滑块位于左侧（`left: 4px`）
- 滑块为浅灰色，无明显投影，整体视觉极度弱化

---

## 交互状态

> 以「默认态（开启）」为基准，其他状态仅列出**发生变化**的属性。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default`（开启） | — | — | （基准状态） | — |
| `unchecked`（未开启） | 用户点击/拨动关闭 | 轨道 `background-color` | `rgba(0,0,0,0.10)` | `miuix_default_color_surface_container_high` |
| | | 滑块 `left` | `4px`（从 `25px`） | — |
| `disabled + checked` | `disabled=true` 且处于开启态 | 轨道 `opacity` | `0.3` | — |
| `disabled + unchecked` | `disabled=true` 且处于关闭态 | 轨道 `background-color` | `rgba(0,0,0,0.04)` | `miuix_default_color_surface_container` |
| | | 滑块 `left` | `4px` | — |
| `hover` | 鼠标悬停 | Figma 未定义，请由设计团队补充 | — | — |
| `focused` | 键盘聚焦 | Figma 未定义，请由设计团队补充 | — | — |
| `active`（按下） | 手指/鼠标按下 | Figma 未定义，请由设计团队补充 | — | — |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

```typescript
interface SwitchProps {
  /** 开关是否处于开启状态 */
  checked?: boolean; // 默认: false
  /** 开关是否不可用 */
  disabled?: boolean; // 默认: false
  /** 状态变化时的回调函数 */
  onChange?: (checked: boolean) => void;
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 状态 | Variant | `checked` + `disabled` | `开启` → `checked=true, disabled=false` | Figma 为单维度枚举，建议在代码中拆分为 `checked` 和 `disabled` 两个布尔属性 |

**Figma 变体 → Props 映射**：

| Figma `状态` 值 | `checked` | `disabled` |
|----------------|-----------|------------|
| `开启` | `true` | `false` |
| `开启不可用` | `true` | `true` |
| `未开启` | `false` | `false` |
| `未开启不可用` | `false` | `true` |

---

## 使用指南

### 何时使用

- **功能开关**：用于即时切换某项功能的开启/关闭，如 Wi-Fi、蓝牙、通知权限等
- **设置项**：在设置页面中作为二元选择控件，用户操作后立即生效
- **列表行尾**：配合列表项使用，放置在行尾区域作为操作入口

### 何时不使用

- **需要确认的操作**：若切换后需额外确认才生效，应使用 Checkbox（复选框）+ 提交按钮代替
- **多选场景**：在多选列表中应使用 Checkbox 代替
- **单选互斥**：多个选项中只能选一个时应使用 Radio（单选框）代替

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 将 Switch 放在设置列表项的右侧 | 将 Switch 放在标签文字左侧 | HyperOS 系统规范中开关始终右对齐 |
| 使用简短的文字标签说明开关控制的内容 | 不提供标签直接放置裸开关 | 用户需要明确知道开关控制的是什么功能 |
| 切换后即时生效并给予视觉反馈 | 切换后无任何反馈或需要额外保存按钮 | Switch 的语义是即时生效 |
| 对不可操作的开关使用 disabled 态 | 隐藏不可用的开关 | 保持界面一致性，disabled 态提示用户此处存在选项但暂不可用 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `miuix_default_color_primary` | `#3482FF` | color | 轨道背景（开启态） |
| `全系统色板/Blue` | `#3482FF` | color | 轨道背景（开启不可用态，配合 opacity: 0.3） |
| `miuix_default_color_surface_container_high` | `rgba(0,0,0,0.10)` / `#0000001A` | color | 轨道背景（未开启态） |
| `miuix_default_color_surface_container` | `rgba(0,0,0,0.04)` / `#0000000A` | color | 轨道背景（未开启不可用态） |
| `miuix_default_color_on_primary` | `#FFFFFF` | color | 滑块填充色 |
| `miuix_theme_radius_circle` | `999px` | radius | 轨道圆角（全圆角胶囊形） |

---

## 设计注释

> 1. 滑块（Oval）在 Figma 中以 SVG 图片资源呈现，包含了投影效果。实际开发中应使用 `border-radius: 50%` + `box-shadow` 实现圆形滑块及其投影，无需使用图片资源。
> 2. 轨道宽度 `49px` 为固定值，在所有变体中保持一致；滑块直径 `20px` 同样固定。
> 3. 开启态和关闭态之间的滑块位移为 `21px`（从 `left: 4px` 到 `left: 25px`），建议使用 CSS `transition` 实现平滑动画。
> 4. 「开启不可用」态使用了 `opacity: 0.3` 应用于整个轨道元素，而非仅修改颜色的 alpha 值，需注意此区别。
> 5. Figma 中未定义 `hover`、`focused`、`active` 等交互态，需由设计团队补充。
