---
title: "Example 08 TOGAF ADM Phase C in Cloud Adoption: The FinOps Cost-Mapping Challenge"
date: 2025-11-11
draft: false
featured: true
slug: example-08-togaf-adm-phase-c-finops-mapping
authors: ["Jeff Taakey"]
description: "A TOGAF-certified architect's analysis of implementing TOGAF ADM Phase C (Information Systems Architecture) and the critical steps for integrating FinOps principles into the required baseline and target architecture definitions."
summary: "Analyzes the practical challenges of mapping high-level TOGAF application and data components to granular cloud resources (e.g., EC2, Serverless, DynamoDB) and the necessity of TCO modeling during the ADM cycle."
weight: 10
categories: ["Governance & Methodologies", "TOGAF Application & Practice Cases"]
tags: ["TOGAF", "Enterprise Architecture", "ADM", "FinOps Mapping", "Cloud Governance"]
showTableOfContents: true
showReadingTime: true
showWordCount: true
---

> ## Jeff's Notes
> 
> The value of TOGAF is not in the diagrams, but in the **Decision Gates** and **Compliance Reviews** it enforces. In modern practice, the biggest failure point is translating **Target Architecture** (Phase C) into an auditable, cost-optimized **FinOps Baseline**.
> 
> This analysis focuses on the practical challenge of ensuring that the **Architecture Vision** defined early in the cycle does not become a **FinOps Nightmare** upon implementation.

---

## Enterprise Architecture Dilemma: Abstract Design vs. Concrete Cost

- **Scenario:** [CREATE A BUSINESS/IT ALIGNMENT SCENARIO. Example: A large enterprise is defining its Target Architecture (Phase C). The architects recommend using a 'Microservices' pattern for high flexibility (good Architecture Vision). However, the implementation team must choose between Kubernetes (Ops Heavy) and Serverless (Cost Variable) deployments, which was not detailed in Phase C.]

- **The Requirement (TOGAF Compliance):** How should the architecture team ensure the Target Architecture's *economic viability* and maintain *compliance* with the Architecture Vision, specifically during the Phase C and D transition?

- **The Trade-offs (Options):**

    A) [OPTION A: Focus strictly on functional requirements per the Architecture Vision. Delegate cost modeling to the implementation team.]
    
    B) [OPTION B: Introduce a **FinOps Cost-Modeling Step** within Phase C, requiring a TCO baseline for all major application components before Phase D (Technology Architecture).]
    
    C) [OPTION C: Defer all cost and operational decisions until the final Phase E (Opportunities and Solutions), making a high-level technology choice only.]

---

## The Enterprise Architect's Analysis

- **Preferred Strategic Approach (FinOps-Integrated ADM):** **Option [B]**

- **The Winning Logic (TOGAF Rationale):** [EXPLAIN WHY Option B maintains the ADM integrity. Reference the need for *economic viability* (a key TOGAF consideration) and how delaying cost integration violates the principle of *minimizing re-work* in later phases.]

---

## 📉 ADM Decision Mapping: Cost and Compliance

| ADM Phase | Deliverable Impacted | FinOps Integration Status | Risk of Non-Compliance / Overspending |
| :--- | :--- | :--- | :--- |
| **Phase A (Vision)** | Architecture Vision | Conceptual | Low |
| **Phase C (IS Arch.)** | Target Application Map | **CRITICAL** (Requires TCO Modeling) | **High** (If deferred) |
| **Phase D (Tech Arch.)** | Technology Roadmap | Execution Focused | Low (If C was done correctly) |
| **Recommendation** | **Target Architecture** must be linked to **TCO per Application Component** in Phase C. | | |

---

## Real-World Application (EA Insight)

- **TOGAF Principle Applied:** [STATE THE CORE TOGAF PRINCIPLE. E.g., The principle of **"Maximizing the Benefit to the Enterprise"**, where benefit includes cost optimization.]

- **Real World:** In practice, successful enterprises treat FinOps as a continuous **Architecture Governance** tool. The Architecture Review Board (ARB) should use TCO analysis (from Phase C/D) as a **Gate-Check** to ensure the implemented architecture remains aligned with the economic targets established in the initial **Architecture Vision**.

---

## Call to Action

> **🚀 Architect for Success, Govern for Profit.**
> 
> Your TOGAF certification proves you know the framework. We teach you how to make it *profitable*. Don't miss the launch of our **Multi-Cloud FinOps Optimization Toolkit**, which includes **TOGAF ADM-integrated TCO Modeling Templates**.
> 
> **👉 Subscribe to ADH Weekly Insights for exclusive early access and advanced strategy notifications!**

---

## Disclaimer

This is a study note based on simulated scenarios for applying **TOGAF** principles. It is not an official question from The Open Group.