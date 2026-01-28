# Secure-by-Design Distributed Cloud Architectures

**Lab Project:** Research-Driven Security Engineering for Cloud-Native Systems

Cloud and distributed systems underpin modern digital infrastructure across government, industry, and research domains. However, security incidents in these environments frequently arise not from zero-day exploits, but from **architectural weaknesses** such as misconfigurations, over-permissive access controls, and poorly defined trust boundaries.

This lab forms the first phase of a structured research programme investigating **secure-by-design distributed cloud architectures**, focusing on how architectural decisions, identity and access management (IAM), and threat modelling can reduce attack surfaces and improve system resilience.

This work is positioned to support **PhD-level research** in distributed systems security, trustworthy systems, and secure software engineering, while remaining grounded in **practical cloud security operations**.

---

## Week 1–2: Foundations

### Day 1 – Research Framing

- **Focus:** Understanding the problem of architectural weaknesses in cloud and distributed systems.  
- **Objective:** Bridge the gap between theoretical secure systems design and practical cloud security implementation.  
- **Outcome:** Defined research hypothesis, security assumptions, and practical research mapping.  

### Day 2 – Secure Architecture Design and Trust Boundary Definition

- **Focus:** Designing a secure distributed cloud architecture that operationalises Day 1 principles.  
- **Components:** External Users, API Gateway, Web Tier, Application Tier, Data Tier, Identity & Access Management, Observability Layer.  
- **Trust Boundaries:** TB1 → TB4 with explicit identity-driven controls.  

**Figure 1: Secure Distributed Cloud Architecture with Trust Boundaries**  

![Figure 1: Secure Distributed Cloud Architecture](diagrams/week1-architecture-v1.1.png)

> This architecture provides the baseline for Week 3–4 threat modelling, attack simulation, and DevSecOps pipeline integration.

---

## Week 3–4: Threat Modelling & STRIDE Analysis

- **Focus:** Systematic threat identification and adversary modelling using STRIDE.  
- **Activities:**  
  - Defining explicit trust boundaries in a cloud-native system  
  - Mapping attack surfaces across ingress, service-to-service, and data layers  
  - Applying STRIDE threat modelling to real cloud components  
  - Aligning threats with identity-driven controls, RBAC, and zero-trust principles  
  - Structuring artefacts for reproducibility, auditability, and future experimentation  

**Figure 2: Threat Model Attack Surface – Secure Distributed Cloud System**

![Figure 2: Threat Model Attack Surface](diagrams/threat-model-attack-surface-week3.png)

> All diagrams, threat models, and documentation are version-controlled and publicly available.

---

## Research Continuity & Lab Outputs

- **Controlled misconfiguration experiments** (Week 4)  
- **Detection engineering and SIEM validation**  
- **DevSecOps pipeline integration**  
- **PhD-level reproducibility** in secure distributed systems research  

---

## GitHub Repository

Access the full research artefacts, diagrams, and threat models here:  

👉 [GitHub: Week 3–4 Threat Modelling](https://github.com/cowajoba-cloud/secure-distributed-cloud-lab/tree/main/research/week3-4-threat-modelling)
