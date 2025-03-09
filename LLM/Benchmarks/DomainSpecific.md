# Benchmarks

## DomainSpecific

### MultiMedQA
‍The MultiMedQA benchmark measures LLMs' ability to provide accurate, reliable, and contextually appropriate responses in the healthcare domain. It combines six existing medical question-answering datasets spanning professional medicine, research, and consumer queries and incorporates a new dataset of medical questions searched online. The benchmark evaluates model answers along multiple axes: factuality, comprehension, reasoning, possible harm, and bias.  
https://www.nature.com/articles/s41586-023-06291-2

### FinBen
FinBen is an open-source benchmark designed to evaluate LLMs in the financial domain. It includes 36 datasets that cover 24 tasks in seven financial domains: information extraction, text analysis, question answering, text generation, risk management, forecasting, and decision-making. FinBen offers a broader range of tasks and datasets compared to its predecessors and is the first to evaluate stock trading. The benchmark revealed that while the latest models excel in information extraction and textual analysis, they struggle with advanced reasoning and complex tasks like text generation and forecasting.  
https://arxiv.org/abs/2402.12659

### LegalBench
LegalBench is a collaborative benchmark designed to evaluate the legal reasoning abilities of LLMs. It consists of 162 tasks, which are crowdsourced by legal professionals. These tasks cover six different types of legal reasoning: issue-spotting, rule-recall, rule-application, rule-conclusion, interpretation, and rhetorical understanding.  
https://arxiv.org/abs/2308.11462


### Berkeley Function-Calling Leaderboard
Berkeley Function Leaderboard (BFCL) evaluates LLMs' function-calling abilities. The dataset consists of 2000 question-answer pairs in multiple languages–including Python, Java, Javascript, and RestAPI–and diverse application domains. It supports multiple and parallel function calls and function relevance detection.  
https://gorilla.cs.berkeley.edu/blogs/8_berkeley_function_calling_leaderboard.html

### GPQA
GPQA stands for Graduate-Level Google-Proof Q&A Benchmark. It’s a challenging dataset of 448 multiple-choice questions spanning the domains of biology, physics, and chemistry. The questions in GPQA can be considered very difficult: experts including those with PhDs can only achieve about 65% accuracy on answering these questions. Questions are actually hard enough to be Google-proof e.g. even with free web access and 30+ minutes of researching a topic, out-of-domain validators (e.g. a biologist answering a chemistry question) could only achieve 34% accuracy. GPQA is part of the Open LLM Leaderboard by Hugging Face.  
https://github.com/idavidrein/gpqa

### MedQA
The abbreviation stands for Medical Question Answering benchmark. It’s a multiple-choice question-answering evaluation based on United States Medical License Exams. This benchmark covers three languages with tons of questions: English (12k+ questions), simplified Chinese (34k+ questions), and traditional Chinese (14k+ questions).  
https://github.com/jind11/MedQA

### PubMedQA
The PubMedQA is a dataset for question answering about biomedical research. Models are required to answer questions with 3 possible answers based on the provided abstracts: yes, no, or maybe.  
https://github.com/pubmedqa/pubmedqa
