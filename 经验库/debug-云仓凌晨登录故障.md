---
type: hindsight
category: debug
aliases: [凌晨登录, JWT过期, token验证失败, 云仓登录故障, token过期]
confidence: high
expires: 2027-05-08
contradicts: 
tags: [云仓, 登录, JWT, 排查, 时间同步]
date: 2026-05-08
related: ["[[云仓]]", "[[JWT]]"]
reinforced: 2026-05-08
reinforce_count: 1
---

## 📋 Task（任务）
排查云仓凌晨3点登录故障

## 🔧 Action（行动）
1. 检查 Nginx 日志发现 token 过期
2. 检查后端日志发现 JWT 签名验证失败
3. 发现系统时间偏差导致 token 提前过期
4. 修复 NTP 时间同步

## 📊 Outcome（结果）
✅ 成功定位并修复

## 💡 Lesson（教训，3句话以内）
JWT token 验证问题优先检查服务器系统时间同步。凌晨故障排查先看日志时间戳是否异常（跳变/回退）。NTP 服务可能静默失败，需监控 ntpstat。

## ⚠️ Pitfall（反模式：什么情况下这条经验不适用）
如果 JWT 的 clock_skew 配置了足够的容差（如60秒），小幅度时间偏差不会导致问题。非 JWT 场景（如 Session 认证）时间偏差影响小。

## 🔗 关联经验
- 相关：[[云仓]]
