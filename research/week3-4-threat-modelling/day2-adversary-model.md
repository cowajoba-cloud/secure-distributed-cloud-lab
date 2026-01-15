# Lab 01 – Week 3: Adversary Model and Attack Surface

## Objective
To define explicit adversary capabilities and systematically map the attack surface of the secure distributed cloud architecture designed in Week 1–2.

This step ensures that all subsequent threat analysis is grounded in realistic and defensible attacker assumptions.

## Adversary Model

### A1 – External Network Attacker
**Capabilities**
- Internet access only
- No valid credentials
- Can craft malicious requests

**Objectives**
- Exploit exposed endpoints
- Bypass authentication
- Disrupt service availability

### A2 – Compromised Identity
**Capabilities**
- Valid low-privileged credentials
- Access to one system component
- Ability to reuse tokens

**Objectives**
- Lateral movement
- Privilege escalation
- Data exfiltration

### A3 – Insider with Limited Privileges
**Capabilities**
- Legitimate internal access
- Knowledge of system architecture

**Objectives**
- Abuse trust assumptions
- Bypass access controls

## Out of Scope
- Cloud provider compromise
- Physical access attacks
- Hardware-level exploits

## Attack Surface Identification

The primary attack surface includes:
- Public API endpoints
- Identity tokens and credentials
- Inter-service communication paths
- IAM role assignments
- Logging and monitoring pipelines

## Attack Surface Visualisation

Figure 2 illustrates the attack surface of the secure distributed cloud architecture, highlighting trust boundaries, entry points, and realistic adversarial paths across system components.

The diagram explicitly marks:
- Public exposure points
- Identity enforcement locations
- Privilege escalation paths
- Lateral movement opportunities

This visual representation serves as the foundation for the STRIDE-based threat analysis conducted in Day 3.

![Figure 2: Threat Model Attack Surface – Secure Distributed Cloud System](../../diagrams/threat-model-attack-surface-week3.png)

Each trust boundary represents a potential escalation point rather than a security guarantee.

## Continuity Note
This adversary model directly informs the STRIDE-based threat analysis conducted in Day 3.
