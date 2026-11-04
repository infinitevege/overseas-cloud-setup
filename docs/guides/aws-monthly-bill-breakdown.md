---
title: 拆一张 AWS 月账单：按服务、地域和用途找出钱花在哪
description: 用 AWS Bills 页面、Cost Explorer 和成本分配标签，把一张月账单拆成服务、地域、用途三个维度，找出可以优化的费用。
category: 充值与账单
---

# 拆一张 AWS 月账单：按服务、地域和用途找出钱花在哪

AWS 的账单项目非常细，一个月几十上百行很正常。这篇给出一个固定的拆账顺序，用控制台自带的工具就能完成，不需要第三方软件。

> 适用对象：已经在使用 AWS 的团队，或者刚完成 [AWS 开户](https://www.clouddalao.com/cloud/aws)、想从第一个月起就把账算清楚的人。

## 准备：让 IAM 用户能看账单

默认情况下只有根用户能进入账单页面。日常不要用根用户登录，应当由根用户在账户设置里开启「IAM 用户和角色访问账单信息」，再给财务或负责人对应的 IAM 权限。根用户的其他保护措施见 [AWS 账号交付后的安全设置清单](https://www.clouddalao.com/guides/aws-account-security-after-handover)。

## 第一层：按服务拆

在 Billing and Cost Management 的 Bills 页面，选择月份，按服务展开。大多数账单 80% 以上的费用集中在少数几个服务：

| 常见大头 | 先看什么 |
| :--- | :--- |
| EC2 | 实例小时数、EBS 卷、弹性 IP、NAT 网关 |
| 数据传输（Data Transfer） | 出网流量、跨可用区、跨区域 |
| RDS | 实例规格、多可用区部署、存储与备份 |
| S3 | 存储量、请求次数、出网流量 |
| CloudWatch | 日志写入量和保存时长 |

数据传输费是最容易被低估的一项，计算方法见 [AWS 数据传输费用估算](https://www.clouddalao.com/guides/aws-data-transfer-cost-estimate)。

## 第二层：按地域拆

打开 Cost Explorer（首次启用后需要等待一段时间才有数据），把分组维度改为 Region。常见发现：

- 某个测试地域里还跑着忘记关闭的实例；
- 快照或 AMI 被复制到了多个地域；
- 全局服务（如 CloudFront、Route 53）单独列为 global，不要和某个地域混在一起看。

## 第三层：按用途拆

按用途拆需要成本分配标签：

1. 给资源统一打 `project`、`env`、`owner` 标签。
2. 在账单控制台的成本分配标签页面**激活**这些标签，激活后的数据才会出现在 Cost Explorer 中，且不追溯激活之前的费用。
3. 在 Cost Explorer 里按标签分组，就能看到每个项目、每个环境各花了多少。

没有标签的费用会显示为「No tag key」，这一块越小，账单越清楚。

## 拆完之后做什么

- 把每月前五大费用项记录下来，和上个月对比，波动超过 20% 的逐项解释。
- 用 AWS Budgets 为每个项目设预算提醒。
- 新账号的配额偏低会限制扩容，提前申请见 [AWS Service Quotas 提额指南](https://www.clouddalao.com/guides/aws-service-quotas-new-account)。
- 预估下个月用量后，再决定 [充值](https://www.clouddalao.com/recharge) 金额：AWS 充值填写交付时的登录账号即可，实例与配置不会变动。

---

上一篇：[腾讯云国际费用中心怎么看](tencent-intl-billing-center.md) · [返回目录](../index.md) · 下一篇：[Google Cloud 新项目上线清单](gcp-project-launch-checklist.md)
