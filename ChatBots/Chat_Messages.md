# Messages

Messages are the unit of communication in chat models. They are used to represent the input and output of a chat model,
as well as any additional context or metadata that may be associated with a conversation.

Each message has a role (e.g., "user", "assistant") and content (e.g., text, multimodal data) with additional metadata
that varies depending on the chat model provider.

LangChain provides a unified message format that can be used across chat models, allowing users to work with different
chat models without worrying about the specific details of the message format used by each model provider.

## What is inside a message?

A message typically consists of the following pieces of information:

    Role: The role of the message (e.g., "user", "assistant").
    Content: The content of the message (e.g., text, multimodal data).
    Additional metadata: id, name, token usage and other model-specific metadata.

### Role

Roles are used to distinguish between different types of messages in a conversation and help the chat model understand
how to respond to a given sequence of messages.
Role Description
system Used to tell the chat model how to behave and provide additional context. Not supported by all chat model
providers.
user Represents input from a user interacting with the model, usually in the form of text or other interactive input.
assistant Represents a response from the model, which can include text or a request to invoke tools.
tool A message used to pass the results of a tool invocation back to the model after external data or processing has
been retrieved. Used with chat models that support tool calling.
function (legacy)    This is a legacy role, corresponding to OpenAI's legacy function-calling API. tool role should be
used instead.

### Content

The content of a message text or a list of dictionaries representing multimodal data (e.g., images, audio, video). The
exact format of the content can vary between different chat model providers.

Currently, most chat models support text as the primary content type, with some models also supporting multimodal data.
However, support for multimodal data is still limited across most chat model providers.

For more information see:

    SystemMessage -- for content which should be passed to direct the conversation
    HumanMessage -- for content in the input from the user.
    AIMessage -- for content in the response from the model.
    Multimodality -- for more information on multimodal content.

### Other Message Data

Depending on the chat model provider, messages can include other data such as:

    ID: An optional unique identifier for the message.
    Name: An optional name property which allows differentiate between different entities/speakers with the same role. Not all models support this!
    Metadata: Additional information about the message, such as timestamps, token usage, etc.
    Tool Calls: A request made by the model to call one or more tools> See tool calling for more information.

## Conversation Structure

The sequence of messages into a chat model should follow a specific structure to ensure that the chat model can generate
a valid response.

For example, a typical conversation structure might look like this:

    User Message: "Hello, how are you?"
    Assistant Message: "I'm doing well, thank you for asking."
    User Message: "Can you tell me a joke?"
    Assistant Message: "Sure! Why did the scarecrow win an award? Because he was outstanding in his field!"

Please read the chat history guide for more information on managing chat history and ensuring that the conversation
structure is correct.

# Resources

- https://python.langchain.com/docs/concepts/messages/