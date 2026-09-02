# Real-time Evidence Streaming v1.0

**Status:** Built — v1.0  
**Type:** Compliance Instrument  
**Parent Stack:** AIGIS Compliance Engine / Audit Evidence Engine  
**Version:** 1.0

---

## PREAMBLE

The Real-time Evidence Streaming framework transforms the Audit Evidence Engine from a batch-oriented system into a continuous, real-time evidence generation and streaming system. It answers: *How do we generate, stream, and consume compliance evidence in real-time, rather than as periodic batch packets?*

IMP logs continuously and Pre-Delivery Log Entries create audit artifacts before every action. But evidence packets are currently generated periodically (batch mode). Real-time Evidence Streaming enables continuous evidence generation, streaming evidence APIs, real-time compliance dashboards, and immediate gap detection — turning compliance from a periodic exercise into a continuous, monitorable state.

**The core insight:** Compliance is not a point-in-time event — it is a continuous state. Real-time evidence streaming makes compliance visible, monitorable, and actionable in real-time, enabling immediate detection of compliance gaps and faster response to regulatory requirements.

---

## SECTION 1: PURPOSE AND SCOPE

### Purpose

Real-time Evidence Streaming ensures that:

1. **Evidence is generated continuously** — Evidence is generated in real-time, not in batches  
2. **Evidence is streamed** — Evidence is streamed to consumers via APIs  
3. **Evidence is aggregated continuously** — Evidence is aggregated into real-time dashboards  
4. **Gaps are detected in real-time** — Compliance gaps are detected immediately  
5. **Alerts are real-time** — Compliance alerts are generated in real-time  
6. **Evidence is consumable** — Evidence is consumable via streaming APIs and dashboards

### Scope

| In Scope | Out of Scope |
| :---- | :---- |
| Continuous evidence generation | Evidence packet generation (Audit Evidence Engine) |
| Real-time evidence streaming | Manual evidence review |
| Real-time compliance dashboards | Periodic compliance reporting (ERDP) |
| Real-time gap detection | Legal interpretation |
| Real-time alerts | Commercial compliance products |

### Streaming vs. Batch

| Aspect | Batch (Current) | Streaming (New) |
| :---- | :---- | :---- |
| **Generation** | Periodic (daily/weekly) | Continuous (real-time) |
| **Latency** | Hours to days | Milliseconds to seconds |
| **Consumption** | Pull-based (download) | Push-based (streaming API) |
| **Dashboards** | Periodic updates | Real-time updates |
| **Gap Detection** | Periodic | Real-time |
| **Alerts** | Periodic | Real-time |

### Governing Relationships

| Instrument | Relationship |
| :---- | :---- |
| **IMP** | Source of continuous evidence |
| **Audit Evidence Engine** | Extended with streaming capabilities |
| **Compliance Crosswalk Engine** | Used for real-time gap detection |
| **MCR** | Controls for real-time coverage |
| **Raidillo** | Real-time action interception and logging |
| **Compliance Dashboard** | Real-time dashboard updates |

---

## SECTION 2: STREAMING ARCHITECTURE

### 2.1 Architecture Overview

┌─────────────────────────────────────────────────────────────────────────────┐  
│                    REAL-TIME EVIDENCE STREAMING                             │  
├─────────────────────────────────────────────────────────────────────────────┤  
│                                                                             │  
│  ┌─────────────────────────────────────────────────────────────────────────┐│  
│  │                    1\. EVIDENCE GENERATORS                               ││  
│  │  • IMP Object Capture (continuous)                                      ││  
│  │  • ADTEP Pre-Delivery Log Entry (pre-action)                            ││  
│  │  • AICA-5 Measurement Framework (continuous)                            ││  
│  │  • RGI-8 Drift Detection (continuous)                                   ││  
│  │  • AOBA Bias Detection (continuous)                                     ││  
│  └─────────────────────────────────────────────────────────────────────────┘│  
│                                      │                                      │  
│                                      ▼                                      │  
│  ┌─────────────────────────────────────────────────────────────────────────┐│  
│  │                    2\. EVIDENCE STREAMING ENGINE                         ││  
│  │  • Evidence transformation                                              ││  
│  │  • Control mapping                                                      ││  
│  │  • Compliance verification                                              ││  
│  │  • Gap detection                                                        ││  
│  └─────────────────────────────────────────────────────────────────────────┘│  
│                                      │                                      │  
│                                      ▼                                      │  
│  ┌─────────────────────────────────────────────────────────────────────────┐│  
│  │                    3\. STREAMING OUTPUTS                                 ││  
│  │  • Streaming API (SSE / WebSocket)                                      ││  
│  │  • Real-time dashboard                                                  ││  
│  │  • Real-time alerts                                                     ││  
│  │  • Continuous evidence store                                            ││  
│  └─────────────────────────────────────────────────────────────────────────┘│  
└─────────────────────────────────────────────────────────────────────────────┘

### 2.2 Streaming Pipeline

| Stage | Description | Components |
| :---- | :---- | :---- |
| **Capture** | Continuous evidence capture | IMP, ADTEP, AICA-5, RGI-8, AOBA |
| **Transform** | Evidence transformation and normalization | Evidence Transformer |
| **Map** | Map evidence to MCR controls | Control Mapper |
| **Verify** | Verify compliance against controls | Compliance Verifier |
| **Detect** | Detect compliance gaps | Gap Detector |
| **Stream** | Stream to consumers | Streaming Engine |
| **Store** | Store in continuous evidence store | Evidence Store |

---

## SECTION 3: EVIDENCE GENERATORS

### 3.1 Continuous Evidence Generators

| Generator | Source | Frequency | Evidence Type |
| :---- | :---- | :---- | :---- |
| **DRO Generator** | IMP DRO records | Per decision | Decision evidence |
| **GAO Generator** | IMP GAO records | Per artifact | Artifact evidence |
| **OEO Generator** | IMP OEO records | Per outcome | Outcome evidence |
| **XOO Generator** | IMP XOO records | Per exception | Exception evidence |
| **Pre-Delivery Log Generator** | ADTEP | Per action | Action evidence |
| **Drift Detection Generator** | RGI-8 | Continuous | Drift evidence |
| **Bias Detection Generator** | AOBA | Continuous | Bias evidence |

### 3.2 Evidence Stream Schema

| \# | Field | Type | Description |
| :---- | :---- | :---- | :---- |
| 1 | `stream_id` | String | Unique stream identifier |
| 2 | `timestamp` | ISO 8601 | Evidence timestamp |
| 3 | `evidence_type` | Enum | DRO / GAO / OEO / XOO / PreDelivery / Drift / Bias |
| 4 | `control_id` | String | MCR control ID (mapped) |
| 5 | `framework` | String | Regulatory framework (if applicable) |
| 6 | `compliance_status` | Enum | Compliant / Non-Compliant / Partial |
| 7 | `raw_evidence` | Object | Raw evidence data |
| 8 | `mapped_evidence` | Object | Evidence mapped to control |
| 9 | `gaps` | List | Identified gaps |
| 10 | `hash` | String | Evidence hash |

---

## SECTION 4: REAL-TIME COMPLIANCE VERIFICATION

### 4.1 Verification Flow

Evidence Captured  
  │  
  ▼  
Control Mapping  
  │  Map evidence to MCR control  
  ▼  
Framework Mapping  
  │  Map control to regulatory framework  
  ▼  
Compliance Verification  
  │  Verify against framework requirements  
  ▼  
Gap Detection  
  │  Detect any gaps  
  ▼  
Alert Generation (if gap)  
  │  Generate real-time alert  
  ▼  
Stream Output  
  │  Stream to consumers

### 4.2 Gap Detection

| Gap Type | Description | Detection |
| :---- | :---- | :---- |
| **Missing Evidence** | No evidence for a control | Real-time detection |
| **Incomplete Evidence** | Evidence missing required fields | Real-time detection |
| **Non-Compliant Evidence** | Evidence violates control | Real-time detection |
| **Control Gap** | No control mapping | Real-time detection |
| **Framework Gap** | No framework mapping | Real-time detection |

### 4.3 Alert Types

| Alert Type | Description | Severity | Response |
| :---- | :---- | :---- | :---- |
| **Missing Evidence** | Evidence expected but not found | High | Immediate investigation |
| **Non-Compliant Action** | Action violates control | Critical | Immediate escalation |
| **Control Coverage Gap** | Control has no evidence | Medium | Review required |
| **Framework Coverage Gap** | Framework has no evidence | Medium | Review required |

---

## SECTION 5: STREAMING IMPLEMENTATION

\# realtime\_evidence\_streaming.py  
"""  
Real-time Evidence Streaming — Complete Implementation  
"""

from enum import Enum  
from typing import List, Dict, Optional, Any  
from dataclasses import dataclass, field  
from datetime import datetime  
import json  
import hashlib  
import asyncio  
from collections import deque

class EvidenceType(Enum):  
    DRO \= "DRO"  
    GAO \= "GAO"  
    OEO \= "OEO"  
    XOO \= "XOO"  
    PRE\_DELIVERY \= "PreDelivery"  
    DRIFT \= "Drift"  
    BIAS \= "Bias"

class ComplianceStatus(Enum):  
    COMPLIANT \= "Compliant"  
    NON\_COMPLIANT \= "Non-Compliant"  
    PARTIAL \= "Partial"  
    PENDING \= "Pending"

class AlertSeverity(Enum):  
    INFO \= "Info"  
    LOW \= "Low"  
    MEDIUM \= "Medium"  
    HIGH \= "High"  
    CRITICAL \= "Critical"

@dataclass  
class EvidenceStream:  
    """A real-time evidence stream entry"""  
    stream\_id: str  
    timestamp: str  
    evidence\_type: EvidenceType  
    control\_id: str  
    framework: Optional\[str\]  
    compliance\_status: ComplianceStatus  
    raw\_evidence: Dict\[str, Any\]  
    mapped\_evidence: Dict\[str, Any\]  
    gaps: List\[Dict\]  
    hash: str

@dataclass  
class ComplianceAlert:  
    """A real-time compliance alert"""  
    alert\_id: str  
    timestamp: str  
    alert\_type: str  
    severity: AlertSeverity  
    description: str  
    evidence\_reference: str  
    control\_id: str  
    framework: Optional\[str\]  
    resolution: Optional\[str\] \= None

class RealtimeEvidenceStreaming:  
    """Real-time Evidence Streaming Framework"""  
      
    def \_\_init\_\_(self, imp\_store, mcr, crosswalk):  
        self.imp \= imp\_store  
        self.mcr \= mcr  
        self.crosswalk \= crosswalk  
        self.stream\_buffer \= deque(maxlen=10000)  \# Last 10,000 stream entries  
        self.alerts \= deque(maxlen=1000)  \# Last 1,000 alerts  
        self.subscribers \= \[\]  \# Active subscribers (for streaming API)  
        self.evidence\_count \= 0  
      
    def process\_evidence(  
        self,  
        evidence\_type: EvidenceType,  
        raw\_evidence: Dict\[str, Any\],  
        source: str \= "system"  
    ) \-\> EvidenceStream:  
        """  
        Process evidence in real-time.  
          
        Args:  
            evidence\_type: Type of evidence  
            raw\_evidence: Raw evidence data  
            source: Source of evidence  
          
        Returns:  
            EvidenceStream: Processed evidence stream entry  
        """  
        self.evidence\_count \+= 1  
          
        \# Step 1: Map evidence to MCR control  
        control\_id, mapped\_evidence \= self.\_map\_to\_control(raw\_evidence)  
          
        \# Step 2: Map control to framework  
        framework \= self.\_map\_to\_framework(control\_id)  
          
        \# Step 3: Verify compliance  
        compliance\_status, gaps \= self.\_verify\_compliance(  
            control\_id, framework, mapped\_evidence  
        )  
          
        \# Step 4: Generate stream entry  
        stream\_id \= f"STREAM-{datetime.now().strftime('%Y%m%d%H%M%S')}-{self.evidence\_count:06d}"  
          
        stream \= EvidenceStream(  
            stream\_id=stream\_id,  
            timestamp=datetime.now().isoformat(),  
            evidence\_type=evidence\_type,  
            control\_id=control\_id,  
            framework=framework,  
            compliance\_status=compliance\_status,  
            raw\_evidence=raw\_evidence,  
            mapped\_evidence=mapped\_evidence,  
            gaps=gaps,  
            hash=self.\_compute\_hash(stream\_id, raw\_evidence, control\_id)  
        )  
          
        \# Step 5: Add to stream buffer  
        self.stream\_buffer.append(stream)  
          
        \# Step 6: Generate alerts if gaps found  
        if gaps:  
            self.\_generate\_alerts(stream)  
          
        \# Step 7: Notify subscribers  
        self.\_notify\_subscribers(stream)  
          
        return stream  
      
    def \_map\_to\_control(self, raw\_evidence: Dict\[str, Any\]) \-\> tuple:  
        """Map evidence to an MCR control"""  
        \# In production, this would perform actual mapping  
        \# For example, based on evidence type, source, etc.  
          
        \# Simple mapping based on evidence type  
        mapping \= {  
            "DRO": "AICA-5-CN-021",  \# Decision Lineage  
            "GAO": "IMP-003",          \# Governance Artifact  
            "OEO": "AICA-5-CN-023",    \# Outcome Validation  
            "XOO": "IMP-006",          \# Exception/Override  
            "PreDelivery": "ADTEP-003", \# Pre-Delivery Log  
            "Drift": "AICA-5-CN-017",   \# Drift Detection  
            "Bias": "AOBA-001"          \# Bias Audit  
        }  
          
        evidence\_type \= raw\_evidence.get("evidence\_type", "UNKNOWN")  
        control\_id \= mapping.get(evidence\_type, "UNKNOWN")  
          
        return control\_id, {  
            "original": raw\_evidence,  
            "mapped\_to": control\_id,  
            "timestamp": datetime.now().isoformat()  
        }  
      
    def \_map\_to\_framework(self, control\_id: str) \-\> Optional\[str\]:  
        """Map a control to a regulatory framework"""  
        \# In production, use crosswalk engine  
        mappings \= self.crosswalk.map\_component\_to\_framework(control\_id, "eu\_ai\_act")  
        if mappings:  
            return "eu\_ai\_act"  
          
        \# Check other frameworks  
        for framework in \["nist\_ai\_rmf", "iso\_42001", "pfrs\_s1\_s2"\]:  
            mappings \= self.crosswalk.map\_component\_to\_framework(control\_id, framework)  
            if mappings:  
                return framework  
          
        return None  
      
    def \_verify\_compliance(  
        self,  
        control\_id: str,  
        framework: Optional\[str\],  
        mapped\_evidence: Dict\[str, Any\]  
    ) \-\> tuple:  
        """Verify compliance against control and framework"""  
        gaps \= \[\]  
          
        \# Check if control exists  
        control \= self.mcr.get\_control(control\_id)  
        if not control:  
            gaps.append({  
                "gap\_type": "Control Gap",  
                "description": f"Control {control\_id} not found in MCR",  
                "severity": AlertSeverity.HIGH  
            })  
            return ComplianceStatus.NON\_COMPLIANT, gaps  
          
        \# Check if framework mapping exists  
        if framework:  
            mappings \= self.crosswalk.map\_component\_to\_framework(control\_id, framework)  
            if not mappings:  
                gaps.append({  
                    "gap\_type": "Framework Gap",  
                    "description": f"No mapping from {control\_id} to {framework}",  
                    "severity": AlertSeverity.MEDIUM  
                })  
          
        \# Check evidence completeness  
        required\_fields \= self.\_get\_required\_fields(control\_id)  
        missing\_fields \= \[f for f in required\_fields if f not in mapped\_evidence\]  
        if missing\_fields:  
            gaps.append({  
                "gap\_type": "Missing Evidence",  
                "description": f"Missing fields: {', '.join(missing\_fields)}",  
                "severity": AlertSeverity.MEDIUM  
            })  
          
        \# Determine compliance status  
        if not gaps:  
            return ComplianceStatus.COMPLIANT, \[\]  
        elif any(g\["severity"\] \== AlertSeverity.HIGH for g in gaps):  
            return ComplianceStatus.NON\_COMPLIANT, gaps  
        else:  
            return ComplianceStatus.PARTIAL, gaps  
      
    def \_get\_required\_fields(self, control\_id: str) \-\> List\[str\]:  
        """Get required fields for a control"""  
        \# In production, define required fields per control  
        return \["timestamp", "agent\_id", "action\_type"\]  
      
    def \_compute\_hash(self, stream\_id: str, evidence: Dict, control\_id: str) \-\> str:  
        """Compute a hash for the evidence stream entry"""  
        data \= {  
            "stream\_id": stream\_id,  
            "evidence": evidence,  
            "control\_id": control\_id,  
            "timestamp": datetime.now().isoformat()  
        }  
        return hashlib.sha256(json.dumps(data, sort\_keys=True).encode()).hexdigest()  
      
    def \_generate\_alerts(self, stream: EvidenceStream):  
        """Generate alerts for gaps"""  
        for gap in stream.gaps:  
            alert \= ComplianceAlert(  
                alert\_id=f"ALERT-{datetime.now().strftime('%Y%m%d%H%M%S')}-{len(self.alerts)+1:06d}",  
                timestamp=datetime.now().isoformat(),  
                alert\_type=gap\["gap\_type"\],  
                severity=gap\["severity"\],  
                description=gap\["description"\],  
                evidence\_reference=stream.stream\_id,  
                control\_id=stream.control\_id,  
                framework=stream.framework  
            )  
            self.alerts.append(alert)  
      
    def \_notify\_subscribers(self, stream: EvidenceStream):  
        """Notify subscribers of new evidence"""  
        \# In production, this would use SSE/WebSocket  
        \# For now, just add to buffer  
        pass  
      
    def get\_stream(self, limit: int \= 100\) \-\> List\[EvidenceStream\]:  
        """Get recent evidence streams"""  
        return list(self.stream\_buffer)\[-limit:\]  
      
    def get\_alerts(  
        self,  
        severity: Optional\[AlertSeverity\] \= None,  
        limit: int \= 100  
    ) \-\> List\[ComplianceAlert\]:  
        """Get recent alerts"""  
        alerts \= list(self.alerts)\[-limit:\]  
        if severity:  
            alerts \= \[a for a in alerts if a.severity \== severity\]  
        return alerts  
      
    def get\_compliance\_summary(self) \-\> Dict:  
        """Get real-time compliance summary"""  
        recent \= list(self.stream\_buffer)\[-1000:\]  \# Last 1000 entries  
          
        if not recent:  
            return {  
                "total\_evidence": 0,  
                "compliance\_rate": 0,  
                "gaps": 0,  
                "alerts": 0  
            }  
          
        compliant \= len(\[s for s in recent if s.compliance\_status \== ComplianceStatus.COMPLIANT\])  
        total \= len(recent)  
        gaps \= len(\[s for s in recent if s.gaps\])  
          
        return {  
            "total\_evidence": total,  
            "compliance\_rate": (compliant / total) \* 100 if total \> 0 else 0,  
            "gaps": gaps,  
            "alerts": len(self.alerts),  
            "by\_framework": self.\_get\_framework\_summary(recent),  
            "by\_control": self.\_get\_control\_summary(recent)  
        }  
      
    def \_get\_framework\_summary(self, entries: List\[EvidenceStream\]) \-\> Dict:  
        """Get summary by framework"""  
        summary \= {}  
        for entry in entries:  
            framework \= entry.framework or "Unmapped"  
            if framework not in summary:  
                summary\[framework\] \= {  
                    "total": 0,  
                    "compliant": 0,  
                    "gaps": 0  
                }  
            summary\[framework\]\["total"\] \+= 1  
            if entry.compliance\_status \== ComplianceStatus.COMPLIANT:  
                summary\[framework\]\["compliant"\] \+= 1  
            if entry.gaps:  
                summary\[framework\]\["gaps"\] \+= 1  
        return summary  
      
    def \_get\_control\_summary(self, entries: List\[EvidenceStream\]) \-\> Dict:  
        """Get summary by control"""  
        summary \= {}  
        for entry in entries:  
            control\_id \= entry.control\_id  
            if control\_id not in summary:  
                summary\[control\_id\] \= {  
                    "total": 0,  
                    "compliant": 0,  
                    "gaps": 0  
                }  
            summary\[control\_id\]\["total"\] \+= 1  
            if entry.compliance\_status \== ComplianceStatus.COMPLIANT:  
                summary\[control\_id\]\["compliant"\] \+= 1  
            if entry.gaps:  
                summary\[control\_id\]\["gaps"\] \+= 1  
        return summary  
      
    def get\_gap\_analysis(self) \-\> Dict:  
        """Get real-time gap analysis"""  
        gaps\_by\_type \= {}  
        for alert in self.alerts:  
            if alert.alert\_type not in gaps\_by\_type:  
                gaps\_by\_type\[alert.alert\_type\] \= {  
                    "count": 0,  
                    "severity": alert.severity.value,  
                    "examples": \[\]  
                }  
            gaps\_by\_type\[alert.alert\_type\]\["count"\] \+= 1  
            if len(gaps\_by\_type\[alert.alert\_type\]\["examples"\]) \< 3:  
                gaps\_by\_type\[alert.alert\_type\]\["examples"\].append(alert.description)  
          
        return {  
            "total\_gaps": len(self.alerts),  
            "by\_type": gaps\_by\_type,  
            "critical\_gaps": len(\[a for a in self.alerts if a.severity \== AlertSeverity.CRITICAL\])  
        }  
      
    def create\_streaming\_endpoint(self) \-\> Dict:  
        """  
        Create a streaming endpoint for real-time evidence consumption.  
        Returns endpoint configuration.  
        """  
        return {  
            "endpoint": "/api/v1/evidence/stream",  
            "protocol": "SSE",  
            "format": "json",  
            "filters": \["control\_id", "framework", "compliance\_status"\],  
            "sample": {  
                "stream\_id": "STREAM-20260901120000-000001",  
                "timestamp": "2026-09-01T12:00:00Z",  
                "evidence\_type": "DRO",  
                "control\_id": "AICA-5-CN-021",  
                "framework": "eu\_ai\_act",  
                "compliance\_status": "Compliant"  
            }  
        }

---

## SECTION 6: STREAMING API

### 6.1 Endpoints

| Endpoint | Method | Description |
| :---- | :---- | :---- |
| `/api/v1/evidence/stream` | GET | SSE streaming endpoint for real-time evidence |
| `/api/v1/evidence/stream/events` | GET | Get recent events |
| `/api/v1/evidence/stream/alerts` | GET | Get real-time alerts |
| `/api/v1/evidence/stream/summary` | GET | Get real-time compliance summary |
| `/api/v1/evidence/stream/gaps` | GET | Get real-time gap analysis |

### 6.2 Streaming Format

event: evidence  
data: {  
  "stream\_id": "STREAM-20260901120000-000001",  
  "timestamp": "2026-09-01T12:00:00Z",  
  "evidence\_type": "DRO",  
  "control\_id": "AICA-5-CN-021",  
  "framework": "eu\_ai\_act",  
  "compliance\_status": "Compliant",  
  "raw\_evidence": {...},  
  "gaps": \[\]  
}

event: alert  
data: {  
  "alert\_id": "ALERT-20260901120000-000001",  
  "timestamp": "2026-09-01T12:00:00Z",  
  "alert\_type": "Missing Evidence",  
  "severity": "High",  
  "description": "Evidence expected but not found for control AICA-5-CN-011",  
  "control\_id": "AICA-5-CN-011"  
}

---

## SECTION 7: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| **IMP** | Source of continuous evidence |
| **Audit Evidence Engine** | Extended with streaming capabilities |
| **Compliance Crosswalk Engine** | Used for real-time gap detection |
| **MCR** | Controls for real-time coverage |
| **Raidillo** | Real-time action interception and logging |
| **Compliance Dashboard** | Real-time dashboard updates |
| **AICA-5** | Continuous measurement framework |

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| Real-time Evidence Streaming v1.0 | Initial specification — streaming architecture, evidence generators, real-time compliance verification, gap detection, alerts, streaming API |

---

## The One-Sentence Summary

> *"Real-time Evidence Streaming v1.0 transforms the Audit Evidence Engine from batch to continuous — with 7 evidence generators (DRO, GAO, OEO, XOO, PreDelivery, Drift, Bias), real-time compliance verification, 4 gap types (Missing Evidence, Incomplete Evidence, Non-Compliant Evidence, Control/Framework Gaps), 5 alert severities (Info, Low, Medium, High, Critical), SSE streaming API, and real-time dashboards — enabling continuous compliance monitoring, immediate gap detection, and real-time regulatory alerts."*
