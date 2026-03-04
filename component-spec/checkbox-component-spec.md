---
component: Checkbox
description: HyperOS 4 设计系统中的多选复选框组件，用于在列表或表单中进行多项选择，支持基础和多媒体两种视觉风格
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=82713-2936
figma_node_id: "82713:2936"
variants: "2 dimensions, 8 variants"
tokens_used: 4
---

# 多选 Checkbox

> HyperOS 4 设计系统中的圆形复选框组件，支持基础（纯色描边）和多媒体（毛玻璃/玻璃态）两种类型，适用于列表多选、媒体资源选择等场景。

## 预览

![多选 Checkbox 全部变体预览](http://localhost:3845/assets/fed8a4e2f7fae9644ecf93e9f804b87c41e2076c.svg)

| 基础/默认 | 基础/已选 | 基础/默认禁用 | 基础/已选禁用 |
|:---------:|:---------:|:------------:|:------------:|
| ![基础 默认](http://localhost:3845/assets/fed8a4e2f7fae9644ecf93e9f804b87c41e2076c.svg) | ![基础 已选](http://localhost:3845/assets/f6185cd4a18f280e48e912327d43cb7a00214861.svg) | ![基础 默认禁用](http://localhost:3845/assets/a0c829ca9214d764bfe06ee687a7294e1f364f11.svg) | ![基础 已选禁用](http://localhost:3845/assets/f6185cd4a18f280e48e912327d43cb7a00214861.svg) |

| 多媒体/默认 | 多媒体/已选 | 多媒体/默认禁用 | 多媒体/已选禁用 |
|:-----------:|:-----------:|:--------------:|:--------------:|
| ![多媒体 默认](http://localhost:3845/assets/d93269b141af7c4f157009f7fcc9e0e2d1238c81.svg) | ![多媒体 已选](http://localhost:3845/assets/ced47c12f842a3ed552c974cd06be79312caf0fd.svg) | ![多媒体 默认禁用](http://localhost:3845/assets/d93269b141af7c4f157009f7fcc9e0e2d1238c81.svg) | ![多媒体 已选禁用](http://localhost:3845/assets/ced47c12f842a3ed552c974cd06be79312caf0fd.svg) |

---

## 组件结构

```
多选 Checkbox                                     // FRAME | 82713:2936
└── 多选                                           // COMPONENT_SET | 80233:14459
    ├── 类型=基础, 状态=默认                        // COMPONENT | 80233:14460
    │   └── Oval 3                                // VECTOR (circle stroke)
    ├── 类型=基础, 状态=已选                        // COMPONENT | 80233:14462
    │   ├── Oval 3                                // VECTOR (circle fill)
    │   └── Checkmark Container                   // FRAME | 80233:14464
    │       └── Vector 15                         // VECTOR (checkmark)
    ├── 类型=基础, 状态=已选禁用                    // COMPONENT | 80233:14465
    │   ├── Oval 3                                // VECTOR (circle fill)
    │   └── Checkmark Container                   // FRAME | 80233:14467
    │       └── Vector 15                         // VECTOR (checkmark)
    ├── 类型=基础, 状态=默认禁用                    // COMPONENT | 80233:14468
    │   └── Oval 3                                // VECTOR (circle stroke)
    ├── 类型=多媒体, 状态=默认                      // COMPONENT | 80233:14470
    │   └── Oval 3                                // VECTOR (circle fill+stroke)
    ├── 类型=多媒体, 状态=默认禁用                  // COMPONENT | 80233:14472
    │   └── Oval 3                                // VECTOR (circle fill+stroke)
    ├── 类型=多媒体, 状态=已选                      // COMPONENT | 80233:14474
    │   ├── Oval 3                                // VECTOR (circle fill+stroke)
    │   └── Checkmark Container                   // FRAME | 80233:14476
    │       └── Vector 15                         // VECTOR (checkmark)
    └── 类型=多媒体, 状态=已选禁用                  // COMPONENT | 80233:14477
        ├── Oval 3                                // VECTOR (circle fill+stroke)
        └── Checkmark Container                   // FRAME | 80233:14479
            └── Vector 15                         // VECTOR (checkmark)
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| 多选 | COMPONENT_SET | `80233:14459` | 组件集容器，包含所有变体 |
| Oval 3 | VECTOR | — | 圆形背景，根据变体不同表现为描边圆或填充圆 |
| Checkmark Container | FRAME | `80233:14464` 等 | 勾选标记定位容器，仅在「已选」状态出现 |
| Vector 15 | VECTOR | — | 白色勾选标记图标 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 容器

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `22px` | — |
| `height` | `22px` | — |
| `position` | `relative` | — |
| `border-radius` | `999px`（完整圆形） | `circle` |

### 子组件: 圆形背景 Oval 3

根据变体类型不同，圆形背景呈现不同的视觉样式：

#### 基础类型 — 默认态

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `22px` | — |
| `height` | `22px` | — |
| `border-radius` | `999px` | `circle` |
| `border-width` | `1.6px` | — |
| `border-style` | `solid` | — |
| `border-color` | `rgba(0, 0, 0, 0.3)` | `文字图标色/on_surface_octonary` |
| `background-color` | 透明 | — |

#### 基础类型 — 已选态

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `22px` | — |
| `height` | `22px` | — |
| `border-radius` | `999px` | `circle` |
| `background-color` | `#4788FF` | `系统主色/primary` |
| `border` | 无 | — |
| `backdrop-filter` | `blur(7.78px)` | — |

#### 基础类型 — 默认禁用态

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `22px` | — |
| `height` | `22px` | — |
| `border-radius` | `999px` | `circle` |
| `border-width` | `1.6px` | — |
| `border-style` | `solid` | — |
| `border-color` | `rgba(0, 0, 0, 0.1)` | `元素色/surface_container_high` |
| `background-color` | 透明 | — |
| `backdrop-filter` | `blur(7.78px)` | — |

#### 多媒体类型 — 默认态

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `22px` | — |
| `height` | `22px` | — |
| `border-radius` | `999px` | `circle` |
| `background-color` | `rgba(0, 0, 0, 0.2)` | — |
| `border-width` | `1.6px` | — |
| `border-style` | `solid` | — |
| `border-color` | `#FFFFFF` | — |
| `backdrop-filter` | `blur(7.78px)` | — |

#### 多媒体类型 — 已选态

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `22px` | — |
| `height` | `22px` | — |
| `border-radius` | `999px` | `circle` |
| `background-color` | `#4788FF` | `系统主色/primary` |
| `border-width` | `1.6px` | — |
| `border-style` | `solid` | — |
| `border-color` | `#FFFFFF` | — |
| `backdrop-filter` | `blur(7.78px)` | — |

### 子组件: 勾选标记 Vector 15

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `9.86px` | — |
| `height` | `8.38px` | — |
| `stroke` | `#FFFFFF` | — |
| `stroke-width` | `2px` | — |
| `stroke-linecap` | `round` | — |
| `fill` | 无 | — |

勾选标记定位方式：

| CSS 属性 | 值 | 说明 |
|---------|----|------|
| `position` | `absolute` | — |
| `top` | `34.84%` | 相对于容器 |
| `left` | `32.13%` | 相对于容器 |
| `right` | `32.13%` | 相对于容器 |
| `bottom` | `34.84%` | 相对于容器 |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 基础默认描边色 | `rgba(0, 0, 0, 0.3)` | `文字图标色/on_surface_octonary` |
| 基础禁用描边色 | `rgba(0, 0, 0, 0.1)` | `元素色/surface_container_high` |
| 已选填充色 | `#4788FF` | `系统主色/primary` |
| 多媒体默认填充色 | `rgba(0, 0, 0, 0.2)` | — |
| 多媒体描边色 | `#FFFFFF` | — |
| 勾选标记色 | `#FFFFFF` | — |

---

## 变体

### 维度定义

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `类型` | `基础` / `多媒体` | 控制视觉风格——基础为纯色描边/填充，多媒体为毛玻璃效果叠加白色描边 |
| 状态 | `状态` | `默认` / `已选` / `默认禁用` / `已选禁用` | 控制选中和禁用状态 |

共计 **2 × 4 = 8 个变体**。

### 变体差异表

> 仅列出各变体之间**有差异**的属性。未列出的属性与默认变体（类型=基础, 状态=默认）相同。

#### 按类型分组

| 属性 | `基础` | `多媒体` |
|-----|--------|---------|
| 圆形 `background-color`（默认态） | 透明 | `rgba(0, 0, 0, 0.2)` |
| 圆形 `border-color`（默认态） | `rgba(0, 0, 0, 0.3)` | `#FFFFFF` |
| 圆形 `border-color`（已选态） | 无 | `#FFFFFF`（`1.6px`） |
| `backdrop-filter` | 无（默认态）/ `blur(7.78px)`（已选态） | `blur(7.78px)`（所有状态） |
| 禁用态 `opacity` | `0.30`（已选禁用） | `0.50`（默认禁用 / 已选禁用） |

#### 按状态分组

| 属性 | `默认` | `已选` | `默认禁用` | `已选禁用` |
|-----|--------|-------|-----------|-----------|
| 圆形填充 | 描边圆 | 填充圆（`#4788FF`） | 描边圆 | 填充圆（`#4788FF`） |
| 勾选标记 | 无 | 有（白色） | 无 | 有（白色） |
| 基础类型 `border-color` | `rgba(0,0,0,0.3)` | — | `rgba(0,0,0,0.1)` | — |
| 基础类型 `opacity` | `1` | `1` | `1` | `0.30` |
| 多媒体类型 `opacity` | `1` | `1` | `0.50` | `0.50` |

---

## 交互状态

> 以「默认态」为基准，其他状态仅列出**发生变化**的属性。

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | — | （基准状态） | — |
| `selected` | 用户点击 / 触摸 | `background-color` | `#4788FF`（圆形填充） | `系统主色/primary` |
| | | `border` | 基础类型移除描边；多媒体类型保留白色描边 | — |
| | | 勾选标记 | 显示白色勾选标记 | — |
| `disabled` | `disabled=true` 且未选中 | 基础: `border-color` | `rgba(0,0,0,0.1)` | `元素色/surface_container_high` |
| | | 多媒体: `opacity` | `0.50` | — |
| `selected-disabled` | `disabled=true` 且已选中 | 基础: `opacity` | `0.30` | — |
| | | 多媒体: `opacity` | `0.50` | — |
| `hover` | 鼠标悬停 | Figma 未定义，请由设计团队补充 | — | — |
| `focused` | 键盘聚焦 | Figma 未定义，请由设计团队补充 | — | — |
| `active` | 鼠标按下 / 触摸中 | Figma 未定义，请由设计团队补充 | — | — |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

```typescript
interface CheckboxProps {
  /** 复选框视觉类型：基础为纯色描边/填充，多媒体为毛玻璃效果适用于图片/视频上层 */
  type: '基础' | '多媒体';
  /** 复选框状态 */
  state: '默认' | '已选' | '默认禁用' | '已选禁用';
}
```

| Figma 属性名 | 类型 | 对应 Prop | 默认值 | 说明 |
|-------------|------|----------|-------|------|
| 类型 | Variant | `type` | `基础` | 控制视觉风格 |
| 状态 | Variant | `state` | `默认` | 控制选中和禁用状态 |

**建议的工程化 Props 拆分**：

```typescript
interface CheckboxProps {
  /** 复选框视觉类型 */
  variant?: 'basic' | 'multimedia';
  /** 是否选中 */
  checked?: boolean;
  /** 是否禁用 */
  disabled?: boolean;
  /** 选中状态变化回调 */
  onChange?: (checked: boolean) => void;
  /** 自定义类名 */
  className?: string;
}
```

---

## 使用指南

### 何时使用

- **列表多选场景**：使用「基础」类型，在纯色背景上提供清晰的选中/未选中视觉反馈
- **媒体资源选择场景**：使用「多媒体」类型，在图片、视频等多媒体内容上层叠加选择控件，毛玻璃效果保证在复杂背景上的可辨识度

### 何时不使用

- **单选场景**：应使用 Radio（单选按钮）组件代替
- **开关切换场景**：应使用 Switch（开关）组件代替
- **仅一个选项需要确认**：应使用 Toggle 或 Switch 组件代替

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 在图片/视频上方使用「多媒体」类型 | 在图片/视频上方使用「基础」类型 | 基础类型的半透明黑色描边在复杂背景上不够醒目，多媒体类型的毛玻璃 + 白色描边在任何背景上都可辨识 |
| 在纯色背景上使用「基础」类型 | 在纯色背景上使用「多媒体」类型 | 多媒体类型的毛玻璃效果在纯色背景上显得多余，增加不必要的渲染开销 |
| 禁用态保留视觉反馈（降低 opacity） | 完全隐藏禁用的复选框 | 用户需要知道该选项存在但当前不可操作 |
| 保持 22×22px 的标准尺寸 | 随意缩放复选框尺寸 | 22px 是经过可用性验证的最小触摸目标尺寸 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `circle` | `999` | border-radius | 所有变体的圆形容器，确保完整圆形 |
| `文字图标色/on_surface_octonary` | `#0000004d`（`rgba(0,0,0,0.3)`） | color | 基础类型默认态圆形描边色 |
| `系统主色/primary` | `#4788FF` | color | 已选态圆形填充色 |
| `元素色/surface_container_high` | `#0000001a`（`rgba(0,0,0,0.1)`） | color | 基础类型默认禁用态圆形描边色 |

---

## SVG 资源清单

> 该组件的视觉外观完全由 SVG 矢量图形实现，以下为各变体对应的 SVG 资源。

| 变体 | 资源 URL | 视觉描述 |
|------|---------|---------|
| 基础/默认 | `http://localhost:3845/assets/fed8a4e2f7fae9644ecf93e9f804b87c41e2076c.svg` | 黑色 30% 不透明度描边圆，描边宽度 1.6px |
| 基础/已选 | `http://localhost:3845/assets/f6185cd4a18f280e48e912327d43cb7a00214861.svg` | `#4788FF` 蓝色填充圆，带 7.78px 模糊背景 |
| 基础/默认禁用 | `http://localhost:3845/assets/a0c829ca9214d764bfe06ee687a7294e1f364f11.svg` | 黑色 10% 不透明度描边圆，描边宽度 1.6px |
| 多媒体/默认 | `http://localhost:3845/assets/d93269b141af7c4f157009f7fcc9e0e2d1238c81.svg` | 黑色 20% 不透明度填充 + 白色 1.6px 描边圆，带 7.78px 模糊背景（毛玻璃效果） |
| 多媒体/已选 | `http://localhost:3845/assets/ced47c12f842a3ed552c974cd06be79312caf0fd.svg` | `#4788FF` 蓝色填充 + 白色 1.6px 描边圆，带 7.78px 模糊背景 |
| 勾选标记 | `http://localhost:3845/assets/999a0f5bf52244ad34764e2780506898462e930c.svg` | 白色圆角勾选标记，描边宽度 2px，尺寸 9.86×8.38px |

---

## 设计注释

> 1. 该组件的圆形背景均通过 SVG 矢量路径实现，非 CSS `border-radius` 构建。实际开发中可选择使用 SVG 资源直接引用，或用 CSS 重新构建圆形样式。
> 2. 多媒体类型使用 `backdrop-filter: blur(7.78px)` 实现毛玻璃效果，需注意浏览器兼容性（移动端 HyperOS WebView 需确认支持情况）。
> 3. 禁用态的实现方式存在差异：基础/已选禁用使用 `opacity: 0.30`，多媒体禁用态使用 `opacity: 0.50`，基础/默认禁用则通过更低的描边不透明度（0.1 vs 0.3）实现视觉弱化。
> 4. Figma 中未定义 `hover`、`focused`、`active` 交互状态，需由设计团队补充。
> 5. 组件尺寸固定为 22×22px，建议实现时考虑为点击区域添加更大的触摸目标（如 44×44px 的透明点击区域）以满足无障碍访问要求。
