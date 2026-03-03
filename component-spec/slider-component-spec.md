# 滑动选择器 Slider

> HyperOS 4 设计系统中的滑动选择器组件，用于在连续或离散的数值范围内进行选择和调节，支持音量、亮度、字号、偏移等场景。

## 预览

![滑动选择器 Slider 全部变体](https://www.figma.com/api/mcp/asset/bffdb547-6d69-4923-b2b4-daa6b51b935e)

---

## 组件结构

```
Slider
├── Slider-Card                    // 卡片容器
│   ├── Slider-Header              // 标题区（仅连续滑动类型）
│   │   ├── Slider-Header-IconContainer  // 图标容器
│   │   └── 标题文本
│   ├── Slider-ProgressSection     // 进度区（仅连续滑动类型）
│   │   └── Slider-TrackWrapper    // 轨道容器
│   ├── Slider-ContentWrapper      // 内容包装器（中心点滑动类型）
│   │   └── Slider-Row
│   │       ├── Slider-Icon-Left
│   │       ├── Slider-CenterTrack / Slider-SteppedTrack / Slider-OffsetTrack
│   │       └── Slider-Icon-Right / Slider-Label-Right
│   └── Slider-Row                 // 行布局（间续滑动 / 中心点偏移类型）
│       ├── Slider-Icon-Left / Slider-Label-Left
│       ├── Track 组件
│       └── Slider-Icon-Right / Slider-Label-Right
```

---

## 设计规范

### 尺寸与布局

| 属性 | 值 |
|-----|-----|
| 宽度 | 392px（固定） |
| 高度 | 连续滑动：Hug（自适应）；其他类型：64px（固定） |
| 布局方向 | 垂直（Flex Column） |
| 外层水平内边距 | 12px |

### 卡片容器 Slider-Card

| 属性 | 连续滑动 | 间续滑动 | 中心点滑动 | 中心点偏移 |
|-----|---------|---------|-----------|-----------|
| 背景色 | `#FFFFFF` | `#FFFFFF` | `#FFFFFF` | `#FFFFFF` |
| 内边距 | 16px（四周） | 0 16px（水平） | 0 16px 10px 16px | 0 10px |
| 布局方向 | 水平 | 垂直 | 垂直 | 垂直 |
| 对齐方式 | 垂直居中 | 水平居中、垂直居中 | 左对齐 | 左对齐、垂直居中 |

### 位置变体圆角

| 位置 | 圆角值 |
|-----|-------|
| 上 | 左上: 20px, 右上: 20px, 右下: 0, 左下: 0 |
| 中 | 0（全部） |
| 下 | 左上: 0, 右上: 0, 右下: 20px, 左下: 20px |
| 独立 | 20px（全角） |

### 颜色

| 用途 | 色值 | Token |
|-----|------|-------|
| 卡片背景色 | `#FFFFFF` | `元素色/container_list` |
| 轨道背景色 | `rgba(0, 0, 0, 0.06)` | `hyperos-color-surface-container-low` |
| 激活色 / 进度填充色 | `#3482FF` | `hyperos-color-primary` |
| 激活色上的前景色 | `#FFFFFF` | `hyperos-color-on-primary` |
| 标题文字色 | `#000000` | `hyperos-color-on-surface` |
| 图标 / 标签文字色 | `rgba(0, 0, 0, 0.6)` | `hyperos-color-on-surface-tertiary` |
| 页面背景色 | `#FFFFFF` | `hyperos_color_surface` |

### 字体排版

#### 标题文字（连续滑动类型 Header）

| 属性 | 值 | Token |
|-----|-----|-------|
| 字体 | MiSans | — |
| 字号 | 17px | `hyperos_font_size_Headline1` |
| 字重 | 380 (Medium) | `hyperos_font_weight_Headline1` |
| 行高 | 100% | — |
| 字间距 | 0 | — |
| 颜色 | `#000000` | `hyperos-color-on-surface` |

#### 图标文字（间续滑动类型）

| 位置 | 字体 | 字号 | 字重 |
|-----|------|------|------|
| 左侧图标 | MiSans | 14px | Medium |
| 右侧图标 | MiSans | 28px | Regular |

#### 图标文字（中心点滑动类型）

| 位置 | 字体 | 字号 | 字重 |
|-----|------|------|------|
| 左侧图标 | MiSans | 22px | Light |
| 右侧图标 | MiSans | 22px | Heavy |

#### 标签文字（中心点偏移类型）

| 位置 | 字体 | 字号 | 字重 |
|-----|------|------|------|
| 左侧标签 (L) | MiSans | 14px | Regular |
| 右侧标签 (R) | MiSans | 14px | Regular |

### 轨道 Track

#### 连续滑动轨道 TrackWrapper

| 属性 | 值 |
|-----|-----|
| 高度 | 28px |
| 宽度 | Fill（自适应父容器） |
| 圆角 | 1000px（全圆角） |
| 背景色 | `rgba(0, 0, 0, 0.06)` |
| 滑块尺寸 | 28 × 28px |

#### 间续滑动轨道 SteppedTrack

| 属性 | 值 |
|-----|-----|
| 高度 | 28px |
| 宽度 | Fill（自适应） |
| 圆角 | 999px |
| 背景色 | `rgba(0, 0, 0, 0.06)` |
| 布局 | 水平 Flex，`justify-between` |
| 激活步骤指示器尺寸 | 20 × 20px |
| 待选步骤点尺寸 | 8 × 8px |
| 激活步骤容器背景色 | `#3482FF` |
| 激活步骤容器内边距 | 左 10px，右 4px |
| 待选步骤容器内边距 | 水平 10px |

#### 中心点滑动轨道 CenterTrack

| 属性 | 值 |
|-----|-----|
| 高度 | Hug |
| 宽度 | Fill（自适应） |
| 圆角 | 999px |
| 背景色 | `rgba(0, 0, 0, 0.06)` |
| 布局 | 水平 Flex |
| 左侧段手柄尺寸 | 28 × 28px |
| 左侧段右内边距 | 40px |
| 右侧段点尺寸 | 8 × 8px |
| 右侧段宽度 | 132px（固定） |

#### 中心点偏移轨道 OffsetTrack

| 属性 | 值 |
|-----|-----|
| 高度 | 28px |
| 宽度 | Fill（自适应） |
| 圆角 | 16px |
| 背景色 | `rgba(0, 0, 0, 0.06)` |
| 水平内边距 | 8px |
| 布局 | 水平 Flex，居中对齐 |
| 滑块尺寸 | 28 × 28px |
| 滑块容器宽度 | 25px |

### 间距与内边距

| 属性 | 值 | Token |
|-----|-----|-------|
| 外层水平内边距 | 12px | — |
| 标题与轨道间距 (gap) | 12px | — |
| 图标与轨道间距 (gap) | 12px | — |
| 中心点滑动内容区垂直内边距 | 18px | — |
| 中心点偏移行水平内边距 | 6px | — |

### 阴影与效果

| 效果 | 值 |
|-----|-----|
| 投影 | 无 |
| 模糊 | 无 |
| 透明度 | 100% |

---

## 变体 (Variants)

### 变体维度

| 维度 | 可选值 | 说明 |
|-----|-------|------|
| 类型 | `连续滑动` / `间续滑动` / `中心点滑动` / `中心点偏移` | 控制滑动器的交互模式和轨道样式 |
| 位置 | `上` / `中` / `下` / `独立` | 控制卡片的圆角位置，用于列表组合 |

共计 **4 × 4 = 16 个变体**。

### 变体详情

#### 类型=连续滑动

![连续滑动变体](https://www.figma.com/api/mcp/asset/b1749aad-5ec9-4ea3-ac68-d7455916d2ec)

连续滑动是最常用的滑动器类型，用于在连续的数值范围内调节（如音量、亮度）。

| 属性 | 值 |
|-----|-----|
| 高度 | Hug（自适应内容） |
| 卡片内边距 | 16px（四周） |
| 包含 Header | 是（图标 28×28 + 标题文本） |
| 轨道类型 | TrackWrapper（连续轨道） |
| 轨道圆角 | 1000px |
| Header 与轨道间距 | 12px |

**组件属性 (Props):**

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| propValue (显示标题) | Boolean | `true` | 是否显示 Header 区域 |
| propValue1 (自定义图标) | Instance Swap | `null` | 替换默认的 Header 图标 |

#### 类型=间续滑动

![间续滑动变体](https://www.figma.com/api/mcp/asset/d5ff31e8-5b02-4ae3-8a19-0659d0c3b5c3)

间续滑动（离散滑动）用于在有限的离散步骤间选择（如字号档位）。

| 属性 | 值 |
|-----|-----|
| 高度 | 64px（固定） |
| 卡片水平内边距 | 16px |
| 包含 Header | 否 |
| 轨道类型 | SteppedTrack（分段轨道） |
| 轨道圆角 | 999px |
| 左侧图标字号 | 14px (Medium) |
| 右侧图标字号 | 28px (Regular) |
| 行高度 | 36px |
| 行垂直内边距 | 4px |

#### 类型=中心点滑动

![中心点滑动变体](https://www.figma.com/api/mcp/asset/c675f835-d5d3-43b1-90e4-df888854d9c2)

中心点滑动用于从中间基准值向两侧调节的场景（如字号缩放）。

| 属性 | 值 |
|-----|-----|
| 高度 | 64px（固定） |
| 卡片水平内边距 | 16px |
| 卡片下内边距 | 10px |
| 包含 Header | 否 |
| 轨道类型 | CenterTrack（中心轨道） |
| 轨道圆角 | 999px |
| 左侧图标字号 | 22px (Light) |
| 右侧图标字号 | 22px (Heavy) |
| ContentWrapper 垂直内边距 | 18px |

#### 类型=中心点偏移

![中心点偏移变体](https://www.figma.com/api/mcp/asset/f73de8ec-5d1f-410b-8623-9ef6d02a6c42)

中心点偏移用于调节方向性偏移的场景（如声道左右平衡）。

| 属性 | 值 |
|-----|-----|
| 高度 | 64px（固定） |
| 卡片水平内边距 | 10px |
| 包含 Header | 否 |
| 轨道类型 | OffsetTrack（偏移轨道） |
| 轨道圆角 | 16px |
| 左侧标签 | "L"，14px (Regular) |
| 右侧标签 | "R"，14px (Regular) |
| Row 水平内边距 | 6px |

---

## 子组件

### Slider-TrackWrapper（连续轨道）

| 属性 | 值 |
|-----|-----|
| 节点 ID | `80373:113270` |
| 高度 | 28px |
| 宽度 | Fill |
| 圆角 | 1000px |
| 背景色 | `rgba(0, 0, 0, 0.06)` |
| 滑块 (Handle) 尺寸 | 28 × 28px |

### Slider-SteppedTrack（分段轨道）

| 属性 | 值 |
|-----|-----|
| 节点 ID | `80384:10620` |
| 高度 | 28px |
| 宽度 | Fill |
| 圆角 | 999px |
| 背景色 | `rgba(0, 0, 0, 0.06)` |
| 布局 | `justify-between` |
| 激活步骤背景色 | `#3482FF` |
| 激活指示器尺寸 | 20 × 20px |
| 待选点尺寸 | 8 × 8px |

### Slider-CenterTrack（中心轨道）

| 属性 | 值 |
|-----|-----|
| 节点 ID | `80384:11213` |
| 高度 | Hug |
| 宽度 | Fill |
| 圆角 | 999px |
| 背景色 | `rgba(0, 0, 0, 0.06)` |
| 左段手柄尺寸 | 28 × 28px |
| 右段点尺寸 | 8 × 8px |

### Slider-OffsetTrack（偏移轨道）

| 属性 | 值 |
|-----|-----|
| 节点 ID | `80384:11822` |
| 高度 | 28px |
| 宽度 | Fill |
| 圆角 | 16px |
| 背景色 | `rgba(0, 0, 0, 0.06)` |
| 水平内边距 | 8px |
| 滑块尺寸 | 28 × 28px |
| 滑块容器宽度 | 25px |

---

## 交互状态

> 以下交互状态基于 Figma 中标注的 `进度` 和 `状态` 属性推断。

| 状态 | 轨道背景色 | 激活色 | 滑块样式 | 说明 |
|-----|-----------|--------|---------|------|
| 初始态 / 默认 | `rgba(0,0,0,0.06)` | `#3482FF` | 圆形手柄 28×28 | 滑块位于初始位置 |
| 拖动中 | `rgba(0,0,0,0.06)` | `#3482FF` | 请由设计团队补充 | 手指按住滑块拖动时 |
| 禁用 | 请由设计团队补充 | 请由设计团队补充 | 请由设计团队补充 | 不可交互状态 |

---

## 使用指南

### 何时使用

- **音量调节**：使用「连续滑动」类型，在连续数值范围内调节系统音量、媒体音量等
- **亮度调节**：使用「连续滑动」类型，调节屏幕亮度
- **字号档位选择**：使用「间续滑动」类型，在预设的离散档位间选择字体大小
- **字号缩放**：使用「中心点滑动」类型，基于默认字号向两个方向缩放
- **声道平衡**：使用「中心点偏移」类型，调节左右声道的偏移量
- **列表中组合使用**：通过「位置」变体（上 / 中 / 下），将多个滑动器组合在同一个卡片组中

### 何时不使用

- **精确数值输入**：需要输入精确数字时，应使用文本输入框而非滑动器
- **开关切换**：仅需要开 / 关两个状态时，应使用 Switch 组件
- **选项选择**：选项为非数值型时，应使用 Radio 或 Select 组件

### Do's & Don'ts

| Do's | Don'ts |
|------|--------|
| 在列表中使用「位置」变体组合多个滑动器，保持圆角连贯 | 在同一组中混用不同「类型」的滑动器 |
| 连续滑动类型搭配 Header 说明滑块用途 | 省略 Header 导致用户不理解滑块含义 |
| 间续滑动用左右图标暗示最小值和最大值的含义 | 使用无关的图标或文字标签 |
| 中心点偏移类型使用 L / R 等方向性标签 | 使用模糊的标签文字 |
| 独立使用时选择「位置=独立」变体 | 单独使用「上」或「下」位置变体 |

---

## 设计 Token 映射

| Token 名称 | 值 | 用途 |
|-----------|-----|------|
| `hyperos-color-primary` | `#3482FF` | 激活色 / 进度填充色 |
| `hyperos-color-on-primary` | `#FFFFFF` | 激活色上的前景色 |
| `hyperos-color-on-surface` | `#000000` | 标题文字色 |
| `hyperos-color-on-surface-tertiary` | `rgba(0, 0, 0, 0.6)` | 图标 / 标签文字色 |
| `hyperos-color-on-surface-octonary` | `rgba(0, 0, 0, 0.3)` | 次要辅助色 |
| `hyperos-color-surface-container-low` | `rgba(0, 0, 0, 0.06)` | 轨道背景色 |
| `hyperos-color-surface-container-medium` | `rgba(0, 0, 0, 0.08)` | 容器中等背景色 |
| `元素色/container_list` | `#FFFFFF` | 卡片背景色 |
| `hyperos_color_surface` | `#FFFFFF` | 页面背景色 |
| `hyperos_theme_radius_common` | `16px` | 偏移轨道圆角 |
| `hyperos_theme_radius_circle` | `999px` | 圆形轨道圆角 |
| `hyperos_theme_radius_medium` | `20px` | 卡片圆角 |
| `hyperos_theme_radius_big` | `36px` | 大容器圆角 |
| `hyperos_font_size_Headline1` | `17px` | 标题字号 |
| `hyperos_font_weight_Headline1` | `380` | 标题字重 |
| `spacing-xl` | `16px` | 大间距 |
| `cos-rounded/sm` | `9px` | 小圆角 |
| `radius-3xl` | `20px` | 超大圆角 |

---

## 设计注释

> 摘自 Figma 组件注释：
> 1. Figma 变体类型从 80 个缩减到 16 个，功能保持一致
> 2. 图层命名和结构优化
> 3. 圆角从 16 提高为 20
