# AI Agents
Agents are autonomous programs that use language models to achieve tasks. They solve problems by running tools, accessing knowledge and memory to improve responses.

Instead of a rigid binary definition, let’s think of Agents in terms of agency and autonomy.

- Level 0: Agents with no tools (basic inference tasks).
- Level 1: Agents with tools for autonomous task execution.
- Level 2: Agents with knowledge, combining memory and reasoning.
- Level 3: Teams of agents collaborating on complex workflows.


## Components

### Tools
Agents use tools to take actions and interact with external systems. Tools are functions that an Agent can run to achieve tasks. For example: searching the web, running SQL, sending an email or calling APIs.

### Knowledge
Agents use knowledge to supplement their training data with domain expertise. Knowledge is stored in a vector database and provides agents with business context at query time, helping them respond in a context-aware manner. 

#### Vector Databases
While any type of storage can act as a knowledge base, vector databases offer the best solution for retrieving relevant results from dense information quickly. 

Here’s how vector databases are used with Agents:

1. Chunk the information: Break down the knowledge into smaller chunks to ensure our search query returns only relevant results.

2.  Load the knowledge base: Convert the chunks into embedding vectors and store them in a vector database.

3.  Search the knowledge base: When the user sends a message, we convert the input message into an embedding and “search” for nearest neighbors in the vector database.


### Prompts
We prompt Agents using description and instructions and a number of other settings. These settings are used to build the system prompt that is sent to the language model. Understanding how these prompts are created will help you build better Agents.

The 2 key parameters are:
- Description: A description that guides the overall behaviour of the agent. 
- Instructions: A list of precise, task-specific instructions on how to achieve its goal.

Description and instructions only provide a formatting benefit, we do not alter or abstract any information and you can always use system_prompt to provide your own system prompt.


### Memory
Consists of short-term memory (allows the agent to recall its previous steps) and long-term memory (provides months-long history of conversations and interactions necessary for the agent to gain contextual knowledge.

### Embeddings
An Embedder converts complex information into vector representations, allowing it to be stored in a vector database. By transforming data into embeddings, the embedder enables efficient searching and retrieval of contextually relevant information. This process enhances the responses of language models by providing them with the necessary business context, ensuring they are context-aware. 

See https://docs.agno.com/embedder/introduction

### Storage
Agents come with built-in memory but it only lasts while the session is active. To continue conversations across sessions, we store Agent sessions in a database like PostgreSQL.

Storage is a necessary component when building user facing AI products as any production application will require users to be able to “continue” their conversation with the Agent.

See https://docs.agno.com/storage/introduction

### Reasoning
Reasoning is an experimental feature that enables an Agent to think through a problem step-by-step before jumping into a response. The Agent works through different ideas, validating and correcting as needed. Once it reaches a final answer, it will validate and provide a response.


## Persona
- https://github.com/microsoft/TinyTroupe (TinyTroupe is an experimental Python library that allows the simulation of people with specific personalities, interests, and goals.)

# Resources
- https://docs.agno.com/agents
- https://github.com/e2b-dev/awesome-ai-agents
- https://www.youtube.com/watch?v=F8NKVhkZZWI
- https://ai.pydantic.dev/
- https://cobusgreyling.medium.com/ai-agent-computer-interface-aci-2ff4b66cd008
- https://github.com/arunpshankar/react-from-scratch
- https://medium.com/google-cloud/building-react-agents-from-scratch-a-hands-on-guide-using-gemini-ffe4621d90ae


## Also interesting
- https://getstream.io/blog/python-assistant/
- https://getstream.io/blog/agentic-ai-rag/
- https://github.com/precize/OWASP-Agentic-AI
