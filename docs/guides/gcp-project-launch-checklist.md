---
title: Google Cloud 新项目上线清单：API、服务账号、日志与标签
description: 在 Google Cloud 新建一个生产项目时的上线清单：项目命名、结算关联、按需启用 API、服务账号最小权限、日志保留、标签与预算提醒。
category: 开户与上手
---

# Google Cloud 新项目上线清单：API、服务账号、日志与标签

Google Cloud 以「项目」为单位组织资源、权限和账单。项目建得随意，后面几乎每件事都会变麻烦：权限分不开、账单拆不清、删除时不敢下手。这篇是一份新项目上线前逐项打勾的清单。

> 适用对象：已经有可用结算账户、准备建第一个生产项目的团队。结算账户与配额的基本概念见 [Google Cloud 开户前要了解的事](https://www.clouddalao.com/guides/google-cloud-billing-account-and-quota)。

## 1. 项目命名与结构

- [ ] 项目 ID 创建后不能修改，用 `团队-业务-环境` 这样的固定格式，例如 `acme-shop-prod`。
- [ ] 生产和测试分成两个项目，不要在一个项目里靠命名区分。
- [ ] 有多个业务时，用文件夹（Folder）归类，权限可以在文件夹层级统一授予。

## 2. 结算关联

- [ ] 确认项目关联的是正确的结算账户（Billing → Account management）。
- [ ] 记录结算账户 ID 和项目 ID 的对应关系。将来办理 Google Cloud 的 [开户或充值](https://www.clouddalao.com/cloud/gcp) 时，需要与专人确认的就是这些信息。

## 3. 只启用需要的 API

新项目默认只启用少量 API。用到什么开什么，不要一次性全部启用：

| 业务 | 常见需要启用的 API |
| :--- | :--- |
| 虚拟机 | Compute Engine API |
| 容器 | Kubernetes Engine API、Artifact Registry API |
| 数据分析 | BigQuery API |
| AI 应用 | Vertex AI API |

启用的 API 越少，被误用或被盗用后能产生费用的面就越小。

## 4. 服务账号最小权限

- [ ] 每个应用一个服务账号，名称写清用途，例如 `shop-api-runtime`。
- [ ] 授予具体的预定义角色，避免直接给 Owner 或 Editor。
- [ ] 尽量不下载 JSON 密钥。运行在 Google Cloud 上的服务直接使用挂载的服务账号；必须下载时，记录密钥 ID、存放位置和轮换日期。
- [ ] 定期在 IAM 页面检查是否有长期未使用的密钥，及时删除。

## 5. 日志与审计

- [ ] 确认管理员活动审计日志可以查看（默认开启）。
- [ ] 按需开启数据访问审计日志，它会产生额外的日志量和费用。
- [ ] 为高流量应用设置日志排除规则或采样，避免日志写入费用失控。

## 6. 标签（Labels）

给虚拟机、磁盘、存储桶等资源统一加 `env`、`team`、`app` 标签。导出到 BigQuery 的结算数据会带上这些标签，按业务拆账时可以直接分组。

## 7. 预算与提醒

- [ ] 在结算账户下为这个项目建预算，设置 50%、90%、100% 三档提醒。
- [ ] 提醒接收人至少两位。
- [ ] 记住预算提醒默认只发通知，不会自动停用服务。

## 8. 上线前最后确认

- [ ] 防火墙规则只对必要来源开放管理端口
- [ ] 关键服务开启了跨可用区部署或备份
- [ ] 项目的配额满足上线峰值，需要 GPU 等资源时提前申请

需要新开 Google Cloud 结算账户的，可以在 [开户页](https://www.clouddalao.com/open-account) 联系专人，Google Cloud 涉及结算结构和配额，需要一对一确认后办理。

---

上一篇：[拆一张 AWS 月账单](aws-monthly-bill-breakdown.md) · [返回目录](../index.md) · 下一篇：[Azure 按项目分账](azure-cost-tags-budgets.md)
