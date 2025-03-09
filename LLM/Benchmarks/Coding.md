# Benchmarks

## Coding

### HumanEval
‍HumanEval evaluates the code-generating abilities of LLMs. It focuses on testing models' capacity to understand programming-related tasks and generate syntactically correct and functionally accurate code according to the provided specifications. Each problem in HumanEval comes with unit tests that verify the correctness of the code. These test cases run the generated code with various inputs and check whether the outputs match the expected results–just like human programmers test their code! A successful model must pass all test cases to be correct for that specific task.  
https://arxiv.org/abs/2107.03374

### Mostly Basic Programming Problems (MBPP)
‍Mostly Basic Programming Problems (MBPP) is designed to measure LLMs' ability to synthesize short Python programs from natural language descriptions. The dataset contains 974 tasks for entry-level programmers focusing on common programming concepts such as list manipulation, string operations, loops, conditionals, and basic algorithms. Each problem contains a task description, an example code solution, and test cases to verify the LLM's output.  
https://arxiv.org/abs/2108.07732

### SWE-bench
SWE-bench (Software Engineering Benchmark) evaluates how well LLMs can solve real-world software issues collected from GitHub. The dataset comprises over 2200 GitHub issues and corresponding pull requests across 12 popular Python repositories. Given a codebase and an issue, a model must generate a patch that resolves the issue. To complete the task, models must interact with execution environments, process long contexts, and perform complex reasoning–tasks beyond basic code generation problems.  
https://arxiv.org/abs/2310.06770

### DevQualityEval
The benchmark is periodically updated with new tasks, models, and their results. The leaderboard has detailed results and visualized data to help find the best model for your use case. Results are validated automatically using static and dynamic analyses , e.g. by dynamically generating tests and executing them. Models are graded in a point-based system based on quality metrics (e.g. providing compiling code, reaching sufficient coverage with the generated test code, etc).  
https://github.com/symflower/eval-dev-quality

### ClassEval
ClassEval is a manually constructed dataset that contains 100 Python classes with coding tasks (100 classes and 410 methods). It challenges models with code generation that spans the logic of a whole class, not just a single function. ClassEval also provides tests (to be precise, an average of 33.1 test cases per class).  
https://github.com/FudanSELab/ClassEval

### Aider
Aider is an open-source solution. The Aider core application basically lets you use models as a pair programmer in your terminal. The creator of Aider, Paul Gauthier, started conducting benchmarks to help users choose between the vast majority of models becoming available. The assessment focuses on how effectively LLMs can be used to translate a natural language coding request into code that executes and passes unit tests. The two types of benchmarks available are code editing and code refactoring.  
https://github.com/paul-gauthier/aider

### BigCodeBench
BigCodeBench is dubbed the next generation of HumanEval. It’s created for function-level code generation with practical and challenging coding tasks. When compared to HumanEval, it contains more complex instructions and a variety of function calls. It comes with 1140 function-level tasks and has LLMs do function calls to 139 libraries. Each task comes with 5.6 test cases on average, with an average branch coverage of 99%. BigCodeBench provides open-source LLM-generated samples.  
https://github.com/bigcode-project/bigcodebench

### DS-1000
DS-1000 is a result of a collaboration of researchers from a number of high-profile universities (including the University of Hong Kong, Stanford, and the University of California, Berkeley) and Meta AI. It’s a Python benchmark of data science use cases based on real StackOverflow questions (451 of them to be precise).  
https://ds1000-code-gen.github.io/

### MultiPL-E
The abbreviation stands for Multi-Programming Language Evaluation of Large Language Models of Code. It’s a system for translating unit test-driven neural code generation benchmarks to new languages. It supports 22 programming languages and also has models themselves translate tests. Based on OpenAI’s HumanEval and MBPP, MultiPL-E uses compilers to translate them to other languages. This benchmark is part of BigCodeBench and that’s the easiest way to use it, but you can also use it directly.  
https://github.com/nuprl/MultiPL-E

### APPS
APPS contains problems sourced from a variety of open-access coding websites (Codeforces, Kattis, etc). The goal of APPS is to mirror the evaluation of human programmers: coding problems are presented in natural language. The dataset contains 10,000 problems (with 131,836 corresponding test cases and 232,444 human-written ground-truth solutions). The problems in APPS range from beginner-level tasks to advanced competition-level problems. The average length of a problem in APPS is 293.2 words, so problems can get fairly complex. APPS aims to measure both coding ability and problem-solving.  
https://github.com/hendrycks/apps  

### CodeXGLUE
CodeXGLUE is a General Language Understanding Evaluation benchmark for CODE. It contains 14 datasets for 10 programming-related tasks. The benchmarks covers many scenarios.  
https://github.com/microsoft/CodeXGLUE