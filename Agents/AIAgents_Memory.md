# Memory

Memory is a cognitive function that allows people to store, retrieve, and use information to understand their present
and future. Consider the frustration of working with a colleague who forgets everything you tell them, requiring
constant repetition! As AI agents undertake more complex tasks involving numerous user interactions, equipping them with
memory becomes equally crucial for efficiency and user satisfaction. With memory, agents can learn from feedback and
adapt to users' preferences. This guide covers two types of memory based on recall scope:

Short-term memory, or thread-scoped memory, can be recalled at any time from within a single conversational thread with
a user. LangGraph manages short-term memory as a part of your agent's state. State is persisted to a database using a
checkpointer so the thread can be resumed at any time. Short-term memory updates when the graph is invoked or a step is
completed, and the State is read at the start of each step.

Long-term memory is shared across conversational threads. It can be recalled at any time and in any thread. Memories are
scoped to any custom namespace, not just within a single thread ID. LangGraph provides stores (reference doc) to let you
save and recall long-term memories.

Both are important to understand and implement for your application.

## Short-term memory
Short-term memory lets your application remember previous interactions within a single thread or conversation. A thread
organizes multiple interactions in a session, similar to the way email groups messages in a single conversation.

LangGraph manages short-term memory as part of the agent's state, persisted via thread-scoped checkpoints. This state
can normally include the conversation history along with other stateful data, such as uploaded files, retrieved
documents, or generated artifacts. By storing these in the graph's state, the bot can access the full context for a
given conversation while maintaining separation between different threads.

Since conversation history is the most common form of representing short-term memory, in the next section, we will cover
techniques for managing conversation history when the list of messages becomes long. If you want to stick to the
high-level concepts, continue on to the long-term memory section.
Managing long conversation history.

Long conversations pose a challenge to today's LLMs. The full history may not even fit inside an LLM's context window,
resulting in an irrecoverable error. Even if your LLM technically supports the full context length, most LLMs still
perform poorly over long contexts. They get "distracted" by stale or off-topic content, all while suffering from slower
response times and higher costs.

Managing short-term memory is an exercise of balancing precision & recall with your application's other performance
requirements (latency & cost). As always, it's important to think critically about how you represent information for
your LLM and to look at your data. We cover a few common techniques for managing message lists below and hope to provide
sufficient context for you to pick the best tradeoffs for your application:

- Editing message lists: How to think about trimming and filtering a list of messages before passing to language model.
- Summarizing past conversations: A common technique to use when you don't just want to filter the list of messages.

### Editing message lists

Chat models accept context using messages, which include developer provided instructions (a system message) and user
inputs (human messages). In chat applications, messages alternate between human inputs and model responses, resulting in
a list of messages that grows longer over time. Because context windows are limited and token-rich message lists can be
costly, many applications can benefit from using techniques to manually remove or forget stale information.

The most direct approach is to remove old messages from a list (similar to a least-recently used cache).

The typical technique for deleting content from a list in LangGraph is to return an update from a node telling the
system to delete some portion of the list. You get to define what this update looks like, but a common approach would be
to let you return an object or dictionary specifying which values to retain.

### Summarizing past conversations

The problem with trimming or removing messages, as shown above, is that we may lose information from culling of the
message queue. Because of this, some applications benefit from a more sophisticated approach of summarizing the message
history using a chat model.

## Long-term memory

Long-term memory in LangGraph allows systems to retain information across different conversations or sessions. Unlike
short-term memory, which is thread-scoped, long-term memory is saved within custom "namespaces."
Storing memories

LangGraph stores long-term memories as JSON documents in a store (reference doc). Each memory is organized under a
custom namespace (similar to a folder) and a distinct key (like a filename). Namespaces often include user or org IDs or
other labels that makes it easier to organize information. This structure enables hierarchical organization of memories.
Cross-namespace searching is then supported through content filters. See the example below for an example.

## Memory types

Different applications require various types of memory. Although the analogy isn't perfect, examining human memory types
can be insightful. Some research (e.g., the CoALA paper) have even mapped these human memory types to those used in AI
agents.

### Semantic Memory

Semantic memory, both in humans and AI agents, involves the retention of specific facts and concepts. In humans, it can
include information learned in school and the understanding of concepts and their relationships. For AI agents, semantic
memory is often used to personalize applications by remembering facts or concepts from past interactions.

### Episodic Memory

Episodic memory, in both humans and AI agents, involves recalling past events or actions. The CoALA paper frames this
well: facts can be written to semantic memory, whereas experiences can be written to episodic memory. For AI agents,
episodic memory is often used to help an agent remember how to accomplish a task.

### Procedural Memory

Procedural memory, in both humans and AI agents, involves remembering the rules used to perform tasks. In humans,
procedural memory is like the internalized knowledge of how to perform tasks, such as riding a bike via basic motor
skills and balance. Episodic memory, on the other hand, involves recalling specific experiences, such as the first time
you successfully rode a bike without training wheels or a memorable bike ride through a scenic route. For AI agents,
procedural memory is a combination of model weights, agent code, and agent's prompt that collectively determine the
agent's functionality.

# Resources

- https://langchain-ai.github.io/langgraph/concepts/memory/#what-is-memory