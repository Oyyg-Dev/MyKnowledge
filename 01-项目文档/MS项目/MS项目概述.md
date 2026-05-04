---
项目: MS项目
创建时间: 2026-05-04
标签: #项目文档 #MS项目
---

## 项目概述
- **项目路径**: E:\000-Work\A002-ProjectCode\MS
- **技术栈**: 若依框架 + Vue 2 + uni-app + Java 8 + MySQL
- **数据库**: ms、oa、T100
- **主分支**: 
  - 前端/后端: develop
  - 小程序: test

## 目录结构
```
MS/
├── faretms-ui/              # 前端项目
│   ├── src/
│   │   ├── api/            # API 接口
│   │   ├── views/          # 页面组件
│   │   └── components/     # 公共组件
│   └── package.json
├── ums-faret/              # 后端项目
│   ├── faret-admin/
│   │   └── src/main/resources/
│   │       └── application.yml  # 配置文件
│   └── pom.xml
└── minicard/MiniCardVue/   # 微信小程序
    └── common/api/         # 小程序 API
```

## 核心功能模块
- [x] 创新平台
- [x] 生产计件功能
- [ ] OA 系统集成
- [ ] 其他功能模块

## 常用命令

### 后端
```bash
# 进入后端目录
cd E:/000-Work/A002-ProjectCode/MS/ums-faret

# 编译打包（跳过测试）
mvn clean package -DskipTests

# 本地运行
mvn spring-boot:run
```

### 前端
```bash
# 进入前端目录
cd E:/000-Work/A002-ProjectCode/MS/faretms-ui

# 安装依赖
npm install

# 开发环境启动
npm run serve

# 生产环境构建
npm run build:prod
```

### 小程序
```bash
# 进入小程序目录
cd E:/000-Work/A002-ProjectCode/MS/minicard/MiniCardVue

# 使用 HBuilderX 打开项目
# 工具路径: E:\300-Software\340-ProgrammingSoftware\HBuilderX

# 使用微信开发者工具预览
# 工具路径: E:\300-Software\340-ProgrammingSoftware\微信web开发者工具
```

## 配置文件位置
- **后端配置**: ums-faret/faret-admin/src/main/resources/application.yml
- **前端配置**: faretms-ui/.env.production
- **小程序配置**: minicard/MiniCardVue/manifest.json

## 数据库连接
- **ms 数据库**: 192.168.1.181:3306/fallada (MySQL)
  - 只读账号: ms_ro
- **oa 数据库**: 192.168.1.244:3306/ekp (MySQL)
- **T100 数据库**: 192.168.1.175:1521 (Oracle 19c)
  - 测试区: toptst (只读账号: T100_RO)
  - 正式区: topprd (只读账号: T100_RO_PROD)

## 服务器信息
- **SSH连接**: 待补充
- **日志路径**: /app/logs (根据 logback.xml 配置)

## 开发规范

### API 修改同步检查
修改后端 API 时，必须检查以下位置是否需要同步：
- PC 端: `faretms-ui/src/api/`
- 小程序: `minicard/MiniCardVue/common/api/`

检查内容：
- [ ] 接口路径是否一致
- [ ] 参数结构是否匹配
- [ ] 返回格式是否统一

### Git 分支规范
- **主分支**: develop (前端/后端), test (小程序)
- **功能开发**: feature/功能名
- **Bug 修复**: bugfix/问题描述
- **紧急修复**: hotfix/问题描述

## 相关文档
- [[MS项目-后端开发指南]]
- [[MS项目-前端开发指南]]
- [[MS项目-小程序开发指南]]
- [[MS项目-API接口清单]]
- [[MS项目-部署文档]]

## 问题记录
- [[问题-OA回调接口幂等性]]
- [[问题-生产计件数据同步]]

## 备注
- OA 回调接口需要特别注意空值防御和幂等性处理
- 小程序与 PC 端共用后端 API，修改时需同步测试
- 数据库连接配置详见: C:\Users\Administrator\.claude\connections.json
