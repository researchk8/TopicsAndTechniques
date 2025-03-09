# Benchmarks

## Reasoning and language understanding

### AI2 Reasoning Challenge (ARC)
The AI2 Reasoning Challenge (ARC) benchmark evaluates the ability of AI models to answer complex science questions that require logical reasoning beyond pattern matching. It was created by the Allen Institute for AI (AI2) and consists of over 7700 grade-school level, multiple-choice science questions. The dataset is split into an Easy Set and a Challenge Set. Easy questions can be answered using simple retrieval techniques, and the Challenge Set contains only the questions answered incorrectly by retrieval-based and word co-occurrence algorithms.   
https://arxiv.org/abs/1803.05457


### HellaSwag
HellaSwag is a benchmark designed to test commonsense natural language inference. It requires the model to predict the most likely ending of a sentence. Similar to ARC, HellaSwag is structured as a multiple-choice task. The answers include adversarial options—machine-generated wrong answers that seem plausible and require deep reasoning to rule out.   
https://arxiv.org/abs/1905.07830

### Massive Multitask Language Understanding (MMLU)
Massive Multitask Language Understanding (MMLU) evaluates LLMs’ general knowledge and problem-solving abilities across 57 subjects, including elementary mathematics, US history, computer science, and law. The dataset contains over 15 thousand multi-choice tasks from high school to expert level. A model’s score for each subject is calculated as the percentage of correct answers, and the final MMLU score is the average of 57 subject scores.  
https://arxiv.org/abs/2009.03300

### SuperGLUE
SuperGLUE stands for Super General Language Understanding Evaluation. It was introduced as an improved and more challenging version of the original GLUE benchmark that was outperformed by LLMs. SuperGLUE aims to measure how well LLMs handle a variety of real-world language tasks, such as understanding context, making inferences, and answering questions. Each task has its own evaluation metric. The final score aggregates these metrics into the overall language understanding score.  
https://arxiv.org/abs/1905.00537

### BigBench
The Beyond the Imitation Game Benchmark (BIG-bench) is a collaborative benchmark that tests language models' reasoning and extrapolating capabilities. The benchmark consists of over 200 tasks contributed by 450 authors from 132 institutions. Task topics vary from linguistics and math to biology and physics and beyond. The tasks are designed to test LLMs beyond pattern matching and explore whether the models can approach human-level reasoning and understanding.  
https://arxiv.org/abs/2206.04615


### TruthfulQA
The TruthfulQA benchmark evaluates how well LLMs generate truthful responses to questions. It identifies whether AI models can avoid generating false or misleading information, particularly in areas where human knowledge is prone to misconceptions. The dataset consists of over 800 questions in 38 categories, such as health, law, finance, and politics. The questions include topics where people often hold false beliefs like urban legends, conspiracy theories, pseudoscience, and myths: "Do vaccines cause autism?" or "Is the Great Wall of China visible from space?" To perform well, models must avoid generating false answers mimicking popular misconceptions.  
https://arxiv.org/abs/2109.07958v2


### WinoGrande
WinoGrande benchmark is based on the Winograd Schema Challenge, a natural language understanding task requiring models to resolve ambiguities in sentences involving pronoun references. WinoGrande offers a significantly larger–44000 tasks–and more complex dataset to improve the scale and robustness against the dataset-specific bias. Questions are formulated as fill-in-a-blank tasks with binary options. To complete the challenge, models must choose the correct option.  
https://arxiv.org/abs/1907.10641


### SQuAD
The Stanford Question Answering Dataset (SQuAD) tests reading comprehension. The benchmark contains 107,785 question-answer pairs on 536 Wikipedia articles written by humans through crowdsourcing SQuAD 2.0 also contains 50,000 un-answerable questions to test whether models can determine when the source material supports no answer and opt not to answer.  
https://rajpurkar.github.io/SQuAD-explorer/

### IFEval
IFEval evaluates the ability of models to follow instructions provided in natural language. It contains 500+ prompts with verifiable instructions like “write in more than 400 words” or “mention the keyword of AI at least 3 times”. IFEval is part of the Open LLM Leaderboard by Hugging Face.  
https://github.com/google-research/google-research/tree/master/instruction_following_eval

### MuSR
MuSR stands for Multi-step Soft Reasoning. The dataset is designed to evaluate models on commonsense chain-of-thought reasoning tasks given in natural language. MuSR has two main characteristics that differentiate it from other benchmarks: Algorithmically generated dataset with complex problems and The dataset contains free-text narratives that correspond to real-world reasoning domains. MuSR requires models to apply multi-step reasoning to solve murder mysteries, object placement questions, and team allocation optimizations. Models have to parse long texts to understand context, and then apply reasoning based on that context. MuSR is part of the Open LLM Leaderboard by Hugging Face.  
https://github.com/Zayne-sprague/MuSR

### MMLU-PRO
The abbreviation stands for Massive Multitask Language Understanding - Professional. It’s an improved version of the standard MMLU dataset. In this benchmark, models have to answer multiple-choice questions with 10 choices (instead of the 4 in basic MMLU) with reasoning required for some questions. The dataset is of higher quality than MMLU, which was considered to have noisy data and data contamination (meaning lots of newer models are likely trained on the questions contained therein), reducing its difficulty for models and therefore, its usefulness. MMLU-PRO rectifies that and is considered more challenging than MMLU. MMLU-PRO is part of the Open LLM Leaderboard by Hugging Face.  
https://github.com/TIGER-AI-Lab/MMLU-Pro

### MT-Bench
MT-Bench is a multi-turn benchmark (with follow-up questions) that evaluates models' ability to participate in coherent, informative, and engaging conversations. This benchmark focuses on conversation flow and instruction-following capabilities. MT-Bench contains 80 questions and 3,300 responses (generated by 6 models) that represent human preferences. The benchmark uses an LLM-as-a-judge approach: strong LLMs like GPT-4 are asked to assess the quality of model responses. Responses were annotated by graduate students with expertise in the corresponding domains.  
https://huggingface.co/datasets/lmsys/mt_bench_human_judgments