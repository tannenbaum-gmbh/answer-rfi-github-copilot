# Prompt Files for GitHub Copilot RFI Assistant

This directory contains ready-to-use prompt files that make it easy to interact with the GitHub Copilot RFI Assistant agent.

## What Are Prompt Files?

Prompt files are pre-written, structured prompts that you can use directly with the RFI Assistant agent. Instead of typing out complex questions, you can simply:
1. Open a prompt file
2. Fill in any customer-specific details
3. Use it with the agent to get comprehensive answers

## How to Use Prompt Files

### In VS Code with GitHub Copilot Chat:

1. **Open the prompt file** you want to use (e.g., `data-collection.prompt.md`)
2. **Customize if needed** - Add your organization's specific context
3. **Select all the content** (Ctrl+A or Cmd+A)
4. **Open GitHub Copilot Chat** (usually Ctrl+Shift+I or via the sidebar)
5. **Type** `@rfi-assistant` (to target the custom agent)
6. **Paste the prompt** content
7. **Send** and receive a comprehensive response

### Using Slash Commands (Quick Access):

If you've configured the VS Code agent, you can use slash commands for quick access:

```
@rfi-assistant /data-collection
@rfi-assistant /security-certs
@rfi-assistant /gdpr
@rfi-assistant /code-privacy
@rfi-assistant /enterprise-controls
@rfi-assistant /encryption
@rfi-assistant /incident-response
```

## Available Prompt Files

### 1. `data-collection.prompt.md`
**Use when:** Completing data privacy impact assessments (DPIA) or data processing documentation

**Covers:**
- What data is collected
- How data is processed
- Data retention policies
- Data deletion procedures

**Best for:** Privacy teams, DPIAs, data governance

---

### 2. `security-certifications.prompt.md`
**Use when:** Procurement requires proof of security certifications

**Covers:**
- SOC 2 Type II
- ISO 27001, ISO 27018
- GDPR, CCPA compliance
- How to obtain audit reports

**Best for:** Procurement, vendor management, security reviews

---

### 3. `gdpr-compliance.prompt.md`
**Use when:** European organizations need GDPR compliance information

**Covers:**
- Data Processing Agreements (DPA)
- Data subject rights
- Data residency
- Cross-border transfers

**Best for:** EU organizations, legal teams, privacy officers

---

### 4. `code-privacy-ip.prompt.md`
**Use when:** Concerned about code confidentiality and intellectual property

**Covers:**
- Whether code is used for training
- IP ownership
- Code confidentiality measures
- Content exclusion options

**Best for:** Software companies, IP-sensitive organizations, legal teams

---

### 5. `enterprise-controls.prompt.md`
**Use when:** Administrators need to understand governance capabilities

**Covers:**
- User management
- Policy controls
- Content exclusion
- Audit logging
- Monitoring and reporting

**Best for:** IT administrators, security teams, compliance officers

---

### 6. `encryption-security.prompt.md`
**Use when:** Security teams need detailed technical security information

**Covers:**
- Encryption in transit and at rest
- Key management
- Network security
- Access controls
- Application security

**Best for:** Security engineers, technical security reviews, audits

---

### 7. `incident-response.prompt.md`
**Use when:** Need to understand security incident handling

**Covers:**
- Incident response process
- Customer notification procedures
- Breach notification
- Communication channels

**Best for:** Security operations, business continuity planning, risk management

---

### 8. `vendor-questionnaire.prompt.md`
**Use when:** Completing comprehensive vendor security questionnaires

**Covers:**
- All major sections of typical vendor questionnaires
- General info, data handling, security, compliance, incident management

**Best for:** Vendor management, comprehensive RFIs, customer questionnaires

---

### 9. `custom-rfi-template.prompt.md`
**Use when:** You have specific questions not covered by other prompts

**How to use:**
1. Open this file
2. Paste your actual RFI questions in the designated section
3. Use with the agent
4. Get customized responses

**Best for:** Unique questionnaires, specific customer requirements, ad-hoc requests

## Tips for Best Results

### 1. Customize the Context
Add your organization-specific information:
```markdown
## Context
We are a healthcare organization in the EU with strict HIPAA and GDPR requirements...
```

### 2. Be Specific About Requirements
```markdown
We need responses that:
- Are suitable for legal review
- Include specific technical details
- Address German data protection requirements
```

### 3. Specify Output Format
```markdown
## Output Format
Please format as a table with columns:
| Question | Answer | Source Documentation | Compliance Notes |
```

### 4. Ask Follow-Up Questions
After receiving initial responses, ask for:
- More detail on specific points
- Clarification of technical terms
- Additional documentation links
- Examples or use cases

## Workflow Example

### Scenario: Customer Security Questionnaire

1. **Receive questionnaire** from customer with 50 questions
2. **Review questions** and identify topics
3. **Use relevant prompt files:**
   - Section on data: `data-collection.prompt.md`
   - Section on security: `encryption-security.prompt.md`
   - Section on compliance: `gdpr-compliance.prompt.md`
4. **Customize each prompt** with specific questions from the questionnaire
5. **Get responses** from the RFI Assistant
6. **Compile into final document**
7. **Have legal/compliance review**
8. **Submit to customer**

**Time saved:** 5-10 hours of documentation research → 1-2 hours of structured prompting and review

## Creating Your Own Prompt Files

Want to create custom prompts for recurring scenarios?

### Template Structure:
```markdown
# [Topic Title]

@rfi-assistant

## Question
[Clear question or request]

## Context
[Your organization's situation and requirements]

## Required Information
[Specific items you need covered]
1. First requirement
2. Second requirement
...

## Output Format
[How you want the response formatted]
```

### Save as:
`prompts/[descriptive-name].prompt.md`

## Integration with Other Tools

### Copy-Paste to RFI Documents:
- Responses are formatted for professional documentation
- Include citations that you can verify
- Add to Word, Google Docs, or other formats

### Export Conversations:
- Save chat history for reference
- Share with team members
- Include in documentation

### Version Control:
- Track changes to your customized prompts
- Share prompt files with team
- Maintain consistency across organization

## Best Practices

✅ **DO:**
- Customize prompts for your specific needs
- Review and verify all responses
- Include citations in your final documents
- Have legal/compliance teams review
- Keep prompts updated as requirements change

❌ **DON'T:**
- Copy responses without verification
- Skip customization for your context
- Submit without legal review
- Use outdated information
- Forget to cite sources

## Support

- **Can't find a prompt for your use case?** Use `custom-rfi-template.prompt.md`
- **Need help customizing?** See examples in `../examples/EXAMPLE_CONVERSATION.md`
- **Want to contribute a prompt?** See `../CONTRIBUTING.md`

## Quick Reference

| Need Information About | Use This Prompt File | Time to Complete |
|------------------------|---------------------|------------------|
| Data collection & privacy | `data-collection.prompt.md` | 5-10 min |
| Security certifications | `security-certifications.prompt.md` | 5 min |
| GDPR compliance | `gdpr-compliance.prompt.md` | 10 min |
| Code privacy & IP | `code-privacy-ip.prompt.md` | 10 min |
| Admin controls | `enterprise-controls.prompt.md` | 10-15 min |
| Encryption & security | `encryption-security.prompt.md` | 10-15 min |
| Incident response | `incident-response.prompt.md` | 10 min |
| Full questionnaire | `vendor-questionnaire.prompt.md` | 30-45 min |
| Custom questions | `custom-rfi-template.prompt.md` | Varies |

---

**Ready to start?** Pick a prompt file relevant to your current needs and try it with the RFI Assistant!
