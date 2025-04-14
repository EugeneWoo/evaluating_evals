<h2>Evaluating Evals for Retrieval Relevance</h2>

I created this notebook to compare **Atla Selene** against GPT4 via Phoenix Arize (I omitted GPT4o due to technical issues), by creating a straightforward comparison of their performances in classifying the relevance or irrelevance of documents retrieved by RAG. To determine relevance to the corresponding query, I evaluated their predictions against a sample of ground-truth labels (n=30) from the Wiki_QA-Train benchmark dataset.

*Link to the GPT4 evaluation in case the notebook is unavailable:
https://colab.research.google.com/drive/1ygW8d1eL4z43IfxmRmfCapLAuqIwhoWI?usp=sharing*

TL;DR it should come as no surprise that **Atla Selene** won this round on account of:
- Accuracy. It was 24% better than GPT4
- Higher precision on 'Relevant' class (1.00 vs 0.56). GPT4 had more False Positives.
- Very clean confusion matrix, with low misclassification rate (False Positive / False Negative both minimal)
- Atla's performance is more balanced between classes, as seen from the identical Macro F1 and Weighted F1
- However, I did not notice material differences in the quality of the critiques between models. The nuances may surface if we deepdive into cohesiveness, helpfulness, faithfulness, etc

Time and budget permitting, I would like to think more critically about the metrics, and benchmark Atla Selene against Claude, Gemini, DeepSeek, and Mistral across various use cases in addition to RAG. 
