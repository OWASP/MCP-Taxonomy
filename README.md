# MCP Security Taxonomy

**A common language for securing agentic AI connections, context, and capability.**

Open, vendor-neutral classification of MCP security risks, weaknesses, attack patterns, controls, detections, and test cases for the [Model Context Protocol](https://modelcontextprotocol.io/) ecosystem.

Start with the complete reference:

**[MCP-SECURITY-TAXONOMY-COMPLETE.md](MCP-SECURITY-TAXONOMY-COMPLETE.md)**

It is a single, combined document covering glossary, design principles, taxonomy structure, framework mappings, CVE-aligned tags, and external crosswalks.

Also in this repository:

**[MCP-Threat-Taxonomy.md](MCP-Threat-Taxonomy.md)**

A structured threat classification: 30 threats across six domains (`T1.1`–`T6.5`) with severity ratings, an attack-chain matrix, kill-chain phases, and OWASP mappings.

Maintained and curated by [Vandana Verma Sehgal](https://github.com/vermava)

## Complete reference (sections)

The combined document includes, in order:

1. **MCP relationship map** — host, client, server, transport, and backend boundaries
2. **Design principles** — taxonomy patterns, 11-domain model, entry quality bar, anti-patterns
3. **Glossary** — MCP terms, AI security terms, and AppSec terms used across MCP security
4. **Common confusions** — host vs client vs server, tool vs resource vs prompt, injection families, CVE vs CWE vs CVSS vs EPSS
5. **Taxonomy overview** — legacy 7-domain grouping for high-level risk navigation
6. **OWASP MCP Top 10 mapping** — MCP01–MCP10 with examples, impacts, and controls
7. **Root cause (weakness family) taxonomy** — CVE-aligned tags such as `INJ-CMD`, `PATH-TRAV`, `SSRF`, `AUTH-BYPASS`, `X-TENANT`
8. **External references** — MCP-38, MCPShield, MCPSecBench, MCP-DPT, community standards, and practitioner guides

## Who this is for

- **Security engineers** threat-modeling MCP hosts, clients, servers, and gateways
- **Developers** building or integrating MCP servers and tools
- **GRC and compliance teams** mapping MCP risks to OWASP, CWE, NIST CSF, ISO 27001, and related frameworks
- **Researchers** comparing MCP taxonomies (MCP-38, MCPShield, MCPSecBench, MCP-DPT)





