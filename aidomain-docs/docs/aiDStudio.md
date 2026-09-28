# AiDStudio 数据集管理平台

面向安防智能相机场景的全流程数据管理平台：原始数据资产化、自研标注画布、主动学习迭代标注、数据集管理、AI 模型训练与评估部署一站完成。

## 核心能力

- **数据资产化**：文件上传 / 视频导入 / 摄像头采集，EXIF 元数据自动提取、MD5 去重
- **自研标注画布**：缩略图导航 + 绘制编辑 + 属性面板一体布局，R/E/C 快捷键；模型预标注 + SAM 智能修正
- **主动学习闭环**：种子组精标 → 训练 → 自动预标注 → 人工修正 → 重训，困难样本优先，持续降低标注成本
- **数据集管理**：版本化管理、一键合并去重、标准格式导出，训练/验证/测试自动划分
- **训练与追踪**：AI 引擎 + MLflow 实验追踪，迭代任务看板
- **部署**：一键导出 ONNX / bmodel / rknn，转换部署到 AiDBox 边缘盒子，AiDBox / AiDCam 两端通用

## 部署

- Docker Compose 一键部署（PostgreSQL / Redis / MinIO / 后端 / 训练 worker），支持 x86 服务器与 GPU 调度

## 详情

- 产品页：https://www.aidomainhub.cn/products/aidstudio.html
- 规格书：https://www.aidomainhub.cn/downloads/AiDStudio-spec.pdf
- 文档中心：https://www.aidomainhub.cn/wiki/
