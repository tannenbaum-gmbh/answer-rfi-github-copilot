# Contributing to GitHub Copilot Enterprise RFI Assistant

Thank you for your interest in contributing to this project! This guide will help you contribute effectively.

## How You Can Contribute

We welcome contributions in several areas:

### 1. Additional RFI Questions
If you've encountered RFI questions not covered in our templates:
- Add them to `examples/SAMPLE_RFI_TEMPLATE.md`
- Organize them in the appropriate section
- Ensure they're enterprise/security focused

### 2. Knowledge Sources
If you find valuable resources that should be included:
- Update `.github/copilot/agent.yml`
- Add to the `knowledge_sources` section
- Include a clear description of what the source provides
- Ensure the source is official and publicly accessible

### 3. Agent Instructions
To improve how the agent responds:
- Edit the `instructions` section in `.github/copilot/agent.yml`
- Focus on clarity and accuracy
- Maintain professional, enterprise-appropriate tone
- Test your changes before submitting

### 4. Example Conversations
Real-world examples help users understand the agent:
- Add to `examples/EXAMPLE_CONVERSATION.md`
- Show both questions and expected response patterns
- Include diverse topics (privacy, security, compliance, etc.)
- Demonstrate best practices for querying

### 5. Documentation Improvements
Help make the documentation clearer:
- Fix typos or unclear language
- Add missing information
- Improve organization and structure
- Update outdated information

## Contribution Process

### Step 1: Check Existing Issues
- Look for existing issues or discussions on your topic
- Comment on existing issues if you plan to work on them
- Avoid duplicating effort

### Step 2: Create an Issue
For larger changes:
- Open an issue describing your proposed contribution
- Explain the rationale and expected benefit
- Get feedback before starting major work

### Step 3: Make Your Changes
- Fork the repository
- Create a feature branch: `git checkout -b feature/your-feature-name`
- Make your changes following our guidelines (see below)
- Test your changes if applicable

### Step 4: Submit a Pull Request
- Push your changes to your fork
- Open a pull request against the main branch
- Provide a clear description of your changes
- Reference any related issues

## Guidelines

### Agent Configuration (`agent.yml`)

**Knowledge Sources:**
- Use official, authoritative sources only
- Include clear descriptions
- Ensure URLs are stable and publicly accessible
- Prioritize GitHub and Microsoft documentation

**Instructions:**
- Keep tone professional and enterprise-focused
- Be specific about what the agent should do
- Maintain focus on RFI/questionnaire context
- Emphasize accuracy and citation of sources

**Conversation Starters:**
- Phrase as real questions enterprise users would ask
- Cover diverse topics (security, privacy, compliance, etc.)
- Make them specific and actionable
- Aim for 6-10 quality starters

### RFI Templates

**Question Format:**
```markdown
**Q: [Clear, specific question]**
```

**Organization:**
- Group related questions in sections
- Use hierarchical numbering (1.1, 1.2, etc.)
- Include section headers for major topics
- Keep questions concise and focused

**Question Quality:**
- Use language common in enterprise RFIs
- Focus on security, privacy, compliance, and data handling
- Avoid overly technical jargon
- Make questions actionable

### Documentation

**Style:**
- Use clear, professional language
- Break information into digestible sections
- Include examples where helpful
- Use markdown formatting consistently

**Structure:**
- Start with overview/introduction
- Provide clear navigation
- Include "How to Use" sections
- End with additional resources

### Commit Messages

Use clear, descriptive commit messages:
- Start with a verb: "Add", "Update", "Fix", "Remove"
- Be specific: "Add HIPAA compliance questions to RFI template"
- Keep first line under 72 characters
- Add details in the body if needed

Examples:
```
Add data residency questions to RFI template

- Added questions about geographic data storage
- Included EU-specific compliance questions
- Organized under Section 2.2
```

## Testing Changes

### For Agent Configuration:
- Verify YAML syntax is valid
- Ensure all URLs are accessible
- Test with GitHub Copilot if you have access
- Check that knowledge sources load properly

### For Documentation:
- Check markdown rendering
- Verify all links work
- Ensure formatting is consistent
- Proofread for typos and clarity

### For Examples:
- Ensure questions are clear and relevant
- Verify examples match current best practices
- Check that response patterns are realistic
- Confirm citations are accurate

## What We're Looking For

### High Priority:
- Real RFI questions from actual enterprise assessments
- Official documentation sources we've missed
- Corrections to inaccurate information
- Improvements to agent response quality

### Medium Priority:
- Additional example conversations
- Documentation clarity improvements
- Better organization of existing content
- More comprehensive coverage of topics

### Lower Priority (but still welcome!):
- Typo fixes
- Formatting improvements
- Minor wording changes

## What to Avoid

- **Speculation**: Don't add information not backed by official sources
- **Promotional Content**: Keep content neutral and factual
- **Legal Advice**: Don't provide specific legal interpretations
- **Unofficial Sources**: Stick to GitHub/Microsoft documentation
- **Excessive Detail**: Keep content focused on RFI use case
- **Breaking Changes**: Avoid major restructuring without discussion

## Questions?

If you're unsure about anything:
- Open an issue with your question
- Tag it as "question"
- We're here to help!

## Code of Conduct

This project follows GitHub's community guidelines:
- Be respectful and inclusive
- Focus on constructive feedback
- Help create a welcoming environment
- Report inappropriate behavior

## Recognition

Contributors will be:
- Listed in pull request history
- Credited in significant changes
- Appreciated for improving this resource!

Thank you for contributing to help enterprises better understand and evaluate GitHub Copilot!
