# 出海上云落地手册

> 国际云账号从开通到稳定运行的分步手册：阿里云国际、腾讯云国际、AWS、Google Cloud、Microsoft Azure 的上手清单、账单拆解与 USDT 付款对账。

**在线阅读：<https://infinitevege.github.io/overseas-cloud-setup/>**

这份手册不讲「哪家云最好」，只讲拿到账号之后具体怎么做：先做什么、后做什么、每一步怎么检查。每篇都是一份可以逐项打勾的清单。

## 手册目录

<!-- GUIDE-INDEX:START -->
| 分类 | 指南 | 一句话说明 |
| :--- | :--- | :--- |
| 开户与上手 | [阿里云国际新账号第一周：从首次登录到第一台 ECS 上线](docs/guides/aliyun-intl-first-week.md) | 阿里云国际新账号到手后七天内的操作顺序：登录核对、安全加固、网络规划、第一台 ECS、监控与费用提醒，每一步给出检查点。 |
| 充值与账单 | [腾讯云国际费用中心怎么看：余额、账单明细与扣费记录](docs/guides/tencent-intl-billing-center.md) | 读懂腾讯云国际费用中心的几个页面：账户余额、账单概览、账单明细和收支流水，学会按产品和实例定位一笔扣费。 |
| 充值与账单 | [拆一张 AWS 月账单：按服务、地域和用途找出钱花在哪](docs/guides/aws-monthly-bill-breakdown.md) | 用 AWS Bills 页面、Cost Explorer 和成本分配标签，把一张月账单拆成服务、地域、用途三个维度，找出可以优化的费用。 |
| 开户与上手 | [Google Cloud 新项目上线清单：API、服务账号、日志与标签](docs/guides/gcp-project-launch-checklist.md) | 在 Google Cloud 新建一个生产项目时的上线清单：项目命名、结算关联、按需启用 API、服务账号最小权限、日志保留、标签与预算提醒。 |
| 充值与账单 | [Azure 按项目分账：标签、资源组与预算提醒的用法](docs/guides/azure-cost-tags-budgets.md) | 用资源组划分边界、用标签补充维度、用 Cost Management 的成本分析和预算做按项目分账，附标签继承和命名规范建议。 |
| 付款与对账 | [团队用 USDT 付云费用：一张对账台账该记哪些字段](docs/guides/usdt-payment-ledger.md) | 团队用 USDT 支付国际云开户与充值费用时，财务和技术如何用一张台账记录订单号、交易哈希、到账金额与账号标识，月底十分钟完成对账。 |
<!-- GUIDE-INDEX:END -->

## 怎么用这份手册

1. **刚开户**：先读「开户与上手」类，按清单把账号加固、网络和告警做好。
2. **已经在跑业务**：读「充值与账单」类，把每月费用拆清楚，再决定充值金额和节奏。
3. **负责付款的同事**：读「付款与对账」类，用统一的台账记录每一笔 USDT。

## 平台速查

| 平台 | 账号标识 | 开户 | 充值 |
| :--- | :--- | :--- | :--- |
| 阿里云国际 | 账号 UID | 在线办理 | 按 UID 在线办理 |
| 腾讯云国际 | 账号 UID | 在线办理 | 按 UID 在线办理 |
| AWS | 登录账号 | 在线办理 | 按登录账号在线办理 |
| Google Cloud | 结算账户 | 专人对接 | 与专人确认 |
| Microsoft Azure | 订阅 ID | 专人对接 | 与专人确认 |

## 关于

本手册由 [云大佬](https://www.clouddalao.com/) 整理。云大佬提供阿里云国际、腾讯云国际、AWS、Google Cloud、Azure 的国际云 [开户](https://www.clouddalao.com/open-account) 与 [充值](https://www.clouddalao.com/recharge)，使用 USDT 结算，计价方式见 [费率说明](https://www.clouddalao.com/rates)。

手册中涉及云厂商规则和控制台菜单的内容，以官方文档和控制台最新界面为准。发现过时内容欢迎提 Issue。

## 许可

文字内容采用 [CC BY 4.0](LICENSE) 许可，转载请注明出处并附原链接。
