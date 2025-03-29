# RAGMetrics

See https://docs.ragas.io/en/stable/concepts/metrics/available_metrics

## Context

### Context Precision / Contextual Precision
\#retriever

### Context Recall / Contextual Recall
\#retriever

### Context Entities Recall

### Contextual Relevancy
\#retriever
https://docs.confident-ai.com/docs/metrics-contextual-relevancy

## Noise Sensitivity
## Response Relevancy / Answer Relevancy
The answer relevancy metric uses LLM-as-a-judge to measure the quality of your RAG pipeline's generator by evaluating
how relevant the actual_output of your LLM application is compared to the provided input. deepeval's answer relevancy
metric is a self-explaining LLM-Eval, meaning it outputs a reason for its metric score.
The Answer Relevance metric allows you to evaluate how relevant and appropriate the LLM’s response is to the given input
question or prompt. To assess the relevance of the answer, you will need to provide the LLM input (question or prompt)
and the LLM output (generated answer). Unlike the Hallucination metric, the Answer Relevance metric focuses on the
appropriateness and pertinence of the response rather than factual accuracy.
\#generator

### Samples
- https://docs.llamaindex.ai/en/stable/examples/evaluation/relevancy_eval/

## Faithfulness
\#generator

### Samples
- https://docs.llamaindex.ai/en/stable/examples/evaluation/faithfulness_eval/


## Batch Eval Runner

## Correctness Eval

## Guideline Eval
https://docs.llamaindex.ai/en/stable/examples/evaluation/guideline_eval/

### Samples
- https://docs.llamaindex.ai/en/stable/examples/evaluation/guideline_eval/

## Pairwise Eval
https://docs.llamaindex.ai/en/stable/examples/evaluation/pairwise_eval/

## Relevancy Eval
https://docs.llamaindex.ai/en/stable/examples/evaluation/relevancy_eval/

## Semantic Similarity Eval


## Tonic Validate
https://docs.llamaindex.ai/en/stable/examples/evaluation/TonicValidateEvaluators/


# Resources
- https://docs.llamaindex.ai/en/stable/examples/evaluation/