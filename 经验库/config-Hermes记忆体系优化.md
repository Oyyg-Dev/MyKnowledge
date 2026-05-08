---
type: hindsight
category: config
aliases: [记忆优化, memory压缩, memory满, Hermes记忆体系]
confidence: high
expires: 2027-05-08
contradicts: 
tags: [Hermes, 记忆体系, memory, skill]
date: 2026-05-08
related: ["[[Hermes]]", "[[知识库]]"]
reinforced: 2026-05-08
reinforce_count: 1
---

## 📋 Task（任务）
优化 Hermes Agent 记忆体系，解决 memory 满载（98%）和信息跨模型丢失问题

## 🔧 Action（行动）
1. 压缩 memory 条目，合并重复和冗余信息（22条→7条）
2. 设计5层记忆架构：Memory(索引) → HERMES.md(详情) → 知识库(数据) → Skills(流程) → Session Search(回溯)
3. 新建 aguang-knowledge-base + schedule-reminder skills
4. 更新3个定时任务加入排班判断逻辑
5. 修正 MS 项目 Vue2→Vue3 技术栈信息
6. 精简 user profile（75%→35%）

## 📊 Outcome（结果）
✅ 成功：Memory 从 98% 降至 25%，User Profile 从 75% 降至 35%

## 💡 Lesson（教训，3句话以内）
Memory 做轻量索引（指针），详细配置放 HERMES.md，原始数据放知识库文件。排班等易变信息必须同时写入 memory + 文件两处同步。Skill 是程序化记忆的最佳载体，比 memory 更适合存工作流。

## ⚠️ Pitfall（反模式：什么情况下这条经验不适用）
纯键值存储场景（如 Redis 缓存）不需要分层，直接存取更高效。memory 3,300字符限制是硬约束，大段内容必须外置。

## 🔗 关联经验
- 相关：[[Hermes]]
