---
component: DrawerWindow
description: 底部弹出的抽屉窗口容器，支持三档高度（高/中/低），带有毛玻璃背景和标题栏导航
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=80384-13374
figma_node_id: "80384:13741"
variants: "1 dimension, 3 variants"
tokens_used: 12
---

# 抽屉窗口 DrawerWindow

> 从屏幕底部弹出的模态抽屉容器，通过三档高度（高 Max / 中 Medium / 低 Min）适配不同内容量场景。容器采用 HyperOS 毛玻璃材质，包含顶部拖拽手柄、标题栏（带关闭和确认操作）以及底部 Home Indicator 指示条。

## 预览

![DrawerWindow 全部变体预览](https://www.figma.com/api/mcp/asset/drawer-window-all-variants)

### 档位=高 Max

![DrawerWindow 高 Max](https://www.figma.com/api/mcp/asset/drawer-window-max)

### 档位=中 Medium

![DrawerWindow 中 Medium](https://www.figma.com/api/mcp/asset/drawer-window-medium)

### 档位=低 Min

![DrawerWindow 低 Min](https://www.figma.com/api/mcp/asset/drawer-window-min)

---

## 组件结构

```
抽屉窗口 Drawer Window                     // COMPONENT_SET | 80384:13741
├── 档位=高 Max                            // COMPONENT | 80384:13778
│   ├── 玻璃材质_原子                       // FRAME (absolute) | 93056:37683
│   │   ├── 背景层1 (rgba(0,0,0,0.15))     // FRAME | —
│   │   ├── 背景层2 (soft-light)            // FRAME | —
│   │   ├── 背景层3 (hard-light + blur)     // FRAME | —
│   │   └── 内阴影层                        // FRAME | —
│   ├── 抽屉手柄                            // FRAME | 80502:18422
│   │   ├── 手柄                            // FRAME | I80502:18422;80502:14226
│   │   │   └── 未激活 (拖拽条)              // FRAME | I80502:18422;80502:14226;80502:14027
│   │   └── 标题栏 Navigation Bar           // INSTANCE | I80502:18422;80502:14227
│   │       ├── Container                   // FRAME | I80502:18422;80502:14227;4614:35949
│   │       │   ├── 左 (关闭按钮区)          // FRAME | I80502:18422;80502:14227;91243:106928
│   │       │   │   └── close               // INSTANCE | 86954:12902
│   │       │   ├── 标题文字                 // TEXT | I80502:18422;80502:14227;1890:3395
│   │       │   └── 右 (确认按钮区)          // FRAME | I80502:18422;80502:14227;91243:107410
│   │       │       └── Checkmark-OK        // INSTANCE | 86954:12900
│   └── 杆子 (Home Indicator)               // INSTANCE | 80384:13795
│       └── 152 (指示条)                     // FRAME | I80384:13795;2710:49168
├── 档位=中 Medium                          // COMPONENT | 80384:13760
│   └── ... (结构同上)
└── 档位=低 Min                             // COMPONENT | 80384:13742
    └── ... (结构同上)
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| 玻璃材质_原子 | FRAME | `93056:37683` (Max) / `93056:37725` (Medium) / `80384:14289` (Min) | 毛玻璃背景材质，包含多层混合模式叠加 |
| 抽屉手柄 | FRAME | `80502:18422` (Max) / `80502:18480` (Medium) / `80502:18517` (Min) | 顶部区域，包含拖拽条和标题栏 |
| 手柄 | FRAME | `I80502:18422;80502:14226` | 拖拽条容器，包含未激活状态的短横条 |
| 标题栏 Navigation Bar | INSTANCE | `I80502:18422;80502:14227` | 导航栏，包含左侧关闭、居中标题、右侧确认 |
| 杆子 | INSTANCE | `80384:13795` (Max) / `80384:13777` (Medium) / `80384:13759` (Min) | 底部 Home Indicator 指示条 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器（以「高 Max」为基准）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `392px` | — |
| `height` | `819px` | — |
| `min-width` | `336px` | — |
| `max-width` | `850px` | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `justify-content` | `space-between` | — |
| `align-items` | `flex-start` | — |
| `border-radius` | `36px 36px 0 0` | `hyperos_theme_radius_big` |
| `overflow` | `hidden` | — |
| `position` | `relative` | — |

### 子组件: 玻璃材质_原子

> 使用绝对定位铺满整个容器的毛玻璃背景层，由多层混合模式叠加实现。

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `position` | `absolute` | — |
| `inset` | `0` | — |
| `border` | `0.8px solid #F9F9F9` | `Stroke/Glass_Stroke_Big_Light` |
| `border-radius` | `36px 36px 0 0` | `hyperos_theme_radius_big` |
| `pointer-events` | `none` | — |

#### 背景层叠加顺序

| 层级 | `background-color` | `mix-blend-mode` | `backdrop-filter` | 说明 |
|------|-------------------|------------------|-------------------|------|
| 1 | `rgba(0,0,0,0.15)` | — | — | 暗色底层 |
| 2 | `rgba(255,255,255,0.8)` | `soft-light` | — | 柔光层 |
| 3 | `rgba(255,255,255,0.8)` | `hard-light` | `blur(30px)` | 强光 + 模糊层 |

#### 内阴影

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `box-shadow` | `inset 0px 2px 2px 0px #9D9D9D` | `FrostShadow/FrostEffect_Thick_ShadowOff` |

### 子组件: 手柄（拖拽条）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%` | — |
| `height` | `24px` | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `padding` | `10px` | — |

#### 拖拽条（未激活状态）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `60px` | — |
| `height` | `3px` | — |
| `border-radius` | `3px` | — |
| `background-color` | `rgba(0,0,0,0.1)` | `hyperos-color-outline` |
| `position` | `absolute` | — |
| `top` | `9px` | — |
| `left` | `50%` | — |
| `transform` | `translateX(-50%)` | — |

### 子组件: 标题栏 Navigation Bar

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%` | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `flex-start` | — |
| `justify-content` | `center` | — |
| `padding` | `6px 12px` | `padding/padding_sm`（水平） |
| `backdrop-filter` | `blur(33px)` | `模糊数值/Default`（参考值 66px，实际 33px） |

#### 左侧操作区（关闭按钮）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `max-width` | `44px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |

#### 按钮触摸区域

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `44px` | — |
| `height` | `44px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `padding` | `0 8px` | — |
| `border-radius` | `1000px` | — |

#### 图标

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `28px` | — |
| `height` | `28px` | — |
| `font-family` | `HyperOS Symbols VF` | — |
| `font-size` | `21px` | — |
| `color` | `#000000` | `hyperos-color-on-surface` |

#### 标题文字

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `position` | `absolute` | — |
| `left` | `50%` | — |
| `top` | `50%` | — |
| `transform` | `translate(-50%, -50%)` | — |
| `width` | `256px` | — |
| `height` | `28px` | — |
| `text-align` | `center` | — |
| `white-space` | `nowrap` | — |
| `overflow` | `hidden` | — |
| `text-overflow` | `ellipsis` | — |

#### 右侧操作区（确认按钮）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `max-width` | `96px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `flex-end` | — |

### 子组件: 杆子（Home Indicator）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%` | — |
| `height` | `16px` | — |
| `position` | `relative` | — |

#### 指示条

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `152px` | — |
| `height` | `4px` | — |
| `border-radius` | `4px` | — |
| `background-color` | `rgba(0,0,0,0.8)` | `hyperos-color-on-surface-secondary` |
| `position` | `absolute` | — |
| `top` | `50%` | — |
| `left` | `50%` | — |
| `transform` | `translate(-50%, -50%)` | — |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| 标题 | MiSans | 18px | 380 (Medium) | 100% | 0 | `#000000` | `Title/Title 4`、`hyperos_font_size_title4`、`hyperos_font_weight_title4` |
| 图标 | HyperOS Symbols VF | 21px | Regular | normal | 0 | `#000000` | `hyperos-color-on-surface` |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 玻璃暗色底层 | `rgba(0,0,0,0.15)` | `Pured/Pured_Thick_Glass_Light` |
| 玻璃亮色层 | `rgba(255,255,255,0.8)` | `Pured/Pured_Thick_Glass_Light` |
| 玻璃边框 | `#F9F9F9` | `Stroke/Glass_Stroke_Big_Light` |
| 拖拽条 | `rgba(0,0,0,0.1)` | `hyperos-color-outline` |
| 标题文字 | `#000000` | `hyperos-color-on-surface` |
| 图标色 | `#000000` | `hyperos-color-on-surface` |
| Home Indicator | `rgba(0,0,0,0.8)` | `hyperos-color-on-surface-secondary` |
| 内阴影 | `#9D9D9D` | `FrostShadow/FrostEffect_Thick_ShadowOff` |

---

## 变体

### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 档位 | `档位` | `高 Max` / `中 Medium` / `低 Min` | 控制抽屉窗口展开高度 |

共计 **1 × 3 = 3 个变体**。

### 变体差异表

> 仅列出各变体之间**有差异**的属性。未列出的属性与默认变体（高 Max）相同。

#### 按档位分组

| 属性 | `高 Max` | `中 Medium` | `低 Min` |
|-----|---------|------------|---------|
| `height` | `819px` | `508px` | `112px` |
| `min-height` | — | — | `112px` |
| `min-width` | `336px` | `336px` | — |
| `max-width` | `850px` | `850px` | — |
| `align-items` | `flex-start` | `flex-start` | `center` |

#### 档位=高 Max 详情

- 高度 `819px`，适用于内容丰富的场景（如设置页、列表选择）
- 设置了 `min-width: 336px` 和 `max-width: 850px`，支持自适应宽度
- 内容区域从标题栏下方延展至 Home Indicator 上方

#### 档位=中 Medium 详情

- 高度 `508px`，适用于中等内容量场景（如简短表单、快捷操作面板）
- 同样设置了 `min-width: 336px` 和 `max-width: 850px`
- 结构与高档位完全一致，仅高度缩小

#### 档位=低 Min 详情

- 高度 `112px`，最小化展示，仅露出标题栏和 Home Indicator
- `min-height: 112px`，确保最小可见高度
- `align-items: center` 使内部元素居中对齐
- 无额外内容区域，适用于折叠/最小化状态

---

## 交互状态

> 以「默认态」为基准，其他状态仅列出**发生变化**的属性。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态） | — |
| `拖拽中` | 用户拖动手柄 | Figma 未定义，请由设计团队补充 | — | — |
| `hover`（操作按钮） | 鼠标悬停关闭/确认按钮 | Figma 未定义，请由设计团队补充 | — | — |
| `active`（操作按钮） | 鼠标按下 / 触摸 | Figma 未定义，请由设计团队补充 | — | — |
| `disabled` | — | Figma 未定义，请由设计团队补充 | — | — |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

```typescript
interface DrawerWindowProps {
  /** 抽屉窗口展开的高度档位 */
  level: '高 Max' | '中 Medium' | '低 Min';
  /** 标题栏文字内容 */
  title?: string; // 默认: "小标题"
  /** 左侧操作按钮图标（默认为关闭图标） */
  leftIcon?: ReactNode; // 默认: Close
  /** 右侧操作按钮图标（默认为确认图标） */
  rightIcon?: ReactNode; // 默认: Checkmark-OK
  /** 点击左侧按钮回调 */
  onClose?: () => void;
  /** 点击右侧按钮回调 */
  onConfirm?: () => void;
  /** 抽屉窗口内的内容 */
  children?: ReactNode;
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 档位 | Variant | `level` | `高 Max` | 控制抽屉展开高度，3 档可选 |
| 标题文字 | Text（推断） | `title` | `"小标题"` | 导航栏居中标题 |
| 左侧图标 | Instance Swap（推断） | `leftIcon` | `Close` | 关闭操作图标 |
| 右侧图标 | Instance Swap（推断） | `rightIcon` | `Checkmark-OK` | 确认操作图标 |

---

## 使用指南

### 何时使用

- **设置/编辑场景**：使用「高 Max」档位，承载完整的设置项列表或编辑表单
- **快捷操作面板**：使用「中 Medium」档位，展示快捷开关、音量调节等操作面板
- **通知/最小化**：使用「低 Min」档位，仅展示标题信息，用户可上拉展开

### 何时不使用

- **全屏内容页**：应使用全屏 Page 组件代替，抽屉不适合展示需要全屏沉浸的内容
- **简单弹窗/对话框**：应使用 Dialog 组件代替，无需底部弹出的交互模式
- **Toast 通知**：应使用 Toast 组件代替，短暂提示不需要手动关闭的容器

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 根据内容量选择合适的档位 | 固定使用高档位展示少量内容 | 过大的空白区域影响用户体验 |
| 保留标题栏的关闭和确认操作 | 移除所有操作按钮 | 用户需要明确的关闭路径 |
| 内容超出时允许内部滚动 | 让内容撑破容器高度 | 抽屉高度应保持固定，内部内容可滚动 |
| 使用毛玻璃材质保持一致性 | 自定义不透明背景色 | HyperOS 设计语言要求统一的玻璃质感 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `hyperos_theme_radius_big` | `36px` | radius | 容器顶部圆角 |
| `hyperos-color-on-surface` | `#000000` | color | 标题文字色、图标色 |
| `hyperos-color-on-surface-secondary` | `rgba(0,0,0,0.8)` | color | Home Indicator 指示条 |
| `hyperos-color-outline` | `rgba(0,0,0,0.1)` | color | 拖拽条（未激活） |
| `hyperos_color_surface` | `#FFFFFF` | color | 基础表面色（参考） |
| `hyperos_font_size_title4` | `18px` | font-size | 标题字号 |
| `hyperos_font_weight_title4` | `380` | font-weight | 标题字重 |
| `padding/padding_sm` | `12px` | spacing | 标题栏水平内边距 |
| `Pured/Pured_Thick_Glass_Light` | `#000000, #FFFFFF, #FFFFFF` | material | 玻璃材质色值组合 |
| `Stroke/Glass_Stroke_Big_Light` | `#F9F9F9` | border | 玻璃材质边框 |
| `FrostShadow/FrostEffect_Thick_ShadowOff` | `inset 0px 2px 2px #9D9D9D + blur(60px)` | effect | 内阴影 + 背景模糊 |
| `模糊数值/Default` | `blur(66px)` | effect | 默认背景模糊值（标题栏实际使用 33px） |

---

## 设计注释

> 1. **毛玻璃材质实现**：玻璃效果通过 3 层背景叠加实现（暗色层 → soft-light 层 → hard-light + blur 层），外加一层内阴影。实现时需注意 `mix-blend-mode` 和 `backdrop-filter` 的兼容性。
> 2. **标题栏 Navigation Bar**：组件提供了默认状态与浮层状态的切换展示。但由于部分原始组件并不包含浮层样式，因此当切换为浮层状态时，会自动回退为默认样式，这是正常表现。
> 3. **档位切换动画**：Figma 中未定义档位切换时的过渡动画，建议实现时添加高度过渡动画（从当前档位平滑切换到目标档位）。
> 4. **拖拽手势**：Figma 中未定义拖拽交互的中间状态（如拖拽条高亮、容器跟手效果），建议由设计团队补充。
> 5. **宽度自适应**：高/中档位设置了 `min-width: 336px` 和 `max-width: 850px`，低档位未设置，实际实现时建议统一处理。
> 6. **图标字体**：关闭和确认图标使用 `HyperOS Symbols VF` 字体图标（Unicode 字符），实现时需确保字体资源已加载。
