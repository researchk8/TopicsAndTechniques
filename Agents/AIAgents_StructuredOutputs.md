# Structured outputs

For many applications, such as chatbots, models need to respond to users directly in natural language. However, there
are scenarios where we need models to output in a structured format. For example, we might want to store the model
output in a database and ensure that the output conforms to the database schema. This need motivates the concept of
structured output, where models can be instructed to respond with a particular output structure.

## Key concepts

(1) Schema definition: The output structure is represented as a schema, which can be defined in several ways. (2)
Returning structured output: The model is given this schema, and is instructed to return output that conforms to it.
Recommended usage

This pseudocode illustrates the recommended workflow when using structured output. LangChain provides a method,
with_structured_output(), that automates the process of binding the schema to the model and parsing the output. This
helper function is available for all model providers that support structured output.

# Define schema

schema = {"foo": "bar"}

# Bind schema to model

model_with_structure = model.with_structured_output(schema)

# Invoke the model to produce structured output that matches the schema

structured_output = model_with_structure.invoke(user_input)

## Schema definition

The central concept is that the output structure of model responses needs to be represented in some way. While types of
objects you can use depend on the model you're working with, there are common types of objects that are typically
allowed or recommended for structured output in Python.

The simplest and most common format for structured output is a JSON-like structure, which in Python can be represented
as a dictionary (dict) or list (list). JSON objects (or dicts in Python) are often used directly when the tool requires
raw, flexible, and minimal-overhead structured data.

{
"answer": "The answer to the user's question",
"followup_question": "A followup question the user could ask"
}

As a second example, Pydantic is particularly useful for defining structured output schemas because it offers type hints
and validation. Here's an example of a Pydantic schema:

## Returning structured output

With a schema defined, we need a way to instruct the model to use it. While one approach is to include this schema in
the prompt and ask nicely for the model to use it, this is not recommended. Several more powerful methods that utilizes
native features in the model provider's API are available.

### Using tool calling

Many model providers support tool calling, a concept discussed in more detail in our tool calling guide. In short, tool
calling involves binding a tool to a model and, when appropriate, the model can decide to call this tool and ensure its
response conforms to the tool's schema. With this in mind, the central concept is straightforward: simply bind our
schema to a model as a tool!

### JSON mode

In addition to tool calling, some model providers support a feature called JSON mode. This supports JSON schema
definition as input and enforces the model to produce a conforming JSON output.

## Structured output method

There are a few challenges when producing structured output with the above methods:

(1) When tool calling is used, tool call arguments needs to be parsed from a dictionary back to the original schema.

(2) In addition, the model needs to be instructed to always use the tool when we want to enforce structured output,
which is a provider specific setting.

(3) When JSON mode is used, the output needs to be parsed into a JSON object.

With these challenges in mind, LangChain provides a helper function (with_structured_output()) to streamline the
process.

# Resources
- https://python.langchain.com/docs/concepts/structured_outputs/