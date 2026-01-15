# Secure Distributed Cloud Lab

## Overview
This lab investigates **secure-by-design distributed cloud architectures**. Modern cloud and distributed systems underpin government, industry, and research infrastructures. Security incidents in these environments often arise from **architectural weaknesses**—misconfigurations, over-permissive access controls, and poorly defined trust boundaries—rather than zero-day exploits.

This structured research programme establishes **practical, reproducible artefacts** to study how architecture, identity, access management (IAM), and threat modelling can **reduce attack surfaces** and improve **system resilience**. The lab supports **PhD-level research** in distributed systems security, trustworthy systems, and secure software engineering, while remaining grounded in real-world cloud operations.

---

## Lab 01 – Week 1–2: Architecture & Design
**Objective:** Design a secure distributed cloud system as a foundation for later threat modelling and security experiments.

### Key Activities
- Layered architecture design: **Web Tier, App Tier, Data Tier**
- Defined **trust boundaries** and IAM enforcement points
- Applied **zero-trust principles** and **least privilege** policies
- Integrated observability: **Azure Log Analytics + Microsoft Sentinel**
- Generated baseline **architecture diagrams** for reproducibility

### Architecture Diagram
**Figure 1: Secure Distributed Cloud Architecture with Trust Boundaries**

[Figure 1: Secure Distributed Cloud Architecture with Trust Boundaries](diagrams/week1-architecture-v1.1.png)

### Artefacts
- `research/week1-2-foundations/day1-research-framing.md`
- `research/week1-2-foundations/day2-architecture-design.md`
- `diagrams/week1-architecture-v1.1.png`
- Version-controlled GitHub repository

---

## Lab 01 – Week 3–4: Threat Modelling & Security Validation
**Objective:** Build on Week 1–2 architecture to identify realistic threats, evaluate misconfigurations, and validate security controls.

### Week 3 – Threat Modelling
- Applied **STRIDE framework** to all components and trust boundaries
- Created **attack surface diagrams**:

**Figure 2: Threat Model Attack Surface – Secure Distributed Cloud System**

![Figure 2: Threat Model Attack Surface](diagrams/threat-model-attack-surface-week3.png)

- Defined **adversary models** (external, compromised identity, insider)
- Structured threats into tables with **mitigations, detection points, and observability checks**

### Week 4 – Controlled Misconfigurations
- Introduced intentional misconfigurations (e.g., over-privileged IAM, public-facing services)
- Measured **blast radius**, attack feasibility, and detection efficacy
- Validated logging and alerting in **Microsoft Sentinel**
- Refined controls and documented **before/after comparisons**

### Artefacts
- `research/week3-4-threat-modelling/day1-threat-model-overview.md`
- `research/week3-4-threat-modelling/day2-adversary-model.md`
- `research/week3-4-threat-modelling/day3-stride-analysis.md`
- `diagrams/threat-model-attack-surface-week3.png`

---

## Research Significance
- Demonstrates practical enforcement of **zero-trust, least privilege, and RBAC principles**
- Provides a **reproducible, auditable foundation** for doctoral-level research
- Supports controlled experiments in threat modelling and detection
- Publicly version-controlled artefacts enhance **transparency and academic credibility**

---

## GitHub Repository
All documentation, diagrams, and experimental artefacts are hosted here:  
https://github.com/cowajoba-cloud/secure-distributed-cloud-lab

---

## LinkedIn Showcase
A consolidated post summarizing Week 3–4 lab outputs:

*"Over the past two weeks, I advanced my secure distributed cloud research from architecture design into formal threat modelling and security validation. All artefacts, diagrams, and threat models are publicly available on GitHub, demonstrating practical enforcement of zero-trust, least privilege, and identity-driven controls in cloud-native systems."*

https://github.com/cowajoba-cloud

