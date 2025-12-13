# 🚀 AI 工作流编排平台


**可前端独立运行、可视化、可拖拽的 AI 多模态工作流编排平台**

---

## 📖 简介

AI 工作流编排平台是一个类似 n8n 的轻量化可视化工作流工具，完全运行在浏览器端，无需后端服务器。支持 AI 对话、文本生成、图像生成、文件处理、数据分析等多种节点类型，通过拖拽连线即可构建复杂的自动化工作流。

### 🎯 适用场景

- 🤖 **AI 应用开发** - 快速构建 AI 对话、文本生成、图像处理流程
- 📊 **数据处理** - 数据提取、转换、分析的可视化编排
- 🔄 **自动化任务** - 定时触发、条件分支、循环处理
- 📝 **文档处理** - 文本摘要、内容生成、格式转换
- 🎵 **多媒体处理** - 音频转录、语音合成、媒体录制

---

## ✨ 功能特性

### 节点类型

| 类别 | 节点 | 描述 |
|------|------|------|
| **AI 节点** | AI 对话、文本生成、文本分析、图像生成、图像编辑、音频转录、文本转语音 | 接入 OpenAI 兼容 API |
| **文件节点** | 文件输入、文件输出、文本输入、可选输入 | 文件读写与用户输入 |
| **控制节点** | 条件判断、循环、延时 | 流程控制逻辑 |
| **触发器** | 定时触发、消息触发、阈值触发、事件触发 | 工作流触发机制 |
| **工具节点** | HTTP 请求、JSON 解析、文本转换、文本分割 | 数据处理工具 |
| **交互节点** | AI 对话窗口、代码编辑器、网页浏览器、数据分析、文档编辑器、多媒体录制 | 交互式操作 |
| **代码节点** | JavaScript 代码、Python 代码 | 自定义代码执行 |
| **服务节点** | MCP 客户端、REST API、Webhook、MQTT、Modbus | 外部服务集成 |

### 核心功能

- 🎨 **可视化编辑** - 拖拽节点、连线编排、实时预览
- 💾 **工作流管理** - 保存、加载、导入、导出工作流
- 📦 **模板系统** - 内置预设模板，快速开始
- 🔗 **变量系统** - 全局变量、节点映射、模板语法
- ⚡ **实时执行** - 执行状态监控、日志输出
- 🔧 **高度可配置** - API 配置、模型选择、参数调整
- 📱 **响应式设计** - 适配桌面和平板设备
- 🔒 **本地运行** - 无需服务器，数据安全

---

## 🚀 快速开始

### 方式一：直接使用

1. 下载或克隆本仓库
```bash
git clone https://github.com/your-username/ai-workflow-platform.git
cd ai-workflow-platform
```

2. 用浏览器直接打开 `index.html`

3. 点击右上角 **设置** 按钮，配置 API：
   - API 地址（如 `https://api.openai.com/v1`）
   - API Key
   - 选择模型

4. 从左侧节点库拖拽节点到工作区

5. 点击 **执行** 按钮运行工作流



### 方式二：本地服务器

```bash
# 使用 Python
python -m http.server 8080

# 或使用 Node.js
npx serve .

# 访问 http://localhost:8080
```

---

## ⌨️ 快捷键

| 快捷键 | 功能 |
|--------|------|
| `F5` | 执行工作流 |
| `F9` | 验证工作流 |
| `Ctrl + S` | 保存工作流 |
| `Ctrl + O` | 加载工作流 |
| `Ctrl + E` | 导出工作流 |
| `Ctrl + ,` | 打开设置 |
| `Delete` | 删除选中节点 |
| `Ctrl + C` | 复制节点 |
| `Ctrl + V` | 粘贴节点 |
| `Ctrl + Shift + D` | 调试模式 |

---

## 📁 项目结构

```
ai-workflow-platform/
├── index.html              # 主入口页面
├── styles.css              # 全局样式
├── css/                    # 模块样式
│   ├── document-editor.css
│   ├── media-recorder.css
│   └── new-modules.css
├── js/                     # JavaScript 模块
│   ├── config.js           # 配置中心
│   ├── utils.js            # 工具函数
│   ├── nodes.js            # 节点模型
│   ├── workflow.js         # 工作流管理
│   ├── execution.js        # 执行引擎
│   ├── ui.js               # UI 交互
│   ├── main.js             # 应用入口
│   ├── agents/             # 智能体模块
│   ├── api/                # API 管理
│   ├── communication/      # 通信模块
│   ├── interaction/        # 交互节点
│   ├── media/              # 媒体处理
│   ├── triggers/           # 触发器引擎
│   └── ...
├── app/                    # 子应用
│   ├── dataextractor.html  # 数据分析系统
│   └── graphanalyzer.html  # 网络可视化分析
├── dist/                   # 混淆后的生产版本
└── docs/                   # 文档
```

---

## 🔧 配置说明

### API 配置

点击设置按钮，配置以下内容：

```json
{
  "apiBaseUrl": "https://api.openai.com/v1",
  "apiKey": "your-api-key",
  "model": "gpt-4",
  "temperature": 0.7,
  "maxTokens": 2000
}
```

支持的 API 服务：
- OpenAI API
- Azure OpenAI
- 其他 OpenAI 兼容 API（如本地部署的 LLM）

### 变量系统

使用双大括号语法引用变量：

```
Hello, {{username}}!
上一步结果：{{previousNode.output}}
```

---

## 🎮 使用示例

### 示例 1：AI 文本生成

1. 拖入 **文本输入** 节点，输入主题
2. 拖入 **文本生成** 节点
3. 连接两个节点
4. 点击执行

### 示例 2：条件分支

1. 拖入 **AI 文本分析** 节点
2. 拖入 **条件判断** 节点
3. 根据分析结果分支处理

### 示例 3：定时任务

1. 拖入 **定时触发** 节点，设置 Cron 表达式
2. 连接后续处理节点
3. 点击执行启动监听

---

## 🛠️ 开发

## 架构总览

- **渲染与画布**: `index.html` + `styles.css` 提供布局；`workflow.js` 负责节点 DOM、连线 SVG、属性面板。
- **节点模型**: `nodes.js` 定义 `WorkflowNode`，统一管理 ID/状态/输入输出/配置/执行与结果展示。
- **执行引擎**: `execution.js` 自起始节点拓展执行，深度优先、按依赖推进，内置循环检测/验证/执行计划。
- **变量系统**: `variable-manager.js` 管理全局变量与节点输入/输出映射，支持模板 `{{var}}`、解析与弹窗审核。
- **弹窗系统**: `popup-manager.js` 管理输入/输出/即时输入弹窗、倒计时与去重防抖。
- **配置中心**: `config.js` 负责 API 配置与预设工作流模板。
- **交互层**: `ui.js` 绑定工具栏/快捷键/拖拽/文件拖拽与模态。
- **应用壳**: `main.js` 负责初始化、兼容性检测、自动加载、调试模式与全局对象。

### 全局对象（给 IDE/脚本使用）

- `window.workflowManager`（WorkflowManager）
- `window.workflowExecutor`（WorkflowExecutor）
- `window.variableManager`（VariableManager）
- `window.appConfig`（Config）
- `window.uiManager`（UIManager）
- `window.aiWorkflowApp`（AIWorkflowApp）
- `window.AI_WORKFLOW`（聚合访问器：`{ app, config, workflow, executor, ui, utils }`）

## 运行机理（从拖拽到执行）

1) 用户拖拽节点 → `WorkflowManager.createNode(type)` 创建 `WorkflowNode`，自动渲染 DOM、连接点、默认配置与状态。
2) 连线 → `WorkflowManager.createConnection(fromNodeId, outputName, toNodeId, inputName)` 建立连接、绘制贝塞尔曲线，并自动更新“变量输入映射”。
3) 配置 → 属性面板由 `WorkflowManager.updatePropertyPanel()` 生成，根据节点类型渲染对应配置表单与“变量映射”区域。
4) 执行 → `WorkflowExecutor.executeWorkflow()` 自无入边节点开始递归执行：
   - 通过 `VariableManager.resolveNodeInputs(nodeId, node)` 解析输入（变量映射 > 连接值 > 默认值），期间按变量弹窗配置触发输入弹窗。
   - `WorkflowNode.execute()` 调度到不同 `process*` 方法；输出由 `VariableManager.saveNodeOutputs` 保存至全局变量（可触发输出审核弹窗）。
   - 执行日志（右下角“执行状态”）由 `WorkflowExecutor.addExecutionLog` 推送。

## 模块与主要接口

### 1) 配置中心：`js/config.js`

- `window.appConfig.getConfig()` / `updateConfig(config)` / `saveConfig(config)` / `reset()`
- `validateConfig(config?)`: 尝试 POST 测试请求校验 API 可用性
- 预设工作流：`getPresetWorkflows()` / `getPresetWorkflow(id)`

注意：源码中的默认配置包含示例 API 地址与模型。严禁在文档或代码中保留真实 Key（详见“安全与不合理项”）。

### 2) 节点模型：`js/nodes.js`（WorkflowNode）

- 标识：`id = WS{workspaceId}_{Type}{序号}`（导入时保留原 `id`）
- 结构：`type` `x` `y` `config` `inputs` `outputs` `connections(inputs: Map, outputs: Map)`
- 渲染：`createNodeElement()` 生成 DOM、连接点；`updateContent()` 更新内容；`showExecutionResult()` 展示执行 I/O
- 执行：`execute()` → `processNode()` → 具体 `processAIChat/processAITextGeneration/...`
- 输入解析：`getInputValue(name)`（先已解析输入→再连线→最后默认）
- 模板：`processTemplateString('Hello {{username}}')` 使用全局变量与节点上下文替换

主要节点类型与 I/O：

- AI 类：`ai-chat(prompt → response)` / `ai-text-generation(topic → text)` / `ai-text-analysis(text → analysis)`
- 文件：`file-input(→ content, filename)` / `file-output(content →)` / `text-input(input? → text)` / `optional-input(→ text)`
- 控制：`condition(input → true/false)` / `loop(input → output)` / `delay(input → output)`
- 工具：`http-request(url,data → response)` / `json-parser(json → data)` / `text-transform(text → transformed)` / `text-splitter(text → chunks)`

### 3) 工作流管理：`js/workflow.js`（WorkflowManager）

- 画布与交互：选择/复制/粘贴/删除节点，创建/删除/更新连线
- 属性面板：`updatePropertyPanel()` 动态渲染表单与“变量映射”区
- 自动变量映射：为节点输出自动创建同名全局变量；在连线时为目标输入自动映射上游变量
- 导入导出：
  - `exportWorkflow()` → 生成 `{ nodes, connections, metadata }`
  - `importWorkflow(file)` → 从 JSON 恢复
  - `save()` / `load()` → 本地存储往返
  - `loadPresetWorkflow(presetId)` → 根据模板索引重建节点与连线
- 其它：`createNode` `createConnection` `drawConnection` `updateConnections` `clear` 等

### 4) 执行引擎：`js/execution.js`（WorkflowExecutor）

- `executeWorkflow()`：串并行结合的递归执行；起点为“无输入连线”的节点
- `stopExecution()`：终止并重置节点状态
- 验证与计划：`validateWorkflow()` / `detectCycles()` / `getExecutionOrder()` / `simulateExecution()` / 执行计划打印
- 历史：内存中保留最多 50 条；最近 10 条写入本地存储
- UI：右下角“执行状态”面板日志（info/success/error/warning/running）

### 5) 变量系统：`js/variable-manager.js`（VariableManager）

- 全局变量：`createGlobalVariable(name, type, value, description, popupConfig)` / `updateGlobalVariable` / `deleteGlobalVariable` / `getAllGlobalVariables`
- 节点映射：`configureNodeVariables(nodeId, inputMappings, outputMappings)` / `setNodeInputVariable` / `setNodeOutputVariable`
- 输入解析：`resolveNodeInputs(nodeId, node)`（优先变量映射，其次连线，最后默认；可触发“输入弹窗”）
- 输出保存：`saveNodeOutputs(nodeId, outputs)`（可触发“输出审核弹窗”；支持解析配置，例如分隔符/字段/正则/序列）
- 模板：`resolveTemplate('Hi {{user.name}}')`
- 导入导出与持久化：`exportVariables()` / `importVariables(data)` / 本地存储自动保存与恢复

变量结构：

```json
{
  "name": "变量名",
  "type": "string|number|boolean|object|array",
  "value": "任意",
  "description": "说明",
  "popupConfig": { "inputPopup": false, "outputPopup": false, "timeout": 20000 }
}
```

### 6) 弹窗系统：`js/popup-manager.js`（PopupManager）

- 输入弹窗：`showVariableInputPopup(nodeId, variableName, currentValue, timeout)`
- 输出弹窗：`showVariableOutputPopup(nodeId, variableName, currentValue, timeout)`
- 即时输入：`showImmediateInputPopup(nodeId, inputName, defaultValue, isOptional, timeout)`
- 公共：倒计时、折叠/关闭、强制清理与防重复

### 7) 应用壳：`js/main.js`（AIWorkflowApp）

- 生命周期：`initialize()` → 兼容性检测 → 读取配置 → 初始化各组件 → 绑定事件 → 初始化 UI → 自动加载/恢复
- 辅助：欢迎/引导、调试面板（内存/节点/连接/执行历史）、导入导出“应用数据”
- 全局：`window.AI_WORKFLOW` 统一聚合访问
```

---
---

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

1. Fork 本仓库
2. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送分支 (`git push origin feature/AmazingFeature`)
5. 提交 Pull Request

---



Made by AI Workflow Team

