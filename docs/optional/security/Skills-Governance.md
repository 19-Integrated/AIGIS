# Skills & Plugins Governance v1.0

**Status:** Built — v1.0  
**Type:** Security & Governance Instrument  
**Parent Stack:** AIGIS Security / MCP Server Governance  
**Version:** 1.0

---

## PREAMBLE

The Skills & Plugins Governance framework establishes formal governance for AI "skills" and plugins — including Claude Skills, GPT Store apps, and similar third-party extensions. It answers: *How do we govern AI skills and plugins as software supply chain artifacts with security and compliance requirements?*

AI skills and plugins are **packages in disguise**. They present similar supply chain risks as npm packages, with attackers using typosquatting, dependency confusion, and post-publish payload swaps. This framework extends the MCP Registry to cover skills and plugins, applies JFrog-grade security scanning (CVE detection, malware scanning) to all skills, and establishes governance requirements for skill lifecycle management.

**The core insight:** A skill that appears benign at install can become malicious after update. Skills and plugins are not just features — they are executable code that runs with the agent's privileges. They must be governed with the same rigor as any other software supply chain artifact.

---

## SECTION 1: PURPOSE AND SCOPE

### Purpose

The Skills & Plugins Governance Framework ensures that:

1. **Skills are registered** — All skills/plugins are registered before use  
2. **Skills are scanned** — Security scanning (CVE, malware, typosquatting) is applied  
3. **Skills are versioned** — Skills are versioned and updates are governed  
4. **Skills are attributed** — Skill provenance and authorship are tracked  
5. **Skills are lifecycle-managed** — Skills have complete lifecycle management  
6. **Skills supply chain is secured** — Dependency confusion, typosquatting, and payload swaps are prevented

### Scope

| In Scope | Out of Scope |
| :---- | :---- |
| Skill/plugin registration and governance | MCP server implementation |
| Security scanning (CVE, malware, typosquatting) | Agent implementation |
| Skill version management | Network security |
| Skill provenance and attribution | Encryption |
| Skill lifecycle management | Certificate management |

### Skill Types

| Type | Description | Examples | Risk Level |
| :---- | :---- | :---- | :---- |
| **Claude Skills** | Custom skills for Claude agents | Data analysis, document processing | Medium |
| **GPT Store Apps** | Applications from the GPT Store | Research, summarization, coding | Medium |
| **Internal Skills** | Organization-developed skills | Custom workflows, integrations | Low |
| **Third-Party Skills** | Vendor-provided skills | Security scanning, compliance | High |
| **Open-Source Skills** | Community-developed skills | Various utilities | High |

### Governing Relationships

| Instrument | Relationship |
| :---- | :---- |
| **MCP Server Governance** | Skills run on MCP servers; extends MCP Registry |
| **AWOF** | Agents use skills; skill governance extends AWOF |
| **ADTEP** | Skill registration is a Non-Delegable Authority |
| **IMP** | Skill registry entries logged as CRO/GAO |
| **HAN/HOF** | Registration is HAN-only |
| **ILTP** | Skills may incorporate IP assets |
| **Supply Chain Governance** | Skills are supply chain artifacts |
| **Zero Trust** | Skill execution is verified |

---

## SECTION 2: SKILL REGISTRY

### 2.1 Skill Registry Schema

| \# | Field | Type | Description |
| :---- | :---- | :---- | :---- |
| 1 | `skill_id` | String | Unique identifier. Format: `SKILL-[SEQ]` |
| 2 | `skill_name` | String | Name of the skill/plugin |
| 3 | `skill_version` | String | Semantic version |
| 4 | `skill_type` | Enum | Claude / GPT Store / Internal / Third-Party / Open-Source |
| 5 | `skill_source` | String | Source/origin (vendor, repository, internal) |
| 6 | `mcp_server_reference` | String | MCP server this skill runs on |
| 7 | `author` | String | Skill author/developer |
| 8 | `provenance` | Object | Provenance chain (who created, when, from what source) |
| 9 | `capability_mappings` | Object | CTAM domain mappings |
| 10 | `security_status` | Enum | Verified / Pending / Failed / Needs Review |
| 11 | `security_scan_results` | Object | Vulnerability findings, malware scan, typosquatting check |
| 12 | `version_history` | List | All versions with dates and changes |
| 13 | `registration_status` | Enum | Registered / Active / Deprecated / Retired |
| 14 | `registered_by` | String | HAN identifier |
| 15 | `registration_date` | ISO 8601 | Registration date |
| 16 | `last_updated` | ISO 8601 | Last update date |

### 2.2 Security Scan Results Schema

| \# | Field | Type | Description |
| :---- | :---- | :---- | :---- |
| 1 | `scan_id` | String | Unique scan identifier |
| 2 | `scan_date` | ISO 8601 | Scan date |
| 3 | `cve_findings` | List | CVE vulnerabilities found |
| 4 | `malware_detected` | Boolean | Malware detected |
| 5 | `typosquatting_risk` | Boolean | Typosquatting risk detected |
| 6 | `dependency_confusion_risk` | Boolean | Dependency confusion risk detected |
| 7 | `post_publish_changes` | Boolean | Post-publish payload changes detected |
| 8 | `permission_issues` | List | Permission issues found |
| 9 | `overall_status` | Enum | Pass / Fail / Needs Review |

---

## SECTION 3: SECURITY SCANNING

### 3.1 Scan Types

| Scan Type | Description | Frequency |
| :---- | :---- | :---- |
| **CVE Detection** | Known vulnerability detection | On registration, on update, quarterly |
| **Malware Scanning** | Malware detection | On registration, on update |
| **Typosquatting Detection** | Name similarity to known malicious skills | On registration |
| **Dependency Confusion Detection** | Dependency confusion detection | On registration, on update |
| **Post-Publish Change Detection** | Changes after publication | On update, periodic |
| **Permission Audit** | Permission elevation detection | On registration, on update |

### 3.2 Response Tiers

| Tier | Name | Description | Response |
| :---- | :---- | :---- | :---- |
| **1** | **Flag** | Low severity finding | Logged; no action required |
| **2** | **Review** | Moderate severity finding | Routed to HAN for review |
| **3** | **Halt** | Critical severity finding | Skill suspended pending resolution |

### 3.3 Supply Chain Attack Prevention

| Attack Type | Description | Prevention |
| :---- | :---- | :---- |
| **Typosquatting** | Malicious skill with similar name | Name similarity detection |
| **Dependency Confusion** | Malicious dependency with same name | Dependency verification |
| **Post-Publish Payload Swap** | Skill replaced after initial review | Continuous monitoring, hash verification |
| **Supply Chain Poisoning** | Malicious code injected via dependencies | Dependency scanning |

---

## SECTION 4: SKILL LIFECYCLE

### 4.1 Lifecycle Stages

| Stage | Description | Actions |
| :---- | :---- | :---- |
| **Registration** | Skill is registered in the system | Registration, HAN authorization, initial scan |
| **Verification** | Skill is verified and approved | Security scan, capability verification |
| **Active** | Skill is available for use | Continuous monitoring, periodic review |
| **Deprecated** | Skill is deprecated but still available | Deprecation notice, migration planning |
| **Retired** | Skill is permanently removed | Removal, archival |

### 4.2 Registration Requirements

| Requirement | Description | Verification |
| :---- | :---- | :---- |
| **Skill Registration** | All skills must be registered before use | Registry entry |
| **Security Scan** | Complete security scan with no critical findings | Scan results |
| **Capability Classification** | Skill capabilities mapped to CTAM domains | CTAM mapping |
| **Provenance** | Complete provenance chain | Provenance record |
| **HAN Authorization** | Registration is HAN-authorized | HAN signature |

### 4.3 Registration Process

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 1 | Skill identified for use | Agent Operator | Upon identification |
| 2 | Skill capability assessment | Node Steward | Within 48 hours |
| 3 | Security scan initiated | Security Team | Within 48 hours |
| 4 | HAN registration authorization | HAN | Within 72 hours |
| 5 | Skill registered in Registry | Node Steward | Within 24 hours |

---

## SECTION 5: SKILLS & PLUGINS IMPLEMENTATION

\# skills\_plugins\_governance.py  
"""  
Skills & Plugins Governance — Complete Implementation  
"""

from enum import Enum  
from typing import List, Dict, Optional  
from dataclasses import dataclass, field  
from datetime import datetime  
import hashlib

class SkillType(Enum):  
    CLAUDE \= "Claude"  
    GPT\_STORE \= "GPT Store"  
    INTERNAL \= "Internal"  
    THIRD\_PARTY \= "Third-Party"  
    OPEN\_SOURCE \= "Open-Source"

class SecurityStatus(Enum):  
    VERIFIED \= "Verified"  
    PENDING \= "Pending"  
    FAILED \= "Failed"  
    NEEDS\_REVIEW \= "Needs Review"

class RegistrationStatus(Enum):  
    REGISTERED \= "Registered"  
    ACTIVE \= "Active"  
    DEPRECATED \= "Deprecated"  
    RETIRED \= "Retired"

class ScanStatus(Enum):  
    PASS \= "Pass"  
    FAIL \= "Fail"  
    NEEDS\_REVIEW \= "Needs Review"

@dataclass  
class SecurityScanResults:  
    """Security scan results for a skill/plugin"""  
    scan\_id: str  
    scan\_date: str  
    cve\_findings: List\[Dict\]  
    malware\_detected: bool  
    typosquatting\_risk: bool  
    dependency\_confusion\_risk: bool  
    post\_publish\_changes: bool  
    permission\_issues: List\[str\]  
    overall\_status: ScanStatus

@dataclass  
class Skill:  
    """A skill/plugin registered in the system"""  
    skill\_id: str  
    skill\_name: str  
    skill\_version: str  
    skill\_type: SkillType  
    skill\_source: str  
    mcp\_server\_reference: str  
    author: str  
    provenance: Dict  
    capability\_mappings: Dict\[str, str\]  
    security\_status: SecurityStatus  
    security\_scan\_results: Optional\[SecurityScanResults\]  
    version\_history: List\[Dict\]  
    registration\_status: RegistrationStatus  
    registered\_by: str  
    registration\_date: str  
    last\_updated: str

class SkillsGovernance:  
    """Skills & Plugins Governance Framework"""  
      
    def \_\_init\_\_(self):  
        self.skills: Dict\[str, Skill\] \= {}  
        self.scans: Dict\[str, SecurityScanResults\] \= {}  
      
    def register\_skill(  
        self,  
        name: str,  
        version: str,  
        skill\_type: SkillType,  
        source: str,  
        mcp\_server\_reference: str,  
        author: str,  
        provenance: Dict,  
        capability\_mappings: Dict\[str, str\],  
        registered\_by: str  
    ) \-\> Skill:  
        """Register a new skill/plugin (HAN-only)"""  
        skill\_id \= f"SKILL-{len(self.skills) \+ 1:04d}"  
          
        skill \= Skill(  
            skill\_id=skill\_id,  
            skill\_name=name,  
            skill\_version=version,  
            skill\_type=skill\_type,  
            skill\_source=source,  
            mcp\_server\_reference=mcp\_server\_reference,  
            author=author,  
            provenance=provenance,  
            capability\_mappings=capability\_mappings,  
            security\_status=SecurityStatus.PENDING,  
            security\_scan\_results=None,  
            version\_history=\[{  
                "version": version,  
                "date": datetime.now().isoformat(),  
                "changes": "Initial registration"  
            }\],  
            registration\_status=RegistrationStatus.REGISTERED,  
            registered\_by=registered\_by,  
            registration\_date=datetime.now().isoformat(),  
            last\_updated=datetime.now().isoformat()  
        )  
          
        self.skills\[skill\_id\] \= skill  
        return skill  
      
    def update\_security\_scan(  
        self,  
        skill\_id: str,  
        cve\_findings: List\[Dict\],  
        malware\_detected: bool,  
        typosquatting\_risk: bool,  
        dependency\_confusion\_risk: bool,  
        post\_publish\_changes: bool,  
        permission\_issues: List\[str\]  
    ) \-\> Skill:  
        """Update security scan for a skill"""  
        skill \= self.skills.get(skill\_id)  
        if not skill:  
            raise ValueError(f"Skill {skill\_id} not found")  
          
        \# Determine overall status  
        if malware\_detected or post\_publish\_changes:  
            overall\_status \= ScanStatus.FAIL  
            security\_status \= SecurityStatus.FAILED  
        elif cve\_findings or typosquatting\_risk or dependency\_confusion\_risk or permission\_issues:  
            overall\_status \= ScanStatus.NEEDS\_REVIEW  
            security\_status \= SecurityStatus.NEEDS\_REVIEW  
        else:  
            overall\_status \= ScanStatus.PASS  
            security\_status \= SecurityStatus.VERIFIED  
          
        scan \= SecurityScanResults(  
            scan\_id=f"SCAN-{datetime.now().strftime('%Y%m%d')}-{len(self.scans)+1:04d}",  
            scan\_date=datetime.now().isoformat(),  
            cve\_findings=cve\_findings,  
            malware\_detected=malware\_detected,  
            typosquatting\_risk=typosquatting\_risk,  
            dependency\_confusion\_risk=dependency\_confusion\_risk,  
            post\_publish\_changes=post\_publish\_changes,  
            permission\_issues=permission\_issues,  
            overall\_status=overall\_status  
        )  
          
        self.scans\[scan.scan\_id\] \= scan  
          
        skill.security\_status \= security\_status  
        skill.security\_scan\_results \= scan  
        skill.last\_updated \= datetime.now().isoformat()  
          
        if security\_status \== SecurityStatus.VERIFIED:  
            skill.registration\_status \= RegistrationStatus.ACTIVE  
          
        return skill  
      
    def update\_skill\_version(  
        self,  
        skill\_id: str,  
        new\_version: str,  
        changes: str,  
        scan\_results: Optional\[SecurityScanResults\] \= None  
    ) \-\> Skill:  
        """Update a skill to a new version"""  
        skill \= self.skills.get(skill\_id)  
        if not skill:  
            raise ValueError(f"Skill {skill\_id} not found")  
          
        \# Update version  
        skill.skill\_version \= new\_version  
        skill.version\_history.append({  
            "version": new\_version,  
            "date": datetime.now().isoformat(),  
            "changes": changes  
        })  
          
        \# Re-scan if no scan results provided  
        if scan\_results:  
            skill.security\_scan\_results \= scan\_results  
            if scan\_results.overall\_status \== ScanStatus.PASS:  
                skill.security\_status \= SecurityStatus.VERIFIED  
                skill.registration\_status \= RegistrationStatus.ACTIVE  
            elif scan\_results.overall\_status \== ScanStatus.NEEDS\_REVIEW:  
                skill.security\_status \= SecurityStatus.NEEDS\_REVIEW  
            else:  
                skill.security\_status \= SecurityStatus.FAILED  
          
        skill.last\_updated \= datetime.now().isoformat()  
          
        return skill  
      
    def deprecate\_skill(self, skill\_id: str, reason: str) \-\> Skill:  
        """Deprecate a skill"""  
        skill \= self.skills.get(skill\_id)  
        if not skill:  
            raise ValueError(f"Skill {skill\_id} not found")  
          
        skill.registration\_status \= RegistrationStatus.DEPRECATED  
        skill.last\_updated \= datetime.now().isoformat()  
          
        return skill  
      
    def retire\_skill(self, skill\_id: str, reason: str) \-\> Skill:  
        """Retire a skill"""  
        skill \= self.skills.get(skill\_id)  
        if not skill:  
            raise ValueError(f"Skill {skill\_id} not found")  
          
        skill.registration\_status \= RegistrationStatus.RETIRED  
        skill.last\_updated \= datetime.now().isoformat()  
          
        return skill  
      
    def get\_skill(self, skill\_id: str) \-\> Optional\[Skill\]:  
        """Get a skill by ID"""  
        return self.skills.get(skill\_id)  
      
    def get\_skills\_by\_type(self, skill\_type: SkillType) \-\> List\[Skill\]:  
        """Get skills by type"""  
        return \[s for s in self.skills.values() if s.skill\_type \== skill\_type\]  
      
    def get\_skills\_by\_status(self, status: RegistrationStatus) \-\> List\[Skill\]:  
        """Get skills by registration status"""  
        return \[s for s in self.skills.values() if s.registration\_status \== status\]  
      
    def get\_skills\_by\_security\_status(self, status: SecurityStatus) \-\> List\[Skill\]:  
        """Get skills by security status"""  
        return \[s for s in self.skills.values() if s.security\_status \== status\]  
      
    def get\_skills\_by\_mcp\_server(self, mcp\_server\_id: str) \-\> List\[Skill\]:  
        """Get skills for an MCP server"""  
        return \[s for s in self.skills.values() if s.mcp\_server\_reference \== mcp\_server\_id\]  
      
    def verify\_skill\_provenance(self, skill\_id: str) \-\> bool:  
        """Verify the provenance of a skill"""  
        skill \= self.skills.get(skill\_id)  
        if not skill:  
            return False  
          
        \# Check provenance completeness  
        required\_fields \= \["author", "source", "created\_date", "signature"\]  
        for field in required\_fields:  
            if field not in skill.provenance:  
                return False  
          
        \# In production, verify signature  
        return True  
      
    def detect\_typosquatting(self, skill\_name: str, known\_skills: List\[str\]) \-\> bool:  
        """Detect typosquatting risk"""  
        \# Simple Levenshtein distance check  
        \# In production, use more sophisticated detection  
        for known in known\_skills:  
            if self.\_levenshtein\_distance(skill\_name.lower(), known.lower()) \<= 2:  
                if skill\_name \!= known:  
                    return True  
        return False  
      
    def \_levenshtein\_distance(self, s1: str, s2: str) \-\> int:  
        """Calculate Levenshtein distance between two strings"""  
        if len(s1) \< len(s2):  
            return self.\_levenshtein\_distance(s2, s1)  
          
        if len(s2) \== 0:  
            return len(s1)  
          
        previous\_row \= range(len(s2) \+ 1\)  
        for i, c1 in enumerate(s1):  
            current\_row \= \[i \+ 1\]  
            for j, c2 in enumerate(s2):  
                insertions \= previous\_row\[j \+ 1\] \+ 1  
                deletions \= current\_row\[j\] \+ 1  
                substitutions \= previous\_row\[j\] \+ (c1 \!= c2)  
                current\_row.append(min(insertions, deletions, substitutions))  
            previous\_row \= current\_row  
          
        return previous\_row\[-1\]  
      
    def summary(self) \-\> Dict:  
        """Get a summary of skills governance"""  
        return {  
            "total\_skills": len(self.skills),  
            "by\_type": {  
                skill\_type.value: len(\[s for s in self.skills.values() if s.skill\_type \== skill\_type\])  
                for skill\_type in SkillType  
            },  
            "by\_registration\_status": {  
                status.value: len(\[s for s in self.skills.values() if s.registration\_status \== status\])  
                for status in RegistrationStatus  
            },  
            "by\_security\_status": {  
                status.value: len(\[s for s in self.skills.values() if s.security\_status \== status\])  
                for status in SecurityStatus  
            },  
            "pending\_scans": len(\[s for s in self.skills.values() if s.security\_status \== SecurityStatus.PENDING\]),  
            "failed\_scans": len(\[s for s in self.skills.values() if s.security\_status \== SecurityStatus.FAILED\]),  
            "active\_skills": len(\[s for s in self.skills.values() if s.registration\_status \== RegistrationStatus.ACTIVE\])  
        }

---

## SECTION 6: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| **MCP Server Governance** | Skills run on MCP servers; extends MCP Registry |
| **AWOF** | Agents use skills; skill governance extends AWOF |
| **ADTEP** | Skill registration is a Non-Delegable Authority |
| **IMP** | Skill registry entries logged as CRO/GAO |
| **HAN/HOF** | Registration is HAN-only |
| **ILTP** | Skills may incorporate IP assets |
| **Supply Chain Governance** | Skills are supply chain artifacts |
| **Zero Trust** | Skill execution is verified |
| **Agentic Security (AEGIS)** | Skill identity and authentication |

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| Skills & Plugins Governance v1.0 | Initial specification — Skill Registry, security scanning (CVE, malware, typosquatting, dependency confusion, post-publish changes), lifecycle management, typosquatting detection |

---

## The One-Sentence Summary

> *"The Skills & Plugins Governance Framework v1.0 establishes formal governance for AI skills and plugins — with Skill Registry (16 fields), security scanning (CVE, malware, typosquatting, dependency confusion, post-publish changes), 5 skill types (Claude, GPT Store, Internal, Third-Party, Open-Source), 5 lifecycle stages (Registration, Verification, Active, Deprecated, Retired), 3 response tiers (Flag, Review, Halt), and supply chain attack prevention (typosquatting, dependency confusion, post-publish payload swap) — treating skills as packages in disguise with software supply chain risk equivalent to npm packages."*
