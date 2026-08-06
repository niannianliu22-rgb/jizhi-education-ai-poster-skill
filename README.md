# 极致教育 AI 海报生成 Skill

面向以下三个品牌的教育海报生成规范：

- 极致 Essay
- DP / Distinction Pass
- 极致 AI 留学生陪跑

Skill 会在生成海报前完成需求解析、产品事实核验、品牌隔离、文案与视觉规划、素材约束和 QA。仓库内包含三个品牌的原始 Logo、已确认归属的 IP 素材，以及 Essay 与 DP 的成功海报视觉参考。仓库默认不包含新客户截图、一次性案例证据、生成海报或一次性案例脚本。

## 安装

将仓库克隆到 Codex Skills 目录：

```bash
git clone <repository-url> ~/.codex/skills/jizhi-education-ai-poster
```

如果已克隆到其他位置，也可以复制整个仓库目录到：

```text
~/.codex/skills/jizhi-education-ai-poster
```

## 使用

在 Codex 中直接描述品牌、产品、海报类型和使用目标，例如：

```text
使用 $jizhi-education-ai-poster，为 DP 做一张产品介绍海报。
```

完整操作方法、提示词模板和常见问题见 [使用说明.md](使用说明.md)。

## 核心约束

- 所有品牌、所有海报默认不添加 CTA。
- DP 与极致 AI 留学生陪跑的 IP 胸标必须严格隔离，不得混用。
- Logo 只能使用用户提供的原始品牌文件。
- 成功海报只用于学习版式、层级、密度和视觉语言，不作为产品事实、价格、承诺或 CTA 来源。
- 案例证据图片只能原图排版，不得重绘、改字、美化或重新生成。
- 案例海报尺寸由内容量决定，不默认制作成长图。
- 不捏造产品、价格、承诺、成绩、截图或客户反馈。
