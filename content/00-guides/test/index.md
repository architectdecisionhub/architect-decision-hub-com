---
title: 'demo guide 01'
date: 2025-11-01
draft: true
featured: false
slug: "demo-guide-01"
authors: ["Jeff Taakey"]
description: "some description."
summary: "some summary."
weight: 10
categories: ["demo"]
tags: ["API Gateway", "Cost Management", "Serverless", "Security"]
showTableOfContents: true
showReadingTime: true
showWordCount: true
---


## Architecture Visualized

example 1:

```mermaid
flowchart LR
    Client["客户端"] --> ALB["ALB（TLS 终止）"]
    ALB --> EC2["EC2 实例"]
```

example 2:

{{< mermaid >}}
flowchart TB
    Partner[Premium Partner]
    
    subgraph "API Gateway (Throttling Layer)"
        CheckKey{Valid API Key?}
        CheckPlan{Usage Plan Check}
        Bucket[Token Bucket Algorithm]
    end
    
    Lambda["Weather Data Lambda"]
    
    Partner -->|Request + API Key| CheckKey
    CheckKey -->|Yes| CheckPlan
    CheckPlan -->|Within Rate/Quota| Bucket
    Bucket -->|Forward| Lambda
    CheckPlan -->|Exceeded| Error[429 Too Many Requests]
    
{{< /mermaid >}}

