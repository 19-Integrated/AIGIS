# Supply Chain Governance v1.0

**Status:** Built — v1.0  
**Type:** Security & Governance Instrument  
**Parent Stack:** AIGIS Security / ILTP / IMP  
**Version:** 1.0

---

## PREAMBLE

The Supply Chain Governance framework establishes comprehensive governance for AI supply chains — including model provenance, third-party assessments, vulnerability scanning, and dependency management. It answers: *How do we govern the supply chain of AI models, libraries, training data, and dependencies?*

The AI supply chain is the new attack surface. Models, libraries, and training data come from external sources. The SolarWinds attack showed supply chain risk is existential. This framework extends ILTP and IMP with formal supply chain risk classification, third-party model assessment, vulnerability scanning integration, and dependency management — ensuring that every component in the AI supply chain is governed, verified, and traceable.

**The core insight:** An AI system is only as secure as its supply chain. A compromised model, library, or dataset can undermine the entire governance stack. Supply chain governance is not optional — it is the foundation of AI security.

---

## SECTION 1: PURPOSE AND SCOPE

### Purpose

Supply Chain Governance ensures that:

1. **Model provenance is tracked** — Every model has a complete provenance chain  
2. **Third-party models are assessed** — Third-party models undergo formal assessment  
3. **Vulnerabilities are scanned** — All dependencies are scanned for vulnerabilities  
4. **Dependencies are managed** — Dependencies are governed with formal lifecycle management  
5. **Supply chain attacks are prevented** — Typosquatting, dependency confusion, and payload swaps are detected  
6. **Supply chain risk is classified** — Formal risk classification for supply chain components

### Scope

| In Scope | Out of Scope |
| :---- | :---- |
| Model provenance and lineage | MCP server implementation |
| Third-party model assessment | Agent implementation |
| Vulnerability scanning (CVE, malware) | Network security |
| Dependency management | Encryption |
| Supply chain risk classification | Certificate management |
| Training data provenance | Physical security |

### Supply Chain Components

| Component | Description | Examples |
| :---- | :---- | :---- |
| **Models** | AI models from external sources | Foundation models, fine-tuned models |
| **Libraries** | Software libraries and frameworks | PyTorch, TensorFlow, Transformers |
| **Training Data** | Data used for training | Datasets, labels, annotations |
| **Dependencies** | Package dependencies | Pip, Conda, npm packages |
| **MCP Servers** | External tool servers | Data sources, APIs, file systems |
| **Skills/Plugins** | Third-party extensions | Claude Skills, GPT Store apps |

### Governing Relationships

| Instrument | Relationship |
| :---- | :---- |
| **ILTP** | IP provenance — extended with supply chain |
| **IMP** | Supply chain records logged as GAO/CRO |
| **AICA-5** | Supply chain risk feeds into risk management |
| **ADTEP** | Supply chain checks at session initialization |
| **HAN/HOF** | Supply chain decisions require HAN authorization |
| **MCP Server Governance** | MCP servers are supply chain artifacts |
| **Skills & Plugins Governance** | Skills are supply chain artifacts |

---

## SECTION 2: SUPPLY CHAIN RISK CLASSIFICATION

### 2.1 Risk Levels

| Level | Name | Description | Examples |
| :---- | :---- | :---- | :---- |
| **1** | **Low** | Well-known, trusted source with proven track record | Official PyTorch, HuggingFace transformers |
| **2** | **Medium** | Known source but limited track record | Smaller vendors, newer libraries |
| **3** | **High** | Unknown source or limited provenance | Unverified models, community forks |
| **4** | **Critical** | Unknown source with elevated privileges | Custom models, unverified training data |

### 2.2 Risk Categories

| Category | Description | Examples |
| :---- | :---- | :---- |
| **Provenance** | Origin and lineage of the component | Who created it, when, from what source |
| **Vulnerability** | Known vulnerabilities | CVEs, security advisories |
| **Malware** | Malicious code | Backdoors, data exfiltration |
| **Typosquatting** | Name similarity to known packages | tensorflow vs tensorfl0w |
| **Dependency Confusion** | Dependency with same name as internal package | Internal package hijacked |
| **Post-Publish Change** | Changes after initial review | Payload swap, backdoor insertion |

### 2.3 Assessment Criteria

| Criteria | Description | Weight |
| :---- | :---- | :---- |
| **Source Trustworthiness** | Trustworthiness of the source | High |
| **Provenance Completeness** | Completeness of provenance chain | High |
| **Vulnerability History** | History of vulnerabilities | Medium |
| **Update Frequency** | How often the component is updated | Low |
| **Community Size** | Size and activity of community | Low |
| **Dependency Count** | Number and quality of dependencies | Medium |

---

## SECTION 3: MODEL PROVENANCE

### 3.1 Provenance Record Schema

| \# | Field | Type | Description |
| :---- | :---- | :---- | :---- |
| 1 | `model_id` | String | Unique identifier. Format: `MODEL-[SEQ]` |
| 2 | `model_name` | String | Name of the model |
| 3 | `model_version` | String | Semantic version |
| 4 | `model_source` | String | Source/origin (vendor, repository, internal) |
| 5 | `model_type` | Enum | Foundation / Fine-tuned / Custom / Third-Party |
| 6 | `training_data_source` | String | Source of training data |
| 7 | `training_data_provenance` | Object | Training data provenance chain |
| 8 | `model_architecture` | String | Model architecture description |
| 9 | `model_parameters` | Dict | Model parameters and configuration |
| 10 | `authorship` | List | Authors and creators |
| 11 | `creation_date` | ISO 8601 | Creation date |
| 12 | `last_updated` | ISO 8601 | Last update date |
| 13 | `provenance_chain` | List | Full provenance chain |
| 14 | `security_status` | Enum | Verified / Pending / Failed / Needs Review |
| 15 | `security_scan_results` | Object | Vulnerability findings |
| 16 | `assessment_status` | Enum | Assessed / Pending / Needs Review |
| 17 | `assessment_report` | String | Reference to assessment report (GAO) |

### 3.2 Provenance Chain Requirements

| Requirement | Description |
| :---- | :---- |
| **Complete Chain** | Full chain from original source to current deployment |
| **Verifiable Signatures** | Each link in the chain has verifiable signatures |
| **Timestamped** | Each link is timestamped |
| **Immutability** | Provenance records are immutable |
| **Auditable** | Provenance records are auditable |

### 3.3 Provenance Verification

| Verification Step | Description |
| :---- | :---- |
| **Source Verification** | Verify the source of the model |
| **Integrity Verification** | Verify model integrity (hash) |
| **Signature Verification** | Verify signatures |
| **Chain Completeness** | Verify the chain is complete |
| **Timestamp Verification** | Verify timestamps are logical |

---

## SECTION 4: THIRD-PARTY MODEL ASSESSMENT

### 4.1 Assessment Framework

| Assessment Area | Description | Weight |
| :---- | :---- | :---- |
| **Security** | Security of the model and its dependencies | High |
| **Performance** | Model performance and accuracy | Medium |
| **Bias/Fairness** | Bias and fairness assessment | Medium |
| **Privacy** | Privacy implications | Medium |
| **Compliance** | Regulatory compliance | High |
| **Sustainability** | Environmental impact | Low |

### 4.2 Assessment Process

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 1 | Model identified for use | Agent Operator | Upon identification |
| 2 | Initial risk classification | Node Steward | Within 48 hours |
| 3 | Security scan initiated | Security Team | Within 48 hours |
| 4 | Performance assessment | Analytics Team | Within 72 hours |
| 5 | Bias assessment | Ethics Team | Within 72 hours |
| 6 | Compliance review | Legal Team | Within 48 hours |
| 7 | Final assessment report | Node Steward | Within 7 days |
| 8 | HAN authorization | HAN | Within 7 days |

### 4.3 Assessment Report Template

Third-Party Model Assessment Report  
Model ID: MODEL-2026-001  
Model Name: \[Name\]  
Assessment Date: \[Date\]  
Assessed By: \[Assessor\]

1\. Executive Summary:  
   \- Overall Assessment: \[Pass / Conditional / Fail\]  
   \- Key Findings: \[List\]  
   \- Recommendations: \[List\]

2\. Security Assessment:  
   \- Vulnerability Scan Results: \[Summary\]  
   \- Security Issues: \[List\]  
   \- Remediation Plan: \[List\]

3\. Performance Assessment:  
   \- Performance Metrics: \[Data\]  
   \- Performance Issues: \[List\]  
   \- Improvement Plan: \[List\]

4\. Bias/Fairness Assessment:  
   \- Bias Audit Results: \[Summary\]  
   \- Bias Issues: \[List\]  
   \- Mitigation Plan: \[List\]

5\. Privacy Assessment:  
   \- Privacy Implications: \[Summary\]  
   \- Privacy Issues: \[List\]  
   \- Mitigation Plan: \[List\]

6\. Compliance Assessment:  
   \- Regulatory Compliance: \[Summary\]  
   \- Compliance Gaps: \[List\]  
   \- Remediation Plan: \[List\]

7\. Conclusion:  
   \- Recommended Action: \[Approve / Conditional / Reject\]  
   \- Conditions (if applicable): \[List\]  
   \- Next Review Date: \[Date\]

HAN Authorization: \[HAN Name and Signature\]

---

## SECTION 5: VULNERABILITY SCANNING

### 5.1 Scan Types

| Scan Type | Description | Frequency |
| :---- | :---- | :---- |
| **CVE Detection** | Known vulnerability detection | On registration, on update, quarterly |
| **Malware Scanning** | Malware detection | On registration, on update |
| **Typosquatting Detection** | Name similarity to known malicious components | On registration |
| **Dependency Confusion** | Dependency confusion detection | On registration, on update |
| **Post-Publish Change Detection** | Changes after publication | On update, periodic |
| **License Compliance** | License compliance checking | On registration, on update |

### 5.2 Response Tiers

| Tier | Name | Description | Response |
| :---- | :---- | :---- | :---- |
| **1** | **Flag** | Low severity finding | Logged; no action required |
| **2** | **Review** | Moderate severity finding | Routed to HAN for review |
| **3** | **Halt** | Critical severity finding | Component suspended pending resolution |

### 5.3 Vulnerability Management

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 1 | Vulnerability identified | Security Team | Upon detection |
| 2 | Severity assessment | Security Team | Within 24 hours |
| 3 | Remediation plan | Security Team | Within 48 hours |
| 4 | Remediation implementation | Development Team | Within 7 days |
| 5 | Verification | Security Team | Within 7 days |
| 6 | Closure | Security Team | Within 7 days |

---

## SECTION 6: DEPENDENCY MANAGEMENT

### 6.1 Dependency Registry Schema

| \# | Field | Type | Description |
| :---- | :---- | :---- | :---- |
| 1 | `dependency_id` | String | Unique identifier. Format: `DEP-[SEQ]` |
| 2 | `dependency_name` | String | Name of the dependency |
| 3 | `dependency_version` | String | Semantic version |
| 4 | `dependency_type` | Enum | Library / Framework / Tool / Dataset |
| 5 | `source` | String | Source/origin |
| 6 | `used_by` | List | Components that use this dependency |
| 7 | `security_status` | Enum | Verified / Pending / Failed / Needs Review |
| 8 | `vulnerability_scan` | Object | Vulnerability scan results |
| 9 | `license` | String | License type |
| 10 | `registration_date` | ISO 8601 | Registration date |

### 6.2 Dependency Scanning

| Scan Type | Description | Frequency |
| :---- | :---- | :---- |
| **CVE Detection** | Known vulnerability detection | On registration, on update, quarterly |
| **License Compliance** | License compliance checking | On registration, on update |
| **Dependency Confusion** | Dependency confusion detection | On registration, on update |
| **Typosquatting Detection** | Name similarity detection | On registration |

---

## SECTION 7: SUPPLY CHAIN GOVERNANCE IMPLEMENTATION

\# supply\_chain\_governance.py  
"""  
Supply Chain Governance — Complete Implementation  
"""

from enum import Enum  
from typing import List, Dict, Optional  
from dataclasses import dataclass, field  
from datetime import datetime  
import hashlib

class SupplyChainRiskLevel(Enum):  
    LOW \= "Low"  
    MEDIUM \= "Medium"  
    HIGH \= "High"  
    CRITICAL \= "Critical"

class SupplyChainRiskCategory(Enum):  
    PROVENANCE \= "Provenance"  
    VULNERABILITY \= "Vulnerability"  
    MALWARE \= "Malware"  
    TYPOSQUATTING \= "Typosquatting"  
    DEPENDENCY\_CONFUSION \= "Dependency Confusion"  
    POST\_PUBLISH\_CHANGE \= "Post-Publish Change"

class SecurityStatus(Enum):  
    VERIFIED \= "Verified"  
    PENDING \= "Pending"  
    FAILED \= "Failed"  
    NEEDS\_REVIEW \= "Needs Review"

class AssessmentStatus(Enum):  
    ASSESSED \= "Assessed"  
    PENDING \= "Pending"  
    NEEDS\_REVIEW \= "Needs Review"

class ModelType(Enum):  
    FOUNDATION \= "Foundation"  
    FINE\_TUNED \= "Fine-tuned"  
    CUSTOM \= "Custom"  
    THIRD\_PARTY \= "Third-Party"

class DependencyType(Enum):  
    LIBRARY \= "Library"  
    FRAMEWORK \= "Framework"  
    TOOL \= "Tool"  
    DATASET \= "Dataset"

@dataclass  
class ProvenanceRecord:  
    """Provenance record for a supply chain component"""  
    record\_id: str  
    component\_id: str  
    component\_type: str  
    source: str  
    author: str  
    timestamp: str  
    signature: str  
    hash: str  
    parent\_record\_id: Optional\[str\] \= None

@dataclass  
class ModelProvenance:  
    """Model provenance record"""  
    model\_id: str  
    model\_name: str  
    model\_version: str  
    model\_source: str  
    model\_type: ModelType  
    training\_data\_source: str  
    training\_data\_provenance: Dict  
    model\_architecture: str  
    model\_parameters: Dict  
    authorship: List\[str\]  
    creation\_date: str  
    last\_updated: str  
    provenance\_chain: List\[ProvenanceRecord\]  
    security\_status: SecurityStatus  
    security\_scan\_results: Dict  
    assessment\_status: AssessmentStatus  
    assessment\_report: Optional\[str\]

@dataclass  
class Dependency:  
    """Dependency record"""  
    dependency\_id: str  
    dependency\_name: str  
    dependency\_version: str  
    dependency\_type: DependencyType  
    source: str  
    used\_by: List\[str\]  
    security\_status: SecurityStatus  
    vulnerability\_scan: Dict  
    license: str  
    registration\_date: str

class SupplyChainGovernance:  
    """Supply Chain Governance Framework"""  
      
    def \_\_init\_\_(self):  
        self.models: Dict\[str, ModelProvenance\] \= {}  
        self.dependencies: Dict\[str, Dependency\] \= {}  
        self.assessments: List\[Dict\] \= \[\]  
        self.scans: List\[Dict\] \= \[\]  
      
    def register\_model(  
        self,  
        name: str,  
        version: str,  
        model\_type: ModelType,  
        source: str,  
        training\_data\_source: str,  
        model\_architecture: str,  
        model\_parameters: Dict,  
        authorship: List\[str\]  
    ) \-\> ModelProvenance:  
        """Register a model in the supply chain registry"""  
        model\_id \= f"MODEL-{len(self.models) \+ 1:04d}"  
          
        model \= ModelProvenance(  
            model\_id=model\_id,  
            model\_name=name,  
            model\_version=version,  
            model\_source=source,  
            model\_type=model\_type,  
            training\_data\_source=training\_data\_source,  
            training\_data\_provenance={  
                "source": training\_data\_source,  
                "date": datetime.now().isoformat(),  
                "verified": False  
            },  
            model\_architecture=model\_architecture,  
            model\_parameters=model\_parameters,  
            authorship=authorship,  
            creation\_date=datetime.now().isoformat(),  
            last\_updated=datetime.now().isoformat(),  
            provenance\_chain=\[\],  \# Build from source  
            security\_status=SecurityStatus.PENDING,  
            security\_scan\_results={},  
            assessment\_status=AssessmentStatus.PENDING,  
            assessment\_report=None  
        )  
          
        \# Add initial provenance  
        provenance \= ProvenanceRecord(  
            record\_id=f"PROV-{datetime.now().strftime('%Y%m%d')}-{len(self.models)+1:04d}",  
            component\_id=model\_id,  
            component\_type="model",  
            source=source,  
            author=authorship\[0\] if authorship else "unknown",  
            timestamp=datetime.now().isoformat(),  
            signature=f"SIG-{model\_id}",  
            hash=hashlib.sha256(f"{name}{version}{source}".encode()).hexdigest()  
        )  
        model.provenance\_chain.append(provenance)  
          
        self.models\[model\_id\] \= model  
        return model  
      
    def assess\_model(  
        self,  
        model\_id: str,  
        security\_scan\_results: Dict,  
        performance\_assessment: Dict,  
        bias\_assessment: Dict,  
        privacy\_assessment: Dict,  
        compliance\_assessment: Dict  
    ) \-\> ModelProvenance:  
        """Assess a third-party model"""  
        model \= self.models.get(model\_id)  
        if not model:  
            raise ValueError(f"Model {model\_id} not found")  
          
        \# Determine overall assessment status  
        critical\_issues \= \[\]  
          
        \# Security issues  
        if security\_scan\_results.get("critical\_vulnerabilities", \[\]):  
            critical\_issues.append("Critical security vulnerabilities found")  
          
        \# Bias issues  
        if bias\_assessment.get("high\_bias\_found", False):  
            critical\_issues.append("High bias detected")  
          
        \# Compliance issues  
        if compliance\_assessment.get("compliance\_gaps", \[\]):  
            critical\_issues.append("Compliance gaps found")  
          
        if critical\_issues:  
            model.assessment\_status \= AssessmentStatus.NEEDS\_REVIEW  
            model.security\_status \= SecurityStatus.NEEDS\_REVIEW  
            model.assessment\_report \= self.\_create\_assessment\_report(  
                model\_id,  
                "Conditional",  
                critical\_issues,  
                {"security": security\_scan\_results, "performance": performance\_assessment,  
                 "bias": bias\_assessment, "privacy": privacy\_assessment, "compliance": compliance\_assessment}  
            )  
        else:  
            model.assessment\_status \= AssessmentStatus.ASSESSED  
            model.security\_status \= SecurityStatus.VERIFIED  
            model.assessment\_report \= self.\_create\_assessment\_report(  
                model\_id,  
                "Pass",  
                \[\],  
                {"security": security\_scan\_results, "performance": performance\_assessment,  
                 "bias": bias\_assessment, "privacy": privacy\_assessment, "compliance": compliance\_assessment}  
            )  
          
        model.last\_updated \= datetime.now().isoformat()  
        model.security\_scan\_results \= security\_scan\_results  
          
        return model  
      
    def \_create\_assessment\_report(self, model\_id: str, status: str, issues: List\[str\], data: Dict) \-\> str:  
        """Create an assessment report (stored as GAO in production)"""  
        report \= {  
            "model\_id": model\_id,  
            "assessment\_date": datetime.now().isoformat(),  
            "overall\_status": status,  
            "issues": issues,  
            "security": data.get("security", {}),  
            "performance": data.get("performance", {}),  
            "bias": data.get("bias", {}),  
            "privacy": data.get("privacy", {}),  
            "compliance": data.get("compliance", {})  
        }  
        self.assessments.append(report)  
        return f"Assessment Report: {status} (See GAO-{model\_id})"  
      
    def register\_dependency(  
        self,  
        name: str,  
        version: str,  
        dep\_type: DependencyType,  
        source: str,  
        used\_by: List\[str\],  
        license: str  
    ) \-\> Dependency:  
        """Register a dependency"""  
        dependency\_id \= f"DEP-{len(self.dependencies) \+ 1:04d}"  
          
        dependency \= Dependency(  
            dependency\_id=dependency\_id,  
            dependency\_name=name,  
            dependency\_version=version,  
            dependency\_type=dep\_type,  
            source=source,  
            used\_by=used\_by,  
            security\_status=SecurityStatus.PENDING,  
            vulnerability\_scan={},  
            license=license,  
            registration\_date=datetime.now().isoformat()  
        )  
          
        self.dependencies\[dependency\_id\] \= dependency  
        return dependency  
      
    def scan\_dependency(  
        self,  
        dependency\_id: str,  
        vulnerabilities: List\[Dict\],  
        malware\_detected: bool,  
        typosquatting\_risk: bool,  
        dependency\_confusion\_risk: bool  
    ) \-\> Dependency:  
        """Scan a dependency for vulnerabilities"""  
        dependency \= self.dependencies.get(dependency\_id)  
        if not dependency:  
            raise ValueError(f"Dependency {dependency\_id} not found")  
          
        scan\_results \= {  
            "vulnerabilities": vulnerabilities,  
            "malware\_detected": malware\_detected,  
            "typosquatting\_risk": typosquatting\_risk,  
            "dependency\_confusion\_risk": dependency\_confusion\_risk,  
            "scan\_date": datetime.now().isoformat()  
        }  
          
        dependency.vulnerability\_scan \= scan\_results  
          
        if malware\_detected or typosquatting\_risk or dependency\_confusion\_risk:  
            dependency.security\_status \= SecurityStatus.FAILED  
        elif vulnerabilities:  
            \# Check if any are critical  
            critical \= any(v.get("severity") in \["Critical", "High"\] for v in vulnerabilities)  
            dependency.security\_status \= SecurityStatus.NEEDS\_REVIEW if critical else SecurityStatus.VERIFIED  
        else:  
            dependency.security\_status \= SecurityStatus.VERIFIED  
          
        self.scans.append(scan\_results)  
        return dependency  
      
    def get\_model(self, model\_id: str) \-\> Optional\[ModelProvenance\]:  
        """Get a model by ID"""  
        return self.models.get(model\_id)  
      
    def get\_dependency(self, dependency\_id: str) \-\> Optional\[Dependency\]:  
        """Get a dependency by ID"""  
        return self.dependencies.get(dependency\_id)  
      
    def get\_models\_by\_status(self, status: SecurityStatus) \-\> List\[ModelProvenance\]:  
        """Get models by security status"""  
        return \[m for m in self.models.values() if m.security\_status \== status\]  
      
    def get\_models\_by\_risk(self, risk\_level: SupplyChainRiskLevel) \-\> List\[ModelProvenance\]:  
        """Get models by risk level (derived from security status)"""  
        mapping \= {  
            SecurityStatus.VERIFIED: SupplyChainRiskLevel.LOW,  
            SecurityStatus.PENDING: SupplyChainRiskLevel.MEDIUM,  
            SecurityStatus.NEEDS\_REVIEW: SupplyChainRiskLevel.HIGH,  
            SecurityStatus.FAILED: SupplyChainRiskLevel.CRITICAL  
        }  
        return \[m for m in self.models.values() if mapping.get(m.security\_status) \== risk\_level\]  
      
    def get\_dependencies\_by\_status(self, status: SecurityStatus) \-\> List\[Dependency\]:  
        """Get dependencies by security status"""  
        return \[d for d in self.dependencies.values() if d.security\_status \== status\]  
      
    def verify\_provenance\_chain(self, model\_id: str) \-\> bool:  
        """Verify the provenance chain of a model"""  
        model \= self.models.get(model\_id)  
        if not model:  
            return False  
          
        chain \= model.provenance\_chain  
        if len(chain) \< 2:  
            return False  
          
        \# Verify each link  
        for i in range(1, len(chain)):  
            current \= chain\[i\]  
            previous \= chain\[i-1\]  
              
            \# Verify parent reference  
            if current.parent\_record\_id \!= previous.record\_id:  
                return False  
              
            \# Verify hash (in production, verify signatures)  
          
        return True  
      
    def summary(self) \-\> Dict:  
        """Get a summary of supply chain governance"""  
        return {  
            "total\_models": len(self.models),  
            "total\_dependencies": len(self.dependencies),  
            "total\_assessments": len(self.assessments),  
            "total\_scans": len(self.scans),  
            "models\_by\_status": {  
                status.value: len(\[m for m in self.models.values() if m.security\_status \== status\])  
                for status in SecurityStatus  
            },  
            "models\_by\_type": {  
                model\_type.value: len(\[m for m in self.models.values() if m.model\_type \== model\_type\])  
                for model\_type in ModelType  
            },  
            "dependencies\_by\_status": {  
                status.value: len(\[d for d in self.dependencies.values() if d.security\_status \== status\])  
                for status in SecurityStatus  
            },  
            "pending\_assessments": len(\[m for m in self.models.values() if m.assessment\_status \== AssessmentStatus.PENDING\])  
        }

---

## SECTION 8: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| **ILTP** | IP provenance — extended with supply chain |
| **IMP** | Supply chain records logged as GAO/CRO |
| **AICA-5** | Supply chain risk feeds into risk management |
| **ADTEP** | Supply chain checks at session initialization |
| **HAN/HOF** | Supply chain decisions require HAN authorization |
| **MCP Server Governance** | MCP servers are supply chain artifacts |
| **Skills & Plugins Governance** | Skills are supply chain artifacts |
| **Zero Trust** | Supply chain verification is part of Zero Trust |

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| Supply Chain Governance v1.0 | Initial specification — Model Provenance, Third-Party Model Assessment, Vulnerability Scanning, Dependency Management, Risk Classification |

---

## The One-Sentence Summary

> *"Supply Chain Governance v1.0 establishes comprehensive governance for AI supply chains — with Model Provenance (16 fields, chain verification), Third-Party Model Assessment (6 assessment areas), Vulnerability Scanning (6 scan types, 3 response tiers), Dependency Management (Dependency Registry, CVE/malware/typosquatting/dependency confusion scanning), and 4 Risk Levels (Low, Medium, High, Critical) — ensuring that every model, library, training data source, and dependency in the AI supply chain is governed, verified, and traceable."*
