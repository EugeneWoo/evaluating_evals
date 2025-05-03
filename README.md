<h2>Evaluating Evals for Retrieval Relevance</h2>

I created this notebook to run a quick comparison **Atla Selene** against GPT4o (via the open-source Phoenix Arize tool), by creating a straightforward comparison of their performances in classifying the relevance or irrelevance of documents retrieved by RAG. To determine relevance to the corresponding query, I evaluated their predictions against a sample of ground-truth labels (n=30) from the Wiki_QA-Train benchmark dataset.

TL;DR it should come as no surprise that **Atla Selene** won this round on account of:
- Accuracy. It was 30% better than GPT4.
- Higher precision on 'Relevant' class (1.00 vs 0.50). GPT4 had substantially more False Positives.
- Very clean confusion matrix, with low misclassification rate (False Positive / False Negative both minimal)
- Atla's performance is more balanced between classes, as seen from the identical Macro F1 and Weighted F1
- No material differences were noted in critique text quality, though a deeper dive into subjective aspects like cohesiveness, helpfulness, and faithfulness etc may reveal nuances.

Time and budget permitting, I would like to expand the breadth of metrics including thinking critically about custom metrics, and benchmark Atla Selene against Claude, Gemini, DeepSeek, and Mistral across various use cases in addition to RAG.
