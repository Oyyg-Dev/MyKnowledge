---
type: hindsight-dashboard
---

## 📊 经验库仪表盘

### 最近经验
```dataview
TABLE category, confidence, date
FROM "经验库"
WHERE type = "hindsight"
SORT date DESC
LIMIT 10
```

### 高置信度经验
```dataview
TABLE category, date
FROM "经验库"
WHERE type = "hindsight" AND confidence = "high"
SORT date DESC
```

### 知识孤岛（无反向链接）
```dataview
LIST
FROM "经验库"
WHERE type = "hindsight" AND length(file.inlinks) = 0
SORT date ASC
```

### 即将过期的经验
```dataview
TABLE category, expires
FROM "经验库"
WHERE type = "hindsight" AND expires < date(today) + dur(30 days)
SORT expires ASC
```

### 按类别统计
```dataview
TABLE length(rows) as 数量
FROM "经验库"
WHERE type = "hindsight"
GROUP BY category
```
