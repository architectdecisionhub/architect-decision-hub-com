---
title: "Example 06: AWS SAA-C03 练习题：多区域灾难恢复策略与 RTO/RPO"
date: 2025-04-01
draft: false
featured: false
slug: aws/saa/example-06-aws-saa-multi-region-dr-drill-t1
authors: ["ADH Content Team"]
description: "SAA 认证的关键考点解析：如何在 AWS 上选择最低 RTO 的多区域灾难恢复方案，并理解 DynamoDB Global Tables 的作用。"
summary: "本题重点解析 AWS SAA 认证中常考的多区域 DR 策略。目标：最小化停机时间。核心考点：RTO/RPO 与 Global Tables 的应用。"
weight: 10
categories: ["Certification Drills", "AWS SAA (T1)"]
tags: ["AWS SAA", "Disaster Recovery", "DynamoDB", "RTO/RPO"]
showTableOfContents: true
showReadingTime: false
showWordCount: true
---

> ## 考试要点提示
> 
> 在 AWS SAA 认证考试中，当题目要求 **“最小化停机时间”** 或 **“低 RTO (Recovery Time Objective)”** 时，您的解决方案必须包含 **预先部署** 和 **实时数据复制** 的机制。请专注于 AWS 服务的内置功能。

---

## 模拟考试题：多区域灾难恢复

- **场景:** Acme 公司运营着一个高流量的交易应用，运行在 AWS US-East-1 区域的 EC2 Auto Scaling groups 后面，数据存储在 DynamoDB 表中。公司需要一个灾难恢复 (DR) 策略，确保应用能在主区域发生故障时，以 **最小停机时间** 切换到另一个 AWS 区域。

- **问题：**
设计一个 DR 解决方案，确保最小的停机时间 (低 RTO)，以下哪种方法最符合 AWS SAA 认证的最佳实践？

- **选项：**

    A) Deploy a fully configured Auto Scaling group and ELB in a secondary region. Convert the DynamoDB table into a global table spanning both regions. Configure Route 53 DNS failover to switch traffic to the secondary region's ELB upon primary region failure.

    B) Prepare an AWS CloudFormation template for launching EC2 instances, ELB, and a DynamoDB table in the secondary region on-demand. Use DNS failover to point traffic to this region only after deployment completes.

    C) Deploy a CloudFormation template that provisions EC2 instances and ELB in the secondary region, but keep the DynamoDB table configured as a global table across both regions. Use DNS failover to redirect traffic when needed.

    D) Create an Auto Scaling group and ELB in the secondary region, configure DynamoDB global tables, and set up an Amazon CloudWatch alarm with a 10-minute evaluation period that triggers a Lambda function to update Route 53 DNS records to redirect traffic to the secondary region upon detecting failure.

---

## 答案与 SAA 核心解析

- **正确答案：** **Option A**

- **SAA 考试解析 (Why A is Correct):** Option A 采用了 **暖备用 (Warm Standby)** 或 **热备用 (Hot Standby)** 的思路，这是实现低 RTO 的关键：
    1.  **预先部署 (Provisioning):** 在次要区域预先部署了 **Auto Scaling Group 和 ELB**，避免了故障发生时等待资源启动的时间。
    2.  **数据实时性 (Data Consistency):** **DynamoDB Global Tables** 提供了跨区域的近实时、自动异步复制，确保了次要区域的数据是最新的（即实现了低 RPO - Recovery Point Objective）。
    3.  **自动化切换 (Failover):** **Route 53 DNS Failover** 是 AWS 官方推荐的、快速、自动化的流量切换机制。

- **错误选项排除 (Exam Tips):** - **排除 B：** “On-demand” 部署意味着需要等待 CloudFormation 栈和 EC2 实例启动，这会导致 **RTO 过高**，不满足“最小停机时间”的要求。
  - **排除 C：** 缺少 Global Table 意味着次要区域的数据是 **陈旧的 (stale)**，不满足数据一致性要求。
  - **排除 D：** CloudWatch 告警的 **10 分钟** 评估周期本身就是延迟。对于低 RTO 场景，应优先使用 Route 53 的健康检查功能。

---

> **📚 想要更多 SAA 认证练习题和知识点精讲？** > 
> 立即免费加入 ADH 邮件列表，每周获取最新的 AWS 认证模拟试题和高频考点总结！
> 
> **👉 免费订阅 ADH 认证精讲！**