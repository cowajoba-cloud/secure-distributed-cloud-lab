# Lab 01 – Week 1, Day 2: Secure Architecture Design and Trust Boundary Definition

**Author:** Charles Owajoba  
**Research Domains:** Secure Systems, Cloud Security, Distributed Systems

---

## **Objective**

The objective of Day 2 is to design a **secure distributed cloud architecture** that operationalises the research framing established in Day 1.  

This phase focuses on translating abstract security principles—such as **zero trust**, **least privilege**, and **defence in depth**—into explicit architectural components, **trust boundaries**, and **identity enforcement points** within a cloud-native system.

---

## **Architecture Overview**

The proposed system follows a **layered, zone-based architecture** that separates components by trust level and security responsibility. Each layer enforces security controls appropriate to its exposure and function.

This architecture is designed to:

- Minimise the attack surface  
- Prevent unauthorised lateral movement  
- Centralise identity and access enforcement  
- Support observability and auditability  

---

## **Architecture Components**

### **3.1 External Users**  
Untrusted external clients that initiate requests to the system over the public internet.

### **3.2 API Gateway (Azure API Management)**  
Acts as the primary ingress point to the system. It enforces **authentication, request validation, and rate limiting** before forwarding traffic to internal services.

### **3.3 Web Tier (Stateless Frontend Services)**  
Handles request routing and presentation logic. This tier is designed to be **stateless** and horizontally scalable.

### **3.4 Application Tier (Private Internal Services)**  
Hosts core business logic and internal service communication. Access to this tier is restricted to **authorised upstream services**.

### **3.5 Data Tier (Private Databases and Storage)**  
Stores persistent and sensitive data. Direct access from public or web-facing components is explicitly prohibited.

### **3.6 Identity and Access Management (Azure AD)**  
Serves as the central identity provider, enforcing **authentication, authorisation, and role-based access control (RBAC)** across all tiers.

### **3.7 Observability Layer (Log Analytics and Microsoft Sentinel)**  
Aggregates logs and security telemetry from all components to support **detection, auditing, and incident response**.

---

## **Trust Boundary Definition**

Trust boundaries define points where the assumed trust level changes and additional security controls must be applied.

| Trust Boundary | Description | Enforced Security Controls |
|----------------|------------|---------------------------|
| TB1: Internet → API Gateway | Public ingress | Authentication, rate limiting, TLS |
| TB2: API Gateway → Web Tier | Controlled internal access | Token validation, TLS |
| TB3: Web Tier → Application Tier | Application logic boundary | Role-based access control, TLS |
| TB4: Application Tier → Data Tier | Data access boundary | RBAC, encryption at rest and in transit |

Each trust boundary is explicitly enforced using **identity-driven controls** rather than implicit network trust.

---

## **Architecture Diagram**

The secure distributed cloud architecture, including trust boundaries and IAM enforcement points, is illustrated in **Figure 1 below**:  

![Figure 1: Secure Distributed Cloud Architecture with Trust Boundaries](../../diagrams/week1-architecture-v1.1.png)

---

## **Identity and Access Enforcement**

Identity is treated as the **primary security perimeter**:

- Azure AD issues tokens to authenticated entities  
- Services assume **narrowly scoped identities**  
- Role assignments are aligned with functional responsibilities  
- No tier has default access to downstream components  

This approach aligns with **zero-trust architecture models** and reduces the blast radius of compromised services.

---

## **Security Design Rationale**

The architecture enforces security through a combination of:

- Explicit **trust boundary segmentation**  
- **Identity-based access control** at each layer  
- **Encryption** of all inter-service communication  
- Centralised **observability and audit logging**  

By combining architectural controls with IAM and monitoring, the system resists common cloud attack patterns such as **credential abuse, lateral movement, and privilege escalation**.

---

## **Alignment with Research Framing (Day 1)**

This architecture directly operationalises the Day 1 research hypotheses by:

- Translating trust boundaries into enforceable controls at each system layer  
- Demonstrating **least-privilege principles** in practice across all tiers  
- Providing a structured platform for **threat modelling and attack path analysis**  
- Enabling **reproducible security experiments** through version-controlled artefacts  
- Aligning **identity-driven access enforcement** with zero-trust principles to reduce lateral movement risks  
- Supporting **observability and auditability** through centralised logging and SIEM integration  
- Establishing a foundation for Week 3–4, where threats are formally modelled using **STRIDE** and misconfigurations are systematically tested  

By linking architectural decisions with measurable security outcomes, this design ensures that theoretical research hypotheses are validated **in a real cloud environment**, bridging the gap between academic models and practical implementation.

---

## **Notes and Continuity**

This architecture serves as the baseline for:

- Threat modelling (**Week 3**)  
- Attack simulation  
- DevSecOps pipeline integration  

All artefacts are **version-controlled and reproducible**. The design is intentionally **cloud-agnostic** at the conceptual level, despite using Azure services.
