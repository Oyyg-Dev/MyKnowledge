---
type: hindsight
category: config
aliases: [tool-tips, cute-claude-hooks, 中文提示hook, 工具翻译]
confidence: medium
expires: 2027-05-08
contradicts: 
tags: [Claude Code, hook, 精简]
date: 2026-05-08
related: ["[[Claude Code]]"]
reinforced: 2026-05-08
reinforce_count: 1
---

## 📋 Task（任务）
评估并清理 Claude Code 的 tool-tips-post.sh hook

## 🔧 Action（行动）
1. 审查了 ~/.claude/hooks/tool-tips-post.sh（387行）
2. 确认功能：给每次工具操作加中文解释提示（🌸 风格）
3. 判断对独立开发者价值不大，且增加延迟

## 📊 Outcome（结果）
⚠️ 待删除，已创建明日待办任务

## 💡 Lesson（教训，3句话以内）
Hook 每次工具执行都会运行，体积越大延迟越高。非必要的装饰性 hook 应及时清理。适合新手的翻译提示对有经验的开发者是噪音。

## ⚠️ Pitfall（反模式：什么情况下这条经验不适用）
团队中有非技术人员需要理解操作时，中文提示有价值。
