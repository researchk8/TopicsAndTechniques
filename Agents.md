# Agents

## Components

### Agents
.

### Models
.

### Tools
Agents use tools to take actions and interact with external systems.
Tools are functions that an Agent can run to achieve tasks. 
For example: searching the web, running SQL, sending an email or calling APIs. You can use any python function as a tool or use a pre-built toolkit.

### Prompts
We prompt Agents using description and instructions and a number of other settings. These settings are used to build the system prompt that is sent to the language model. Understanding how these prompts are created will help you build better Agents.

The 2 key parameters are:
- Description: A description that guides the overall behaviour of the agent. 
- Instructions: A list of precise, task-specific instructions on how to achieve its goal.

Description and instructions only provide a formatting benefit, we do not alter or abstract any information and you can always use system_prompt to provide your own system prompt.

### Knowledge
The fine-tuned LLM provides the necessary information or is extracted from a database.

### Memory
Consists of short-term memory (allows the agent to recall its previous steps) and long-term memory (provides months-long history of conversations and interactions necessary for the agent to gain contextual knowledge.

### Embeddings

### Storage

### Reasoning
Reasoning is an experimental feature that enables an Agent to think through a problem step-by-step before jumping into a response. The Agent works through different ideas, validating and correcting as needed. Once it reaches a final answer, it will validate and provide a response.



## Also interesting
- https://getstream.io/blog/python-assistant/
- https://getstream.io/blog/agentic-ai-rag/