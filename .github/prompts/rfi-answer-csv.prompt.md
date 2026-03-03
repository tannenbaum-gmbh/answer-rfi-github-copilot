## Task
Answer all questions of the Questionnaire/RFI input. In short precise manner with citations. Where requested in RFI adapt to answering pattern like free text, yes/no, multiple choice etc.

## Questionnaire/RFI Input
Will be given by the user in the prompt clarification message. It will be a CSV file with the following structure:
```
Use Case,Capability name,Capability description,Priority (must / should / could),Confirmed 14.01.2026,Confirmed 14.01.2027
```

## Response Format
Provide the answers with a copy of that CSV and append following columns:
```
Supported,Answer,Citations
```
Supported column should contain 'yes'/'no'/'yes with GHE' based on whether the capability described in the Capability description column is supported by GitHub Copilot or by GitHub Copilot on GitHub Enterprise.
Answer column should contain the answer to the question in the Capability description column. Citations column should contain links to official documentation that support the answer. 
Ensure clarity and professionalism throughout the document.

