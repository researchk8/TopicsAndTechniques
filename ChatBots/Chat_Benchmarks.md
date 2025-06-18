# ChatBots

## Benchmarks

### Chatbot Arena

Chatbot Arena follows a rather unique approach: it is an open-source platform for evaluating LLMs by directly comparing
their conversational abilities in a competitive environment. Chatbots powered by different LLM systems are paired
against each other in a virtual “arena” where users can interact with both models simultaneously. The chatbots take
turns responding to user prompts, and after the conversation, the user is asked to rate or vote for the model that gave
the best response. The models' identities are hidden and revealed after the user has voted.  
https://arxiv.org/abs/2403.04132

### MT-Bench

MT-bench is designed to test LLMs' ability to sustain multi-turn conversations. It consists of 80 multi-turn questions
from 8 categories: writing, roleplay, extraction, reasoning, math, coding, STEM, and social science. There are two
turns: the model is asked an open-ended question (1st turn), then a follow-up question is added (2nd turn). To automate
the evaluation process, MT-bench uses LLM-as-a-judge to score the model’s response for each question on a scale from 1
to 10.  
https://huggingface.co/datasets/lmsys/mt_bench_human_judgments  