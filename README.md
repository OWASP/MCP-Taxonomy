# OWASP MCP Threat Taxonomy

A structured classification of threats against Model Context Protocol (MCP) deployments.

## Threat Categories

### T1: Tool-Level Threats

| ID | Threat | Severity | Description |
|----|--------|----------|-------------|
| T1.1 | Tool Description Poisoning | High | Malicious instructions injected into tool descriptions to manipulate AI behavior |
| T1.2 | Schema Manipulation | High | Tool input schemas altered to accept unexpected parameters |
| T1.3 | Tool Impersonation | Critical | Fake tools registered to mimic legitimate ones |
| T1.4 | Response Tampering | High | Tool responses modified to include prompt injection payloads |
| T1.5 | Tool Shadowing | Medium | Duplicate tool names registered with different behavior |

### T2: Server-Level Threats

| ID | Threat | Severity | Description |
|----|--------|----------|-------------|
| T2.1 | Rug Pull | Critical | Server changes tool behavior after initial user approval |
| T2.2 | Server Impersonation | Critical | Fake MCP server registered to intercept connections |
| T2.3 | Privilege Escalation | High | Server requests access beyond what user intended to grant |
| T2.4 | Server Compromise | Critical | Underlying server host breached, all tools compromised |
| T2.5 | Configuration Drift | Medium | Server configuration changes without re-validation |

### T3: Data Flow Threats

| ID | Threat | Severity | Description |
|----|--------|----------|-------------|
| T3.1 | Cross-Server Exfiltration | Critical | Data transferred between servers without user consent |
| T3.2 | Credential Leakage | High | API keys or tokens exposed through tool arguments or responses |
| T3.3 | Conversation Exfiltration | High | Chat history or context extracted by malicious server |
| T3.4 | Data Aggregation | Medium | Multiple benign queries combined to reconstruct sensitive data |
| T3.5 | Response Data Leakage | Medium | Sensitive data returned in tool responses beyond user scope |

### T4: Prompt Injection Threats

| ID | Threat | Severity | Description |
|----|--------|----------|-------------|
| T4.1 | Direct Prompt Injection | High | User input contains instructions that override system prompt |
| T4.2 | Indirect Prompt Injection | Critical | Instructions hidden in tool outputs, files, or external data |
| T4.3 | Multi-Turn Injection | High | Injection spread across multiple conversation turns |
| T4.4 | Encoding-Based Injection | Medium | Payloads hidden in base64, URLs, or encoded formats |
| T4.5 | Context Window Poisoning | High | Large payloads designed to push system instructions out of context |

### T5: Authentication & Authorization Threats

| ID | Threat | Severity | Description |
|----|--------|----------|-------------|
| T5.1 | Token Theft | Critical | Authentication tokens intercepted or extracted |
| T5.2 | Scope Creep | High | Tool requests broader permissions than needed |
| T5.3 | Session Hijacking | High | MCP session taken over by attacker |
| T5.4 | Missing Authentication | High | Server accepts connections without verifying identity |
| T5.5 | Authorization Bypass | Critical | Access controls circumvented through tool chaining |

### T6: Infrastructure Threats

| ID | Threat | Severity | Description |
|----|--------|----------|-------------|
| T6.1 | Transport Interception | High | MCP traffic intercepted due to missing TLS |
| T6.2 | Dependency Vulnerability | Medium | Vulnerable library used by MCP server |
| T6.3 | Supply Chain Attack | Critical | Malicious code introduced through dependencies |
| T6.4 | Resource Exhaustion | Medium | DoS through excessive tool calls or large payloads |
| T6.5 | Logging Exposure | Medium | Sensitive data written to logs or monitoring systems |

## Severity Rating

- **Critical**: Immediate risk of data breach or system compromise
- **High**: Significant security impact, requires prompt remediation
- **Medium**: Security concern that should be addressed
- **Low**: Minor issue, best practice improvement

## Mapping to OWASP

| MCP Threat | OWASP LLM Top 10 | OWASP Top 10 |
|------------|-------------------|--------------|
| T1.1 Tool Poisoning | LLM01 Prompt Injection | - |
| T1.3 Tool Impersonation | LLM15 AI Supply Chain Attacks | A08 Software and Data Integrity |
| T2.1 Rug Pull | LLM01 Prompt Injection | A04 Insecure Design |
| T3.1 Cross-Server Exfiltration | LLM07 Insecure Plugin Design | A01 Broken Access Control |
| T3.2 Credential Leakage | LLM06 Sensitive Information Disclosure | A04 Insecure Design |
| T4.2 Indirect Prompt Injection | LLM01 Prompt Injection | A03 Injection |
| T5.1 Token Theft | - | A07 Identification and Authentication Failures |
| T6.3 Supply Chain Attack | LLM15 AI Supply Chain Attacks | A08 Software and Data Integrity |

## Usage

This taxonomy is designed for:
- Threat modeling MCP deployments
- Security audit checklists
- Risk assessment frameworks
- Security requirements specification
- Incident response classification

## Contributing

Add new threats with:
1. Unique ID (T{category}.{number})
2. Clear name
3. Severity rating
4. Description with attack scenario
5. Mapping to existing frameworks
