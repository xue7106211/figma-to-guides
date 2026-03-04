---
component: ProximityPairing
description: HyperOS 配对提示组件，用于蓝牙设备靠近时弹出连接弹窗，覆盖耳机、手柄、车载、IoT 等设备类型
figma_source: https://www.figma.com/design/7PVSm4yEbknNLFaqauI4EM/branch/oeFOra0gr6B7Nft61ekir8/Xiaomi-Hyper-OS4-UI-Kit?node-id=42927-167304
figma_node_id: "42927:167304"
variants: "4 component sets: 基础耳机连接弹窗 (5 types), 商业标签耳机连接弹窗 (5 types), 手柄连接弹窗 (5 types), 更多连接场景 (9 types); 连接弹窗/Light (glass wrapper)"
tokens_used: 16
---

# 配对提示 ProximityPairing

> HyperOS 系统级蓝牙设备靠近配对弹窗组件，当用户将蓝牙设备靠近手机时自动弹出。提供设备识别、连接进度、连接结果（成功/失败）和附加操作（安装配套应用、绑定 IoT 设备等）的完整流程覆盖。支持耳机、游戏手柄、车载设备、IoT 设备等多种设备类型，并区分标准样式和商业标签增强样式。

## 预览

![配对提示 ProximityPairing 全部变体预览](figma-screenshot-42927-167304.png)

---

## 组件结构

```
页面指示器 Page controls                            // SECTION | 42927:167304
├── .Page header                                   // INSTANCE | 42927:167305
├── 连接弹窗 (预览区)                               // FRAME | 80326:11028
├── 连接弹窗/Light                                  // COMPONENT | 80326:11029
│   └── 基础耳机连接弹窗 (instance slot)            // INSTANCE
│       ├── 标题+内容                              // FRAME
│       │   ├── 标题                               // FRAME
│       │   │   └── Title Text                     // TEXT (设备名)
│       │   └── 内容区域                           // FRAME (overflow: clip)
│       │       └── 设备配图区域                    // FRAME
│       │           └── 设备配图 200px / 128px     // FRAME (设备图片)
│       ├── 默认按钮                               // INSTANCE (操作按钮)
│       └── close                                  // INSTANCE (关闭按钮, absolute)
├── 基础耳机连接弹窗                                // COMPONENT_SET | 48303:30604
│   ├── 类型=待连接                                // COMPONENT | 36521:4714
│   ├── 类型=正在连接                              // COMPONENT | 36521:5041
│   ├── 类型=连接完成                              // COMPONENT | 36521:7832
│   ├── 类型=非首次连接完成                         // COMPONENT | 36521:8832 (hidden)
│   └── 类型=连接失败                              // COMPONENT | 36521:8831
├── 商业标签耳机连接弹窗                            // COMPONENT_SET | 48303:30605
│   ├── 类型=待连接                                // COMPONENT | 36611:27152
│   │   ├── 弹窗标题                               // FRAME
│   │   │   ├── 产品名称                           // FRAME
│   │   │   └── 卖点信息区域                       // FRAME
│   │   │       └── 标签组                         // FRAME (一级标签 + 二级标签)
│   │   ├── 内容区域                               // FRAME (设备图)
│   │   ├── 默认按钮                               // INSTANCE
│   │   └── 清除 3.1                               // INSTANCE (close)
│   ├── 类型=商业标签弹窗-连接中                    // COMPONENT | 36752:9530
│   ├── 类型=连接完成                              // COMPONENT | 36752:9657
│   ├── 类型=非首次连接完成                         // COMPONENT | 36752:9726 (hidden)
│   └── 类型=Variant5                              // COMPONENT | 48303:30646
├── 手柄连接弹窗                                   // COMPONENT_SET | 48303:30689
│   ├── 类型=发现左手柄                            // COMPONENT | 36611:28284
│   ├── 类型=发现双手柄                            // COMPONENT | 36794:5500
│   ├── 类型=正在连接                              // COMPONENT | 36794:5519
│   ├── 类型=手柄-连接成功                          // COMPONENT | 36794:5785
│   └── 类型=手柄-连接失败提示开启蓝牙              // COMPONENT | 36794:5538
└── 更多连接场景                                   // COMPONENT_SET | 48303:30690
    ├── 类型=重置提示                              // COMPONENT | 36611:28292
    ├── 类型=安装小米健康                           // COMPONENT | 36521:8814
    ├── 类型=安装米家                              // COMPONENT | 36918:4887
    ├── 类型=连接车                                // COMPONENT | 36918:4806
    ├── 类型=一起听                                // COMPONENT | 36577:13832
    ├── 类型=发现耳机-缺省图                        // COMPONENT | 37075:7946
    ├── 类型=连接成功-缺省图                        // COMPONENT | 37075:7947
    ├── 类型=连接成功-缺少一只耳机                  // COMPONENT | 37184:17332
    └── 类型=米家-绑定                             // COMPONENT | 36577:14198
```

### 子节点清单

| 节点名称 | 类型 | Figma nodeId | 说明 |
|---------|------|-------------|------|
| 连接弹窗/Light | COMPONENT | `80326:11029` | 毛玻璃包装层，作为所有连接弹窗的视觉外壳 |
| 基础耳机连接弹窗 | COMPONENT_SET | `48303:30604` | 标准耳机配对弹窗，5 种连接状态 |
| 商业标签耳机连接弹窗 | COMPONENT_SET | `48303:30605` | 带商业卖点标签的耳机配对弹窗，5 种变体 |
| 手柄连接弹窗 | COMPONENT_SET | `48303:30689` | 游戏手柄配对弹窗，5 种连接状态 |
| 更多连接场景 | COMPONENT_SET | `48303:30690` | 其他设备连接场景，9 种变体 |

---

## 设计规范

> 以下所有值可直接映射到 CSS 属性。Token 列标注该值对应的设计系统 Token 名称。

### 通用弹窗容器（所有类型共享）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `368px` | — |
| `height` | `422px` | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `gap` | `16px` | — |
| `padding` | `32px` | — |
| `border-radius` | `46px` | — |
| `position` | `relative` | — |

### 子组件: 连接弹窗/Light（毛玻璃包装层）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `border-radius` | `36px` | `hyperos_theme_radius_big` |
| `border` | `1px solid #F9F9F9` | — |
| `background` | 多层叠加 (见下方玻璃效果详情) | `Pured/Pured_Extra_Thick_Light` |
| `box-shadow` | `inset 0px 2px 2px #9D9D9D` | `GlassShadow/GlassEffect_Regular_ShadowOff` |

#### 玻璃效果详情

| 层级 | CSS 属性 | 值 |
|-----|---------|---|
| 基底层 | `background-color` | `rgba(0,0,0,0.02)` |
| 柔光层 | `background-color` | `rgba(255,255,255,0.6)` |
| 柔光层 | `mix-blend-mode` | `soft-light` |
| 强光层 | `background-color` | `rgba(255,255,255,0.6)` |
| 强光层 | `mix-blend-mode` | `hard-light` |
| 阴影层 | `box-shadow` | `inset 0px 2px 2px #9D9D9D` |

### 子组件: 标题区域

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%` | — |
| `display` | `flex` | — |
| `flex-direction` | `column` | — |
| `align-items` | `center` | — |
| `gap` | `8px` | — |
| `padding` | `0 20px`（标题文字容器） | — |

### 子组件: 内容区域（设备配图）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `width` | `100%` | — |
| `flex` | `1 0 0` | — |
| `min-height` | `200px` | — |
| `overflow` | `clip` | — |
| `display` | `flex` | — |
| `align-items` | `center` | — |
| `justify-content` | `center` | — |

#### 设备配图尺寸

| 场景 | 容器尺寸 | 图片尺寸 |
|-----|---------|---------|
| 待连接/正在连接/失败 | `304 × 200px` | `200 × 200px` |
| 连接完成（双耳） | `304 × 200px` | `128 × 128px` × 2（网格排列） |
| 手柄（单手柄） | `304 × 128px` | `160 × 128px` |
| 手柄（双手柄） | `304 × 128px` | `160 × 128px` × 2（重叠） |

### 子组件: 操作按钮

| CSS 属性 | 值（基础按钮） | 值（强调按钮） | Token |
|---------|----|-------|-------|
| `width` | `100%` | `100%` | — |
| `height` | `auto` | `50px` | — |
| `padding` | `13.5px 20px` | `8px 20px` | — |
| `background-color` | `rgba(0,0,0,0.06)` | `#3482FF` | `hyperos-color-tertiary` / `hyperos-color-primary` |
| `color` | `rgba(0,0,0,0.8)` | `#FFFFFF` | `hyperos-color-on-tertiary` / `hyperos-color-on-primary` |
| `border-radius` | `16px` | `16px` | `hyperos_theme_radius_common` |
| `font-size` | `17px` | `17px` | `hyperos_font_size_button` |
| `font-weight` | `380` | `380` | `hyperos_font_weight_button` |

### 子组件: 关闭按钮

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `position` | `absolute` | — |
| `top` | `20px` | — |
| `right` | `20px` | — |
| `width` | `28px` | — |
| `height` | `28px` | — |

### 子组件: 电池信息（连接完成态）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| 电池图标 `width` | `26px` | — |
| 电池图标 `height` | `14px` | — |
| 电池填充色 | `#36D167` | `系统色-light/green-light-primary-default` |
| 电池边框 | `1.66px solid #000000` | — |
| 电量文字 `font-size` | `13px` | — |
| 电量文字 `color` | `rgba(0,0,0,0.8)` | — |
| 电量文字 `font-family` | MiSans Regular | — |

### 子组件: 商业标签区域（商业标签弹窗专有）

| CSS 属性 | 值 | Token |
|---------|----|-------|
| `backdrop-filter` | `blur(50px)` | — |
| `border` | `0.8px solid white` | — |
| 内阴影 | `inset 0.5px 1.2px 1.2px rgba(255,255,255,0.6)` | — |
| 一级标签描述 `font-size` | `12px` | — |
| 一级标签描述 `font-weight` | Semibold | — |
| 一级标签描述 `letter-spacing` | `1px` | — |
| 二级标签描述 `font-size` | `10.5px` / `10px` | — |

### 文字样式

| 文字元素 | `font-family` | `font-size` | `font-weight` | `line-height` | `letter-spacing` | `color` | Token 前缀 |
|---------|--------------|-------------|---------------|--------------|-----------------|---------|-----------|
| 设备名称（标题） | MiSans | 20px | Demibold | normal | 0 | `#000000` | `hyperos_font_size_title3` |
| 操作按钮文字 | MiSans | 17px | 380 (Medium) | 100% | 0 | 按类型 | `Button/Button` |
| 电量百分比 | MiSans | 13px | Regular | normal | 0 | `rgba(0,0,0,0.8)` | — |
| 商业一级标签 | MiSans | 12px | Semibold | normal | 1px | `#232323` | — |
| 商业二级标签 | MiSans | 10~10.5px | Semibold | normal | 0.8px | `#232323` | — |
| 位置选项标签 | MiSans | 14px | 380 (Medium) | 100% | 0 | `rgba(0,0,0,0.8)` | `Body/Body 2` |

### 颜色一览

| 语义用途 | 值 | Token |
|---------|---|-------|
| 标题文字 | `#000000` | `hyperos-color-on-surface` |
| 基础按钮背景 | `rgba(0,0,0,0.06)` | `hyperos-color-tertiary` |
| 基础按钮文字 | `rgba(0,0,0,0.8)` | `hyperos-color-on-tertiary` |
| 强调按钮背景 | `#3482FF` | `hyperos-color-primary` |
| 强调按钮文字 | `#FFFFFF` | `hyperos-color-on-primary` |
| 电池填充色 | `#36D167` | `系统色-light/green-light-primary-default` |
| 商业标签文字 | `#232323` | — |
| 辅助文字 | `rgba(0,0,0,0.6)` | `hyperos-color-on-surface-tertiary` |

---

## 变体

### 维度定义

#### 基础耳机连接弹窗

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `类型` | `待连接` / `正在连接` / `连接完成` / `非首次连接完成` / `连接失败` | 蓝牙耳机配对流程状态 |

共计 **5 个变体**（非首次连接完成为 hidden）。

#### 商业标签耳机连接弹窗

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `类型` | `待连接` / `商业标签弹窗-连接中` / `连接完成` / `非首次连接完成` / `Variant5` | 带商业标签的配对流程 |

共计 **5 个变体**（非首次连接完成为 hidden）。

#### 手柄连接弹窗

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `类型` | `发现左手柄` / `发现双手柄` / `正在连接` / `手柄-连接成功` / `手柄-连接失败提示开启蓝牙` | 游戏手柄配对流程 |

共计 **5 个变体**。

#### 更多连接场景

| 维度名称 | Figma 属性名 | 可选值 | 说明 |
|---------|-------------|-------|------|
| 类型 | `类型` | `重置提示` / `安装小米健康` / `安装米家` / `连接车` / `一起听` / `发现耳机-缺省图` / `连接成功-缺省图` / `连接成功-缺少一只耳机` / `米家-绑定` | 扩展连接场景 |

共计 **9 个变体**。

### 变体差异表

#### 按连接流程状态分组（基础耳机为基准）

| 属性 | `待连接` | `正在连接` | `连接完成` | `连接失败` |
|-----|---------|-----------|-----------|-----------|
| 标题文字 | 设备名 | 设备名 | 设备名 | 设备名 + "未连接" |
| 设备图尺寸 | 200×200 | 200×200 | 128×128 × 2 | 200×200 |
| 电池信息 | 无 | 无 | 有（左/右/充电盒） | 无 |
| 按钮文字 | "连接" | "正在连接..." | "更多设置" | "重试" |
| 按钮类型 | 基础 | 基础（无背景） | 基础 | 基础 |
| `border` | 无 | 无 | `0.8px solid white` | 无 |

#### 按弹窗类别分组

| 特征 | 基础耳机 | 商业标签耳机 | 手柄 | 安装应用 |
|-----|---------|------------|------|---------|
| `backdrop-filter` | 无 | `blur(50px)` | `blur(50px)` | 无 |
| `border` | 无（待连接）/ 0.8px white（完成） | `0.8px solid white` | `0.8px solid white` | 无 |
| 内阴影 | 无 | `inset 0.5px 1.2px 1.2px rgba(255,255,255,0.6)` | `inset 0.5px 1.2px 1.2px rgba(255,255,255,0.6)` | 无 |
| 商业标签 | 无 | 有（一级 + 二级标签） | 无 | 无 |
| 设备图高度 | 200px | 200px | 128px | 200px |
| 按钮类型 | 基础（灰色） | 基础（灰色） | 基础（灰色） | **强调**（蓝色） |
| 标题+内容 gap | 8px | 8px | 16px | 8px |

---

## 交互状态

> 配对弹窗本身是一个状态驱动的组件，每个连接状态对应一个独立变体。

| 状态 | 触发条件 | 视觉变化 | 按钮操作 |
|-----|---------|---------|---------|
| `待连接` | 设备靠近被检测到 | 显示设备大图，标准关闭按钮 | "连接" → 触发配对 |
| `正在连接` | 用户点击连接 | 同上，按钮文字变化 | "正在连接..." → 不可操作 |
| `连接完成` | 配对成功 | 设备图缩小为 128px，显示电池信息 | "更多设置" → 跳转设置页 |
| `连接失败` | 配对超时/失败 | 标题追加"未连接" | "重试" → 重新配对 |

### 关闭按钮

| 状态 | 说明 |
|-----|------|
| 默认 | 始终显示在右上角，点击关闭弹窗 |
| 所有流程状态 | 均可关闭，关闭后取消配对流程 |

---

## 组件 API

> 从 Figma 组件属性中提取的 Props 定义，使用 TypeScript 风格描述类型。

### 连接弹窗/Light（包装层）

```typescript
interface PairingDialogLightProps {
  /** 内部弹窗内容（Instance Swap） */
  instance?: ReactNode; // 默认: 基础耳机连接弹窗-待连接
}
```

### 基础耳机连接弹窗

```typescript
interface BasicHeadphonePairingProps {
  /** 连接流程状态 */
  type: '待连接' | '正在连接' | '连接完成' | '非首次连接完成' | '连接失败';
}
```

### 商业标签耳机连接弹窗

```typescript
interface CommercialHeadphonePairingProps {
  /** 连接流程状态 */
  type: '待连接' | '商业标签弹窗-连接中' | '连接完成' | '非首次连接完成' | 'Variant5';
}
```

### 手柄连接弹窗

```typescript
interface ControllerPairingProps {
  /** 连接流程状态 */
  type: '发现左手柄' | '发现双手柄' | '正在连接' | '手柄-连接成功' | '手柄-连接失败提示开启蓝牙';
}
```

### 更多连接场景

```typescript
interface ExtendedPairingProps {
  /** 连接场景类型 */
  type: '重置提示' | '安装小米健康' | '安装米家' | '连接车' | '一起听' | '发现耳机-缺省图' | '连接成功-缺省图' | '连接成功-缺少一只耳机' | '米家-绑定';
}
```

| Figma 属性名 | 类型 | 对应组件 | 对应 Prop | 默认值 | 说明 |
|-------------|------|---------|----------|-------|------|
| instance | Instance Swap | 连接弹窗/Light | `instance` | 基础耳机连接弹窗 | 可替换内部弹窗内容 |
| 类型 | Variant | 基础耳机连接弹窗 | `type` | `待连接` | 连接流程状态 |
| 类型 | Variant | 商业标签耳机连接弹窗 | `type` | `待连接` | 连接流程状态 |
| 类型 | Variant | 手柄连接弹窗 | `type` | `发现左手柄` | 连接流程状态 |
| 类型 | Variant | 更多连接场景 | `type` | `重置提示` | 连接场景类型 |
| propValue | Variant | 基础耳机连接弹窗（内部） | `propValue` | `待连接` | 弹窗流程子状态 |

---

## 使用指南

### 何时使用

- **耳机配对**：用户将蓝牙耳机靠近手机时，使用「基础耳机连接弹窗」展示配对流程
- **商业推广耳机**：带有品牌卖点标签的耳机产品，使用「商业标签耳机连接弹窗」展示产品特性
- **游戏手柄**：用户将游戏手柄靠近手机时，使用「手柄连接弹窗」，支持单/双手柄发现
- **IoT 设备绑定**：如米家设备绑定、车载连接等场景，使用「更多连接场景」对应变体
- **配套应用安装**：设备需要配套应用（如小米健康、米家）时，使用安装类变体引导下载

### 何时不使用

- **手动蓝牙配对**：用户从系统设置中手动搜索配对，应使用系统蓝牙设置界面
- **WiFi 连接**：WiFi 设备连接应使用网络设置界面
- **文件传输**：设备间文件传输应使用 Share Sheet 或专用传输界面
- **通知提醒**：非配对类的设备通知应使用 Notification 组件

### Do's & Don'ts

| Do | Don't | 原因 |
|----|-------|------|
| 连接成功后展示电池电量信息 | 连接成功仅显示文字"连接成功" | 用户期望确认设备状态 |
| "安装应用"场景使用强调蓝色按钮 | 安装场景使用灰色基础按钮 | 安装操作需要明确的 CTA 引导 |
| 连接失败标题明确标注"未连接" | 连接失败仅改变按钮文字 | 用户需要从标题快速感知当前状态 |
| 始终提供关闭按钮 | 移除关闭按钮强制用户操作 | 用户应能随时取消配对流程 |
| 商业标签弹窗使用 `backdrop-blur` 增强质感 | 基础弹窗也添加 backdrop-blur | 仅商业推广场景需要增强视觉表现 |

---

## 设计 Token 映射

> 该组件使用的所有设计 Token 汇总。

| Token | 值 | 类型 | 引用位置 |
|-------|---|------|---------|
| `hyperos-color-on-surface` | `#000000` | color | 标题文字 |
| `hyperos-color-primary` | `#3482FF` | color | 强调按钮背景（安装类变体） |
| `hyperos-color-on-primary` | `#FFFFFF` | color | 强调按钮文字 |
| `hyperos-color-tertiary` | `rgba(0,0,0,0.06)` | color | 基础按钮背景 |
| `hyperos-color-on-tertiary` | `rgba(0,0,0,0.8)` | color | 基础按钮文字 |
| `hyperos-color-on-surface-tertiary` | `rgba(0,0,0,0.6)` | color | 辅助文字色 |
| `hyperos-color-on-surface-secondary` | `rgba(0,0,0,0.8)` | color | 次级文字色 |
| `hyperos-color-on-surface-quaternary` | `rgba(0,0,0,0.4)` | color | 弱化文字色 |
| `hyperos-color-surface-highest` | `#FFFFFF` | color | 弹窗基础背景 |
| `hyperos-color-surface-container-high` | `rgba(0,0,0,0.1)` | color | 容器背景 |
| `系统色-light/green-light-primary-default` | `#36D167` | color | 电池充电指示 |
| `hyperos_theme_radius_big` | `36px` | radius | 连接弹窗/Light 圆角 |
| `hyperos_theme_radius_common` | `16px` | radius | 操作按钮圆角 |
| `hyperos_theme_radius_medium` | `20px` | radius | 中等圆角 |
| `hyperos_font_size_title3` | `20px` | font-size | 标题字号 |
| `hyperos_font_size_button` | `17px` | font-size | 按钮字号 |
| `hyperos_font_weight_button` | `380` | font-weight | 按钮字重 |
| `Button/Button` | `MiSans, Medium, 17px, 380, lh:100%, ls:0` | typography | 按钮完整文字样式 |
| `Body/Body 2` | `MiSans, Regular, 14px, 330, lh:100%, ls:0` | typography | 辅助说明文字 |
| `Pured/Pured_Extra_Thick_Light` | `#FFFFFF, #F5F5F5` | effect | 连接弹窗 Light 毛玻璃 |
| `Pured/Pured_Extra_Thick_Dark` | `#191919, #313131` | effect | 连接弹窗 Dark 毛玻璃 |
| `Pured/Pured_Regular_Glass_Light` | `#000000, #FFFFFF, #FFFFFF` | effect | 常规毛玻璃 |
| `Blur-L` | `70px` | blur | 大模糊半径 |
| `GlassShadow/GlassEffect_Regular_ShadowOff` | `INNER_SHADOW + GLASS(40)` | effect | 玻璃阴影效果 |

---

## 设计注释

> 1. 配对弹窗的容器圆角为 **46px**（非 Token 值），比 Dialog 弹窗的 36px 更大，这是该组件的特殊视觉标识。
> 2. **连接弹窗/Light** 作为毛玻璃包装层，使用多层 `mix-blend-mode`（soft-light + hard-light）实现 HyperOS Extra Thick Glass 效果，内部弹窗通过 Instance Swap 可替换。
> 3. **商业标签弹窗** 额外使用了 `backdrop-filter: blur(50px)` 和白色边框，标签区域包含品牌卖点信息（如"无损音质"、音频认证 logo 等），属于商业化增强样式。
> 4. **手柄弹窗** 的标题与内容区域 gap 为 **16px**（其他弹窗为 8px），以适应手柄设备图片的展示需求。
> 5. **安装类变体**（安装小米健康、安装米家）是唯一使用**强调蓝色按钮**的变体，其余所有变体均使用灰色基础按钮。
> 6. 连接完成态的**电池信息**使用绿色 `#36D167` 标识电量充足，电池图标为自定义绘制（border 1.66px + 圆角 4px），非标准 icon。
> 7. 弹窗高度固定为 **422px**，不随内容自适应，这保证了不同状态切换时弹窗大小保持一致，避免布局跳动。
> 8. 存在两个 `hidden` 变体：「非首次连接完成」（基础和商业标签各一个），可能用于已配对设备的快速重连场景。
