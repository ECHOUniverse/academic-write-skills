# 材料学学术写作助手

智能调度器，按需调用17个专业学术写作 skills。支持自然语言隐式调用和链式调用。

## 功能概览

| 功能 | 命令关键词 | 说明 |
|------|-----------|------|
| 中文→英文 | 翻译、中译英、translate | 中文翻译为英文学术论文 |
| 英文→中文 | 英译中、英转中 | 英文翻译为中文 |
| 中文润色 | 中文润色、润色中文 | 优化中文表达 |
| 英文润色 | 英文润色、润色英文、polish | 优化英文表达 |
| 英文缩写 | 缩写、精简、condense | 精简英文内容 |
| 英文扩写 | 扩写、扩展、expand | 丰富英文内容 |
| 中文扩写 | 中文扩写、中扩 | 丰富中文内容 |
| 去AI味 | 去AI、去ai、humanize | 去除机器翻译痕迹 |
| 逻辑检查 | 逻辑检查、logic | 检查论证逻辑 |
| 架构图 | 架构图、流程图、diagram | 设计论文架构图 |
| 绘图推荐 | 绘图、图表、plot | 推荐实验数据可视化方案 |
| 图标题 | 图标题、caption | 生成图表标题 |
| 表标题 | 表标题、table-caption | 生成表格标题 |
| 实验分析 | 分析、数据分析 | 分析实验数据 |
| 审稿审视 | 审稿、review | Reviewer视角审视 |

## 使用方法

### 基本用法

```bash
/academic-writing [功能指令]
[待处理的文本内容]
```

### 单功能调用示例

**翻译（中文→英文）：**
```bash
/academic-writing 翻译
我们制备了AlCoCrFeNi高熵合金...
```

**中文润色：**
```bash
/academic-writing 中文润色
本文研究了新型催化剂...
```

**去AI味：**
```bash
/academic-writing 去AI
为系统解析所制备催化剂的微观结构...
```

### 链式调用示例

支持使用多种分隔符：`,`, `，`, `、`, `→`, `->`

```bash
/academic-writing 翻译，润色，去AI
我们制备了AlCoCrFeNi高熵合金...
```

```bash
/academic-writing 扩写 → polish → humanize
The alloy shows good properties.
```

```bash
/academic-writing 中文扩写，中文润色
为系统解析所制备催化剂的微观结构...
```

### 显式模式调用

```bash
/academic-writing mode=zh-to-en,polish-en,humanize-en
[待处理的英文文本]
```

## 报告文件

每次调用（除 help 外）都会**自动生成报告文件**，保存在当前工作目录：

- **文件名格式**：`{YYYYMMDD}_{mode1-mode2-...-modeN}_report.md`
  - 例如：`20260317_zh-to-en-polish-en-humanize-en_report.md`
- **文件内容**：
  - 调用时间和执行链路
  - 每步的完整输出和修改说明
  - 最终结果汇总
- **文件已存在时**：自动覆盖

## 推荐链路

| 使用场景 | 推荐链路 |
|---------|---------|
| 中文→英文论文 | `翻译，润色，去AI` |
| 口语化中文→学术英文 | `中文学术化 → 翻译 → 润色` |
| 丰富并优化英文 | `扩写，润色` |
| 丰富并优化中文 | `中文扩写，中文润色` |
| 数据→分析段落 | `绘图，分析` |
| 投稿前审查 | `润色，逻辑检查，审稿` |

## 注意事项

1. **顺序重要**：内容生成 → 语言优化 → 最终检查
2. **避免冲突**：condense 和 expand 不要连续使用
3. **适度链路**：建议 3-5 步
4. **语言检测**：模糊指令会根据文本语言自动判断

## 子 Skill 列表

本调度器会自动调用以下子 skills：

- `zh-to-en-materials` - 中文→英文学术论文
- `en-to-zh-materials` - 英文→中文
- `zh-to-zh-materials` - 中文润色
- `condense-materials` - 英文缩写
- `expand-materials` - 英文扩写
- `expand-zh-materials` - 中文扩写
- `polish-en-materials` - 英文润色
- `polish-zh-materials` - 中文润色
- `logic-check-materials` - 逻辑检查
- `humanize-en-materials` - 英文去AI
- `humanize-zh-materials` - 中文去AI
- `architecture-diagram-materials` - 架构图设计
- `plot-recommendation-materials` - 绘图推荐
- `figure-caption-materials` - 图标题
- `table-caption-materials` - 表标题
- `experiment-analysis-materials` - 实验分析
- `reviewer-review-materials` - Reviewer审视

## 获取帮助

```bash
/academic-writing help
```

## 作者

材料学研究专用学术写作助手
