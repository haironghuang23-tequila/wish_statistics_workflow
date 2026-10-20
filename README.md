# 心愿统计表

> 上传Excel/照片/文字 → 自动提取物品并七分类计数 → 追加到固定心愿统计表。

- Dify 应用类型：workflow（工作流）
- Dify DSL 版本：0.7.0
- 在线演示：[https://incredible-hummingbird-86dee1.netlify.app/](https://incredible-hummingbird-86dee1.netlify.app/)

## 目录结构

`
.
├── 心愿统计表.yml   # 从 Dify 导出的应用 DSL（已清空飞书 Secret）
├── README.md
└── .gitignore
`

## 如何导入 Dify

1. 打开 Dify，选择 **创建应用 / Create App**。
2. 选择 **导入 DSL / Import DSL File**。
3. 上传本仓库的 心愿统计表.yml。
4. 导入后补填环境变量（见下文）。

## 必填环境变量

| 变量 | 说明 |
| --- | --- |
| FEISHU_APP_ID | 飞书自建应用 App ID |
| FEISHU_APP_SECRET | 飞书自建应用 App Secret（**本仓库已清空**，导入后请填写） |

> 该工作流通过飞书开放平台 API 读写一个固定的电子表格，因此还需要确保该飞书应用有对应表格的读写权限。

## 安全说明

- 心愿统计表.yml 中的 FEISHU_APP_SECRET 已在提交前清空，请勿把真实 Secret 提交到公开仓库。
- 原始导出的 DSL 内含明文 Secret 和一个固定的飞书表格 ID，**建议使用 Private 仓库**；若必须公开，请先到飞书开放平台重置（轮换）App Secret，并把表格 ID 也改为环境变量。
