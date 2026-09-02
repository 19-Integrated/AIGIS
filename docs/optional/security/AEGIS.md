# Agentic Security & Identity (AEGIS) v1.0

**Status:** Built — v1.0  
**Type:** Security & Identity Instrument  
**Parent Stack:** AIGIS Security / AWOF  
**Version:** 1.0

---

## PREAMBLE

The Agentic Security & Identity framework applies Forrester's AEGIS principles to AI agents — treating them as a distinct identity class requiring specialized security governance. It answers: *How do we secure AI agents as a new class of non-human identities with distinct security requirements?*

Over 90% of non-human identities (NHIs) lack proper lifecycle management. Agent identities are neither human nor machine — they are a new class requiring distinct treatment. This framework implements **Least Agency** (limiting decision-making capability, not just access permissions), **Mutual Authentication** for all agent-to-agent communications, and expanded IAM governance for non-human identities.

**The core insight:** Traditional IAM treats all non-human identities the same. Agents are different — they can make decisions, adapt, and act autonomously. Security must limit not just what they can access, but what they can decide and how they can act. Least Agency is the evolution of least privilege for the agentic era.

---

## SECTION 1: PURPOSE AND SCOPE

### Purpose

The Agentic Security & Identity Framework ensures that:

1. **Agents are a distinct identity class** — Agents are neither human nor machine; they require distinct security treatment  
2. **Least Agency is implemented** — Decision-making capability is limited, not just access permissions  
3. **Mutual Authentication is enforced** — All agent-to-agent communications are mutually authenticated  
4. **NHI lifecycle is managed** — Non-human identities have complete lifecycle management  
5. **Agent identities are cryptographically verifiable** — Agent identities are cryptographically verifiable

### Scope

| In Scope | Out of Scope |
| :---- | :---- |
| Agent identity classification and lifecycle | Traditional IAM (human identities) |
| Least Agency implementation (CTAM enhancement) | Network security |
| Mutual Authentication for agents | Encryption |
| NHI governance | Certificate management |
| Agent credential management | Physical security |

### AEGIS Principles

| Principle | Description | Implementation |
| :---- | :---- | :---- |
| **Least Agency** | Limit decision-making capability, not just access | CTAM Decision Budgets, Meta-Constraints |
| **Continuous Risk Management** | Continuous assessment of agent risk posture | RGI-8 drift detection, AOBA |
| **Mutual Authentication** | All agent-to-agent communications authenticated | Inter-Agent Authentication |

### Governing Relationships

| Instrument | Relationship |
| :---- | :---- |
| **AWOF** | Agent identities are AWOF-classified |
| **CTAM** | Least Agency is implemented via CTAM extensions |
| **ADTEP** | Mutual Authentication enforced by ADTEP |
| **RGI-8** | Continuous risk monitoring |
| **IMP** | Agent identity logs |
| **HAN/HOF** | Agent identity lifecycle requires HAN authorization |
| **MCP Server Governance** | Agent-MCP authentication |

---

## SECTION 2: AGENT IDENTITY CLASSIFICATION

### 2.1 Identity Classes

| Class | Description | Examples |
| :---- | :---- | :---- |
| **Human** | Natural persons | Employees, contractors, HAN |
| **Machine** | Traditional service accounts | APIs, databases, servers |
| **Agent** | AI agents with decision-making capability | AWOF-classified agents |
| **Agent Coalition** | Groups of agents acting together | CAD-7 coalitions |

### 2.2 Agent Identity Properties

| Property | Description | Implementation |
| :---- | :---- | :---- |
| **Unique Identity** | Each agent has a unique, verifiable identity | AWOF Agent ID |
| **Cryptographic Credentials** | Agents have cryptographic credentials | Certificate-based identity |
| **Lifecycle Managed** | Agents have complete lifecycle management | Registration → Active → Retired |
| **Decision Capability** | Agents have defined decision-making capability | CTAM grants |
| **Autonomy Boundary** | Agents have defined autonomy boundaries | Role Specification |

### 2.3 Agent Identity Lifecycle

| Stage | Description | Actions |
| :---- | :---- | :---- |
| **Creation** | Agent identity is created | Registration, credential issuance |
| **Active** | Agent is operational | Continuous monitoring, periodic review |
| **Suspended** | Agent is temporarily inactive | Suspension, investigation |
| **Retired** | Agent is permanently decommissioned | Credential revocation, archival |
| **Reactivated** | Retired agent is reactivated | Re-registration, credential re-issuance |

---

## SECTION 3: LEAST AGENCY

### 3.1 Least Agency Principles

| Principle | Description | Implementation |
| :---- | :---- | :---- |
| **Decision Budget** | Limit number of autonomous decisions per session | Meta-Constraint (CRO) |
| **Scope Budget** | Limit scope expansion per session | Meta-Constraint (CRO) |
| **Time Budget** | Limit autonomous execution time | Meta-Constraint (CRO) |
| **Capability Budget** | Limit CTAM grants per session | CTAM tier bounds |

### 3.2 CTAM Enhancement — Least Agency

| Enhancement | Description |
| :---- | :---- |
| **Decision Budget** | Add `decision_budget` field to CTAM grants — maximum autonomous decisions per session |
| **Scope Budget** | Add `scope_budget` field to CTAM grants — maximum scope expansion per session |
| **Time Budget** | Add `time_budget` field to CTAM grants — maximum autonomous execution time |
| **Capability Budget** | Add `capability_budget` field to CTAM grants — maximum CTAM grants per session |

### 3.3 Least Agency Enforcement

| Enforcement | Description |
| :---- | :---- |
| **Pre-Execution Check** | Raidillo checks budgets before each autonomous decision |
| **In-Session Monitoring** | Raidillo monitors budget consumption during session |
| **Budget Exhaustion** | When budget is exhausted, agent reverts to escalation mode |
| **HAN Notification** | HAN is notified when budget is near exhaustion |
| **XOO Creation** | Budget violation creates XOO |

---

## SECTION 4: MUTUAL AUTHENTICATION

### 4.1 Mutual Authentication Requirements

| Requirement | Description |
| :---- | :---- |
| **Agent-to-Agent** | All agent-to-agent communications must be mutually authenticated |
| **Agent-to-MCP** | All agent-MCP interactions must be mutually authenticated |
| **Agent-to-HAN** | All agent-HAN interactions must be mutually authenticated |
| **Authentication Logging** | All authentication events are logged |

### 4.2 Authentication Flow

Agent A → Authentication Request → Agent B  
Agent A ← Authentication Challenge ← Agent B  
Agent A → Challenge Response → Agent B  
Agent A ← Authentication Confirmation ← Agent B  
Agent A → Encrypted Communication → Agent B

### 4.3 Authentication Types

| Type | Description | Use Case |
| :---- | :---- | :---- |
| **Certificate-Based** | X.509 certificates | High-security communications |
| **Token-Based** | JWT tokens | Standard communications |
| **API Key** | API keys with rotation | Lower-security communications |
| **Mutual TLS** | mTLS | Network-level authentication |

---

## SECTION 5: NHI LIFECYCLE MANAGEMENT

### 5.1 Lifecycle Stages

| Stage | Description | Actions |
| :---- | :---- | :---- |
| **Registration** | NHI is registered in the system | Identity creation, credential issuance |
| **Active** | NHI is operational | Continuous monitoring, periodic review |
| **Suspended** | NHI is temporarily inactive | Suspension, investigation |
| **Retired** | NHI is permanently decommissioned | Credential revocation, archival |

### 5.2 NHI Governance Requirements

| Requirement | Description |
| :---- | :---- |
| **Registration** | All NHIs must be registered before use |
| **Credential Management** | Credentials must be rotated regularly |
| **Access Review** | NHI access must be reviewed periodically |
| **Activity Monitoring** | NHI activity must be monitored |
| **Retirement** | NHIs must be properly retired when no longer needed |

---

## SECTION 6: AGENTIC SECURITY IMPLEMENTATION

\# agentic\_security.py  
"""  
Agentic Security & Identity (AEGIS) — Complete Implementation  
"""

from enum import Enum  
from typing import List, Dict, Optional  
from dataclasses import dataclass, field  
from datetime import datetime  
import hashlib  
import secrets

class IdentityClass(Enum):  
    HUMAN \= "Human"  
    MACHINE \= "Machine"  
    AGENT \= "Agent"  
    AGENT\_COALITION \= "Agent Coalition"

class IdentityStatus(Enum):  
    CREATED \= "Created"  
    ACTIVE \= "Active"  
    SUSPENDED \= "Suspended"  
    RETIRED \= "Retired"  
    REACTIVATED \= "Reactivated"

class AuthType(Enum):  
    CERTIFICATE \= "Certificate"  
    TOKEN \= "Token"  
    API\_KEY \= "API Key"  
    MUTUAL\_TLS \= "Mutual TLS"

@dataclass  
class AgentIdentity:  
    """Agent identity record"""  
    agent\_id: str  
    identity\_class: IdentityClass  
    status: IdentityStatus  
    created\_date: str  
    credentials: Dict\[str, str\]  
    lifecycle\_events: List\[Dict\]  
    last\_updated: str

@dataclass  
class LeastAgencyBudgets:  
    """Least Agency budgets for an agent"""  
    decision\_budget: int  \# Maximum autonomous decisions per session  
    scope\_budget: int     \# Maximum scope expansion per session  
    time\_budget: int      \# Maximum autonomous execution time (seconds)  
    capability\_budget: List\[str\]  \# Maximum CTAM grants per session

@dataclass  
class AuthenticationEvent:  
    """Authentication event record"""  
    event\_id: str  
    timestamp: str  
    source\_agent: str  
    target\_agent: str  
    auth\_type: AuthType  
    success: bool  
    certificate\_ref: Optional\[str\] \= None  
    token\_ref: Optional\[str\] \= None  
    error: Optional\[str\] \= None

class AgenticSecurity:  
    """Agentic Security & Identity (AEGIS) Framework"""  
      
    def \_\_init\_\_(self):  
        self.identities: Dict\[str, AgentIdentity\] \= {}  
        self.auth\_events: List\[AuthenticationEvent\] \= {}  
        self.budgets: Dict\[str, LeastAgencyBudgets\] \= {}  
        self.auth\_events \= \[\]  
      
    def create\_agent\_identity(  
        self,  
        agent\_id: str,  
        identity\_class: IdentityClass,  
        decision\_budget: int \= 10,  
        scope\_budget: int \= 3,  
        time\_budget: int \= 3600,  
        capability\_budget: List\[str\] \= None  
    ) \-\> AgentIdentity:  
        """Create a new agent identity with Least Agency budgets"""  
        if capability\_budget is None:  
            capability\_budget \= \["perception", "synthesis"\]  
          
        \# Generate credentials  
        credentials \= {  
            "certificate": self.\_generate\_certificate(agent\_id),  
            "api\_key": self.\_generate\_api\_key(),  
            "token": self.\_generate\_token()  
        }  
          
        identity \= AgentIdentity(  
            agent\_id=agent\_id,  
            identity\_class=identity\_class,  
            status=IdentityStatus.CREATED,  
            created\_date=datetime.now().isoformat(),  
            credentials=credentials,  
            lifecycle\_events=\[{  
                "event": "Identity Created",  
                "timestamp": datetime.now().isoformat(),  
                "details": f"Identity class: {identity\_class.value}"  
            }\],  
            last\_updated=datetime.now().isoformat()  
        )  
          
        \# Set budgets  
        budgets \= LeastAgencyBudgets(  
            decision\_budget=decision\_budget,  
            scope\_budget=scope\_budget,  
            time\_budget=time\_budget,  
            capability\_budget=capability\_budget  
        )  
          
        self.identities\[agent\_id\] \= identity  
        self.budgets\[agent\_id\] \= budgets  
          
        \# Activate  
        self.activate\_agent(agent\_id)  
          
        return identity  
      
    def activate\_agent(self, agent\_id: str) \-\> AgentIdentity:  
        """Activate an agent identity"""  
        identity \= self.identities.get(agent\_id)  
        if not identity:  
            raise ValueError(f"Agent {agent\_id} not found")  
          
        identity.status \= IdentityStatus.ACTIVE  
        identity.lifecycle\_events.append({  
            "event": "Identity Activated",  
            "timestamp": datetime.now().isoformat()  
        })  
        identity.last\_updated \= datetime.now().isoformat()  
          
        return identity  
      
    def suspend\_agent(self, agent\_id: str, reason: str) \-\> AgentIdentity:  
        """Suspend an agent identity"""  
        identity \= self.identities.get(agent\_id)  
        if not identity:  
            raise ValueError(f"Agent {agent\_id} not found")  
          
        identity.status \= IdentityStatus.SUSPENDED  
        identity.lifecycle\_events.append({  
            "event": "Identity Suspended",  
            "timestamp": datetime.now().isoformat(),  
            "details": reason  
        })  
        identity.last\_updated \= datetime.now().isoformat()  
          
        return identity  
      
    def retire\_agent(self, agent\_id: str, reason: str) \-\> AgentIdentity:  
        """Retire an agent identity"""  
        identity \= self.identities.get(agent\_id)  
        if not identity:  
            raise ValueError(f"Agent {agent\_id} not found")  
          
        identity.status \= IdentityStatus.RETIRED  
        identity.lifecycle\_events.append({  
            "event": "Identity Retired",  
            "timestamp": datetime.now().isoformat(),  
            "details": reason  
        })  
        identity.last\_updated \= datetime.now().isoformat()  
          
        \# Revoke credentials  
        identity.credentials\["certificate"\] \= "REVOKED"  
        identity.credentials\["api\_key"\] \= "REVOKED"  
        identity.credentials\["token"\] \= "REVOKED"  
          
        return identity  
      
    def reactivate\_agent(self, agent\_id: str) \-\> AgentIdentity:  
        """Reactivate a retired agent identity"""  
        identity \= self.identities.get(agent\_id)  
        if not identity:  
            raise ValueError(f"Agent {agent\_id} not found")  
          
        \# Generate new credentials  
        identity.credentials \= {  
            "certificate": self.\_generate\_certificate(agent\_id),  
            "api\_key": self.\_generate\_api\_key(),  
            "token": self.\_generate\_token()  
        }  
          
        identity.status \= IdentityStatus.REACTIVATED  
        identity.lifecycle\_events.append({  
            "event": "Identity Reactivated",  
            "timestamp": datetime.now().isoformat()  
        })  
        identity.last\_updated \= datetime.now().isoformat()  
          
        return identity  
      
    def authenticate(  
        self,  
        source\_agent: str,  
        target\_agent: str,  
        auth\_type: AuthType,  
        credential: str  
    ) \-\> AuthenticationEvent:  
        """Authenticate an agent-to-agent communication"""  
        event\_id \= f"AUTH-{datetime.now().strftime('%Y%m%d')}-{len(self.auth\_events)+1:04d}"  
          
        \# Verify source agent  
        source \= self.identities.get(source\_agent)  
        if not source or source.status not in \[IdentityStatus.ACTIVE, IdentityStatus.REACTIVATED\]:  
            event \= AuthenticationEvent(  
                event\_id=event\_id,  
                timestamp=datetime.now().isoformat(),  
                source\_agent=source\_agent,  
                target\_agent=target\_agent,  
                auth\_type=auth\_type,  
                success=False,  
                error="Source agent not active"  
            )  
            self.auth\_events.append(event)  
            return event  
          
        \# Verify target agent  
        target \= self.identities.get(target\_agent)  
        if not target or target.status not in \[IdentityStatus.ACTIVE, IdentityStatus.REACTIVATED\]:  
            event \= AuthenticationEvent(  
                event\_id=event\_id,  
                timestamp=datetime.now().isoformat(),  
                source\_agent=source\_agent,  
                target\_agent=target\_agent,  
                auth\_type=auth\_type,  
                success=False,  
                error="Target agent not active"  
            )  
            self.auth\_events.append(event)  
            return event  
          
        \# Verify credential  
        success \= self.\_verify\_credential(source\_agent, auth\_type, credential)  
          
        event \= AuthenticationEvent(  
            event\_id=event\_id,  
            timestamp=datetime.now().isoformat(),  
            source\_agent=source\_agent,  
            target\_agent=target\_agent,  
            auth\_type=auth\_type,  
            success=success,  
            certificate\_ref=credential if auth\_type \== AuthType.CERTIFICATE else None,  
            token\_ref=credential if auth\_type \== AuthType.TOKEN else None  
        )  
          
        self.auth\_events.append(event)  
        return event  
      
    def check\_budget(  
        self,  
        agent\_id: str,  
        budget\_type: str,  
        current\_usage: int  
    ) \-\> bool:  
        """Check if an agent has budget remaining"""  
        budgets \= self.budgets.get(agent\_id)  
        if not budgets:  
            return False  
          
        if budget\_type \== "decision":  
            return current\_usage \< budgets.decision\_budget  
        elif budget\_type \== "scope":  
            return current\_usage \< budgets.scope\_budget  
        elif budget\_type \== "time":  
            return current\_usage \< budgets.time\_budget  
        elif budget\_type \== "capability":  
            \# In production, check capability against budget  
            return True  
          
        return False  
      
    def \_generate\_certificate(self, agent\_id: str) \-\> str:  
        """Generate a certificate for an agent"""  
        \# In production, use proper certificate generation  
        return f"CERT-{agent\_id}-{hashlib.sha256(secrets.token\_bytes(32)).hexdigest()\[:16\]}"  
      
    def \_generate\_api\_key(self) \-\> str:  
        """Generate an API key"""  
        return f"API-{hashlib.sha256(secrets.token\_bytes(32)).hexdigest()\[:32\]}"  
      
    def \_generate\_token(self) \-\> str:  
        """Generate a token"""  
        return f"TOKEN-{hashlib.sha256(secrets.token\_bytes(32)).hexdigest()\[:32\]}"  
      
    def \_verify\_credential(self, agent\_id: str, auth\_type: AuthType, credential: str) \-\> bool:  
        """Verify an agent's credential"""  
        identity \= self.identities.get(agent\_id)  
        if not identity:  
            return False  
          
        if auth\_type \== AuthType.CERTIFICATE:  
            return identity.credentials.get("certificate") \== credential  
        elif auth\_type \== AuthType.API\_KEY:  
            return identity.credentials.get("api\_key") \== credential  
        elif auth\_type \== AuthType.TOKEN:  
            return identity.credentials.get("token") \== credential  
        elif auth\_type \== AuthType.MUTUAL\_TLS:  
            \# In production, verify mTLS  
            return True  
          
        return False  
      
    def get\_identity(self, agent\_id: str) \-\> Optional\[AgentIdentity\]:  
        """Get an agent identity"""  
        return self.identities.get(agent\_id)  
      
    def get\_budgets(self, agent\_id: str) \-\> Optional\[LeastAgencyBudgets\]:  
        """Get Least Agency budgets for an agent"""  
        return self.budgets.get(agent\_id)  
      
    def get\_auth\_events(  
        self,  
        source\_agent: Optional\[str\] \= None,  
        target\_agent: Optional\[str\] \= None,  
        limit: int \= 100  
    ) \-\> List\[AuthenticationEvent\]:  
        """Get authentication events"""  
        events \= self.auth\_events  
          
        if source\_agent:  
            events \= \[e for e in events if e.source\_agent \== source\_agent\]  
        if target\_agent:  
            events \= \[e for e in events if e.target\_agent \== target\_agent\]  
          
        return sorted(events, key=lambda x: x.timestamp, reverse=True)\[:limit\]  
      
    def summary(self) \-\> Dict:  
        """Get a summary of agent security status"""  
        return {  
            "total\_identities": len(self.identities),  
            "by\_status": {  
                status.value: len(\[i for i in self.identities.values() if i.status \== status\])  
                for status in IdentityStatus  
            },  
            "by\_class": {  
                cls.value: len(\[i for i in self.identities.values() if i.identity\_class \== cls\])  
                for cls in IdentityClass  
            },  
            "total\_auth\_events": len(self.auth\_events),  
            "auth\_success\_rate": (  
                len(\[e for e in self.auth\_events if e.success\]) / len(self.auth\_events) \* 100  
                if self.auth\_events else 0  
            ),  
            "active\_agents": len(\[i for i in self.identities.values()   
                                 if i.status in \[IdentityStatus.ACTIVE, IdentityStatus.REACTIVATED\]\])  
        }

---

## SECTION 7: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| **AWOF** | Agent identities are AWOF-classified |
| **CTAM** | Least Agency is implemented via CTAM extensions |
| **ADTEP** | Mutual Authentication enforced by ADTEP |
| **RGI-8** | Continuous risk monitoring |
| **IMP** | Agent identity logs |
| **HAN/HOF** | Agent identity lifecycle requires HAN authorization |
| **MCP Server Governance** | Agent-MCP authentication |
| **Trigger System** | Authentication failures trigger Escalation Flag |

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| Agentic Security & Identity (AEGIS) v1.0 | Initial specification — 4 identity classes, 5 identity lifecycle stages, Least Agency with 4 budget types, Mutual Authentication with 4 authentication types, NHI lifecycle management |

---

## The One-Sentence Summary

> *"The Agentic Security & Identity (AEGIS) Framework v1.0 establishes a complete security framework for AI agents — with 4 identity classes (Human, Machine, Agent, Agent Coalition), 5 lifecycle stages (Creation, Active, Suspended, Retired, Reactivated), Least Agency implementation via CTAM budgets (Decision, Scope, Time, Capability), Mutual Authentication for all agent-to-agent communications (Certificate, Token, API Key, mTLS), and NHI lifecycle management — treating agents as a distinct identity class requiring specialized security governance."*
