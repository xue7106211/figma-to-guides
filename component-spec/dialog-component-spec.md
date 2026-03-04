---
component: Dialog
description: HyperOS 系统级弹窗组件，包含确认、警示、授权、引导说明、输入、进度和选择弹窗等七种类型
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=88387-41753
figma_node_id: "88387:41753"
variants: "7 dialog types: 确认弹窗 (5), 警示弹窗 (3), 授权弹窗 (4), 引导说明弹窗 (2), 输入弹窗 (2), 进度弹窗 (2), 选择弹窗 (5); 权限弹窗图标 (~35 types × 2 themes)"
tokens_used: 28
---

# 弹窗 Dialog

> HyperOS 系统级模态弹窗组件，用于需要用户确认、输入或选择的场景。弹窗覆盖于页面之上，阻断用户操作流以获取明确响应。包含确认弹窗、警示弹窗、授权弹窗、引导说明弹窗、输入弹窗、进度弹窗和选择弹窗七种类型，涵盖系统级交互的全部模态场景。

## 预览

![弹窗 Dialog 全部变体预览](figma-screenshot-88387-41753.png)

---

## 组件结构

```
弹窗 Dialog                                        // FRAME | 88387:41753
├── 表头_Component&Instance                        // INSTANCE | 88387:41754
├── Alert 弹窗                                     // FRAME | 80475:14498
├── 确认弹窗                                       // COMPONENT_SET | 51823:275966
│   ├── 类型=单行正文                              // COMPONENT | 2982:38148
│   │   ├── 标题区域                               // FRAME
│   │   │   └── 标题                               // FRAME (overflow: clip)
│   │   │       └── Title Text                     // TEXT
│   │   ├── 正文                                   // FRAME (overflow: clip)
│   │   │   └── Body Text                          // TEXT
│   │   └── 按钮区域/两个按钮/左右布局              // FRAME
│   │       └── 弹窗按钮组                          // INSTANCE
│   │           ├── Cancel Button                  // INSTANCE (基础按钮)
│   │           └── Confirm Button                 // INSTANCE (强调按钮)
│   ├── 类型=多行正文                              // COMPONENT | 2982:38108
│   ├── 类型=带勾选能力                            // COMPONENT | 2982:38096
│   ├── 类型=2个以上按钮                           // COMPONENT | 42927:168176
│   └── 类型=通知弹窗                              // COMPONENT | 51823:281273
├── 警示弹窗                                       // COMPONENT_SET | 51823:276063
│   ├── Property 1=单行正文                        // COMPONENT | 51823:275997
│   ├── Property 1=多行正文                        // COMPONENT | 51823:276077
│   └── Property 1=卸载弹窗                        // COMPONENT | 42447:38983
├── 授权弹窗                                       // COMPONENT_SET | 51823:276091
│   ├── Property 1=基础弹窗                        // COMPONENT | 42447:38528
│   │   ├── 权限弹窗图标                           // INSTANCE (32×32)
│   │   ├── 标题区域                               // FRAME
│   │   ├── 正文                                   // FRAME
│   │   └── 按钮区域                               // FRAME
│   ├── Property 1=中立选项弹窗                    // COMPONENT | 51823:276206
│   ├── Property 1=位置授权                        // COMPONENT | 42506:20076
│   │   ├── 权限弹窗图标                           // INSTANCE
│   │   ├── 标题区域                               // FRAME
│   │   ├── 定位选项                               // FRAME (模糊/精准定位缩略图)
│   │   └── 按钮区域 (4个按钮)                     // FRAME
│   └── Property 1=批量授权                        // COMPONENT | 42447:39070
├── 引导说明弹窗                                   // COMPONENT_SET | 51823:276573
│   ├── Property 1=图文弹窗                        // COMPONENT | 42506:19668
│   │   ├── 标题区域                               // FRAME
│   │   │   ├── 标题                               // FRAME
│   │   │   └── 插图 (320×160)                    // FRAME (backdrop-blur)
│   │   ├── 正文                                   // FRAME
│   │   └── 按钮区域                               // FRAME
│   └── Property 1=低电量弹窗                      // COMPONENT | 42506:19947
├── 输入弹窗                                       // COMPONENT_SET | 51823:280798
│   ├── Property 1=输入框弹窗                      // COMPONENT | 2982:38054
│   │   ├── 标题                                   // FRAME
│   │   ├── 单行输入框                             // FRAME
│   │   │   └── 输入框背景                         // FRAME (border + rounded)
│   │   │       └── 输入区                         // FRAME
│   │   │           ├── Input Text                 // TEXT
│   │   │           └── 光标                       // DIV
│   │   └── 按钮区域                               // FRAME
│   └── Property 1=2个输入框                       // COMPONENT | 51823:276591
├── 进度弹窗                                       // COMPONENT_SET | 51823:276572
│   ├── Property 1=加载状态                        // COMPONENT | 2982:38085
│   │   └── 文字内容                               // FRAME
│   │       ├── Loading/icon (24×24)              // INSTANCE
│   │       └── Text                               // TEXT
│   └── Property 1=进度条状态                      // COMPONENT | 2982:38089
├── 选择弹窗（尽量避免使用）                        // COMPONENT_SET | 53475:7056
│   ├── 类型=单选                                  // COMPONENT | 53475:6853
│   │   ├── 标题                                   // FRAME
│   │   ├── 列表区域                               // FRAME
│   │   │   ├── 单选列表 (未选中)                  // INSTANCE
│   │   │   └── 单选列表 (选中 + Checkmark)        // INSTANCE
│   │   └── 按钮区域                               // FRAME
│   ├── 类型=单选双行                              // COMPONENT | 53475:6852
│   ├── 类型=多选                                  // COMPONENT | 53475:6851
│   ├── 类型=多选多行                              // COMPONENT | 53475:6850
│   └── 类型=选择弹窗-时间型                       // COMPONENT | 60481:143022
└── 权限弹窗图标                                   // COMPONENT_SET | 51823:276223
    ├── Property 2=麦克风, light=on                // COMPONENT | 51823:276224
    ├── Property 2=定位, light=on                  // COMPONENT | 51823:276226
    ├── ... (~35 种图标类型)
    └── Property 2=笔记, light=off                 // COMPONENT | 51823:276547
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| 确认弹窗 | COMPONENT_SET | `51823:275966` | 标准确认对话框，5 种变体 |
| 警示弹窗 | COMPONENT_SET | `51823:276063` | 警示/删除确认对话框，3 种变体 |
| 授权弹窗 | COMPONENT_SET | `51823:276091` | 权限授权对话框，4 种变体 |
| 引导说明弹窗 | COMPONENT_SET | `51823:276573` | 图文引导对话框，2 种变体 |
| 输入弹窗 | COMPONENT_SET | `51823:280798` | 含输入框的对话框，2 种变体 |
| 进度弹窗 | COMPONENT_SET | `51823:276572` | 加载/进度反馈对话框，2 种变体 |
| 选择弹窗 | COMPONENT_SET | `53475:7056` | 选择列表对话框（尽量避免使用），5 种变体 |
| 权限弹窗图标 | COMPONENT_SET | `51823:276223` | 授权弹窗配套图标集，约 35 种图标 × Light/Dark |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 通用弹窗容器（所有类型共享）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `368px` | — |
| `max-width` | `370px` | — |
| `height` | `auto`（hug） | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `gap` | `16px` | — |
| `padding` | `24px 0` | — |
| `border-radius` | `36px` | `hyperos_theme_radius_big` |
| `background` | 毛玻璃效果 | `Pured/Pured_Thick_Glass_Light` |

### 子组件: 标题区域

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%` | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |

#### 标题文字容器

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%` | — |
| `padding` | `0 36px` | — |
| `overflow` | `clip` | — |

### 子组件: 正文区域

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%` | — |
| `padding` | `0 28px` | — |
| `overflow` | `clip` | — |
| 单行正文 `text-align` | `center` | — |
| 多行正文 `text-align` | `left` | — |

### 子组件: 按钮区域

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%` | — |
| `padding` | `8px 24px 0` | — |
| `overflow` | `clip` | — |
| `border-radius` (底部) | `0 0 20px 20px` | `hyperos_theme_radius_medium` |

### 子组件: 输入框（输入弹窗）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%`（容器 px 24px） | — |
| `height` | `56px` | — |
| `background-color` | `rgba(0,0,0,0.06)` | `hyperos-color-surface-container-low` |
| `border-radius` | `16px` | `hyperos_theme_radius_common` |
| `border` (聚焦态) | `2px solid #3482FF` | `hyperos-color-primary` |
| `padding` | `16.5px 16px` | — |

### 子组件: 选择列表项（选择弹窗）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `368px` | — |
| `height` | `56px` | — |
| `min-height` | `56px` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `padding` | `14px 28px` | — |

### 子组件: 进度弹窗内容行

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `gap` | `8px` | — |
| `padding` | `0 24px` | — |
| `background-color` | `#FFFFFF` | `hyperos-color-surface-high` |

#### Loading 图标

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `24px` | — |
| `height` | `24px` | — |
| `flex-shrink` | `0` | — |

### 子组件: 权限弹窗图标

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `32px` | — |
| `height` | `32px` | — |
| `background-color` | `rgba(0,0,0,0.1)` | `hyperos-color-surface-container-high` |
| `border-radius` | `8px` | — |

### 子组件: 引导说明弹窗插图

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `320px` | — |
| `height` | `160px` | — |
| `backdrop-filter` | `blur(12px)` | — |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| 弹窗标题 | MiSans | 18px | 380 (Medium) | 100% | 0 | `#000000` | `Title/Title 4` |
| 正文（弹窗专用） | MiSans | 16px | 330 (Regular) | 22.4px | 0 | `rgba(0,0,0,0.8)` | `Body/Body 1 - window` |
| 按钮文字 | MiSans | 17px | 380 (Medium) | 100% | 0 | 按类型 | `Button/Button` |
| 进度弹窗文字 | MiSans | 17px | 380 (Medium) | 100% | 0 | `rgba(0,0,0,0.8)` | `Headline/Headline 1` |
| 输入框文字 | MiSans | 17px | 380 (Medium) | 100% | 0 | `#000000` | `Headline/Headline 1` |
| 选择列表文字 | MiSans | 17px | 380 (Medium) | 100% | 0 | `#000000` | `Headline/Headline 1` |
| 选择列表-选中 | MiSans | 17px | 380 (Medium) | 100% | 0 | `#3482FF` | `Headline/Headline 1` |
| 位置选项标签 | MiSans | 14px | 380 (Medium) | 100% | 0 | `rgba(0,0,0,0.8)` | `Subtitle/Subtitle` |
| 位置选项-选中 | MiSans | 14px | 380 (Medium) | 100% | 0 | `#3482FF` | `Subtitle/Subtitle` |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 弹窗标题文字 | `#000000` | `hyperos-color-on-surface` |
| 正文文字 | `rgba(0,0,0,0.8)` | `hyperos-color-on-surface-secondary` |
| 确认按钮背景 | `#3482FF` | `hyperos-color-primary` |
| 确认按钮文字 | `#FFFFFF` | `hyperos-color-on-primary` |
| 取消按钮背景 | `rgba(0,0,0,0.06)` | `hyperos-color-tertiary` |
| 取消按钮文字 | `rgba(0,0,0,0.8)` | `hyperos-color-on-tertiary` |
| 警示操作文字 | `#FA382E` | `hyperos-color-error` |
| 选中态文字 | `#3482FF` | `hyperos-color-primary` |
| 输入框背景 | `rgba(0,0,0,0.06)` | `hyperos-color-surface-container-low` |
| 输入框聚焦边框 | `#3482FF` | `hyperos-color-primary` |
| 进度弹窗背景 | `#FFFFFF` | `hyperos-color-surface-high` |
| 权限图标背景 | `rgba(0,0,0,0.1)` | `hyperos-color-surface-container-high` |
| 辅助文字色 | `rgba(0,0,0,0.6)` | `hyperos-color-on-surface-tertiary` |

---

## 变体

### 维度定义

#### 确认弹窗

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `类型` | `单行正文` / `多行正文` / `带勾选能力` / `2个以上按钮` / `通知弹窗` | 控制弹窗内容和按钮布局 |

共计 **5 个变体**。

#### 警示弹窗

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `Property 1` | `单行正文` / `多行正文` / `卸载弹窗` | 控制警示场景 |

共计 **3 个变体**。

#### 授权弹窗

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `Property 1` | `基础弹窗` / `中立选项弹窗` / `位置授权` / `批量授权` | 控制授权场景和按钮数量 |

共计 **4 个变体**。

#### 引导说明弹窗

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `Property 1` | `图文弹窗` / `低电量弹窗` | 控制引导场景 |

共计 **2 个变体**。

#### 输入弹窗

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `Property 1` | `输入框弹窗` / `2个输入框` | 控制输入框数量 |

共计 **2 个变体**。

#### 进度弹窗

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `Property 1` | `加载状态` / `进度条状态` | 控制进度展示方式 |

共计 **2 个变体**。

#### 选择弹窗（尽量避免使用）

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `类型` | `单选` / `单选双行` / `多选` / `多选多行` / `选择弹窗-时间型` | 控制选择模式 |

共计 **5 个变体**。

#### 权限弹窗图标

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 图标类型 | `Property 2` | `麦克风` / `定位` / `相机` / `联系人` / `存储文件` / `短信` / `日历` / `链式启动` / `跟踪` / `wifi` / `通话` / `通话记录` / `身体传感器` / `账户` / `NFC` / `聊天信息` / `相册` / `音频` / `其他` / `邮件` / `屏幕内容` / `身体运动` / `上网记录` / `蓝牙` / `信息列表` / `通知` / `传感器` / `身体传感器2` / `隐私` / `警示` / `警告` / `读取通知` / `安装应用` / `读取屏幕` / `操作行为` / `录音` / `笔记` | 权限图标类型 |
| 主题 | `light` | `on` / `off` | Light / Dark 主题 |

共计约 **35 × 2 = 70 个变体**。

### 变体差异表

#### 各弹窗类型结构差异

> 以「确认弹窗-单行正文」为基准，仅列出各类型差异。

| 特征 | 确认弹窗 | 警示弹窗 | 授权弹窗 | 引导说明弹窗 | 输入弹窗 | 进度弹窗 | 选择弹窗 |
|-----|---------|---------|---------|------------|---------|---------|---------|
| 标题 | 有 | 有 | 有 | 有 | 有 | 无 | 有 |
| 正文 | 有 | 有 | 有 | 有 | 无 | 仅文字 | 无 |
| 图标 | 无 | 无 | 权限图标 32×32 | 无 | 无 | Loading 24×24 | 无 |
| 插图 | 无 | 无 | 位置缩略图（可选） | 320×160 插图 | 无 | 无 | 无 |
| 输入框 | 无 | 无 | 无 | 无 | 1~2 个 | 无 | 无 |
| 选择列表 | 无 | 无 | 无 | 无 | 无 | 无 | 有 |
| 勾选能力 | 可选 | 无 | 无 | 无 | 无 | 无 | 多选变体 |
| 确认按钮样式 | 强调（蓝色） | 警示（红色文字） | 强调（蓝色） | 强调（蓝色） | 强调（蓝色） | 无按钮 | 强调（蓝色） |
| 按钮数量 | 2（可扩展） | 2 | 2~4 | 2 | 2 | 0 | 2 |

#### 警示弹窗 vs 确认弹窗差异

| 属性 | 确认弹窗 | 警示弹窗 |
|-----|---------|---------|
| 确认按钮 `background-color` | `#3482FF` (primary) | `rgba(0,0,0,0.06)` (tertiary) |
| 确认按钮 `color` | `#FFFFFF` (on-primary) | `#FA382E` (error) |
| 语义 | 积极确认操作 | 破坏性操作警告 |

---

## 交互状态

> 弹窗本身无交互状态变化。以下列出弹窗内子组件的交互状态。

### 按钮区域

参见 [Button 按钮组件规范](./button-component-spec.md)，弹窗内使用「弹窗按钮组」组件。

### 输入框

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `default` | — | `border` | 无边框 | — |
| `focused` | 输入框获得焦点 | `border` | `2px solid #3482FF` | `hyperos-color-primary` |
| `focused` | 输入框获得焦点 | 光标 | 显示 2.18px 宽蓝色光标 | `hyperos-color-primary` |

### 选择列表项

| 状态 | 触发条件 | 变化的属性 | 变化值 | Token |
|-----|---------|-----------|-------|-------|
| `unselected` | — | `color` | `#000000` | `hyperos-color-on-surface` |
| `selected` | 用户选中 | `color` | `#3482FF` | `hyperos-color-primary` |
| `selected` | 用户选中 | 尾部 | 显示 Checkmark 图标 (20×20) | — |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

### 确认弹窗

```typescript
interface ConfirmDialogProps {
  /** 弹窗内容类型 */
  type: '单行正文' | '多行正文' | '带勾选能力' | '2个以上按钮' | '通知弹窗';
}
```

### 警示弹窗

```typescript
interface WarningDialogProps {
  /** 警示场景类型 */
  type: '单行正文' | '多行正文' | '卸载弹窗';
}
```

### 授权弹窗

```typescript
interface PermissionDialogProps {
  /** 授权场景类型 */
  type: '基础弹窗' | '中立选项弹窗' | '位置授权' | '批量授权';
}
```

### 引导说明弹窗

```typescript
interface GuideDialogProps {
  /** 引导类型 */
  type: '图文弹窗' | '低电量弹窗';
}
```

### 输入弹窗

```typescript
interface InputDialogProps {
  /** 输入框数量 */
  type: '输入框弹窗' | '2个输入框';
}
```

### 进度弹窗

```typescript
interface ProgressDialogProps {
  /** 进度展示方式 */
  type: '加载状态' | '进度条状态';
}
```

### 选择弹窗

```typescript
interface SelectionDialogProps {
  /** 选择模式 */
  type: '单选' | '单选双行' | '多选' | '多选多行' | '选择弹窗-时间型';
}
```

### 权限弹窗图标

```typescript
interface PermissionIconProps {
  /** 权限图标类型 */
  iconType: '麦克风' | '定位' | '相机' | '联系人' | '存储文件' | '短信' | '日历' | /* ... 约35种 */;
  /** Light / Dark 主题 */
  light: 'on' | 'off';
}
```

| Figma 属性名 | 类型 | 对应组件 | 对应 Prop | 默认值 | 说明 |
|-------------|------|---------|----------|-------|------|
| 类型 | Variant | 确认弹窗 | `type` | `单行正文` | 弹窗内容类型 |
| Property 1 | Variant | 警示/授权/引导/输入/进度弹窗 | `type` | 首个变体 | 弹窗场景类型 |
| 类型 | Variant | 选择弹窗 | `type` | `单选` | 选择模式 |
| Property 2 | Variant | 权限弹窗图标 | `iconType` | `麦克风` | 图标类型 |
| light | Variant | 权限弹窗图标 | `light` | `on` | 主题模式 |

---

## 使用指南

### 何时使用

- **操作确认**：用户执行重要操作前需要二次确认时，使用「确认弹窗」
- **危险操作警告**：删除、卸载等不可逆操作前，使用「警示弹窗」
- **权限请求**：应用首次请求系统权限时，使用「授权弹窗」
- **功能引导**：向用户介绍新功能或展示图文说明时，使用「引导说明弹窗」
- **信息输入**：需要用户输入少量文本（如重命名、密码）时，使用「输入弹窗」
- **异步进度反馈**：耗时操作需要展示加载状态或进度条时，使用「进度弹窗」
- **选项选择**：需要从列表中单选/多选时，使用「选择弹窗」（尽量避免，优先考虑其他交互方式）

### 何时不使用

- **轻量提示**：短暂的成功/失败反馈，应使用 Toast 代替
- **非阻断信息**：不需要用户响应的信息，应使用 Snackbar 或 Banner 代替
- **复杂表单**：多字段输入场景，应使用独立页面代替
- **底部操作面板**：可选操作列表，应使用 ActionSheet 代替
- **系统级通知**：推送通知应使用 Notification 组件

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 弹窗标题简洁明了（1 行内） | 标题过长导致多行换行 | 标题区域有 `overflow: clip`，超长文字会被截断 |
| 正文单行时居中，多行时左对齐 | 多行正文仍然居中对齐 | 左对齐可读性更好 |
| 警示弹窗的确认按钮使用 error 色 | 警示弹窗使用强调蓝色确认按钮 | 红色文字明确传达操作的破坏性 |
| 授权弹窗提供明确的权限说明正文 | 仅显示标题不给出权限用途说明 | 用户需要理解为什么需要该权限 |
| 进度弹窗不包含操作按钮 | 进度弹窗添加取消按钮 | 进度弹窗应由系统自动关闭 |
| 选择弹窗标注"尽量避免使用" | 大量使用选择弹窗 | Figma 组件名称已标注应优先使用其他交互方式 |
| 输入弹窗限制在 1~2 个输入框 | 在弹窗内放置 3 个以上输入框 | 弹窗空间有限，复杂表单应使用独立页面 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `hyperos-color-on-surface` | `#000000` | color | 弹窗标题文字 |
| `hyperos-color-on-surface-secondary` | `rgba(0,0,0,0.8)` | color | 正文文字 |
| `hyperos-color-on-surface-tertiary` | `rgba(0,0,0,0.6)` | color | 辅助文字 |
| `hyperos-color-on-surface-quaternary` | `rgba(0,0,0,0.4)` | color | 次级辅助色 |
| `hyperos-color-on-surface-octonary` | `rgba(0,0,0,0.3)` | color | 禁用文字色 |
| `hyperos-color-primary` | `#3482FF` | color | 确认按钮背景、选中态、输入框聚焦边框 |
| `hyperos-color-on-primary` | `#FFFFFF` | color | 确认按钮文字 |
| `hyperos-color-tertiary` | `rgba(0,0,0,0.06)` | color | 取消按钮背景 |
| `hyperos-color-on-tertiary` | `rgba(0,0,0,0.8)` | color | 取消按钮文字 |
| `hyperos-color-error` | `#FA382E` | color | 警示操作文字 |
| `hyperos-color-surface-high` | `#FFFFFF` | color | 进度弹窗背景 |
| `hyperos-color-surface-highest` | `#FFFFFF` | color | 弹窗基础背景 |
| `hyperos-color-surface-container-low` | `rgba(0,0,0,0.06)` | color | 输入框背景 |
| `hyperos-color-surface-container-high` | `rgba(0,0,0,0.1)` | color | 权限图标背景 |
| `hyperos-color-surface-container` | `rgba(0,0,0,0.04)` | color | 容器背景 |
| `元素色/container_list` | `#FFFFFF` | color | 列表背景 |
| `hyperos_theme_radius_big` | `36px` | radius | 弹窗容器圆角 |
| `hyperos_theme_radius_medium` | `20px` | radius | 按钮区域底部圆角 |
| `hyperos_theme_radius_common` | `16px` | radius | 按钮圆角、输入框圆角 |
| `hyperos_theme_radius_small` | `12px` | radius | 位置缩略图圆角 |
| `hyperos_theme_radius_circle` | `999px` | radius | 圆形元素 |
| `hyperos_font_size_title4` | `18px` | font-size | 弹窗标题字号 |
| `hyperos_font_weight_title4` | `380` | font-weight | 弹窗标题字重 |
| `hyperos_font_size_body1` | `16px` | font-size | 正文字号 |
| `hyperos_font_weight_body1` | `330` | font-weight | 正文字重 |
| `Row Height/body 1 - window` | `22.4px` | line-height | 弹窗正文行高 |
| `hyperos_font_size_Headline1` | `17px` | font-size | 输入/选择列表/进度文字字号 |
| `hyperos_font_weight_Headline1` | `380` | font-weight | 输入/选择列表/进度文字字重 |
| `hyperos_font_size_button` | `17px` | font-size | 按钮字号 |
| `hyperos_font_weight_button` | `380` | font-weight | 按钮字重 |
| `hyperos_font_size_subtitle` | `14px` | font-size | 位置选项标签字号 |
| `hyperos_font_weight_subtitle` | `380` | font-weight | 位置选项标签字重 |
| `Title/Title 4` | `MiSans, Medium, 18px, 380, lh:100%, ls:0` | typography | 弹窗标题完整样式 |
| `Body/Body 1 - window` | `MiSans, Regular, 16px, 330, lh:22.4px, ls:0` | typography | 弹窗正文完整样式 |
| `Headline/Headline 1` | `MiSans, Medium, 17px, 380, lh:100%, ls:0` | typography | 列表/输入文字完整样式 |
| `Button/Button` | `MiSans, Medium, 17px, 380, lh:100%, ls:0` | typography | 按钮文字完整样式 |
| `Subtitle/Subtitle` | `MiSans, Medium, 14px, 380, lh:100%, ls:0` | typography | 位置选项标签完整样式 |
| `Pured/Pured_Thick_Glass_Light` | `#000000, #FFFFFF, #FFFFFF` | effect | Light 模式毛玻璃 |
| `Pured/Pured_Thick_Glass_Dark` | `#000000, #575757, #060606` | effect | Dark 模式毛玻璃 |
| `FrostShadow/FrostEffect_Regular_ShadowOff` | `INNER_SHADOW + BLUR(60)` | effect | 弹窗毛玻璃效果 |

---

## 设计注释

> 1. 弹窗宽度固定为 **368px**（max-width: 370px），所有类型共享此尺寸。高度由内容自适应（hug）。
> 2. 弹窗使用 **Thick Glass（厚毛玻璃）** 效果，与 Menu 的 Regular Glass 有所不同。Light 和 Dark 模式使用不同的 Pured Token。
> 3. 弹窗容器圆角为 **36px**（`hyperos_theme_radius_big`），是系统中最大圆角值之一，突出弹窗的独立性和层级。
> 4. 正文区域使用了弹窗专用的 **`Body/Body 1 - window`** 文字样式，其 `line-height` 为 **22.4px**，与标准 `Body/Body 1`（100%）不同，为多行阅读优化。
> 5. **选择弹窗** 的 Figma 组件名称中明确标注了"尽量避免使用"，建议优先采用 ActionSheet 或其他非模态交互方式。
> 6. **警示弹窗** 的确认按钮不使用强调蓝色背景，而是使用基础按钮样式 + 红色文字（error 色），以避免鼓励用户执行危险操作。
> 7. **授权弹窗-位置授权** 包含地图缩略图预览，提供「模糊定位」和「精准定位」两个可视化选项，帮助用户理解权限级别。
> 8. **进度弹窗** 是唯一没有操作按钮的弹窗类型，且显式设置了 `background-color: white`（其他弹窗使用毛玻璃效果）。
> 9. 输入框聚焦态通过 **2px 蓝色实线边框** 标识，与 HyperOS 全局的聚焦态视觉规范一致。
> 10. 权限弹窗图标集包含约 35 种系统权限类型，每种提供 Light（`light=on`）和 Dark（`light=off`）两个主题变体。
