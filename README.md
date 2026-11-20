# 任务闭环与交接 · Task Closure & Handoff

一个可安装到 Codex 的通用技能：让多步骤与异步任务有明确终点、完成证据、接手责任和续接方式。

## 适用场景

- 文件导入、任务排队、生成并归档成果等跨系统流程。
- 判断“已提交”“处理中”“可使用”之间的区别。
- 交接时交代剩余事项、负责人和结束条件。
- 在材料显示缺失时先核对已有证据。

普通问答无需套用完整流程。技能不会增加后台运行能力，也不会扩展用户授权。

## 安装到 Codex

需要 Git。以下命令适用于 macOS / Linux；目标目录已存在时请先检查原版本，避免覆盖。

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
git clone https://github.com/Roaemary125-lab/task-closure-handoff.git "${CODEX_HOME:-$HOME/.codex}/skills/task-closure-handoff"
```

安装后重新开启 Codex 会话，让它发现新技能。配置允许按任务自动选择，但不保证每次对话都调用。

也可手动下载仓库，将包含 SKILL.md 和 agents 目录的文件夹放到上述 skills 目录下。

## 使用

显式调用示例：

> 使用 $task-closure-handoff 处理本次资料导入，核验完成条件，并交代剩余事项和接手责任。

方法包含四个动作：约定终点、核对证据、明确接手、交付回执。完整流程及验证场景见 [SKILL.md](SKILL.md)。

示例：上传已成功、平台仍在排队时，应报告“尚未完成”，说明谁查询后续状态；没有后台跟进能力时，提供可用的续接方式，不承诺自动回来。

## 验证状态

技能结构已通过 skill-creator 校验。跨场景行为仍待实际使用验证；不宣称已通过完整行为测试。

## 来源与许可

本仓库的方法来自实践复盘，概念参考 [Anthropic AI Fluency 课程](https://academy.claude.com/courses/ai-fluency-framework-foundations)中的 Delegation、Description、Discernment 和 Diligence。四项回执与异步续接流程为本仓库的实践归纳，不是 Anthropic 官方技能，也不代表官方认可。

本仓库原创内容按 [MIT License](LICENSE) 分发。外链课程及其他第三方内容不在此许可范围内；仓库不分发课程原文、视频或图表。
