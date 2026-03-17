# 材料学研究写作 Skills 集合

本目录包含针对材料学研究（特别是高熵合金、催化剂等领域）优化的 Claude Skills，帮助研究人员提升论文写作效率和质量。

## 原项目说明

本 skills 集合改编自开源项目 [awesome-ai-research-writing](https://github.com/Leey21/awesome-ai-research-writing)，将原项目中针对计算机科学的写作 prompts 转换为 Claude Skills 格式，并适配到材料学研究领域。

## Skills 列表

### 语言转换类

| Skill 名称 | 调用命令 | 功能描述 |
|------------|----------|----------|
| **中转英** | `/zh-to-en-materials` | 将中文材料学草稿翻译并润色为英文学术论文片段 |
| **英转中** | `/en-to-zh-materials` | 将英文材料学论文翻译为流畅中文，清洗 LaTeX 格式 |
| **中转中** | `/zh-to-zh-materials` | 将口语化中文重写为学术规范中文 |

### 文本优化类

| Skill 名称 | 调用命令 | 功能描述 |
|------------|----------|----------|
| **缩写** | `/condense-materials` | 在保持信息完整前提下压缩文本长度 |
| **扩写** | `/expand-materials` | 通过深挖内容深度使英文文本更加饱满 |
| **中文扩写** | `/expand-zh-materials` | 通过深挖内容深度使中文文本更加饱满 |
| **英文润色** | `/polish-en-materials` | 深度润色英文论文，提升学术严谨性 |
| **中文润色** | `/polish-zh-materials` | 专业审视中文论文，修复语病与逻辑漏洞 |
| **逻辑检查** | `/logic-check-materials` | 进行一致性检查与逻辑核对 |

### 风格优化类

| Skill 名称 | 调用命令 | 功能描述 |
|------------|----------|----------|
| **去AI味（英文）** | `/humanize-en-materials` | 将机械化文本重写为自然学术表达 |
| **去AI味（中文）** | `/humanize-zh-materials` | 去除中文文本的机器味和翻译腔 |

### 图表相关类

| Skill 名称 | 调用命令 | 功能描述 |
|------------|----------|----------|
| **论文架构图** | `/architecture-diagram-materials` | 设计材料学论文的专业架构图 |
| **实验绘图推荐** | `/plot-recommendation-materials` | 基于数据推荐最佳可视化方案 |
| **生成图标题** | `/figure-caption-materials` | 将中文描述转化为规范英文图标题 |
| **生成表标题** | `/table-caption-materials` | 将中文描述转化为规范英文表标题 |

### 分析审查类

| Skill 名称 | 调用命令 | 功能描述 |
|------------|----------|----------|
| **实验分析** | `/experiment-analysis-materials` | 从实验数据中挖掘关键特征并撰写分析段落 |
| **Reviewer审视** | `/reviewer-review-materials` | 以审稿人视角审视论文，发现潜在问题 |

## 使用方法

### 方式一：使用整合式学术写作助手（推荐）

我们提供了一个整合式的 `academic-writing-materials` skill，支持**自然语言隐式调用**和**链式调用**：

### 自然语言调用（推荐）

使用中文或英文关键词直接调用，系统自动识别功能：

```
/academic-writing 翻译
我们制备了AlCoCrFeNi高熵合金...
```

```
/academic-writing 润色
The alloy was made by arc melting...
```

```
/academic-writing 中文学术化
我们做了个合金，强度挺高的...
```

### 链式调用

用逗号、空格、箭头等分隔多个功能，依次执行：

```
/academic-writing 翻译，润色，去AI
我们制备了AlCoCrFeNi高熵合金...
```

```
/academic-writing 扩写 → polish → humanize
The alloy shows good properties.
```

```
/academic-writing 绘图 分析 润色
[实验数据...]
```

**常用链式组合：**
| 链路 | 适用场景 |
|------|---------|
| `翻译，润色，去AI` | 中文草稿→英文论文完整流程 |
| `中文学术化 → 翻译 → 润色` | 口语化中文→学术英文 |
| `缩写，润色` 或 `扩写，润色` | 调整文本长度并润色 |
| `中文扩写，中文润色` | 丰富中文内容并优化 |
| `绘图，分析，润色` | 实验数据→分析段落 |
| `润色，逻辑检查，审稿` | 投稿前全面审查 |

### 显式 mode 调用（传统方式）

也支持传统的 `mode=` 格式：

```
/academic-writing mode=zh-to-en
[文本内容]
```

```
/academic-writing mode=zh-to-en,polish-en,humanize-en
[文本内容]
```

### Help 功能

```
/academic-writing help
```

查看所有可用功能、自然语言关键词和详细使用说明

### 支持的自然语言关键词

| 功能类别 | 支持的关键词 |
|---------|-------------|
| **翻译** | 翻译、译、translate、中转英、中译英、英转中、英译中 |
| **缩写/扩写** | 缩写、精简、缩短、condense、扩写、扩展、expand |
| **润色** | 润色、polish、英文润色（英文输入）、中文润色（中文输入）|
| **去AI** | 去AI、去ai、去AI味、humanize |
| **逻辑检查** | 逻辑检查、检查逻辑、logic-check |
| **图表** | 架构图、流程图、diagram、绘图、plot、图标题、表标题 |
| **分析** | 分析、数据分析、analysis、审稿、review |

**优势：**
- 只需加载一个 skill，节省资源
- 统一入口 `/academic-writing`，记忆负担小
- 支持自然语言调用，无需记忆mode名称
- 智能语言检测，自动选择中英文功能
- 支持链式调用，一次完成完整工作流程
- 自动保存 Markdown 报告，便于查阅和存档
- 内置 help 功能，随时查看用法

### 自动保存报告

每次链式调用完成后，系统会自动在当前目录生成 Markdown 格式的报告文件：

- **文件名格式**：`{YYYYMMDD}_{mode1-mode2-...-modeN}_report.md`
  - 例如：`20260317_zh-to-en-polish-en-humanize-en_report.md`
- **文件内容**：包含每步输出、最终结果和执行链路总结
- **保存位置**：当前工作目录

### 方式二：使用独立 Skills

如果你需要单独使用某个功能，也可以使用独立的 skill：

1. 将本 skills 目录复制到你的项目 `.claude/skills/` 目录下
2. 在对话中直接使用 `/` + skill 名称调用
3. 例如：`/zh-to-en-materials` 然后粘贴你的中文草稿

### 直接复制 Prompt 使用

每个 skill 目录下的 `SKILL.md` 文件包含了完整的系统提示（system prompt），你可以直接复制其中的内容到 ChatGPT、Claude 等其他 AI 工具中使用。

## 材料学领域适配说明

与原项目相比，本 skills 集合做了以下材料学领域适配：

1. **期刊标准**：将 NeurIPS/ICML/CVPR 等计算机会议替换为 Acta Materialia/Nature Materials/Advanced Materials 等材料学期刊

2. **专业术语**：添加了材料学常用术语对照表：
   - 高熵合金 (HEA)、催化剂 (Catalyst)
   - XRD、SEM、TEM、EDS 等表征手段
   - FCC、BCC 等晶体结构
   - 屈服强度、延伸率、硬度等力学性能指标

3. **图表类型**：针对材料学数据特点优化了图表推荐：
   - XRD 谱图、应力-应变曲线
   - 相图、极图、反极图
   - 晶粒尺寸分布、元素分布图

4. **分析框架**：增加了材料学特有的分析维度：
   - 成分-结构-性能关联
   - 强化机制分析（固溶强化、细晶强化等）
   - 相变与微观组织演化

## 目录结构

```
skills/
├── README.md                          # 本文件
├── academic-writing-materials/        # 【推荐】整合式学术写作助手
│   └── SKILL.md                       # 包含全部17种功能的统一入口
├── zh-to-en/SKILL.md                  # 中转英（独立版）
├── en-to-zh/SKILL.md                  # 英转中（独立版）
├── zh-to-zh/SKILL.md                  # 中转中（独立版）
├── condense/SKILL.md                  # 缩写（独立版）
├── expand-zh/SKILL.md                 # 中文扩写（独立版）
├── expand/SKILL.md                    # 扩写（独立版）
├── polish-en/SKILL.md                 # 英文润色（独立版）
├── polish-zh/SKILL.md                 # 中文润色（独立版）
├── logic-check/SKILL.md               # 逻辑检查（独立版）
├── humanize-en/SKILL.md               # 去AI味（英文独立版）
├── humanize-zh/SKILL.md               # 去AI味（中文独立版）
├── architecture-diagram/SKILL.md      # 论文架构图（独立版）
├── plot-recommendation/SKILL.md       # 实验绘图推荐（独立版）
├── figure-caption/SKILL.md            # 生成图标题（独立版）
├── table-caption/SKILL.md             # 生成表标题（独立版）
├── experiment-analysis/SKILL.md       # 实验分析（独立版）
└── reviewer-review/SKILL.md           # Reviewer审视（独立版）
```

**说明**：
- `academic-writing-materials/` 是**整合式skill**，包含全部17种功能，通过 `mode` 参数切换，推荐使用
- 其他17个目录是**独立skill**，适合只需要特定功能的场景

## 注意事项

1. **按需调用**：不同 skill 针对不同场景，请根据实际需要选择合适的 skill
2. **分段处理**：对于长文本，建议分段使用 skills 处理，以获得更好的效果
3. **人工审核**：AI 辅助写作仅供参考，最终投稿前请务必人工审核
4. **数据保密**：处理未发表论文时，请注意数据保密，避免上传到公共平台

## 贡献与反馈

本 skills 集合基于开源项目进行材料学领域适配。如有改进建议或发现错误，欢迎反馈。

## 许可

与原项目保持一致。
