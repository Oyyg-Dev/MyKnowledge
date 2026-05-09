---
type: hindsight
category: config
aliases: [环境自检, 记忆清理, cron清理, Hermes优化, 环境维护]
confidence: high
expires: 2027-05-09
contradicts: 
tags: [Hermes, 维护, 记忆, cron, 自检]
date: 2026-05-09
related: ["[[Hermes]]", "[[经验库]]"]
reinforced: 2026-05-09
reinforce_count: 1
---

## 📋 Task（任务）
定期自检 Hermes/Claude Code 使用环境，清理记忆噪音、过时cron、冗余文件

## 🔧 Action（行动）
1. 检查记忆：删除密码/重复/过时条目，合并冗余，从41%压缩到22%
2. 检查cron：确认4个定时任务是否还在用，暂停已完成任务的cron
3. 检查skills：94个内置skill无需手动清理，核心9个+常用4个
4. 清理文件：删6个过时config备份、清旧checkpoints、清错误日志
5. 升级Hermes：v0.12.0→v0.13.0，git stash+pull+pip install -e .
6. 修复hindsight搜索脚本：Lesson/Pitfall正则不支持无>前缀格式

## 📊 Outcome（结果）
✅ 记忆从41%降到22%，磁盘释放约100MB，Hermes升级到v0.13.0

## 💡 Lesson（教训，3句话以内）
密码和敏感信息不要存memory（每次会话加载不安全，放.env即可）。已完成的cron任务要及时关闭避免浪费token。config备份文件会自动堆积需定期清理。

## ⚠️ Pitfall（反模式：什么情况下这条经验不适用）
如果Hermes版本升级引入breaking change，git pull前应先看changelog。pip install -e .在依赖变更大时可能需要--force-reinstall。

## 🔗 关联经验
- 相关：[[config-Hermes记忆体系优化]]
