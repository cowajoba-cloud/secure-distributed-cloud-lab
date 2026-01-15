# Lab 01 – Week 3: Threat Modelling Foundations

**Author:** Charles Owajoba  
**Research Domain:** Secure Distributed Cloud Architectures  

## Objective
To systematically identify, analyse, and document realistic security threats against a secure distributed cloud architecture using formal threat modelling techniques.

This lab builds directly on Week 1–2:

- Architecture and trust boundaries
- IAM enforcement points
- Layered services (Web, App, Data)
- Observability / SIEM telemetry

## Scope
The threat model applies to the architecture defined in Week 1–2, focusing on:

- Trust boundary violations
- IAM misuse and privilege escalation
- Lateral movement across tiers
- Data access abuse

## Threat Modelling Methodology
This lab adopts the STRIDE framework:

- Spoofing
- Tampering
- Repudiation
- Information Disclosure
- Denial of Service
- Elevation of Privilege

**Rationale:** STRIDE is suitable for distributed systems and architectural analysis. It allows measurable and reproducible research artefacts.

