# 双语技术英语精读

`obsidian-build-bilingual-technical-english-notes` 是一个面向简体中文母语学习者的 Codex Skill，用于把英文技术文章、工程博客和技术文档整理成适合在 Obsidian 中长期学习的中英双语精读笔记。

它同时服务两个目标：

- **语言学习**：逐段解释生词、词组、词性、搭配和语境含义。
- **技术学习**：讲解架构、组件职责、执行流程、工程取舍和容易混淆的概念。

原始英文、文章结构和配图会被保留；中文学习内容放在默认折叠的 Obsidian Callout 中，因此收起注释后仍然是一篇干净、连续的英文文章。

## 功能

- 将公开英文技术文章导入 Obsidian。
- 保留标题、作者、发布时间、章节、列表、表格、代码和图片题注。
- 下载封面与正文配图，并改为 Obsidian 本地嵌入。
- 在每个有效学习单元后添加 `Vocabulary｜词汇` 注释。
- 使用简体中文解释学术词汇、工程搭配、专业术语和缩写。
- 在词汇注释后添加 `Technical Notes｜技术理解`。
- 解释技术机制、架构关系、数据流、信任边界和设计取舍。
- 将连续步骤或紧密相关的列表作为一个整体讲解，避免破坏原文格式。
- 在文章末尾生成词汇表、概念对照、组件职责、架构图和复习问题。
- 支持先处理前三段作为样例，确认风格后再扩展到全文。
- 在交付前检查图片、Callout 配对、Markdown、Mermaid 和 UTF-8 中文编码。

## 适合谁

- 母语为简体中文、希望通过真实材料学习技术英语的学生。
- 需要同时理解英文表达和计算机技术内容的开发者。
- 使用 Obsidian 整理英文工程博客、官方文档或论文阅读笔记的人。
- 希望保留原文，而不是只得到一份中文摘要或全文翻译的人。

## 生成效果

原始英文段落保持不变：

```markdown
AI agents often run as workloads performing tasks on behalf of a human.

> [!note]- Vocabulary｜词汇
> - **workload** *n.*：工作负载；在容器、Pod 或服务器中运行的应用实例。
> - **on behalf of**：代表……行动，强调委托关系。

> [!tip]- Technical Notes｜技术理解
> - 工作负载身份只能说明“哪段计算环境正在运行”，Agent 身份还需要说明“哪个 Agent 正代表谁执行任务”。
> - 因此，Agent 身份模型必须同时表达执行主体和原始委托来源。
```

在 Obsidian 阅读视图中，两个 Callout 默认折叠。需要学习时展开，不需要时收起即可连续阅读原文。

## 安装

### 方法一：让 Codex 安装

向支持 Skill 安装的 Codex 发送：

```text
请从 GitHub 仓库安装这个 Skill：
https://github.com/Skywardeyes/obsidian-build-bilingual-technical-english-notes
```

### 方法二：使用 Git 克隆

Windows PowerShell：

```powershell
git clone https://github.com/Skywardeyes/obsidian-build-bilingual-technical-english-notes.git `
  "$env:USERPROFILE\.codex\skills\obsidian-build-bilingual-technical-english-notes"
```

macOS 或 Linux：

```bash
git clone https://github.com/Skywardeyes/obsidian-build-bilingual-technical-english-notes.git \
  ~/.codex/skills/obsidian-build-bilingual-technical-english-notes
```

安装后重新启动 Codex，或开启一个新任务以刷新可用 Skill 列表。

## 使用方法

可以显式调用 Skill，也可以直接用自然语言描述需求。

### 从网页创建完整精读笔记

```text
使用 $obsidian-build-bilingual-technical-english-notes，
把这篇英文技术文章保存到我的 Obsidian，下载全部正文配图，
并添加双语词汇注释、技术讲解和文末复习汇总：
https://example.com/technical-article
```

### 为已有笔记添加学习层

```text
使用 $obsidian-build-bilingual-technical-english-notes，
为这篇 Obsidian 英文技术笔记添加逐段 Vocabulary 和 Technical Notes，
不要改动原始英文、标题、代码和图片。
```

### 先生成少量样例

```text
先为 Introduction 的前三个自然段制作双语精读示例，
其他段落暂时不要修改。
```

### 将确认后的样式扩展到全文

```text
沿用已经确认的注释样式，为全文其他技术段落添加注释，
并在文章末尾生成去重后的词汇和技术汇总。
```

## 工作流程

1. 提取网页正文和元数据，排除导航、广告及相关文章卡片。
2. 下载有意义的封面和正文图片，建立本地附件目录。
3. 生成保留完整英文结构的 Obsidian Markdown。
4. 按自然段或紧密相关的列表划分学习单元。
5. 添加默认折叠的词汇与技术 Callout。
6. 生成全文词汇表、概念对照、架构总结和复习问题。
7. 校验本地图片、嵌入链接、Callout、表格、代码块和 Mermaid。

## 文末汇总内容

Skill 会根据文章内容选择真正有帮助的汇总模块，而不是机械填充全部模板：

- 一句话技术主旨
- 核心架构 Mermaid 图
- 去重后的核心词汇表
- 易混概念对照表
- 组件职责表
- 分层模型或执行流程
- 性能指标解读与适用范围
- 5～10 道主动回忆问题
- 一条便于记忆的全文技术主线

## 仓库结构

```text
obsidian-build-bilingual-technical-english-notes/
├── SKILL.md
├── agents/
│   └── openai.yaml
├── references/
│   └── output-patterns.md
├── README.md
└── LICENSE
```

- [`SKILL.md`](SKILL.md)：触发条件、完整工作流和质量要求。
- [`agents/openai.yaml`](agents/openai.yaml)：Codex 界面名称、简介和默认提示词。
- [`references/output-patterns.md`](references/output-patterns.md)：按需读取的 Obsidian 输出模板。

## 设计原则

- **原文优先**：不擅自翻译、改写或压缩英文内容。
- **双层学习**：语言注释和技术解释分开呈现。
- **语境释义**：解释单词在当前技术文章中的真实含义，而不是堆砌字典释义。
- **格式稳定**：不因注释破坏列表、代码、表格、图片或段落顺序。
- **默认折叠**：收起注释后仍能顺畅阅读原文。
- **技术严谨**：区分事实、作者观点、未来规划和基于原文的推断。
- **可验证交付**：不在未检查时声称图片或链接有效。

## 注意事项

- 某些网站可能限制自动抓取，Skill 会尝试更换读取方式，但不会编造缺失内容。
- 图片和全文保存能力取决于当前 Codex 环境可用的网页与文件工具。
- Obsidian CLI 并非必需；在无法使用 CLI 时，可以直接写入 Vault 文件。
- 使用者应确认自己有权保存和使用文章全文及配图，并遵守原网站条款和版权要求。
- Skill 默认面向“英文原文 + 简体中文解释”；其他语言组合需要调整提示词和输出约定。

## 许可证

本项目采用 [GNU Affero General Public License v3.0](LICENSE) 许可证。
