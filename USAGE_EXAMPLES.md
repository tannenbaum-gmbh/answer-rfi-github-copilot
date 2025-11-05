# Usage Examples: GitHub Copilot RFI Assistant

This guide shows real-world examples of how to use the RFI Assistant with prompt files.

## Table of Contents
- [Quick Demo: Using a Prompt File](#quick-demo-using-a-prompt-file)
- [Example 1: Responding to a Customer RFI](#example-1-responding-to-a-customer-rfi)
- [Example 2: Data Privacy Impact Assessment](#example-2-data-privacy-impact-assessment)
- [Example 3: Security Certification Verification](#example-3-security-certification-verification)
- [Example 4: Custom Questions](#example-4-custom-questions)

---

## Quick Demo: Using a Prompt File

### Step-by-Step with VS Code

1. **Open the Repository in VS Code**
   ```
   File > Open Folder > answer-rfi-github-copilot
   ```

2. **Open a Prompt File**
   ```
   Navigate to: prompts/data-collection.prompt.md
   ```

3. **Customize (Optional)**
   ```markdown
   ## Context
   We are a healthcare organization in California and need...
   [Add your specific context]
   ```

4. **Open GitHub Copilot Chat**
   - Press `Ctrl+Shift+I` (Windows/Linux) or `Cmd+Shift+I` (Mac)
   - Or click the chat icon in the sidebar

5. **Use the Agent**
   - Type: `@rfi-assistant`
   - Paste the entire prompt file content
   - Or use slash command: `@rfi-assistant /data-collection`

6. **Receive Response**
   - Detailed, structured answer
   - Citations to official sources
   - Ready for RFI document

---

## Example 1: Responding to a Customer RFI

### Scenario
Your customer sends a 30-question security assessment focusing on data handling and compliance.

### Approach

#### Step 1: Identify Question Categories
Review the RFI and group questions:
- 10 questions about data collection/processing
- 8 questions about security certifications
- 7 questions about GDPR compliance
- 5 questions about incident response

#### Step 2: Use Relevant Prompt Files

**For Data Questions:**
```
1. Open: prompts/data-collection.prompt.md
2. In VS Code, open GitHub Copilot Chat
3. Use: @rfi-assistant
4. Paste prompt content
5. Save response for questions 1-10
```

**For Security Certifications:**
```
1. Open: prompts/security-certifications.prompt.md
2. Use: @rfi-assistant /security-certs
3. Save response for questions 11-18
```

**For GDPR Questions:**
```
1. Open: prompts/gdpr-compliance.prompt.md
2. Customize with specific GDPR questions from RFI
3. Use: @rfi-assistant
4. Save response for questions 19-25
```

**For Incident Response:**
```
1. Open: prompts/incident-response.prompt.md
2. Use: @rfi-assistant /incident-response
3. Save response for questions 26-30
```

#### Step 3: Compile Responses
1. Create RFI response document
2. Map agent responses to specific questions
3. Add organization-specific details
4. Include citations
5. Have legal/compliance review

#### Result
- **Time saved**: ~8 hours → 2 hours
- **Quality**: Consistent, well-cited responses
- **Coverage**: Comprehensive answers from official sources

---

## Example 2: Data Privacy Impact Assessment

### Scenario
Your organization needs to complete a DPIA for GitHub Copilot deployment.

### Workflow

#### Phase 1: Data Collection Assessment

**Use:** `prompts/data-collection.prompt.md`

```markdown
@rfi-assistant

I'm conducting a DPIA for GitHub Copilot. Using the data-collection prompt,
please provide comprehensive information about data processing activities.

[Paste data-collection.prompt.md content]
```

**Response covers:**
- What data is processed
- Legal basis for processing
- Categories of data subjects
- Retention periods
- Data recipients

#### Phase 2: Security Measures

**Use:** `prompts/encryption-security.prompt.md`

```markdown
@rfi-assistant

For our DPIA, we need details on security measures protecting personal data.

[Paste encryption-security.prompt.md content]
```

**Response covers:**
- Technical security measures
- Organizational security measures
- Encryption standards
- Access controls

#### Phase 3: Rights and Compliance

**Use:** `prompts/gdpr-compliance.prompt.md`

```markdown
@rfi-assistant

For DPIA completion, explain how data subject rights can be exercised.

[Paste gdpr-compliance.prompt.md content]
```

**Response covers:**
- Rights to access, rectification, erasure
- Data portability
- Right to object
- Processes for exercising rights

#### Phase 4: Risk Assessment

**Use:** `prompts/incident-response.prompt.md` + custom questions

```markdown
@rfi-assistant

What risks exist related to data processing, and what mitigations are in place?

Consider:
- Data breach risks
- Unauthorized access risks
- Data loss risks
- Mitigation measures
```

#### Document Structure
```
DPIA for GitHub Copilot
├── 1. Overview
├── 2. Data Processing Activities [from data-collection prompt]
├── 3. Legal Basis
├── 4. Security Measures [from encryption-security prompt]
├── 5. Data Subject Rights [from gdpr-compliance prompt]
├── 6. Risk Assessment [from incident-response + custom]
├── 7. Consultation
└── 8. Conclusions
```

---

## Example 3: Security Certification Verification

### Scenario
Procurement requires proof of SOC 2 Type II and ISO 27001 certifications.

### Quick Resolution

**Use:** `prompts/security-certifications.prompt.md`

```markdown
@rfi-assistant /security-certs

We need to verify the following for procurement approval:
1. Current SOC 2 Type II certification status
2. How to obtain SOC 2 report
3. ISO 27001 certification details
4. ISO 27018 compliance
5. Links to official certification documentation

[Can include the full prompt file for more comprehensive response]
```

**Response provides:**
- Certification status: ✅ SOC 2 Type II (annually renewed)
- How to request reports through GitHub Enterprise Support
- ISO 27001 certified
- ISO 27018 certified (privacy)
- Links to official documentation
- GitHub Trust Center reference

**Follow-up:**
```markdown
@rfi-assistant

How do we request a copy of the SOC 2 report for our procurement team?
```

**Total time:** 10 minutes (vs. hours of searching/waiting for vendor response)

---

## Example 4: Custom Questions

### Scenario
You have unique questions not covered by existing prompts.

### Approach

**Use:** `prompts/custom-rfi-template.prompt.md`

#### Step 1: Prepare Your Questions

Open the template and add your questions:

```markdown
# Custom RFI Response Template

@rfi-assistant

## Your Questions

**Q1: Does GitHub Copilot support air-gapped environments?**

**Q2: What is the process for security vulnerability disclosure?**

**Q3: Can we use GitHub Copilot with our on-premises GitHub Enterprise Server?**

**Q4: What telemetry can be disabled for privacy-sensitive environments?**

**Q5: Are there options for custom model fine-tuning with our code?**

## Context
We are a defense contractor with strict air-gap requirements and 
need to understand deployment options and privacy controls.

## Required Information
For each question, provide:
1. Direct answer
2. Technical details
3. Limitations or constraints
4. Links to documentation
```

#### Step 2: Use with Agent

```
1. Open GitHub Copilot Chat
2. Type: @rfi-assistant
3. Paste the customized template
4. Send
```

#### Step 3: Review and Follow-Up

Review the response and ask follow-ups:

```markdown
@rfi-assistant

For Q3 about GitHub Enterprise Server, can you provide more details 
on the specific versions supported and any limitations?
```

---

## Pro Tips

### Tip 1: Chain Multiple Prompts
For comprehensive questionnaires, use multiple prompts in sequence:

```markdown
@rfi-assistant

I need comprehensive information for a vendor assessment. 
I'll use multiple prompts. First, let's start with data collection.

[Paste data-collection.prompt.md]
```

Then:
```markdown
@rfi-assistant

Now for security certifications...

[Paste security-certifications.prompt.md]
```

### Tip 2: Save Conversation History
- Export chat history for documentation
- Share with team members
- Reference for future RFIs

### Tip 3: Customize Context Sections
Always add your organization's specific context:

```markdown
## Context
- Industry: Healthcare
- Location: EU (Germany)
- Compliance needs: GDPR, HIPAA
- Deployment: Enterprise plan with 500+ developers
- Sensitivity: Processing medical research code
```

### Tip 4: Request Specific Formats

```markdown
## Output Format
Please provide responses in a table format:

| Question | Answer | Citation | Risk Level |
|----------|--------|----------|------------|
| ...      | ...    | ...      | ...        |
```

### Tip 5: Iterate and Refine

First pass:
```markdown
@rfi-assistant /data-collection
```

Follow-up:
```markdown
@rfi-assistant

Can you provide more specific details about the data retention 
period for code snippets? Our legal team needs exact timeframes.
```

---

## Common Workflows

### Workflow 1: New Customer Onboarding
```
1. Customer sends security questionnaire
2. Categorize questions by topic
3. Use relevant prompt files
4. Compile responses in customer's format
5. Legal/compliance review
6. Submit
```

### Workflow 2: Annual Vendor Review
```
1. Review last year's assessment
2. Check for changes using agent
3. Update responses where needed
4. Use @rfi-assistant to verify current information
5. Document changes
```

### Workflow 3: Internal Audit Preparation
```
1. Use vendor-questionnaire.prompt.md
2. Generate comprehensive documentation
3. Review with internal stakeholders
4. Prepare supporting evidence
5. Ready for audit
```

### Workflow 4: Sales Enablement
```
1. Create standard response library using prompt files
2. Train sales team on using @rfi-assistant
3. Maintain updated responses
4. Quick turnaround on customer questions
```

---

## Measuring Success

### Metrics to Track
- **Time per RFI**: Before vs. After using assistant
- **Response Quality**: Completeness, accuracy, citations
- **Customer Satisfaction**: Faster responses, better information
- **Team Efficiency**: Hours saved per month

### Success Story Example
```
Before:
- Average RFI completion: 12 hours
- 3-5 business day turnaround
- Inconsistent responses
- Multiple stakeholder meetings needed

After:
- Average RFI completion: 3 hours
- Same-day turnaround possible
- Consistent, well-cited responses
- Self-service for common questions

Result: 75% time reduction, faster sales cycles
```

---

## Need Help?

- **Prompt not working as expected?** Check [prompts/README.md](prompts/README.md)
- **Want to create custom prompts?** See [CONTRIBUTING.md](CONTRIBUTING.md)
- **Need more examples?** See [examples/EXAMPLE_CONVERSATION.md](examples/EXAMPLE_CONVERSATION.md)
- **General guidance?** See [AGENT_GUIDE.md](AGENT_GUIDE.md)

---

**Ready to try it yourself?** Start with the simplest prompt and work your way up to more complex scenarios!
