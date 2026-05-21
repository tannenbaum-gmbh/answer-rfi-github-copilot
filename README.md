# GitHub Copilot RFI Assistant

A repository of custom GitHub Copilot agents and reusable prompts designed to help answer **RFI (Request for Information)** questionnaires about GitHub Copilot from an enterprise perspective.

## Overview

Responding to enterprise RFI questionnaires about GitHub Copilot, GitHub Advanced Security, and Microsoft platform licensing can be time-consuming. This repository provides specialized Copilot agents and ready-made prompt files that streamline the process by leveraging official documentation, the GitHub Copilot Trust Center, and Microsoft Learn.

## Repository Structure

```
.github/
  agents/
    rfi-assistant-ghcp.md                       # Agent: GitHub Copilot features & capabilities
    rfi-assistant-governance.md                 # Agent: Governance, privacy, security & compliance
    rfi-assistant-ghas.md                       # Agent: GitHub Advanced Security
    rfi-assistant-defender-for-cloud-devops.md  # Agent: Microsoft Defender for Cloud DevOps
    rfi-orchestrator-github-security.md         # Orchestrator: GHAS + Defender for Cloud DevOps
    rfi-assistant-azure-platform-licensing-cost-management.md # Agent: Azure licensing & cost management
    rfi-assistant-microsoft-defender-licensing.md # Agent: Microsoft Defender licensing
    rfi-assistant-github-licensing.md # Agent: GitHub platform licensing
    rfi-orchestrator-licensing.md # Orchestrator: Azure + Defender + GitHub licensing
  prompts/
    rfi-answer-csv.prompt.md     # Reusable prompt: answer RFI as CSV
    rfi-answer-markdown.prompt.md # Reusable prompt: answer RFI as Markdown
questions/                        # Sample RFI questionnaires (CSV)
```

## Agents

### `rfi-assistant-ghcp` — Features & Capabilities

Answers questions about GitHub Copilot's product functionality:

- Code completion, Chat, and Agent mode
- Supported languages, IDEs, and extensions
- GitHub Copilot CLI, SDK, and ACP server
- CI/CD integration on GitHub and non-GitHub platforms
- Figma MCP server integration
- Plan tiers and feature differences

### `rfi-assistant-governance` — Governance & Compliance

Answers questions about enterprise data privacy and security:

- Data processing, retention, and deletion
- Security certifications (SOC 2, ISO 27001, etc.)
- GDPR and data residency
- Enterprise administrative controls
- Incident response and audit logging
- GitHub Data Protection Agreement

### `rfi-assistant-azure-platform-licensing-cost-management` — Azure Licensing & Cost Management

Answers enterprise procurement and FinOps-focused questions about Microsoft Azure:

- Licensing and purchasing channels (MCA, EA, CSP)
- Billing scopes, subscription/account structures, and invoicing
- Cost analysis, budgeting, alerting, and forecasting
- Reservations, savings plans, and Azure Hybrid Benefit
- Cost governance guardrails and chargeback/showback patterns

### `rfi-assistant-microsoft-defender-licensing` — Microsoft Defender Licensing

Answers enterprise licensing and entitlement questions for Microsoft Defender:

- Plan and SKU boundary clarification across Microsoft Defender products
- Suite versus standalone entitlement mapping
- Prerequisite and dependency identification for key Defender services
- Microsoft Defender for Cloud billing model and pricing references
- Procurement-ready licensing response patterns for RFI submissions

### `rfi-assistant-github-licensing` — GitHub Licensing

Answers enterprise licensing and commercial questions for GitHub platform plans:

- Plan and entitlement mapping across GitHub Team, GitHub Enterprise Cloud, and GitHub Enterprise Server
- Add-on licensing boundaries for GitHub Advanced Security and GitHub Copilot plans
- Billing constructs, seat governance, and lifecycle controls
- Procurement-ready plan comparison and migration considerations
- Documentation-based guidance for formal RFI licensing responses

### `rfi-assistant-ghas` — GitHub Advanced Security

Answers questions about GitHub Advanced Security features, capabilities, and deployment:

- GitHub Code Security and GitHub Secret Protection
- Code scanning with CodeQL and third-party tools
- Secret scanning, push protection, delegated bypass, and custom patterns
- Dependabot alerts, security updates, and auto-triage
- Dependency review and dependency review action workflows
- Security overview, risk assessment, and security campaigns
- Large-scale enablement, security configurations, and global settings
- REST APIs, webhooks, and automation for security operations
- Billing, licensing, and public-repository availability

### `rfi-assistant-defender-for-cloud-devops` — Microsoft Defender for Cloud DevOps

Answers questions about Microsoft Defender for Cloud DevOps security and its integration with GitHub Advanced Security:

- Defender for Cloud DevOps security capabilities and architecture
- Native integration between Defender for Cloud and GitHub Advanced Security
- Code-to-cloud correlation from repository to artifact to runtime workload
- Runtime risk context and deployment-aware security triage
- Organization-level runtime-aware filtering and campaign targeting
- GitHub issue creation from Defender for Cloud recommendations
- Prerequisites, licensing, permissions, and cloud availability boundaries
- Data flow, integration dependencies, and API/automation options
- Product boundaries between GitHub-native controls and Defender-side controls

### `rfi-orchestrator-github-security` — GitHub Security Orchestrator

An orchestrator agent that intelligently routes RFI questions spanning GitHub Advanced Security and Microsoft Defender for Cloud DevOps, invoking the appropriate specialist agents and synthesizing cross-product responses:

- Routes GHAS-only questions to `rfi-assistant-ghas`
- Routes Defender for Cloud DevOps-only questions to `rfi-assistant-defender-for-cloud-devops`
- Coordinates both agents for integration or cross-product scenarios
- Clearly separates product boundaries in combined responses
- Ideal for procurement, architecture, and governance questionnaires that cover the full GitHub security stack

## Prerequisites

- **GitHub Copilot Business** or **GitHub Copilot Enterprise** subscription
- GitHub Copilot Chat enabled in your IDE (VS Code, Visual Studio, JetBrains, etc.) or on GitHub.com
- This repository cloned or accessible within your GitHub organization

## How to Use

### 1. Using the Agents in VS Code (Copilot Chat)

1. Open this repository in VS Code.
2. Open Copilot Chat and switch to **Agent mode**.
3. Invoke an agent by selecting it from the agent picker or mentioning it:
   - `@rfi-assistant-ghcp` for GitHub Copilot feature and capability questions
   - `@rfi-assistant-governance` for governance and compliance questions
   - `@rfi-assistant-ghas` for GitHub Advanced Security questions
   - `@rfi-assistant-defender-for-cloud-devops` for Microsoft Defender for Cloud DevOps questions
   - `@rfi-orchestrator-github-security` for questions spanning GHAS and Defender for Cloud DevOps
   - `@rfi-assistant-azure-platform-licensing-cost-management` for Microsoft Azure licensing and cost management questions
   - `@rfi-assistant-microsoft-defender-licensing` for Microsoft Defender licensing and entitlement questions
   - `@rfi-assistant-github-licensing` for GitHub licensing and entitlement questions
   - `@rfi-orchestrator-licensing` for cross-product licensing and procurement questions
4. Paste your RFI questions into the chat and the agent will provide cited, enterprise-ready answers.

### 2. Using the Reusable Prompts

The `prompts/` folder contains two prompt files for different output formats:

| Prompt file | Output format | Description |
|---|---|---|
| `rfi-answer-csv.prompt.md` | CSV | Appends `Supported`, `Answer`, and `Citations` columns to the input CSV |
| `rfi-answer-markdown.prompt.md` | Markdown | Generates a structured Markdown document with an appendix of citations |

To use a prompt:

1. Open Copilot Chat in Agent mode.
2. Attach the desired prompt file.
3. Provide the RFI questionnaire (paste or attach the CSV / text).
4. Review the generated answers and customize for your organization.

### 3. Working with the Sample Questions

The `questions/` folder contains sample RFI questionnaires in CSV format. Use them as input when testing the agents or prompts, or as a reference for the kinds of questions the agents can handle.

## Example Workflow

```
1. Receive an RFI questionnaire from a customer (CSV or document).
2. Place the CSV in the questions/ folder.
3. Open Copilot Chat → Agent mode → select the appropriate agent:
   - rfi-assistant-ghcp         (GitHub Copilot features)
   - rfi-assistant-governance   (Copilot governance & compliance)
   - rfi-assistant-ghas         (GitHub Advanced Security)
   - rfi-assistant-defender-for-cloud-devops  (Defender for Cloud DevOps)
   - rfi-orchestrator-github-security         (cross-product security questions)
   - rfi-assistant-azure-platform-licensing-cost-management (Azure licensing & cost management)
   - rfi-assistant-microsoft-defender-licensing (Microsoft Defender licensing)
   - rfi-assistant-github-licensing (GitHub platform licensing)
   - rfi-orchestrator-licensing (cross-product licensing questions)
4. Attach the rfi-answer-csv.prompt.md prompt.
5. Paste or reference the CSV file.
6. Review, refine, and export the answers.
7. Have your legal/compliance team review before submission.
```

## Important Notes

- **Verify currency** — GitHub Copilot evolves rapidly. Always cross-check answers against the latest official documentation.
- **Customize for your context** — Add organization-specific policies and contract terms.
- **Legal review** — Have legal/compliance teams review responses before formal RFI submission.
- **Not legal advice** — The agents provide factual information from public documentation, not legal guidance.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on adding questions, improving agent instructions, and submitting pull requests.

## License

This project is licensed under the [MIT License](LICENSE).
