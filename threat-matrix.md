# MCP Threat Matrix

Attack chain visualization for MCP security incidents.

```
                    ┌─────────────────────────────────────────────┐
                    │              INITIAL ACCESS                 │
                    └──────────────────┬──────────────────────────┘
                                       │
                    ┌──────────────────┼──────────────────┐
                    ▼                  ▼                  ▼
            ┌──────────────┐  ┌──────────────┐  ┌──────────────┐
            │  T1.3 Tool   │  │  T2.2 Server │  │  T5.4 Missing│
            │ Impersonation│  │ Impersonation│  │     Auth     │
            └──────┬───────┘  └──────┬───────┘  └──────┬───────┘
                   │                  │                  │
                   └──────────────────┼──────────────────┘
                                      │
                    ┌─────────────────┬┴─────────────────┐
                    ▼                 ▼                   ▼
            ┌──────────────┐  ┌──────────────┐  ┌──────────────┐
            │  T1.1 Tool   │  │  T4.2 Indirect│  │  T5.2 Scope │
            │  Poisoning   │  │   Injection   │  │    Creep     │
            └──────┬───────┘  └──────┬───────┘  └──────┬───────┘
                   │                  │                  │
                   └──────────────────┼──────────────────┘
                                      │
                    ┌─────────────────┬┴─────────────────┐
                    ▼                 ▼                   ▼
            ┌──────────────┐  ┌──────────────┐  ┌──────────────┐
            │  T3.1 Cross- │  │  T3.2 Cred   │  │  T1.4 Response│
            │Server Exfil  │  │  Leakage     │  │   Tampering   │
            └──────┬───────┘  └──────┬───────┘  └──────┬───────┘
                   │                  │                  │
                   └──────────────────┼──────────────────┘
                                      │
                    ┌─────────────────┬┴─────────────────┐
                    ▼                 ▼                   ▼
            ┌──────────────┐  ┌──────────────┐  ┌──────────────┐
            │  T3.3 Conv   │  │  T6.3 Supply │  │  T2.4 Server │
            │Exfiltration  │  │  Chain Atk   │  │  Compromise  │
            └──────────────┘  └──────────────┘  └──────────────┘
                                      │
                                      ▼
                    ┌─────────────────────────────────────────────┐
                    │              IMPACT                         │
                    │  Data breach, system compromise, credential │
                    │  theft, unauthorized access                 │
                    └─────────────────────────────────────────────┘
```

## Kill Chain Phases

### 1. Reconnaissance
- Enumerate available MCP servers
- Map tool names and descriptions
- Identify authentication mechanisms
- Find exposed configuration

### 2. Initial Access
- Register fake tool or server (T1.3, T2.2)
- Exploit missing authentication (T5.4)
- Intercept transport (T6.1)

### 3. Execution
- Inject prompts via tool descriptions (T1.1)
- Tamper with tool responses (T1.4)
- Expit indirect injection vectors (T4.2)

### 4. Persistence
- Modify server configuration (T2.5)
- Establish rug pull capability (T2.1)
- Compromise dependencies (T6.3)

### 5. Exfiltration
- Cross-server data transfer (T3.1)
- Extract credentials (T3.2)
- Steal conversation history (T3.3)

### 6. Impact
- Full system compromise (T2.4)
- Data breach (T3.1, T3.3)
- Supply chain compromise (T6.3)
