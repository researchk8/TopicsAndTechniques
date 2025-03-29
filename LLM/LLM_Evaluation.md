# LLM Evaluation

## Ground Truth Comparison Evals

## Response Quality Evals

### Response Completeness

### Response Conciseness

### Response Relevance
more for RAG

See

- https://docs.confident-ai.com/docs/metrics-answer-relevancy
- https://www.comet.com/docs/opik/evaluation/metrics/answer_relevance

### Response Validity

Checks if the response generated is valid or not. A response is considered to be valid if it contains any information.

In some cases, an LLM might fail to generate a response due to reasons like limited knowledge or the asked question not
being clear.

Response Validity score can be used to identify these cases, where a model is not generating an informative response.

### Response Consistency

## Context Awareness Evals

### Contextual relevance

## Security Evals

## Language Quality Evals

## Query Clarity Evals

## Code Related Evals

## Conversation Evals

## Creating Custom Evals

## Conversations Evals / Conversational Evals

### Conversational G-Eval
### Knowledge Retention
### Role Adherence
### Conversation Completeness
### Conversation Relevancy

## not sorted

- Exactly Match (EM)
- Multitask Accuracy
- Generalization
- Correctness
- Fluency
- Accuracy
- Coherence
- Knowledge grounding
- Understand and execute complex instructions
- Success rate in answering questions

## Others

### Json Correctness
### Ragas

### Hallucination
The hallucination metric uses LLM-as-a-judge to determine whether your LLM generates factually correct information by comparing the actual_output to the provided context.

See:
- https://docs.confident-ai.com/docs/metrics-hallucination

### Toxicity

### Bias
The bias metric uses LLM-as-a-judge to determine whether your LLM output contains gender, racial, or political bias. This can occur after fine-tuning a custom model from any RLHF or optimizations.

See: 
- https://docs.confident-ai.com/docs/metrics-bias

### Summarization

### structured reasoning metrics

- ROSCOE

### reasoning graph accuracy and similarity

- STREET

## DAG
The DAG metric is a decision-tree based LLM-evaluated metric, and is currently the most versitile metric deepeval has to offer.

## G-Eval

## Datasets

- Natural Questions (NQ)
- HotpotQA (HPQA)
- TriviaQA
- HaluEvalQA
- TruthfulQA
- FreshQA
- FinanceBench
- LLM-AggreFact (https://huggingface.co/datasets/lytang/LLM-AggreFact)

# Resources
- https://docs.confident-ai.com/docs/metrics-introduction
- https://www.ibm.com/docs/en/watsonx/saas?topic=models-evaluation-metrics