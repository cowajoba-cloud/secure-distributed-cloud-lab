# Lab 01 – Week 3, Day 3: STRIDE Threat Analysis

## Objective
Systematically identify threats in the secure distributed cloud architecture using the **STRIDE framework**, map them to **trust boundaries**, and propose **mitigations** for each threat. This forms the foundation for **Week 4: Controlled Misconfigurations** and **PhD-level reproducibility**.

---

## Reference Diagram
**Figure 2: Threat Model Attack Surface – Secure Distributed Cloud System**

![Threat Model Attack Surface](../../diagrams/threat-model-attack-surface-week3.png)

*All trust boundaries (TB1–TB4) and attack paths are illustrated.*

---

## STRIDE Threat Tables

### TB1 – Internet → API Gateway
| Threat | Description | Mitigation / Control | Detection / Observability |
|--------|------------|--------------------|--------------------------|
| Spoofing | External attacker impersonates a legitimate user | OAuth2, JWT validation, Azure AD authentication | SIEM alert for failed login patterns |
| Tampering | Payload manipulation or malicious requests | TLS encryption, input validation, API Gateway validation | Azure Application Gateway WAF logs |
| Repudiation | Untracked user actions | Centralized logging and audit trails | Sentinel analytics alert for unusual activity |
| Information Disclosure | Sensitive data leakage via API | TLS, token validation, scoped API roles | Data access audit in SIEM |
| Denial of Service | Request flooding | Rate limiting, WAF, autoscaling | Traffic anomaly alerts in Sentinel |
| Elevation of Privilege | Exploit misconfigured endpoints | Principle of least privilege, RBAC enforcement | Alert on privilege escalations |

### TB2 – API Gateway → Web Tier
| Threat | Description | Mitigation / Control | Detection / Observability |
|--------|------------|--------------------|--------------------------|
| Spoofing | Compromised token reuse | Token expiration, JWT validation | SIEM token reuse alerts |
| Tampering | Malformed requests to web tier | Input validation, schema checks | Web server logs + Sentinel |
| Repudiation | User actions unlogged | Central logging enforced | Sentinel analytics alerts |
| Information Disclosure | Internal API data exposure | Scoped API permissions, TLS | Log monitoring for unusual access |
| Denial of Service | Overload web tier | Rate limiting, autoscaling | Traffic anomaly detection |
| Elevation of Privilege | Accessing web admin endpoints | RBAC, endpoint access controls | Alert on admin endpoint access |

### TB3 – Web Tier → Application Tier
| Threat | Description | Mitigation / Control | Detection / Observability |
|--------|------------|--------------------|--------------------------|
| Spoofing | Service-to-service impersonation | Mutual TLS, scoped service identity | Audit logs for service auth failures |
| Tampering | Inter-service message modification | TLS, payload validation | Sentinel alert for invalid requests |
| Repudiation | Unlogged actions in app tier | Central logging, immutable audit trails | Sentinel / Log Analytics |
| Information Disclosure | Internal data leakage | Role-based access control, encryption | DB access monitoring |
| Denial of Service | Malicious app calls | Rate limiting per service | Metrics monitoring + alerts |
| Elevation of Privilege | Excessive IAM roles exploited | Principle of least privilege | IAM change monitoring, alerts |

### TB4 – Application Tier → Data Tier
| Threat | Description | Mitigation / Control | Detection / Observability |
|--------|------------|--------------------|--------------------------|
| Spoofing | Unauthorized service access | Token validation, scoped DB roles | DB audit logs |
| Tampering | Data modification by attacker | Database transaction validation, encryption | Sentinel alerts for abnormal DB writes |
| Repudiation | Data changes unlogged | Centralized DB logging | SIEM alerts for critical table changes |
| Information Disclosure | Unauthorized queries | Role-based DB access, encryption at rest | SIEM query monitoring |
| Denial of Service | DB request flooding | Connection throttling, resource limits | DB performance alerts |
| Elevation of Privilege | Admin role misuse | Least-privilege assignments, audit | IAM role change alerts |

---

## Notes
- STRIDE tables are **reproducible** and **version-controlled**, suitable for academic and industrial review.
- All mitigations are **aligned with your Week 1–2 architecture**, Figure 1, and Week 3 attack surface, Figure 2.
- These tables form the baseline for **Week 4 controlled misconfigurations**, enabling measurable risk assessment.
