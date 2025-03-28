## Large Action Models

In Large Action Models (LAMs), neuro-symbolic programming empowers neural models like LLMs with reasoning and planning
abilities from symbolic AI methods.

The core concept of AI agents is used to execute the generated plans and possibly adapt to new challenges. Open-source
LAMs often integrate logic programming with vision and language models, connecting the software to tools and APIs of
useful apps and services to perform tasks.

Several key characteristics set LAMs apart from other AI models:

- Action-oriented: The primary function of LAMs is to perform actions, not just generate text or provide information.
  This action-oriented design allows them to interact with and manipulate their environment in ways that traditional
  language models cannot.
- Contextual understanding: LAMs are equipped with the ability to comprehend the context of a situation. This deep
  understanding enables them to take appropriate actions that are relevant and meaningful within the given
  circumstances.
- Goal-driven: LAMs often operate with specific objectives or goals in mind. Whether it's completing a task, solving a
  problem, or optimizing a process, these models are designed to work towards defined outcomes.

## Components

- Pattern-Recognition: Neural networks
- Symbolic AI: Logical Reasoning
- Action Model: Execute Tasks (Agents)

## Models

### Cogagent

CogAgent is an open-source Action Model, based on CogVLM, an open-source vision language model. It is a visual agent
capable of generating plans, determining the next action, and providing precise coordinates for specific operations
within any given GUI screenshot.

Cogagent Hong, W., Wang, W., Lv, Q., Xu, J., Yu, W., Ji, J., ... & Ding, M. (2023). Cogagent: A visual language model
for gui agents. arXiv preprint arXiv:2312.08914.

### WebVoyager

WebVoyager He, H., Yao, W., Ma, K., Yu, W., Dai, Y., Zhang, H., ... & Yu, D. (2024). WebVoyager: Building an End-to-End
Web Agent with Large Multimodal Models. arXiv preprint arXiv:2401.13919.

### Agent-E

Agent-E - Abuelsaad, T., Akkil, D., Dey, P., Jagmohan, A., Vempaty, A., & Kokku, R. (2024). Agent-E: From Autonomous Web
Navigation to Foundational Design Principles in Agentic Systems. arXiv preprint arXiv:2407.13032.

### Gorilla

Gorilla is an impressive open-source large action model empowering LLMs to utilize thousands of tools through precise
API calls. It accurately identifies and executes the appropriate API call, by understanding the needed action from
natural language queries.

## Benchmarks

- Berkeley Function-Calling Leaderboard (BFCL)
- BOLAA
- HotpotQA
- AgentLite
- ToolBench
- MINT-BENCH
- Tool-Query

## Resources

- https://www.trinetix.com/en-de/insights/what-are-large-action-models-and-how-do-they-work
- https://www.iese.fraunhofer.de/blog/large-action-models-multi-agents/
- https://www.rabbit.tech/research/a-peek-into-rabbit-s-progress-with-LAM-playground
- https://viso.ai/deep-learning/large-action-models-beyond-language-into-action/