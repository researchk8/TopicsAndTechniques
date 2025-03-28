# AI Agents

Agents are autonomous programs that use language models to achieve tasks. They solve problems by running tools,
accessing knowledge and memory to improve responses.

Instead of a rigid binary definition, let’s think of Agents in terms of agency and autonomy.

- Level 0: Agents with no tools (basic inference tasks).
- Level 1: Agents with tools for autonomous task execution.
- Level 2: Agents with knowledge, combining memory and reasoning.
- Level 3: Teams of agents collaborating on complex workflows.

## Common use-cases

One of the most common use-cases for an LLM application is to answer questions about a set of documents. LlamaIndex has
rich support for many forms of question & answering.

- Semantic search: finding data that matches not just your query terms, but your intent and the meaning behind your
  question. This is sometimes known as “top k” search.
- Summarization: condensing a large amount of data into a short summary relevant to your current question

Where to search

- Over documents: LlamaIndex can pull in unstructured text, PDFs, Notion and Slack documents and more and index the data
  within them.
- Over structured data: if your data already exists in a SQL database, as JSON or as any number of other structured
  formats, LlamaIndex can query the data in these sources.

## Agents

An “agent” is an automated reasoning and decision engine. It takes in a user input/query and can make internal decisions
for executing that query in order to return the correct result. The key agent components can include, but are not
limited to:

- Breaking down a complex question into smaller ones
- Choosing an external Tool to use + coming up with parameters for calling the Tool
- Planning out a set of tasks
- Storing previously completed tasks in a memory module

Research developments in LLMs (e.g. ChatGPT Plugins), LLM research (ReAct, Toolformer) and LLM tooling (LangChain,
Semantic Kernel) have popularized the concept of agents.

Data Agents are LLM-powered knowledge workers in LlamaIndex that can intelligently perform various tasks over your data,
in both a “read” and “write” function. They are capable of the following:

- Perform automated search and retrieval over different types of data - unstructured, semi-structured, and structured.
- Calling any external service API in a structured fashion, and processing the response + storing it for later.

In that sense, agents are a step beyond our query engines in that they can not only “read” from a static source of data,
but can dynamically ingest and modify data from a variety of different tools.

Building a data agent requires the following core components:

- A reasoning loop
- Tool abstractions

A data agent is initialized with set of APIs, or Tools, to interact with; these APIs can be called by the agent to
return information or modify state. Given an input task, the data agent uses a reasoning loop to decide which tools to
use, in which sequence, and the parameters to call each tool.

## Components

### Tools

Agents use tools to take actions and interact with external systems. Tools are functions that an Agent can run to
achieve tasks. For example: searching the web, running SQL, sending an email or calling APIs.

### Knowledge

Agents use knowledge to supplement their training data with domain expertise. Knowledge is stored in a vector database
and provides agents with business context at query time, helping them respond in a context-aware manner.

#### Vector Databases

While any type of storage can act as a knowledge base, vector databases offer the best solution for retrieving relevant
results from dense information quickly.

Here’s how vector databases are used with Agents:

1. Chunk the information: Break down the knowledge into smaller chunks to ensure our search query returns only relevant
   results.

2. Load the knowledge base: Convert the chunks into embedding vectors and store them in a vector database.

3. Search the knowledge base: When the user sends a message, we convert the input message into an embedding and “search”
   for nearest neighbors in the vector database.

### Prompts

We prompt Agents using description and instructions and a number of other settings. These settings are used to build the
system prompt that is sent to the language model. Understanding how these prompts are created will help you build better
Agents.

The 2 key parameters are:

- Description: A description that guides the overall behaviour of the agent.
- Instructions: A list of precise, task-specific instructions on how to achieve its goal.

Description and instructions only provide a formatting benefit, we do not alter or abstract any information and you can
always use system_prompt to provide your own system prompt.

### Memory

Consists of short-term memory (allows the agent to recall its previous steps) and long-term memory (provides months-long
history of conversations and interactions necessary for the agent to gain contextual knowledge.

### Embeddings

An Embedder converts complex information into vector representations, allowing it to be stored in a vector database. By
transforming data into embeddings, the embedder enables efficient searching and retrieval of contextually relevant
information. This process enhances the responses of language models by providing them with the necessary business
context, ensuring they are context-aware.

See https://docs.agno.com/embedder/introduction

### Storage

Agents come with built-in memory but it only lasts while the session is active. To continue conversations across
sessions, we store Agent sessions in a database like PostgreSQL.

Storage is a necessary component when building user facing AI products as any production application will require users
to be able to “continue” their conversation with the Agent.

See https://docs.agno.com/storage/introduction

### Reasoning

Reasoning is an experimental feature that enables an Agent to think through a problem step-by-step before jumping into a
response. The Agent works through different ideas, validating and correcting as needed. Once it reaches a final answer,
it will validate and provide a response.

### Output parsers
Output Parsers are responsible for taking the output of an LLM and parsing into more structured format.

# Agentic Applications

When an LLM is used within an application, it is often used to make decisions, take actions, and/or interact with the
world. This is the core definition of an agentic application.

While the definition of an agentic application is broad, there are several key characteristics that define an agentic
application:

- LLM Augmentation: The LLM is augmented with tools (i.e. arbitrary callable functions in code), memory, and/or dynamic
  prompts.
- Prompt Chaining: Several LLM calls are used that build on each other, with the output of one LLM call being used as
  the input to the next.
- Routing: The LLM is used to route the application to the next appropriate step or state in the application.
- Parallelism: The application can perform multiple steps or actions in parallel.
- Orchestration: A hierarchical structure of LLMs is used to orchestrate lower-level actions and LLMs.
- Reflection: The LLM is used to reflect and validate outputs of previous steps or LLM calls, which can be used to guide
  the application to the next appropriate step or state.

## Persona

- https://github.com/microsoft/TinyTroupe (TinyTroupe is an experimental Python library that allows the simulation of
  people with specific personalities, interests, and goals.)

# Paper
- https://github.com/shizhl/Multi-Agent-Papers
- https://github.com/lafmdp/Awesome-Papers-Autonomous-Agent

# Resources

- https://docs.agno.com/agents
- https://github.com/e2b-dev/awesome-ai-agents
- https://www.youtube.com/watch?v=F8NKVhkZZWI
- https://ai.pydantic.dev/
- https://cobusgreyling.medium.com/ai-agent-computer-interface-aci-2ff4b66cd008
- https://github.com/arunpshankar/react-from-scratch
- https://medium.com/google-cloud/building-react-agents-from-scratch-a-hands-on-guide-using-gemini-ffe4621d90ae
- https://docs.llamaindex.ai/en/stable/getting_started/concepts/#agentic-applications

## Also interesting

- https://getstream.io/blog/python-assistant/
- https://getstream.io/blog/agentic-ai-rag/
- https://github.com/precize/OWASP-Agentic-AI
