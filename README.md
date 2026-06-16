# 审稿skill

`审稿skill` 是一个面向科技论文同行评审的 Codex Skill，底层 skill 名称为 `scientific-manuscript-review`。它的目标不是简单总结论文，而是帮助研究者系统完成 SCI 论文审稿判断：识别核心科学问题、检查数据和方法可靠性、评估证据链是否支撑结论、区分 major concerns 与 minor comments，并生成可直接粘贴到期刊审稿系统的英文审稿意见。

## 适用场景

这个 skill 特别适合以下任务：

- 审阅完整科技论文 PDF 或 Word 稿件。
- 快速判断摘要、章节、图表或补充材料中的主要问题。
- 生成中文思考版审稿分析和英文 reviewer comments。
- 润色已有中文或英文审稿意见草稿。
- 检查作者回复和修改稿是否真正解决审稿意见。
- 输出 SCI 期刊系统可直接粘贴的 `Comments to the Authors` 和 `Confidential Comments to the Editor`。

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
| Mode 1: Quick Review | 快速判断论文主要问题和推荐意见 | 简短中文分析和核心评论 |
| Mode 2: Full Review | 完整审稿 | 中文思考版、英文审稿意见、期刊系统版 |
| Mode 3: English Review Only | 只要英文审稿意见 | Formal SCI reviewer comments |
| Mode 4: Review Polishing | 润色已有审稿意见 | 更正式、清晰、建设性的版本 |
| Mode 5: Response Assessment | 检查作者回复和修改稿 | 回复评估表和二审推荐意见 |
| Mode 6: Journal-ready Format | 期刊系统直接粘贴 | Comments to Authors + Confidential Comments |

## 默认输出结构

默认完整审稿会输出：

### A. 中文思考版

- 论文一句话总结
- 主要贡献
- 主要优点
- 核心问题
- Major concerns
- Minor comments
- 推荐意见
- 建议作者补充的分析
- 需要降级表达的结论

### B. English Reviewer Comments

- Summary
- General Assessment
- Major Comments
- Minor Comments
- Recommendation

### C. Journal-ready Version

- Comments to the Authors
- Confidential Comments to the Editor

### D. Optional Short Version

用于有字数限制的期刊系统。

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
使用 scientific-manuscript-review，帮我审这篇论文，输出中文思考版和 SCI 系统可粘贴的英文审稿意见。
```

```text
使用审稿skill，快速判断这篇摘要是否适合大修、拒稿还是小修，并给出主要理由。
```

```text
使用 scientific-manuscript-review，帮我检查作者回复是否充分解决上一轮 major comments。
```

```text
使用审稿skill，把我写好的中文审稿意见润色成正式英文 reviewer comments。
```

## 文件结构

```text
SKILL.md
agents/openai.yaml
references/
  review-checklist.md
  geophysics-seismology-checklist.md
  response-assessment.md
  output-templates.md
```

## 注意事项

- 该 skill 不会代替审稿人的科学判断，而是帮助审稿人更系统地组织判断。
- 如果用户只提供摘要或部分章节，输出会标注 `based on the provided material`。
- 不应虚构论文中没有的数据、图件、样本量、方法或参考文献。
- 对诱发地震和工程活动相关地震论文，时间或空间相关性不能直接等同于因果关系。
- 当论文有价值但证据链不完整时，优先建议 major revision，而不是直接 reject。
