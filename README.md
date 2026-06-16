# 审稿skill

`审稿skill` 是一个面向科技论文同行评审的 Codex Skill，底层 skill 名称为 `scientific-manuscript-review`。它的目标不是简单总结论文，而是帮助研究者系统完成 SCI 论文审稿判断：识别核心科学问题、检查数据和方法可靠性、评估证据链是否支撑结论、区分 major concerns 与 minor comments，并生成可归档、可编辑的 Word 审稿报告。

## 默认最终交付

默认不只输出纯文本。除非用户明确要求 text-only，该 skill 的最终交付方式是：

1. 在对话中输出简要中文总结；
2. 生成完整 `.docx` Word 审稿报告；
3. Word 报告中包含中文思考版、英文审稿意见、SCI 系统可直接粘贴版本、Confidential Comments、核心结论-证据链表、审稿检查清单和作者需要补充的修改清单。

Word 文件默认命名：

```text
review_report_[short_title]_[yyyy-mm-dd].docx
```

如果无法识别短标题：

```text
review_report_manuscript_[yyyy-mm-dd].docx
```

如果是作者回复检查：

```text
response_assessment_[short_title]_[yyyy-mm-dd].docx
```

## Word 报告格式

- 页面大小：A4
- 页边距：上下左右 2.54 cm
- 中文字体：宋体
- 英文字体：Times New Roman
- 正文字号：12 pt / 小四
- 行距：1.5 倍
- 一级标题：加粗，14 pt
- 二级标题：加粗，12 pt
- 页眉：`Scientific Manuscript Review Report`
- 页脚：页码
- 表格：三线表或简洁网格表，自动换行，适应页面宽度
- 风格：正式、简洁、无花哨颜色，适合科研归档

Word 报告中必须包含独立章节：

```text
Section 4. Journal-ready Version
```

该章节只放英文审稿意见，供用户直接复制到 SCI 期刊审稿系统。不得混入中文分析、内部推理或非正式说明。

## 适用场景

- 审阅完整科技论文 PDF 或 Word 稿件
- 快速判断摘要、章节、图表或补充材料中的主要问题
- 生成中文思考版审稿分析和英文 reviewer comments
- 润色已有中文或英文审稿意见草稿
- 检查作者回复和修改稿是否真正解决审稿意见
- 输出 SCI 期刊系统可直接粘贴的 `Comments to the Authors` 和 `Confidential Comments to the Editor`

## 重点领域

该 skill 默认加强了地球物理和地震学方向的审稿逻辑，尤其适用于：

- 地球物理学与地震学论文
- 水库诱发地震
- 工程活动相关地震
- 构造地震与触发机制
- 地震目录分析
- 震源定位与双差重定位
- b 值分析
- 库仑应力计算
- 孔压扩散与孔弹性模拟
- 黏弹性或热-流-固耦合模拟
- 有限元数值模拟
- 地震危险性和风险推断

## 核心审稿逻辑

每次审稿时，skill 会围绕以下问题展开：

1. 论文的核心科学问题是什么？
2. 作者最重要的科学主张是什么？
3. 这些主张由哪些数据、方法和图件支撑？
4. 证据链中最薄弱的环节是什么？
5. 这些问题是否影响论文主要结论？
6. 作者需要补充哪些分析才能使结论可信？
7. 如果证据不足，哪些结论需要降级表达？
8. 论文更适合接收、小修、大修，还是拒稿？

## 输出模式

默认使用 **Mode 2: Full Review**。

| Mode | 用途 | 输出 |
| --- | --- | --- |
| Mode 1: Quick Review | 快速判断论文主要问题和推荐意见 | 简短中文总结 + Word 快速审稿报告 |
| Mode 2: Full Review | 完整审稿 | 简要中文对话总结 + 完整 Word 审稿报告 |
| Mode 3: English Review Only | 只要英文审稿意见 | Word 报告中的英文审稿部分 |
| Mode 4: Review Polishing | 润色已有审稿意见 | 润色后的 Word 审稿意见 |
| Mode 5: Response Assessment | 检查作者回复和修改稿 | Word 二审评估报告 |
| Mode 6: Journal-ready Format | 期刊系统直接粘贴 | 含独立 Section 4 的 Word 报告 |

## 安装方式

在 Codex 中可通过 skill installer 从 GitHub 安装：

```bash
python ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo GuangyaoYin/skill-scientific-manuscript-review \
  --path . \
  --name scientific-manuscript-review
```

安装后重启 Codex，使新 skill 被自动加载。

## 使用示例

```text
使用 scientific-manuscript-review，帮我审这篇论文，生成完整 Word 审稿报告。
```

```text
使用审稿skill，快速判断这篇摘要是否适合大修、拒稿还是小修，并生成 Word 报告。
```

```text
使用 scientific-manuscript-review，帮我检查作者回复是否充分解决上一轮 major comments，并输出 response assessment docx。
```

```text
使用审稿skill，把我写好的中文审稿意见润色成正式英文 reviewer comments，并整理成 Word 文档。
```

## 文件结构

```text
SKILL.md
README.md
agents/openai.yaml
references/
  review-checklist.md
  geophysics-seismology-checklist.md
  response-assessment.md
  output-templates.md
  word-output.md
```

## 注意事项

- 该 skill 不会代替审稿人的科学判断，而是帮助审稿人更系统地组织判断。
- 如果用户只提供摘要或部分章节，Word 报告会注明 `This review is based on the provided material rather than the full manuscript.`
- 不应虚构论文中没有的数据、图件、样本量、方法或参考文献。
- 缺失信息应标注 `Not provided`。
- 对诱发地震和工程活动相关地震论文，时间或空间相关性不能直接等同于因果关系。
- 当论文有价值但证据链不完整时，优先建议 major revision，而不是直接 reject。
