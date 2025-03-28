## Agent types

See https://docs.cognify.cx/system-architecture/agents/main-agents

### Summarize Agent

    Purpose: Extract key information from lengthy documents.
    Inputs: Raw text.
    Outputs: Summarized content.

### Write Article Agent

    Purpose: Generate draft research articles.
    Inputs: Topic, optional outline.
    Outputs: Article draft.

### Sanitize Data Agent

    Purpose: Detect and remove PHI from datasets.
    Inputs: Raw dataset.
    Outputs: Sanitized dataset.

### Refinement Agents

    File: agents/refiner_agent.py
    Purpose: Improve article drafts for clarity, coherence, and academic quality.
    Key Method: RefinerAgent.execute(draft)

### Validator Agents
The Validator Agents play a crucial role in ensuring the accuracy and quality of content. 

See https://docs.cognify.cx/system-architecture/agents/validator-agents

#### Summarize Validator
Validates summary quality. The Summarize Validator checks the quality of summaries, ensuring they accurately and concisely convey the intended information.

#### Refiner Validator
Enhances research article drafts. The Refiner Validator focuses on improving research article drafts, enhancing their clarity and coherence. 

#### Sanitize Validator
Ensures complete PHI removal. The Sanitize Validator is dedicated to safeguarding sensitive data by meticulously removing all Personally Identifiable Information (PHI) from documents, ensuring compliance with data protection standards.

# Resources
- https://python.langchain.com/v0.1/docs/modules/agents/agent_types/
