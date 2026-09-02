# MCP Server Governance v1.0

**Status:** Built — v1.0  
**Type:** Security & Governance Instrument  
**Parent Stack:** AIGIS Technical Enforcement / ADTEP  
**Version:** 1.0

---

## PREAMBLE

The MCP Server Governance instrument establishes a system of record for Model Context Protocol (MCP) servers, which are the primary way AI agents connect to external tools, data sources, and APIs. It answers: *What MCP servers are in use, who authorized them, what capabilities do they expose, and how are they monitored for security and compliance?*

MCP servers are the new software supply chain risk. Unmanaged MCP servers create "blind spots" and can execute arbitrary, potentially malicious code with elevated privileges. This instrument extends the Agent Registry with an MCP Server Registry and Skill Registry, establishes MCP Server Registration as a Non-Delegable Authority, and creates governance functions for MCP server lifecycle management.

**The core insight:** An agent is only as secure as the MCP servers it uses. Without MCP governance, agents are operating with unverified, unmonitored, and potentially malicious tools — undermining the entire governance stack.

---

## SECTION 1: PURPOSE AND SCOPE

### Purpose

MCP Server Governance ensures that:

1. **MCP servers are registered** — All MCP servers in use are registered in a system of record  
2. **MCP servers are authorized** — Registration is a Non-Delegable Authority (HAN-only)  
3. **MCP capabilities are classified** — Each MCP server's capabilities are mapped to CTAM domains  
4. **MCP security is assessed** — Security scanning and vulnerability detection are applied  
5. **MCP usage is logged** — All agent-MCP interactions are authenticated and logged  
6. **MCP lifecycle is managed** — Registration, updates, and retirement are governed

### Scope

| In Scope | Out of Scope |
| :---- | :---- |
| MCP server registration and authorization | Agent registration (separate) |
| MCP capability classification | Skill/plugin governance (separate but related) |
| MCP security scanning | Runtime security (Zero Trust) |
| Agent-MCP interaction logging | MCP server implementation |
| MCP lifecycle management | MCP server hosting |

### Governing Relationships

| Instrument | Relationship |
| :---- | :---- |
| **AWOF** | Agents use MCP servers; MCP governance extends AWOF |
| **ADTEP** | MCP Server Registration is a Non-Delegable Authority |
| **AICA-5** | MCP capabilities map to CTAM domains |
| **IMP** | MCP registry entries logged as CRO/GAO |
| **HAN/HOF** | Registration is HAN-only |
| **ILTP** | MCP servers may incorporate IP assets |
| **Supply Chain Governance** | MCP servers are supply chain artifacts |

---

## SECTION 2: MCP REGISTRY STRUCTURE

### 2.1 MCP Server Registry Schema

| \# | Field | Type | Description |
| :---- | :---- | :---- | :---- |
| 1 | `mcp_server_id` | String | Unique identifier. Format: `MCP-[SEQ]` |
| 2 | `mcp_server_name` | String | Name of the MCP server |
| 3 | `mcp_server_version` | String | Semantic version |
| 4 | `mcp_server_source` | String | Source/origin (vendor, open-source, internal) |
| 5 | `mcp_server_type` | Enum | Data / API / File / Search / Custom / Other |
| 6 | `capability_mappings` | Object | CTAM domain mappings (Perception, Interaction, etc.) |
| 7 | `authorized_agents` | List | Agent IDs authorized to use this MCP server |
| 8 | `registration_status` | Enum | Registered / Active / Deprecated / Retired |
| 9 | `security_status` | Enum | Verified / Pending / Failed / Needs Review |
| 10 | `last_security_scan` | ISO 8601 | Date of last security scan |
| 11 | `security_scan_results` | Object | Vulnerability findings |
| 12 | `registered_by` | String | HAN identifier |
| 13 | `registration_date` | ISO 8601 | Registration date |
| 14 | `last_updated` | ISO 8601 | Last update date |
| 15 | `skill_registry_reference` | String | Reference to Skill Registry if applicable |

### 2.2 Skill Registry Schema

| \# | Field | Type | Description |
| :---- | :---- | :---- | :---- |
| 1 | `skill_id` | String | Unique identifier. Format: `SKILL-[SEQ]` |
| 2 | `skill_name` | String | Name of the skill/plugin |
| 3 | `skill_version` | String | Semantic version |
| 4 | `skill_source` | String | Source (Claude Skills, GPT Store, internal) |
| 5 | `mcp_server_reference` | String | MCP server this skill runs on |
| 6 | `capability_mappings` | Object | CTAM domain mappings |
| 7 | `security_status` | Enum | Verified / Pending / Failed / Needs Review |
| 8 | `vulnerability_scan` | Object | Vulnerability scan results |
| 9 | `registered_by` | String | HAN identifier |
| 10 | `registration_date` | ISO 8601 | Registration date |
| 11 | `last_updated` | ISO 8601 | Last update date |

### 2.3 Skill Types

| Type | Description | Examples |
| :---- | :---- | :---- |
| **Claude Skills** | Custom skills for Claude agents | Data analysis, document processing |
| **GPT Store Apps** | Applications from the GPT Store | Research, summarization, coding |
| **Internal Skills** | Organization-developed skills | Custom workflows, integrations |
| **Third-Party Skills** | Vendor-provided skills | Security scanning, compliance checking |

---

## SECTION 3: REGISTRATION REQUIREMENTS

### 3.1 Registration Process

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 1 | MCP server identified for use | Agent Operator | Upon identification |
| 2 | MCP server capability assessment | Node Steward | Within 48 hours |
| 3 | Security scan initiated | Security Team | Within 48 hours |
| 4 | HAN registration authorization | HAN | Within 72 hours |
| 5 | MCP server registered in Registry | Node Steward | Within 24 hours of authorization |
| 6 | Skill registration (if applicable) | Node Steward | Within 24 hours of authorization |

### 3.2 Registration Requirements

| Requirement | Description | Verification |
| :---- | :---- | :---- |
| **Capability Classification** | MCP server capabilities mapped to CTAM domains | CTAM mapping validation |
| **Security Scan** | Vulnerability scan completed with no critical findings | Security scan results |
| **Agent Authorization** | Agents authorized to use this MCP server are listed | Agent registry check |
| **Skill Registration** | Skills/plugins are registered separately | Skill registry check |
| **HAN Authorization** | Registration is HAN-authorized | HAN signature |

### 3.3 Non-Delegable Authority

MCP Server Registration is a Non-Delegable Authority:

| Rule | Description |
| :---- | :---- |
| **HAN-Only** | MCP server registration, modification, or deregistration is HAN-only |
| **No AI Delegation** | AI agents cannot register, modify, or deregister MCP servers |
| **IMP Logging** | All registration actions are logged in IMP |
| **Suspension on HAN Unavailability** | Registration is suspended if HAN is unavailable |

---

## SECTION 4: MCP SERVER SECURITY

### 4.1 Security Scan Requirements

| Scan Type | Frequency | Description |
| :---- | :---- | :---- |
| **Vulnerability Scan** | On registration, quarterly updates | CVE detection, known vulnerabilities |
| **Malware Scan** | On registration, quarterly updates | Malware detection |
| **Permission Audit** | On registration, quarterly updates | Permission elevation detection |
| **Typosquatting Detection** | On registration | Name similarity to known malicious servers |
| **Dependency Confusion** | On registration | Dependency confusion detection |

### 4.2 Security Response Tiers

| Tier | Name | Description | Response |
| :---- | :---- | :---- | :---- |
| **1** | **Flag** | Low severity finding | Logged; no action required |
| **2** | **Review** | Moderate severity finding | Routed to HAN for review |
| **3** | **Halt** | Critical severity finding | MCP server suspended pending resolution |

### 4.3 MCP Server Risk Classification

| Risk Level | Criteria | Actions |
| :---- | :---- | :---- |
| **Low** | Read-only capabilities, well-known source | Standard registration |
| **Medium** | Write capabilities, moderate source | Enhanced review |
| **High** | Critical system access, unknown source | HAN review required |
| **Critical** | Privileged access, high-impact capabilities | HAN authorization \+ enhanced monitoring |

---

## SECTION 5: MCP SERVER-AGENT INTERACTION

### 5.1 Interaction Requirements

| Requirement | Description |
| :---- | :---- |
| **Authentication** | Agent-MCP interactions must be mutually authenticated |
| **Authorization** | Agent must have explicit authorization to use the MCP server |
| **Logging** | All interactions are logged as inter-agent communication (DRO) |
| **Scope Limitation** | Agent can only use capabilities authorized by CTAM mapping |

### 5.2 Inter-Agent Communication Logging

When an agent interacts with an MCP server, it is logged as inter-agent communication:

| Field | Description |
| :---- | :---- |
| `dro_id` | Unique identifier |
| `decision_type` | `inter_agent_communication` |
| `sender_agent_id` | Agent initiating the interaction |
| `receiver_agent_id` | MCP server ID (as agent-like entity) |
| `communication_type` | `mcp_interaction` |
| `mcp_capability` | Capability being used |
| `authorization_check_result` | Pass/Fail |
| `timestamp` | Interaction timestamp |

---

## SECTION 6: MCP REGISTRY IMPLEMENTATION

\# mcp\_registry.py  
"""  
MCP Server Governance — Complete Implementation  
"""

from enum import Enum  
from typing import List, Dict, Optional  
from dataclasses import dataclass, field  
from datetime import datetime

class MCPServerType(Enum):  
    DATA \= "Data"  
    API \= "API"  
    FILE \= "File"  
    SEARCH \= "Search"  
    CUSTOM \= "Custom"  
    OTHER \= "Other"

class RegistrationStatus(Enum):  
    REGISTERED \= "Registered"  
    ACTIVE \= "Active"  
    DEPRECATED \= "Deprecated"  
    RETIRED \= "Retired"

class SecurityStatus(Enum):  
    VERIFIED \= "Verified"  
    PENDING \= "Pending"  
    FAILED \= "Failed"  
    NEEDS\_REVIEW \= "Needs Review"

class RiskLevel(Enum):  
    LOW \= "Low"  
    MEDIUM \= "Medium"  
    HIGH \= "High"  
    CRITICAL \= "Critical"

@dataclass  
class SecurityScan:  
    """Security scan results for an MCP server"""  
    scan\_id: str  
    scan\_date: str  
    vulnerabilities: List\[Dict\]  
    malware\_detected: bool  
    permission\_issues: List\[str\]  
    typosquatting\_risk: bool  
    dependency\_confusion\_risk: bool  
    overall\_status: SecurityStatus

@dataclass  
class MCPServer:  
    """An MCP server registered in the system"""  
    mcp\_server\_id: str  
    mcp\_server\_name: str  
    mcp\_server\_version: str  
    mcp\_server\_source: str  
    mcp\_server\_type: MCPServerType  
    capability\_mappings: Dict\[str, str\]  \# CTAM domain → specific capability  
    authorized\_agents: List\[str\]  
    registration\_status: RegistrationStatus  
    security\_status: SecurityStatus  
    last\_security\_scan: Optional\[str\]  
    security\_scan\_results: Optional\[SecurityScan\]  
    registered\_by: str  
    registration\_date: str  
    last\_updated: str  
    risk\_level: RiskLevel  
    skill\_registry\_reference: Optional\[str\]

@dataclass  
class Skill:  
    """A skill/plugin registered in the system"""  
    skill\_id: str  
    skill\_name: str  
    skill\_version: str  
    skill\_source: str  
    mcp\_server\_reference: str  
    capability\_mappings: Dict\[str, str\]  
    security\_status: SecurityStatus  
    vulnerability\_scan: Optional\[Dict\]  
    registered\_by: str  
    registration\_date: str  
    last\_updated: str

class MCPRegistry:  
    """System of record for MCP servers and skills"""  
      
    def \_\_init\_\_(self):  
        self.mcp\_servers: Dict\[str, MCPServer\] \= {}  
        self.skills: Dict\[str, Skill\] \= {}  
        self.interaction\_logs: List\[Dict\] \= \[\]  
      
    def register\_mcp\_server(  
        self,  
        name: str,  
        version: str,  
        source: str,  
        mcp\_type: MCPServerType,  
        capability\_mappings: Dict\[str, str\],  
        authorized\_agents: List\[str\],  
        risk\_level: RiskLevel,  
        registered\_by: str  
    ) \-\> MCPServer:  
        """Register a new MCP server (HAN-only)"""  
        server\_id \= f"MCP-{len(self.mcp\_servers) \+ 1:04d}"  
          
        server \= MCPServer(  
            mcp\_server\_id=server\_id,  
            mcp\_server\_name=name,  
            mcp\_server\_version=version,  
            mcp\_server\_source=source,  
            mcp\_server\_type=mcp\_type,  
            capability\_mappings=capability\_mappings,  
            authorized\_agents=authorized\_agents,  
            registration\_status=RegistrationStatus.REGISTERED,  
            security\_status=SecurityStatus.PENDING,  
            last\_security\_scan=None,  
            security\_scan\_results=None,  
            registered\_by=registered\_by,  
            registration\_date=datetime.now().isoformat(),  
            last\_updated=datetime.now().isoformat(),  
            risk\_level=risk\_level,  
            skill\_registry\_reference=None  
        )  
          
        self.mcp\_servers\[server\_id\] \= server  
        return server  
      
    def register\_skill(  
        self,  
        name: str,  
        version: str,  
        source: str,  
        mcp\_server\_reference: str,  
        capability\_mappings: Dict\[str, str\],  
        registered\_by: str  
    ) \-\> Skill:  
        """Register a new skill/plugin"""  
        skill\_id \= f"SKILL-{len(self.skills) \+ 1:04d}"  
          
        skill \= Skill(  
            skill\_id=skill\_id,  
            skill\_name=name,  
            skill\_version=version,  
            skill\_source=source,  
            mcp\_server\_reference=mcp\_server\_reference,  
            capability\_mappings=capability\_mappings,  
            security\_status=SecurityStatus.PENDING,  
            vulnerability\_scan=None,  
            registered\_by=registered\_by,  
            registration\_date=datetime.now().isoformat(),  
            last\_updated=datetime.now().isoformat()  
        )  
          
        self.skills\[skill\_id\] \= skill  
        return skill  
      
    def update\_security\_status(  
        self,  
        mcp\_server\_id: str,  
        security\_status: SecurityStatus,  
        scan\_results: SecurityScan  
    ) \-\> MCPServer:  
        """Update MCP server security status"""  
        server \= self.mcp\_servers.get(mcp\_server\_id)  
        if not server:  
            raise ValueError(f"MCP server {mcp\_server\_id} not found")  
          
        server.security\_status \= security\_status  
        server.security\_scan\_results \= scan\_results  
        server.last\_security\_scan \= scan\_results.scan\_date  
        server.last\_updated \= datetime.now().isoformat()  
          
        return server  
      
    def authorize\_agent(self, mcp\_server\_id: str, agent\_id: str) \-\> MCPServer:  
        """Authorize an agent to use an MCP server"""  
        server \= self.mcp\_servers.get(mcp\_server\_id)  
        if not server:  
            raise ValueError(f"MCP server {mcp\_server\_id} not found")  
          
        if agent\_id not in server.authorized\_agents:  
            server.authorized\_agents.append(agent\_id)  
            server.last\_updated \= datetime.now().isoformat()  
          
        return server  
      
    def log\_interaction(  
        self,  
        agent\_id: str,  
        mcp\_server\_id: str,  
        capability: str,  
        authorized: bool  
    ) \-\> Dict:  
        """Log an agent-MCP interaction"""  
        log\_entry \= {  
            "timestamp": datetime.now().isoformat(),  
            "agent\_id": agent\_id,  
            "mcp\_server\_id": mcp\_server\_id,  
            "capability": capability,  
            "authorized": authorized,  
            "decision\_type": "inter\_agent\_communication",  
            "communication\_type": "mcp\_interaction"  
        }  
          
        self.interaction\_logs.append(log\_entry)  
        return log\_entry  
      
    def get\_server(self, mcp\_server\_id: str) \-\> Optional\[MCPServer\]:  
        """Get an MCP server by ID"""  
        return self.mcp\_servers.get(mcp\_server\_id)  
      
    def get\_servers\_by\_agent(self, agent\_id: str) \-\> List\[MCPServer\]:  
        """Get all MCP servers authorized for an agent"""  
        return \[s for s in self.mcp\_servers.values()   
                if agent\_id in s.authorized\_agents\]  
      
    def get\_servers\_by\_risk\_level(self, risk\_level: RiskLevel) \-\> List\[MCPServer\]:  
        """Get MCP servers by risk level"""  
        return \[s for s in self.mcp\_servers.values()   
                if s.risk\_level \== risk\_level\]  
      
    def get\_pending\_security\_scans(self) \-\> List\[MCPServer\]:  
        """Get MCP servers pending security scans"""  
        return \[s for s in self.mcp\_servers.values()   
                if s.security\_status \== SecurityStatus.PENDING\]  
      
    def get\_failed\_security\_scans(self) \-\> List\[MCPServer\]:  
        """Get MCP servers with failed security scans"""  
        return \[s for s in self.mcp\_servers.values()   
                if s.security\_status \== SecurityStatus.FAILED\]  
      
    def get\_skill(self, skill\_id: str) \-\> Optional\[Skill\]:  
        """Get a skill by ID"""  
        return self.skills.get(skill\_id)  
      
    def get\_skills\_by\_server(self, mcp\_server\_id: str) \-\> List\[Skill\]:  
        """Get all skills for an MCP server"""  
        return \[s for s in self.skills.values()   
                if s.mcp\_server\_reference \== mcp\_server\_id\]  
      
    def summary(self) \-\> Dict:  
        """Get a summary of the registry"""  
        return {  
            "total\_mcp\_servers": len(self.mcp\_servers),  
            "total\_skills": len(self.skills),  
            "total\_interactions": len(self.interaction\_logs),  
            "by\_security\_status": {  
                status.value: len(\[s for s in self.mcp\_servers.values()   
                                   if s.security\_status \== status\])  
                for status in SecurityStatus  
            },  
            "by\_risk\_level": {  
                level.value: len(\[s for s in self.mcp\_servers.values()   
                                  if s.risk\_level \== level\])  
                for level in RiskLevel  
            },  
            "pending\_scans": len(self.get\_pending\_security\_scans()),  
            "failed\_scans": len(self.get\_failed\_security\_scans())  
        }  
---

## SECTION 7: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| **AWOF** | Agents use MCP servers; MCP governance extends AWOF |
| **ADTEP** | MCP Server Registration is a Non-Delegable Authority |
| **AICA-5** | MCP capabilities map to CTAM domains |
| **IMP** | MCP registry entries logged as CRO/GAO |
| **HAN/HOF** | Registration is HAN-only |
| **ILTP** | MCP servers may incorporate IP assets |
| **Supply Chain Governance** | MCP servers are supply chain artifacts |
| **Session Initialization Checklist** | MCP Server Registry check is a checklist item |
| **Escalation Triggers** | MCP Server Violation is an Escalation Trigger |

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| MCP Server Governance v1.0 | Initial specification — MCP Registry, Skill Registry, security scanning, agent-MCP interaction logging, Non-Delegable Authority |

---

## The One-Sentence Summary

> *"MCP Server Governance v1.0 establishes a system of record for Model Context Protocol (MCP) servers and skills — with MCP Registry and Skill Registry schemas, HAN-only registration (Non-Delegable Authority), security scanning (vulnerability, malware, typosquatting, dependency confusion), risk classification (Low to Critical), agent-MCP interaction logging, and integration with AWOF, ADTEP, AICA-5, and IMP — treating MCP servers as the new software supply chain risk that must be governed like any other institutional asset."*
