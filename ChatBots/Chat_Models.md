# Chat Models

Chat models are language models that use a sequence of messages as inputs and return messages as outputs (as opposed to
using plain text). These are generally newer models.

Large Language Models (LLMs) are advanced machine learning models that excel in a wide range of language-related tasks
such as text generation, translation, summarization, question answering, and more, without needing task-specific fine
tuning for every scenario.

Modern LLMs are typically accessed through a chat model interface that takes a list of messages as input and returns a
message as output. Messages are typically associated with a role (e.g., "system", "human", "assistant") and one or more
content blocks that contain text or potentially multimodal data (e.g., images, audio, video).

The newest generation of chat models offer additional capabilities:

- Tool calling: Many popular chat models offer a native tool calling API. This API allows developers to build rich
  applications that enable LLMs to interact with external services, APIs, and databases. Tool calling can also be used
  to extract structured information from unstructured data and perform various other tasks.
- Structured output: A technique to make a chat model respond in a structured format, such as JSON that matches a given
  schema.
- Multimodality: The ability to work with data other than text; for example, images, audio, and video.

## Tool calling

Chat models can call tools to perform tasks such as fetching data from a database, making API requests, or running
custom code. Please see the tool calling guide for more information.

## Structured outputs

Chat models can be requested to respond in a particular format (e.g., JSON or matching a particular schema). This
feature is extremely useful for information extraction tasks. Please read more about the technique in the structured
outputs guide.

## Multimodality

Large Language Models (LLMs) are not limited to processing text. They can also be used to process other types of data,
such as images, audio, and video. This is known as multimodality.

Currently, only some LLMs support multimodal inputs, and almost none support multimodal outputs. Please consult the
specific model documentation for details.

## Context window

A chat model's context window refers to the maximum size of the input sequence the model can process at one time. While
the context windows of modern LLMs are quite large, they still present a limitation that developers must keep in mind
when working with chat models.

If the input exceeds the context window, the model may not be able to process the entire input and could raise an error.
In conversational applications, this is especially important because the context window determines how much information
the model can "remember" throughout a conversation. Developers often need to manage the input within the context window
to maintain a coherent dialogue without exceeding the limit. For more details on handling memory in conversations, refer
to the memory.

The size of the input is measured in tokens which are the unit of processing that the model uses.

## Rate-limiting

Many chat model providers impose a limit on the number of requests that can be made in a given time period.

If you hit a rate limit, you will typically receive a rate limit error response from the provider, and will need to wait
before making more requests.

You have a few options to deal with rate limits:

- Try to avoid hitting rate limits by spacing out requests: Chat models accept a rate_limiter parameter that can be
  provided during initialization. This parameter is used to control the rate at which requests are made to the model
  provider. Spacing out the requests to a given model is a particularly useful strategy when benchmarking models to
  evaluate their performance. Please see the how to handle rate limits for more information on how to use this feature.
- Try to recover from rate limit errors: If you receive a rate limit error, you can wait a certain amount of time before
  retrying the request. The amount of time to wait can be increased with each subsequent rate limit error. Chat models
  have a max_retries parameter that can be used to control the number of retries. See the standard parameters section
  for more information.
- Fallback to another chat model: If you hit a rate limit with one chat model, you can switch to another chat model that
  is not rate-limited.

##Caching

Chat model APIs can be slow, so a natural question is whether to cache the results of previous conversations.
Theoretically, caching can help improve performance by reducing the number of requests made to the model provider. In
practice, caching chat model responses is a complex problem and should be approached with caution.

The reason is that getting a cache hit is unlikely after the first or second interaction in a conversation if relying on
caching the exact inputs into the model. For example, how likely do you think that multiple conversations start with the
exact same message? What about the exact same three messages?

An alternative approach is to use semantic caching, where you cache responses based on the meaning of the input rather
than the exact input itself. This can be effective in some situations, but not in others.

A semantic cache introduces a dependency on another model on the critical path of your application (e.g., the semantic
cache may rely on an embedding model to convert text to a vector representation), and it's not guaranteed to capture the
meaning of the input accurately.

However, there might be situations where caching chat model responses is beneficial. For example, if you have a chat
model that is used to answer frequently asked questions, caching responses can help reduce the load on the model
provider, costs, and improve response times.

# Resources

- https://python.langchain.com/docs/integrations/chat/
- https://python.langchain.com/docs/concepts/chat_models/