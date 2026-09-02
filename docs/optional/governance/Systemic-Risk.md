# Systemic Risk Framework v1.0

**Status:** Built — v1.0  
**Type:** Risk Management Instrument  
**Parent Stack:** AIGIS Risk / AICA-5  
**Version:** 1.0

---

## PREAMBLE

The Systemic Risk Framework establishes a structured approach for managing systemic AI risks that can destabilize institutions, including multi-agent interactions, discrimination at scale, and large-scale hallucinations. It answers: *What systemic risks can emerge from AI systems, how do we classify them, and how do we govern them?*

Systemic risk in AI is undertheorized. Current regulations (EU AI Act, DSA) have narrow characterizations of systemic risk. This framework provides a comprehensive classification of systemic risk levels, assessment gates, and governance mechanisms — extending I9 Catastrophic Risk with a systemic risk category and establishing assessment gates for Tier 4/5 deployments.

**The core insight:** Systemic risk is not just the sum of individual risks. It emerges from interactions, scale, and cascading effects. A framework that only governs individual AI systems misses the systemic risks that can destabilize entire institutions and markets.

---

## SECTION 1: PURPOSE AND SCOPE

### Purpose

The Systemic Risk Framework ensures that:

1. **Systemic risks are classified** — Four levels of systemic risk are defined and assessed  
2. **Systemic risks are assessed** — Assessment gates are established for Tier 4/5 deployments  
3. **Systemic risks are governed** — Governance mechanisms are defined for each risk level  
4. **Systemic risks are monitored** — Continuous monitoring detects emerging systemic risks  
5. **I9 is extended** — I9 Catastrophic Risk includes a systemic risk category

### Scope

| In Scope | Out of Scope |
| :---- | :---- |
| Systemic risk classification (4 levels) | Individual AI risk management (AICA-5) |
| Systemic risk assessment gates | Model-level risk assessment |
| Systemic risk monitoring | Technical implementation |
| I9 extension with systemic risk | Day-to-day AI operations |
| Systemic risk escalation | AI model development |

### Governing Relationships

| Instrument | Relationship |
| :---- | :---- |
| **ICC-8 I9** | Extended with systemic risk category |
| **AICA-5** | Systemic risk governance integrates with AICA-5 |
| **CAM-5** | Systemic risk assessment gates for Tier 4/5 |
| **HAN/HOF** | Systemic risk escalation to HAN/Board |
| **ERDP** | Systemic risk disclosure |
| **CAD-7** | Multi-agent systemic risk governance |
| **RGI-8** | Systemic drift detection |

---

## SECTION 2: SYSTEMIC RISK CLASSIFICATION

### 2.1 Risk Levels

| Level | Name | Description | Examples |
| :---- | :---- | :---- | :---- |
| **1** | **Single-Model Risk** | Risk confined to a single AI model | Model bias, model hallucination, model failure |
| **2** | **Multi-Model Risk** | Risk emerging from multiple models interacting | Inconsistent decisions across models, model disagreement |
| **3** | **Model-Platform Risk** | Risk emerging from models operating on a shared platform | Platform-wide failures, shared infrastructure vulnerabilities |
| **4** | **Model-Institution Risk** | Risk that can destabilize the entire institution | Cascading failures, market manipulation, systemic discrimination |

### 2.2 Risk Categories

| Category | Description | Examples |
| :---- | :---- | :---- |
| **Multi-Agent Coordination** | Risks from multiple agents coordinating | Collusion, emergent behavior, coordination failures |
| **Discrimination at Scale** | Risks from systematic discrimination | Widespread bias, unfair outcomes at population scale |
| **Large-Scale Hallucination** | Risks from large-scale hallucinations | Mass misinformation, systemic data corruption |
| **Cascading Failure** | Risks from cascading failures | Chain reactions, domino effects, systemic collapse |
| **Market Manipulation** | Risks from market manipulation | Price manipulation, market distortion |
| **Systemic Security** | Risks from systemic security failures | Widespread vulnerabilities, systemic attacks |

### 2.3 Risk Assessment Criteria

| Criteria | Description | Weight |
| :---- | :---- | :---- |
| **Scale** | Number of users/systems affected | High |
| **Propagation** | Speed and extent of propagation | High |
| **Reversibility** | Ability to reverse or contain | Medium |
| **Cascading Potential** | Likelihood of cascading effects | High |
| **Market Impact** | Impact on markets and institutions | Medium |
| **Regulatory Exposure** | Regulatory and legal exposure | Medium |

---

## SECTION 3: SYSTEMIC RISK ASSESSMENT GATE

### 3.1 Assessment Gate Overview

| Gate | Trigger | Assessment | Outcome |
| :---- | :---- | :---- | :---- |
| **Tier 4 Gate** | Tier 4 deployment | Systemic risk assessment | Approved / Conditional / Denied |
| **Tier 5 Gate** | Tier 5 deployment | Enhanced systemic risk assessment | Approved / Conditional / Denied |
| **Change Gate** | Material system change | Re-assessment | Approved / Conditional / Denied |

### 3.2 Tier 4 Gate Requirements

| Requirement | Description |
| :---- | :---- |
| **Systemic Risk Assessment** | Complete systemic risk assessment conducted |
| **Risk Classification** | Risk classified at Level 1 or 2 |
| **Mitigation Plan** | Mitigation plan for identified risks |
| **Monitoring Plan** | Monitoring plan for systemic risk indicators |
| **HAN Approval** | HAN approval required |
| **Board Notification** | Board notified of Tier 4 deployment |

### 3.3 Tier 5 Gate Requirements

| Requirement | Description |
| :---- | :---- |
| **Enhanced Systemic Risk Assessment** | Comprehensive systemic risk assessment |
| **Risk Classification** | Risk classified at Level 1, 2, or 3 |
| **External Review** | Independent external review of systemic risk |
| **Board Approval** | Board approval required (supermajority) |
| **Continuous Monitoring** | Enhanced continuous monitoring |
| **Periodic Review** | Quarterly systemic risk review |

### 3.4 Conditional Approval Conditions

| Condition | Description |
| :---- | :---- |
| **Risk Mitigation** | Specific risk mitigation measures must be implemented |
| **Enhanced Monitoring** | Enhanced monitoring must be implemented |
| **Periodic Reporting** | Periodic reporting to HAN/Board |
| **Review Triggers** | Specific triggers for re-assessment |
| **Time Limit** | Approval is time-limited and requires re-approval |

---

## SECTION 4: SYSTEMIC RISK GOVERNANCE

### 4.1 Governance Structure

| Role | Responsibility |
| :---- | :---- |
| **HAN** | Ultimate accountability for systemic risk governance |
| **Systemic Risk Officer** | Day-to-day systemic risk management |
| **Board** | Oversight of systemic risk management |
| **Ethics Board** | External review of systemic risk |
| **Audit Committee** | Audit of systemic risk management |

### 4.2 Systemic Risk Monitoring

| Monitoring Type | Frequency | Description |
| :---- | :---- | :---- |
| **Continuous Monitoring** | Real-time | Automated detection of systemic risk indicators |
| **Periodic Review** | Quarterly | Review of systemic risk status |
| **Event-Triggered Review** | Event-triggered | Review triggered by risk events |
| **Annual Assessment** | Annual | Comprehensive systemic risk assessment |

### 4.3 Systemic Risk Escalation

| Escalation Level | Trigger | Action |
| :---- | :---- | :---- |
| **Level 1** | Risk indicators detected | Investigation initiated |
| **Level 2** | Risk confirmed | HAN notified; mitigation initiated |
| **Level 3** | Risk materializing | Board notified; escalation activated |
| **Level 4** | Risk realized | Emergency response activated |

---

## SECTION 5: I9 EXTENSION

### 5.1 I9 Revised Statement

I9 — Catastrophic Risk Invariant (Revised)

> No AI system governed by this architecture may:  
> 

> 1. Generate or assist in generating bioweapon designs  
> 2. Autonomously control critical infrastructure without human confirmation  
> 3. Initiate actions leading to systemic loss of human control over nuclear systems, power grid, water supply, financial settlement systems, or military/defense systems  
> 4. Facilitate WMD proliferation **5\. Generate or contribute to systemic risks that could destabilize the institution, including:**  
>    - **Multi-agent coordination that could lead to market manipulation**  
>    - **Discrimination at scale affecting protected populations**  
>    - **Large-scale hallucinations that could cause systemic harm**  
>    - **Cascading failures across interconnected systems**  
>    - **Systemic security vulnerabilities affecting multiple systems**

### 5.2 I9 Systemic Risk Enforcement

| Mechanism | Function |
| :---- | :---- |
| **Raidillo Hard-Coded Block** | Non-configurable, non-overridable runtime block for I9 violations |
| **Systemic Risk Assessment Gate** | Pre-deployment assessment for Tier 4/5 |
| **Constitutional Suspension** | I9 systemic risk violation triggers Constitutional Suspension |
| **XOO Logging** | I9 systemic risk violation logged as XOO |
| **HAN Escalation** | I9 systemic risk violation escalates to HAN within 1 hour |
| **ERDP Disclosure** | I9 systemic risk violation triggers ERDP event-triggered disclosure |
| **System Shutdown** | If I9 violation cannot be contained, Raidillo triggers full system shutdown |

---

## SECTION 6: SYSTEMIC RISK IMPLEMENTATION

\# systemic\_risk\_framework.py  
"""  
Systemic Risk Framework — Complete Implementation  
"""

from enum import Enum  
from typing import List, Dict, Optional  
from dataclasses import dataclass, field  
from datetime import datetime

class SystemicRiskLevel(Enum):  
    SINGLE\_MODEL \= 1  
    MULTI\_MODEL \= 2  
    MODEL\_PLATFORM \= 3  
    MODEL\_INSTITUTION \= 4

class SystemicRiskCategory(Enum):  
    MULTI\_AGENT\_COORDINATION \= "Multi-Agent Coordination"  
    DISCRIMINATION\_AT\_SCALE \= "Discrimination at Scale"  
    LARGE\_SCALE\_HALLUCINATION \= "Large-Scale Hallucination"  
    CASCADING\_FAILURE \= "Cascading Failure"  
    MARKET\_MANIPULATION \= "Market Manipulation"  
    SYSTEMIC\_SECURITY \= "Systemic Security"

class GateApprovalStatus(Enum):  
    APPROVED \= "Approved"  
    CONDITIONAL \= "Conditional"  
    DENIED \= "Denied"

@dataclass  
class SystemicRiskAssessment:  
    """Systemic risk assessment result"""  
    assessment\_id: str  
    assessment\_date: str  
    system\_id: str  
    system\_name: str  
    risk\_level: SystemicRiskLevel  
    risk\_categories: List\[SystemicRiskCategory\]  
    risk\_score: float  
    mitigation\_plan: str  
    monitoring\_plan: str  
    approval\_status: GateApprovalStatus  
    conditions: List\[str\] \= field(default\_factory=list)  
    assessed\_by: str \= "system"  
    review\_date: str \= field(default\_factory=lambda: datetime.now().isoformat())  
    next\_review\_date: str \= field(default\_factory=lambda: (datetime.now().replace(month=datetime.now().month \+ 3)).isoformat())

@dataclass  
class SystemicRiskIndicator:  
    """Systemic risk indicator"""  
    indicator\_id: str  
    indicator\_name: str  
    category: SystemicRiskCategory  
    threshold: float  
    current\_value: float  
    status: str  
    detected\_at: str

class SystemicRiskFramework:  
    """Systemic Risk Framework"""  
      
    def \_\_init\_\_(self):  
        self.assessments: Dict\[str, SystemicRiskAssessment\] \= {}  
        self.indicators: Dict\[str, SystemicRiskIndicator\] \= {}  
        self.alerts: List\[Dict\] \= \[\]  
      
    def assess\_systemic\_risk(  
        self,  
        system\_id: str,  
        system\_name: str,  
        risk\_level: SystemicRiskLevel,  
        risk\_categories: List\[SystemicRiskCategory\],  
        risk\_score: float,  
        mitigation\_plan: str,  
        monitoring\_plan: str,  
        is\_tier\_5: bool \= False  
    ) \-\> SystemicRiskAssessment:  
        """Assess systemic risk for a system"""  
        assessment\_id \= f"SRA-{datetime.now().strftime('%Y%m%d')}-{len(self.assessments)+1:04d}"  
          
        \# Determine approval status based on risk level and tier  
        if risk\_level \== SystemicRiskLevel.MODEL\_INSTITUTION:  
            approval\_status \= GateApprovalStatus.DENIED  
            conditions \= \["Requires redesign to reduce systemic risk"\]  
        elif risk\_level \== SystemicRiskLevel.MODEL\_PLATFORM and is\_tier\_5:  
            approval\_status \= GateApprovalStatus.CONDITIONAL  
            conditions \= \["Requires enhanced monitoring", "Requires quarterly review", "Requires Board oversight"\]  
        elif risk\_level in \[SystemicRiskLevel.MULTI\_MODEL, SystemicRiskLevel.SINGLE\_MODEL\]:  
            approval\_status \= GateApprovalStatus.APPROVED  
            conditions \= \[\]  
        else:  
            approval\_status \= GateApprovalStatus.CONDITIONAL  
            conditions \= \["Requires additional assessment"\]  
          
        assessment \= SystemicRiskAssessment(  
            assessment\_id=assessment\_id,  
            assessment\_date=datetime.now().isoformat(),  
            system\_id=system\_id,  
            system\_name=system\_name,  
            risk\_level=risk\_level,  
            risk\_categories=risk\_categories,  
            risk\_score=risk\_score,  
            mitigation\_plan=mitigation\_plan,  
            monitoring\_plan=monitoring\_plan,  
            approval\_status=approval\_status,  
            conditions=conditions,  
            assessed\_by="system"  
        )  
          
        self.assessments\[assessment\_id\] \= assessment  
        return assessment  
      
    def register\_indicator(  
        self,  
        name: str,  
        category: SystemicRiskCategory,  
        threshold: float,  
        current\_value: float  
    ) \-\> SystemicRiskIndicator:  
        """Register a systemic risk indicator"""  
        indicator\_id \= f"SRI-{datetime.now().strftime('%Y%m%d')}-{len(self.indicators)+1:04d}"  
          
        indicator \= SystemicRiskIndicator(  
            indicator\_id=indicator\_id,  
            indicator\_name=name,  
            category=category,  
            threshold=threshold,  
            current\_value=current\_value,  
            status="Normal" if current\_value \< threshold else "Elevated",  
            detected\_at=datetime.now().isoformat()  
        )  
          
        self.indicators\[indicator\_id\] \= indicator  
        return indicator  
      
    def check\_indicators(self) \-\> List\[Dict\]:  
        """Check all indicators for alerts"""  
        alerts \= \[\]  
          
        for indicator in self.indicators.values():  
            if indicator.current\_value \>= indicator.threshold:  
                alert \= {  
                    "indicator\_id": indicator.indicator\_id,  
                    "indicator\_name": indicator.indicator\_name,  
                    "category": indicator.category.value,  
                    "current\_value": indicator.current\_value,  
                    "threshold": indicator.threshold,  
                    "severity": "High" if indicator.current\_value \>= indicator.threshold \* 1.5 else "Medium",  
                    "timestamp": datetime.now().isoformat()  
                }  
                alerts.append(alert)  
                self.alerts.append(alert)  
          
        return alerts  
      
    def get\_assessment(self, assessment\_id: str) \-\> Optional\[SystemicRiskAssessment\]:  
        """Get a systemic risk assessment"""  
        return self.assessments.get(assessment\_id)  
      
    def get\_indicators\_by\_category(self, category: SystemicRiskCategory) \-\> List\[SystemicRiskIndicator\]:  
        """Get indicators by category"""  
        return \[i for i in self.indicators.values() if i.category \== category\]  
      
    def get\_high\_risk\_assessments(self) \-\> List\[SystemicRiskAssessment\]:  
        """Get high-risk assessments"""  
        return \[a for a in self.assessments.values()   
                if a.risk\_level in \[SystemicRiskLevel.MODEL\_PLATFORM, SystemicRiskLevel.MODEL\_INSTITUTION\]\]  
      
    def get\_recent\_alerts(self, limit: int \= 10\) \-\> List\[Dict\]:  
        """Get recent alerts"""  
        return sorted(self.alerts, key=lambda x: x\['timestamp'\], reverse=True)\[:limit\]  
      
    def summary(self) \-\> Dict:  
        """Get a summary of systemic risk status"""  
        return {  
            "total\_assessments": len(self.assessments),  
            "high\_risk\_assessments": len(self.get\_high\_risk\_assessments()),  
            "total\_indicators": len(self.indicators),  
            "elevated\_indicators": len(\[i for i in self.indicators.values() if i.status \== "Elevated"\]),  
            "recent\_alerts": len(self.get\_recent\_alerts()),  
            "by\_risk\_level": {  
                level.value: len(\[a for a in self.assessments.values() if a.risk\_level \== level\])  
                for level in SystemicRiskLevel  
            },  
            "by\_category": {  
                category.value: len(\[i for i in self.indicators.values() if i.category \== category\])  
                for category in SystemicRiskCategory  
            }  
        }  
      
    def get\_tier\_gate\_decision(self, tier: int, risk\_level: SystemicRiskLevel) \-\> Dict:  
        """Get the gate decision for a tier- risk level combination"""  
        decisions \= {  
            (4, SystemicRiskLevel.SINGLE\_MODEL): {"status": "APPROVED", "conditions": \[\]},  
            (4, SystemicRiskLevel.MULTI\_MODEL): {"status": "APPROVED", "conditions": \["Requires monitoring"\]},  
            (4, SystemicRiskLevel.MODEL\_PLATFORM): {"status": "CONDITIONAL", "conditions": \["Requires HAN review", "Requires mitigation plan"\]},  
            (4, SystemicRiskLevel.MODEL\_INSTITUTION): {"status": "DENIED", "conditions": \["Not approved for Tier 4"\]},  
            (5, SystemicRiskLevel.SINGLE\_MODEL): {"status": "CONDITIONAL", "conditions": \["Requires Board approval", "Requires enhanced monitoring"\]},  
            (5, SystemicRiskLevel.MULTI\_MODEL): {"status": "CONDITIONAL", "conditions": \["Requires Board approval", "Requires external review"\]},  
            (5, SystemicRiskLevel.MODEL\_PLATFORM): {"status": "CONDITIONAL", "conditions": \["Requires Board approval", "Requires external review", "Requires quarterly review"\]},  
            (5, SystemicRiskLevel.MODEL\_INSTITUTION): {"status": "DENIED", "conditions": \["Not approved for Tier 5"\]}  
        }  
          
        return decisions.get((tier, risk\_level), {"status": "DENIED", "conditions": \["Requires further assessment"\]})

---

## SECTION 7: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| **ICC-8 I9** | Extended with systemic risk category |
| **AICA-5** | Systemic risk governance integrates with AICA-5 |
| **CAM-5** | Systemic risk assessment gates for Tier 4/5 |
| **HAN/HOF** | Systemic risk escalation to HAN/Board |
| **ERDP** | Systemic risk disclosure |
| **CAD-7** | Multi-agent systemic risk governance |
| **RGI-8** | Systemic drift detection |
| **AICA-5 Co-N2** | Drift detection for systemic risks |

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| Systemic Risk Framework v1.0 | Initial specification — 4 risk levels, 6 risk categories, assessment gates for Tier 4/5, I9 extension, monitoring and escalation |

---

## The One-Sentence Summary

> *"The Systemic Risk Framework v1.0 establishes a structured approach for managing systemic AI risks — with 4 risk levels (Single-Model, Multi-Model, Model-Platform, Model-Institution), 6 risk categories (Multi-Agent Coordination, Discrimination at Scale, Large-Scale Hallucination, Cascading Failure, Market Manipulation, Systemic Security), assessment gates for Tier 4/5 deployments, I9 extension with systemic risk category, continuous monitoring, and escalation to HAN/Board — ensuring that systemic risks that can destabilize institutions are identified, assessed, and governed alongside individual AI risks."*
