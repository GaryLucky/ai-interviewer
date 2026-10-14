# AI 面试官

Electron 桌面客户端与 Python FastAPI 服务端分离。当前仅创建目录骨架，尚未初始化依赖或实现业务代码。

```text
ai-interviewer/
├── desktop/                  # Electron + React + TypeScript + Vite 客户端
│   ├── electron/             # 主进程与桌面能力
│   ├── public/
│   └── src/
│       ├── pages/
│       ├── features/
│       │   ├── resume/
│       │   ├── interview/
│       │   └── report/
│       ├── components/
│       └── lib/api/          # FastAPI 接口客户端
├── backend/                  # FastAPI：业务模块与技术层混合组织
│   ├── app/
│   │   ├── api/              # 路由统一注册
│   │   ├── core/
│   │   │   ├── exceptions/
│   │   │   ├── security/
│   │   │   └── middleware/
│   │   ├── db/
│   │   │   └── repositories/
│   │   ├── shared/           # 跨模块服务
│   │   │   ├── ai/
│   │   │   ├── storage/
│   │   │   ├── cache/
│   │   │   ├── messaging/
│   │   │   └── utils/
│   │   ├── modules/
│   │   │   ├── users/
│   │   │   ├── resumes/
│   │   │   ├── interviews/
│   │   │   ├── evaluations/
│   │   │   └── reports/
│   │   └── tasks/           # Celery 后台任务
│   ├── migrations/           # 数据库迁移
│   ├── tests/modules/        # 按业务模块组织测试
│   ├── scripts/
│   └── docs/
├── infra/                    # 部署配置
└── docs/                     # 项目文档
```

FastAPI 目录参考：[FastAPI 项目工程化结构设计指南](https://blog.mapin.net/posts/FastAPI%20%E9%A1%B9%E7%9B%AE%E5%B7%A5%E7%A8%8B%E5%8C%96%E7%BB%93%E6%9E%84%E8%AE%BE%E8%AE%A1%E6%8C%87%E5%8D%97)。每个业务模块计划使用 `models.py`、`schemas.py`、`repositories.py`、`services.py`、`routers.py`，并按需添加 `dependencies.py`。
