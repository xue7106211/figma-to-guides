---
component: ListAtom
description: HyperOS 4 列表原子组件系统，包含基础列表项、图标列表、多选列表、单选列表、按钮列表等一系列列表相关原子组件
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=82800-1195
figma_node_id: "82800:1195"
variants: "多个子组件集，基础列_原子含 6 维度 ~256 个变体"
tokens_used: 12
---

# 列表原子组件 ListAtom

> HyperOS 4 列表系统的原子级组件集合，用于构建设置页面、选择列表、导航列表等场景。包含基础列表项、图标列表项、多选列表项、单选列表项、按钮列表项以及配套的图标、分割线、分组标题等辅助组件。

## 预览

### 基础列_原子 全量变体

![基础列_原子全量变体预览](https://www.figma.com/api/mcp/asset/basic-list-atom-all)

### 图标列_原子

![图标列_原子预览](https://www.figma.com/api/mcp/asset/icon-list-atom)

### 多选列_原子

![多选列_原子预览](https://www.figma.com/api/mcp/asset/multiselect-list-atom)

### 单选列_原子

![单选列_原子预览](https://www.figma.com/api/mcp/asset/radio-list-atom)

### 按钮列表

![按钮列表预览](https://www.figma.com/api/mcp/asset/button-list)

### 多选（Checkbox）

![多选 Checkbox 预览](https://www.figma.com/api/mcp/asset/checkbox)

---

## 组件结构

```
列表_原子组件                                    // SECTION | 82800:1195
├── .基础列_原子                                 // COMPONENT_SET | 80584:33871
│   ├── 交互状态=默认态, 列表位置=独立列表, ...    // COMPONENT | 80584:33872
│   │   └── 列表                                // FRAME | 80584:33873
│   │       ├── 左侧图标区域                     // FRAME | 83406:66845 (条件显示)
│   │       │   └── 套底图标                     // INSTANCE
│   │       ├── 文本区域                         // FRAME | 80584:33874
│   │       │   ├── 标题文字                     // TEXT
│   │       │   └── 辅助文案                     // TEXT (条件显示)
│   │       └── DatePicker-Header-Config-TrailingArea  // INSTANCE (条件显示)
│   ├── 交互状态=按下态, ...                     // COMPONENT (pressed variants)
│   ├── 交互状态=悬停态, ...                     // COMPONENT (hover variants)
│   └── 交互状态=禁用态, ...                     // COMPONENT (disabled variants)
├── 图标列_原子                                  // COMPONENT_SET | 80584:34356
│   └── (20 个变体)
├── .多选列_原子                                 // COMPONENT_SET | 80252:18346
│   └── (16 个变体)
├── .单选列_原子                                 // COMPONENT_SET | 83445:48835
│   └── (多个变体)
├── 多选 (Checkbox)                             // COMPONENT_SET | 2677:72136
│   └── (4 个变体)
├── 按钮列表                                    // COMPONENT_SET | 80584:34535
│   └── (10 个变体)
├── 列表/分组标题                                // COMPONENT_SET | 82227:1029
├── 列表组/分割线                                // COMPONENT_SET | 82227:1034
├── 套卡列表/分割线                              // COMPONENT_SET | 82355:7760
├── 列表/注释文字                                // COMPONENT_SET | 82227:1037
├── 列表/备案号文字                              // COMPONENT_SET | 80584:34608
├── DatePicker-Header-Config-TrailingArea        // COMPONENT_SET | 80584:35059
├── 左侧图标区域                                 // COMPONENT_SET | 83406:66719
├── 辅助信息                                    // COMPONENT_SET | 82948:65023
├── 小图标_设置                                  // COMPONENT_SET | 80584:34643
├── 超大图标                                    // COMPONENT_SET | 80584:34786
├── 套底图标                                    // COMPONENT_SET | 82818:1870
├── 图标                                        // COMPONENT_SET | 82818:2046
├── 头像与大图标                                 // COMPONENT_SET | 80584:34888
├── 头像                                        // COMPONENT_SET | 80584:34893
├── 大图标_大图标&头像                            // COMPONENT_SET | 80584:34619
├── 大图标_设置图标                               // COMPONENT_SET | 80584:34630
├── 特殊列表-网络                                // COMPONENT_SET | 80584:34513
├── 展开收起 3.1                                 // COMPONENT_SET | 80584:35139
├── 排序 3.1                                    // COMPONENT_SET | 80584:35146
├── 清除 3.1                                    // COMPONENT_SET | 80584:35153
├── 小按钮 3.1                                  // COMPONENT_SET | 80584:35157
├── 日期组件                                    // COMPONENT_SET | 80584:35164
├── 单独进入二级 3.1                             // COMPONENT_SET | 2677:72177
└── DatePicker-Header-Config-DateTimeSegmentControl // COMPONENT_SET | 82867:104585
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| .基础列_原子 | COMPONENT_SET | `80584:33871` | 核心列表项组件，支持全部交互状态与布局变体 |
| 图标列_原子 | COMPONENT_SET | `80584:34356` | 带左侧图标的列表项，支持选中态 |
| .多选列_原子 | COMPONENT_SET | `80252:18346` | 带多选 Checkbox 的列表项 |
| .单选列_原子 | COMPONENT_SET | `83445:48835` | 带单选指示的列表项 |
| 多选 (Checkbox) | COMPONENT_SET | `2677:72136` | 独立多选勾选框组件 |
| 按钮列表 | COMPONENT_SET | `80584:34535` | 文字按钮样式的列表项 |
| 列表/分组标题 | COMPONENT_SET | `82227:1029` | 列表分组标题 |
| 列表组/分割线 | COMPONENT_SET | `82227:1034` | 列表组之间的分割线 |
| 套卡列表/分割线 | COMPONENT_SET | `82355:7760` | 卡片内列表分割线 |
| DatePicker-Header-Config-TrailingArea | COMPONENT_SET | `80584:35059` | 列表右侧功能区配置集合 |
| 左侧图标区域 | COMPONENT_SET | `83406:66719` | 列表左侧图标占位区域 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 核心组件：.基础列_原子

#### 容器（默认态 · 独立列表 · 非通栏）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `368px`（容器宽度，实际使用时为 `fill`） | — |
| `min-height` | `56px`（单行）/ `70px`（双行含辅助描述） | — |
| `display` | `flex` | — |
| `flex-direction` | `row` | — |
| `align-items` | `center` | — |
| `justify-content` | `space-between` | — |
| `padding` | `14px 16px` | — |
| `gap` | `14px`（左侧图标与文本区域） | — |
| `background-color` | `#FFFFFF` | `元素色/container_list` |
| `border-radius` | `20px` | `hyperos_theme_radius_medium` |
| `overflow` | `hidden` | — |

#### 文本区域

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `flex` | `1 0 0` | — |
| `gap` | `0`（标题与辅助文字紧密排列） | — |
| `min-width` | `1px` | — |
| `min-height` | `1px` | — |

#### 左侧图标区域（条件显示，左侧缩进区=on）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `gap` | `10px` | — |
| `flex-shrink` | `0` | — |

#### 右侧功能区 TrailingArea（条件显示，右侧功能区=on）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `28px` | — |
| `height` | `28px` | — |
| `flex-shrink` | `0` | — |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| 标题 | MiSans | 17px | 380 (Medium) | 100% | 0 | `#000000` | `Headline/Headline 1` |
| 辅助描述 | MiSans | 14px | 330 (Regular) | 100% | 0 | `rgba(0,0,0,0.6)` | `Body/Body 2` |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 列表背景色（默认态） | `#FFFFFF` | `元素色/container_list` |
| 列表背景色（按下态） | `rgba(0,0,0,0.12)` | `新增色彩变量/container_list_touch` |
| 列表背景色（悬停态） | `rgba(0,0,0,0.06)` | `新增色彩变量/container_list_hover` |
| 列表背景色（禁用态） | `rgba(0,0,0,0.06)` | `新增色彩变量/container_list_hover` |
| 文字色-主（标题） | `#000000` | `hyperos-color-on-surface` |
| 文字色-辅助 | `rgba(0,0,0,0.6)` | `hyperos-color-on-surface-tertiary` |
| 文字色-禁用 | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |
| 右侧按钮背景色 | `rgba(0,0,0,0.05)` | `文字图标色/on_Surface_right_button_bg` |
| 右侧图标色 | `rgba(0,0,0,0.3)` | `文字图标色/on_Surface_right_icon` |
| 分割线颜色 | `rgba(0,0,0,0.1)` | `hyperos-color-outline` |

### 子组件: 图标列_原子

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `368px` | — |
| `height` | `70px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `padding` | `14px 16px` | — |
| `background-color` | `#FFFFFF` | `元素色/container_list` |
| `border-radius` | `20px`（依据列表位置变化） | `hyperos_theme_radius_medium` |
| `overflow` | `hidden` | — |

### 子组件: 多选 (Checkbox)

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `28px` | — |
| `height` | `28px` | — |

### 子组件: 按钮列表

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `392px` | — |
| `height` | `56px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |
| `text-align` | `center` | — |

---

## 变体

### 维度定义

#### .基础列_原子

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 交互状态 | `交互状态` | `默认态` / `按下态` / `悬停态` / `禁用态` | 列表项的交互反馈状态 |
| 列表位置 | `列表位置` | `独立列表` / `顶部` / `中部` / `底部` | 控制圆角显示，用于列表分组 |
| 通栏列表 | `通栏列表` | `on` / `off` | 是否为通栏（无圆角无边距）样式 |
| 辅助描述 | `辅助描述` | `on` / `off` | 是否显示副标题/辅助描述文字 |
| 右侧功能区 | `右侧功能区` | `on` / `off` | 是否显示右侧操作区域（箭头/开关等） |
| 左侧缩进区 | `左侧缩进区` | `on` / `off` | 是否显示左侧图标区域 |

共计 **4 × 4 × 2 × 2 × 2 × 2 = 256 个变体**。

#### 图标列_原子

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 列表类型 | `列表类型` | `默认类型` / `通栏类型` | 默认带圆角，通栏无圆角 |
| 辅助描述 | `辅助描述` | `展示` / `隐藏` | 是否显示辅助文字 |
| 列表位置 | `列表位置` | `独立` / `上` / `中` / `下` | 控制圆角位置 |
| 列表状态 | `列表状态` | `默认态` / `选中态` | 是否显示选中勾选标记 |

共计 **2 × 2 × 4 × 2 = 32 个变体**（实际 20 个，通栏类型仅独立位置）。

#### .多选列_原子

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 选中状态 | `选中状态` | `未选中` / `已选中` | Checkbox 选中状态 |
| 列表位置 | `列表位置` | `上` / `中` / `下` / `通栏` | 控制圆角位置 |
| 单双行 | `单双行` | `单行` / `双行` | 单行56px / 双行70px含辅助描述 |

共计 **2 × 4 × 2 = 16 个变体**。

#### .单选列_原子

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 列表状态 | `列表状态` | `默认状态` / `通栏状态` | 默认带圆角，通栏无圆角 |
| 列表位置 | `列表位置` | `独立列表` / `顶部` / `中部` / `底部` | 控制圆角位置 |
| 组件状态 | `组件状态` | `已选` / `未选` | 单选选中指示 |
| 显示：右侧功能区 | `显示：右侧功能区` | `on` / `off` | 是否显示右侧功能区 |
| 显示：辅助描述 | `显示：辅助描述` | `on` / `off` | 是否显示辅助描述 |
| 显示：左侧缩进区 | `显示：左侧缩进区` | `on` / `off` | 是否显示左侧缩进区 |

#### 多选 (Checkbox)

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 状态 | `状态` | `未选中` / `选中` / `未选中不可用` / `选中不可用` | Checkbox 选中与可用性组合 |

#### 按钮列表

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 列表位置 | `列表位置` | `独立` / `上` / `中` / `下` / `通栏` | 控制圆角位置 |
| 文字颜色 | `文字颜色` | `红色` / `蓝色` | 按钮文字颜色，红色为危险操作，蓝色为普通操作 |

共计 **5 × 2 = 10 个变体**。

### 变体差异表

#### 按 交互状态 分组（.基础列_原子）

> 仅列出各状态之间**有差异**的属性。未列出的属性与默认态相同。

| 属性 | `默认态` | `按下态` | `悬停态` | `禁用态` |
|-----|---------|---------|---------|---------|
| `background-color` | `#FFFFFF` | `rgba(0,0,0,0.12)` | `rgba(0,0,0,0.06)` | `rgba(0,0,0,0.06)` |
| 标题 `color` | `#000000` | `#000000` | `#000000` | `rgba(0,0,0,0.3)` |
| 辅助描述 `color` | `rgba(0,0,0,0.6)` | `rgba(0,0,0,0.6)` | `rgba(0,0,0,0.6)` | `rgba(0,0,0,0.3)` |
| 右侧图标 `opacity` | `1` | `1` | `1` | 降低透明度 |

#### 按 列表位置 分组（圆角差异）

> `border-radius` 的四角值随列表位置变化，用于列表项分组视觉效果。

| 属性 | `独立列表` | `顶部` | `中部` | `底部` |
|-----|-----------|-------|-------|-------|
| `border-radius` 左上 | `20px` | `20px` | `0` | `0` |
| `border-radius` 右上 | `20px` | `20px` | `0` | `0` |
| `border-radius` 左下 | `20px` | `0` | `0` | `20px` |
| `border-radius` 右下 | `20px` | `0` | `0` | `20px` |

#### 按 通栏列表 分组

| 属性 | `off`（默认） | `on`（通栏） |
|-----|-------------|------------|
| `border-radius` | `20px`（依位置变化） | `0` |
| `margin` | 有水平边距 | 无水平边距，贴边显示 |

#### 按 辅助描述 分组

| 属性 | `off` | `on` |
|-----|-------|------|
| `min-height` | `56px` | `70px` |
| 辅助文字 | 隐藏 | 显示，位于标题下方 |

---

## 交互状态

> 以「默认态」为基准，其他状态仅列出**发生变化**的属性。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态） | — |
| `hover` | 鼠标悬停 | `background-color` | `rgba(0,0,0,0.06)` | `新增色彩变量/container_list_hover` |
| `active` / `pressed` | 鼠标按下 / 触摸 | `background-color` | `rgba(0,0,0,0.12)` | `新增色彩变量/container_list_touch` |
| `disabled` | 禁用状态 | `background-color` | `rgba(0,0,0,0.06)` | `新增色彩变量/container_list_hover` |
| `disabled` | 禁用状态 | 标题 `color` | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |
| `disabled` | 禁用状态 | 辅助描述 `color` | `rgba(0,0,0,0.3)` | `hyperos-color-on-surface-octonary` |
| `selected` | 选中（图标列/单选列/多选列） | 显示选中指示器（勾选图标） | — | — |

---

## 组件 API

### .基础列_原子 BasicListItem

```typescript
interface BasicListItemProps {
  /** 列表项标题文字 */
  title: string; // 默认: "标题"
  /** 是否显示辅助描述文字 */
  showDescription?: boolean; // 默认: false
  /** 辅助描述文字内容 */
  description?: string; // 默认: "辅助文案"
  /** 列表项在分组中的位置，控制圆角 */
  position: 'standalone' | 'top' | 'middle' | 'bottom';
  /** 是否为通栏样式（无圆角贴边） */
  fullWidth?: boolean; // 默认: false
  /** 是否显示右侧功能区 */
  showTrailing?: boolean; // 默认: false
  /** 右侧功能区内容 */
  trailing?: ReactNode; // 默认: ChevronIcon
  /** 是否显示左侧图标区域 */
  showLeading?: boolean; // 默认: false
  /** 左侧图标内容 */
  leading?: ReactNode; // 默认: null
  /** 是否禁用 */
  disabled?: boolean; // 默认: false
  /** 点击事件 */
  onPress?: () => void;
}
```

### 图标列_原子 IconListItem

```typescript
interface IconListItemProps {
  /** 列表项标题 */
  title: string;
  /** 辅助描述 */
  description?: string;
  /** 是否显示辅助描述 */
  showDescription?: boolean; // 默认: false
  /** 列表类型 */
  type: 'default' | 'fullWidth';
  /** 列表位置 */
  position: 'standalone' | 'top' | 'middle' | 'bottom';
  /** 选中状态 */
  selected?: boolean; // 默认: false
  /** 左侧图标 */
  icon: ReactNode;
}
```

### .多选列_原子 MultiSelectListItem

```typescript
interface MultiSelectListItemProps {
  /** 列表项标题 */
  title: string;
  /** 辅助描述（双行模式） */
  description?: string;
  /** 选中状态 */
  checked: boolean;
  /** 列表位置 */
  position: 'top' | 'middle' | 'bottom' | 'fullWidth';
  /** 单行或双行 */
  rows: 'single' | 'double';
  /** 选中状态变化回调 */
  onChange?: (checked: boolean) => void;
}
```

### .单选列_原子 RadioListItem

```typescript
interface RadioListItemProps {
  /** 列表项标题 */
  title: string;
  /** 辅助描述 */
  description?: string;
  /** 是否选中 */
  selected: boolean;
  /** 列表状态 */
  listStyle: 'default' | 'fullWidth';
  /** 列表位置 */
  position: 'standalone' | 'top' | 'middle' | 'bottom';
  /** 是否显示右侧功能区 */
  showTrailing?: boolean;
  /** 是否显示辅助描述 */
  showDescription?: boolean;
  /** 是否显示左侧缩进区 */
  showLeading?: boolean;
  /** 选中回调 */
  onSelect?: () => void;
}
```

### 多选 Checkbox

```typescript
interface CheckboxProps {
  /** 选中状态 */
  checked: boolean;
  /** 是否禁用 */
  disabled?: boolean; // 默认: false
  /** 状态变化回调 */
  onChange?: (checked: boolean) => void;
}
```

### 按钮列表 ButtonListItem

```typescript
interface ButtonListItemProps {
  /** 按钮文字 */
  label: string;
  /** 文字颜色类型 */
  color: 'red' | 'blue';
  /** 列表位置 */
  position: 'standalone' | 'top' | 'middle' | 'bottom' | 'fullWidth';
  /** 点击事件 */
  onPress?: () => void;
}
```

### Figma 属性映射表

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 交互状态 | Variant | `disabled` + 交互行为 | `默认态` | 通过 `disabled` prop + CSS 伪类实现 |
| 列表位置 | Variant | `position` | `standalone` | 控制圆角显示位置 |
| 通栏列表 | Variant (Boolean) | `fullWidth` | `false` | 通栏模式取消圆角和边距 |
| 辅助描述 | Boolean | `showDescription` | `false` | 控制辅助文字显示 |
| 右侧功能区 | Boolean | `showTrailing` | `false` | 控制右侧操作区显示 |
| 左侧缩进区 | Boolean | `showLeading` | `false` | 控制左侧图标区显示 |
| propValue | Text | `title` | `"标题"` | 标题文字内容 |

---

## 使用指南

### 何时使用

- **设置页面**：使用「基础列_原子」构建系统设置项列表，搭配右侧功能区显示进入箭头、开关等
- **选择列表**：使用「单选列_原子」或「多选列_原子」构建单选/多选列表
- **带图标的列表**：使用「图标列_原子」在列表左侧展示应用图标或功能图标
- **危险操作/功能操作**：使用「按钮列表」展示居中对齐的操作按钮，红色用于危险操作、蓝色用于普通操作
- **列表分组**：使用「列表/分组标题」+列表位置（顶部/中部/底部）+「列表组/分割线」组合实现分组

### 何时不使用

- **复杂卡片内容**：如需展示多媒体、图表等复杂内容，应使用 Card 组件代替
- **网格布局**：如需网格排列展示内容，应使用 Grid 组件代替
- **导航标签**：如需底部/顶部导航切换，应使用 TabBar / NavigationBar 组件代替

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 同一分组内列表项使用正确的 `position` 值（top/middle/bottom） | 所有项都使用 `standalone` | 正确的 position 可让圆角组合形成视觉分组 |
| 通栏模式用于无卡片包裹的全宽列表 | 在卡片内使用通栏模式 | 通栏模式取消圆角和边距，在卡片内会破坏视觉层级 |
| 禁用态的列表项同时禁用右侧功能区的交互 | 仅改变文字颜色而保留右侧按钮可交互 | 禁用应完整覆盖整个列表项 |
| 使用 `辅助描述` 提供补充说明 | 在辅助描述中放置过长文字 | 辅助描述应简短，过长会影响布局 |
| 红色按钮列表用于删除/退出等破坏性操作 | 将红色按钮用于常规操作 | 红色传达危险/警告语义 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `元素色/container_list` | `#FFFFFF` | color | 列表项默认背景色 |
| `新增色彩变量/container_list_touch` | `rgba(0,0,0,0.12)` | color | 列表项按下态背景色 |
| `新增色彩变量/container_list_hover` | `rgba(0,0,0,0.06)` | color | 列表项悬停态/禁用态背景色 |
| `hyperos-color-on-surface` | `#000000` | color | 标题文字颜色 |
| `hyperos-color-on-surface-tertiary` | `rgba(0,0,0,0.6)` | color | 辅助描述文字颜色 |
| `hyperos-color-on-surface-octonary` | `rgba(0,0,0,0.3)` | color | 禁用态文字颜色、右侧图标颜色 |
| `hyperos-color-outline` | `rgba(0,0,0,0.1)` | color | 分割线颜色 |
| `文字图标色/on_Surface_right_button_bg` | `rgba(0,0,0,0.05)` | color | 右侧按钮背景色 |
| `文字图标色/on_Surface_right_icon` | `rgba(0,0,0,0.3)` | color | 右侧图标颜色 |
| `hyperos_theme_radius_medium` | `20px` | radius | 列表项圆角 |
| `hyperos_font_size_Headline1` | `17px` | font-size | 标题字号 |
| `hyperos_font_weight_Headline1` | `380` | font-weight | 标题字重 |
| `hyperos_font_size_body2` | `14px` | font-size | 辅助描述字号 |
| `hyperos_font_weight_body2` | `330` | font-weight | 辅助描述字重 |

### 文字样式 Token

| Token | 定义 |
|-------|-----|
| `Headline/Headline 1` | `Font(family: "MiSans", style: Medium, size: hyperos_font_size_Headline1, weight: hyperos_font_weight_Headline1, lineHeight: 100%, letterSpacing: 0)` |
| `Body/Body 2` | `Font(family: "MiSans", style: Regular, size: hyperos_font_size_body2, weight: hyperos_font_weight_body2, lineHeight: 100%, letterSpacing: 0)` |

---

## 设计注释

> 1. **列表位置圆角规则**：`独立列表` 四角均为 20px；`顶部` 仅上方两角 20px；`中部` 四角均为 0；`底部` 仅下方两角 20px。多个列表项组合时形成统一的圆角卡片效果。
> 2. **通栏模式**：通栏列表取消所有圆角和水平边距，适用于全屏宽度的设置列表。通栏模式仅在 `独立列表` 位置可用。
> 3. **左侧图标尺寸规格**：套底图标 28×28px（圆角 7.47px）；小图标 24×24px；大图标 40×40px；头像 28×28px（圆形）。
> 4. **右侧功能区类型**：支持多种右侧操作类型，包括进入二级页面箭头、开关（Switch）、多选框、单独进入二级、右侧文字、展开收起、清除按钮、纯文字、单选按钮、状态+弹窗、Loading、小按钮、日期选择控件等。
> 5. **辅助信息类型**：辅助描述支持两种子类型——「辅助文案」（文字描述）和「当前设备」（设备标识）。
> 6. **Checkbox 四态**：多选框包含未选中、选中、未选中不可用、选中不可用四种状态，选中态为蓝色圆形勾选图标。
> 7. **按钮列表居中对齐**：按钮列表文字居中，不同于其他列表项的左对齐，语义上为操作按钮而非导航项。
