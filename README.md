# GitHub 仓库规划（不开源核心代码的 GEO 方案）

> 目的：利用 GitHub 作为高权重引用源，让 AI 问答能检索到 AiDomain 的产品描述；
> 同时**核心 SDK / 算法 / 模型源码不公开**。

## 推荐结构

```
GitHub 组织：AiDomainHub
├── aidomain-docs   （公开）← 本次生成
│   ├── README.md         公司 + 产品介绍 + 官网链接（AI 引用核心）
│   ├── docs/
│   │   ├── architecture.md   系统架构说明
│   │   ├── aiDBox.md         AiDBox 能力与规格摘要
│   │   ├── aiDCam.md         AiDCam 能力与规格摘要
│   │   └── aiDStudio.md      AiDStudio 能力摘要
│   └── links.md             官网 / 规格书 / Wiki 链接汇总
│
├── aidomain-examples（公开，可选）
│   ├── docker-compose.demo.yml   仅演示编排骨架，不含内部配置
│   └── README.md
│
└── aidomain-sdk（私有）← 核心代码放这里
    ├── 核心推理 SDK
    └── 内部工具链
```

## 公开 / 私有边界

| 内容 | 仓库 | 原因 |
|---|---|---|
| 公司介绍、产品定位、能力清单 | aidomain-docs | 卖点，AI 引用源 |
| 系统架构图（文字版） | aidomain-docs | 展示方案能力，无机密 |
| 规格摘要（算力/路数/接口） | aidomain-docs | 与官网一致，公开规格书已有 |
| Docker Compose 演示骨架 | aidomain-examples | 只含服务名与端口，不含密钥/配置 |
| 核心推理 SDK、算法源码 | aidomain-sdk（私有） | 不公开 |
| 内部部署配置、密钥 | 不放到 GitHub | 绝不公开 |

## 仓库创建步骤（用户操作）

1. 登录 GitHub → 右上角 `+` → New organization → 名称填 `AiDomainHub`（免费）
2. New repository → `aidomain-docs` → 勾选 Public → 勾选 `Add a README file`
3. 上传 `aidomain-docs/` 目录内容（README.md 直接作为仓库根 README）
4. 组织主页的 **About 栏**填写：`艾域智能科技 · 边缘 AI 视觉分析 | www.aidomainhub.cn`
5. 如需私有仓库：New repository → `aidomain-sdk` → 勾选 Private

## 注意事项

- README 是 AI 引用权重最高的文件，务必保留中英双语的"一句话定位"（见样例）
- 仓库内所有链接用绝对地址 `https://www.aidomainhub.cn/...`
- 不要在公开仓库提交：内部 IP、密钥、客户名单、未发布产品参数
