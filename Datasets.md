# Datasets

Accuracy: Samples should be factually correct and relevant to their corresponding instructions. This can involve using solvers for math and unit tests for code.
Diversity: You want to cover as many use cases as possible to make sure you're never out of distribution. High diversity is essential as it leads to better generalization.
Complexity: Answers should be both detailed (to maximize helpfulness) and include system 2 techniques like chain of thought (to force step-by-step reasoning).


## Types 

### General-purpose mixtures
General-purpose datasets offer balanced mixtures of different types of data, including chat, code, and math. These datasets can be used to create general-purpose models that can handle various types of queries.

### Math
LLMs often struggle with mathematical reasoning and formal logic, which has led to the creation of specialized datasets. These datasets can include systematic thinking and step-by-step reasoning.

### Code
Code is another challenging domain for LLMs. Code datasets, containing diverse programming language examples, are used to fine-tune LLMs and enhance their ability to understand, generate, and analyze code.

### Instruction following
Instruction following corresponds to the ability to properly follow constraints in the user prompt, such as "write only two paragraphs", "write your answer in French", etc. Strong instruction-following capabilities is a must-have for modern LLMs.


### Multilingual
Learning new languages "from scratch" is a pre-training task, but providing multilingual instruction samples is useful to boost performance in the languages of interest.


### Agent & Function calling
Function calling allows large language models (LLMs) to execute predefined functions with parameters inferred from user prompts, rather than generating standard text responses. This enables LLMs to seamlessly integrate with external systems, perform complex operations, and provide more accurate and contextually relevant responses.

### Real conversations
Real-world conversations provide valuable insights into how people naturally interact with LLMs, helping us identify the most important use cases and understand typical usage patterns.


Preference alignment
Unlike instruction data, preference datasets consist of chosen and rejected answers. Preference alignment is used to align LLM's answers with human preferences to adopt the desired style and values.

# Resources
- https://github.com/mlabonne/llm-datasets