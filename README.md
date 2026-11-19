# KIWI · Skill 与提示词共创教练

把重复工作变成可验证的 Agent Skill。KIWI 面向希望把团队惯例或业务判断固化到 AI 工作流里的使用者。

KIWI helps turn recurring work into testable Agent Skills. This first release targets Codex and includes a Chinese walkthrough.

## 在 Codex 中使用

需要 Codex 和可用的 `skill-creator`。以下命令把 KIWI 安装到当前工作目录下的项目级 Skills 目录。在要使用 KIWI 的项目根目录执行。首次安装使用空的目标目录。

```sh
git clone https://github.com/felixfeng1202-cyber/kiwi-prompt-coach.git
mkdir -p .agents/skills
cp -R kiwi-prompt-coach/skills/kiwi-prompt-coach .agents/skills/
```

在该项目中打开 Codex，输入 `$kiwi-prompt-coach` 后描述任务。刚安装的 Skill 如果没有出现在选单里，重新打开 Codex。可以先确认同一环境可以调用 `$skill-creator`，它负责 Skill 的文件结构、实现和技术校验。

## 试一个例子

> $kiwi-prompt-coach 我每周会收到四个项目的 Markdown 更新。请在当前项目创建一个 Skill，把更新合并成周报。每个项目保留最新进展、风险和下周动作。输入缺少负责人或日期时，标为待确认。只生成草稿，由我审核和发送。请用虚构数据试跑。

这个虚构需求演示了三个可以验收的环节。

1. **定义触发与边界**。收到跨项目周报汇总请求时使用该 Skill。单独润色一份周报属于另一类任务。
2. **生成可用的 Skill**。把输入、输出、合并规则、缺项处理和交付权限写成可重复执行的规则。
3. **验证并交接**。试跑包含缺项的样例，查看输出是否保留了四个项目、明确标出待确认项，并提供人工核验卡和验证结果。

已有 Skill 也可以交给 KIWI 迭代。明确只需要一次性提示词时，可以使用 Prompt 模式。

[查看 Skill 源码](skills/kiwi-prompt-coach/SKILL.md) · [MIT 许可证](LICENSE)
