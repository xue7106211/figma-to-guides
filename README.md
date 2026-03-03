# Figma to Guides

从 Figma 组件自动生成**面向 AI 消费的结构化组件规范文档**。

生成的文档数值精确、结构一致，所有属性值可直接映射到 CSS，供下游 AI Agent 读取并实现代码。

## 工作原理

```
Figma 组件链接 → Figma MCP 获取设计数据 → Agent 解析整合 → 结构化 Markdown 规范文档
```

核心流程：

1. **解析 URL** — 从 Figma 链接提取 `fileKey` 和 `nodeId`
2. **获取结构** — 通过 `get_metadata` 了解组件层级和变体维度
3. **获取设计数据** — 通过 `get_design_context` 提取完整的视觉属性（尺寸、布局、颜色、文字等）
4. **获取截图** — 通过 `get_screenshot` 获取组件预览图
5. **获取 Token** — 通过 `get_variable_defs` 建立 Token 与实际值的映射
6. **生成文档** — 按固定结构整合为 Markdown 规范文档

## 文档结构

生成的规范文档包含以下固定 section：

| Section | 内容 |
|---------|------|
| YAML Frontmatter | 组件元数据（名称、来源、变体数量等） |
| 预览 | 组件截图 |
| 组件结构 | ASCII 节点树 + 子节点清单 |
| 设计规范 | CSS 属性 / 值 / Token 三列表格 |
| 变体 | 维度定义 + 差异表（仅记录与基准不同的属性） |
| 交互状态 | 状态 → 样式变化的差异描述 |
| 组件 API | TypeScript Props 类型定义 |
| 使用指南 | 何时用 / 不用 / Do's & Don'ts |
| 设计 Token 映射 | Token 全量汇总 |
| 设计注释 | Figma 中的标注和备注 |

## 项目结构

```
figma-to-guides/
├── figma-component-spec-prompt.md   # Agent Prompt（核心规则定义）
└── component-spec/                  # 生成的组件规范文档
    └── slider-component-spec.md     # 示例：Slider 组件规范
```

## 使用方式

### 前置要求

- 配置好 [Figma MCP Server](https://github.com/nicepkg/figma-mcp)（提供 `get_metadata`、`get_design_context`、`get_screenshot`、`get_variable_defs` 等工具）
- 支持 MCP 调用的 AI Agent 环境（如 Cursor、Cline 等）

### 生成文档

1. 将 `figma-component-spec-prompt.md` 作为 Agent 的系统提示词加载
2. 提供 Figma 组件链接：

```
请为这个组件生成规范文档：https://figma.com/design/abc123xyz/DesignSystem?node-id=100-42
```

3. Agent 会自动调用 Figma MCP 获取数据并输出结构化文档
4. 将生成的文档保存到 `component-spec/` 目录

## 设计原则

- **CSS-ready** — 属性名使用标准 CSS 命名，值包含单位，可直接用于代码
- **Token 双轨** — 每个值同时标注原始值和 Token 名称，适配不同项目
- **差异驱动** — 变体和状态仅描述与基准的差异，减少冗余
- **固定结构** — heading 层级和名称不变，AI 可按 heading 定位任意 section

## License

MIT
