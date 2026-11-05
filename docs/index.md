---
title: 出海上云落地手册
description: 阿里云国际、腾讯云国际、AWS、Google Cloud、Azure 从开户到稳定运行的分步清单，含账单拆解与 USDT 付款对账。
---

# 出海上云落地手册

拿到国际云账号之后，先做什么、后做什么、每一步怎么检查。每篇都是一份可以逐项打勾的清单。

## 全部指南

<!-- GUIDE-INDEX:START -->
| 分类 | 指南 |
| :--- | :--- |
| 开户与上手 | [阿里云国际新账号第一周：从首次登录到第一台 ECS 上线](guides/aliyun-intl-first-week.md) |
| 充值与账单 | [腾讯云国际费用中心怎么看：余额、账单明细与扣费记录](guides/tencent-intl-billing-center.md) |
| 充值与账单 | [拆一张 AWS 月账单：按服务、地域和用途找出钱花在哪](guides/aws-monthly-bill-breakdown.md) |
| 开户与上手 | [Google Cloud 新项目上线清单：API、服务账号、日志与标签](guides/gcp-project-launch-checklist.md) |
| 充值与账单 | [Azure 按项目分账：标签、资源组与预算提醒的用法](guides/azure-cost-tags-budgets.md) |
| 付款与对账 | [团队用 USDT 付云费用：一张对账台账该记哪些字段](guides/usdt-payment-ledger.md) |
| 账号安全 | [Azure 订阅到手后的安全基线：MFA、角色分配、活动日志与网络入口](guides/azure-subscription-security-baseline.md) |
<!-- GUIDE-INDEX:END -->

## 三个原则

1. **先加固，再上业务。** MFA、子用户、告警没做好之前，不部署正式服务。
2. **先打标签，再谈分账。** 资源没有标签，账单永远拆不清。
3. **每笔付款都留痕。** 订单号、交易哈希、到账金额缺一不可。

---

本手册由 [云大佬](https://www.clouddalao.com/) 整理，提供国际云 [开户](https://www.clouddalao.com/open-account) 与 [充值](https://www.clouddalao.com/recharge)。内容采用 CC BY 4.0 许可，云厂商规则以官方文档为准。
