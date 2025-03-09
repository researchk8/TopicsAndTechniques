# Benchmarks

## Safety

### AgentHarm
The AgentHarm benchmark was introduced to facilitate research on LLM agent misuse. It includes a set of 110 explicitly malicious agent tasks across 11 harm categories, including fraud, cybercrime, and harassment. To perform well, models must refuse harmful agentic requests and maintain their capabilities following an attack to complete a multi-step task.  
https://arxiv.org/abs/2410.09024

### SafetyBench
SafetyBench is a benchmark for evaluating the safety of LLMs. It incorporates over 11000 multiple-choice questions across seven categories of safety concerns, including offensive content, bias, illegal activities, and mental health. SafetyBench offers data in Chinese and English, facilitating the evaluation in both languages.   
https://arxiv.org/abs/2309.07045


### PyRIT
PyRIT stands for Python Risk Identification Tool for generative AI (PyRIT). It’s more of a framework than a standalone benchmark, but a useful tool developed by Microsoft. PyRIT is a tool to evaluate LLM robustness against a range of harm categories. It can be used to identify harm categories including fabricated/ungrounded content (for instance, hallucination), misuse (bias, malware generation, jailbreaking), prohibited content (such as harassment), and privacy harms (identity theft). The tool automates red teaming tasks for foundation models, and thus aims to contribute to the efforts of securing the future of AI.  
https://github.com/Azure/PyRIT

### Purple Llama CyberSecEval
CyberSecEval a product of Meta’s Purple Llama project focuses on the cybersecurity of models used in coding. It claims to be the most extensive unified cybersecurity safety benchmark. CyberSecEval covers two crucial security domains: the likelihood of generating insecure code AND compliance when prompted to help with cyberattacks.  
https://github.com/meta-llama/PurpleLlama