# 仓库说明

本仓库存放用户的个人技能与资料。

## 持仓资产

当用户询问股票、加密货币、基金或投资组合相关分析时，先读取仓库根目录的 `portfolio.md` 获取最新持仓清单（含 A 股 / 港股 / 加密货币 / 基金），将其作为分析的事实基础，而不是凭空假设。

若用户上传新的持仓导出文件或截图，调用 `cangwei` skill（见 `.claude/skills/cangwei/SKILL.md`）按既定流程更新 `portfolio.md` 并 push。

## 单标的深度投资分析

当用户要求"详细分析 / 深度研究 / 多智能体分析"某一只股票或加密货币、给出量化收益目标（如 10 倍 / 30% 年化）、或希望"结合持仓给出投资建议"时，调用 `shibei` skill（见 `.claude/skills/shibei/SKILL.md`）：并行启动 3 个子代理跑技术面 / 基本面+资金面 / 消息政策面，合成报告保存到 `research/` 目录，commit + push 后用 SendUserFile 发给用户。
