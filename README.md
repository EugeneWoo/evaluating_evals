<h2>Evaluating Evals for Retrieval Relevance</h2>

I created this notebook to compare **Atla Selene** against GPT4 via Phoenix Arize (I omitted GPT4o due to technical reasons), by creating a straightforward comparing of their performance when classifying the relevance or irrelevance of documents retrieved by RAG. To determine relevance to the corresponding query, I evaluated their predictions against ground-truth labels from the Wiki_QA-Train benchmark dataset.

*Link to the GPT4 evaluation in case the notebook is unavailable:
https://colab.research.google.com/drive/1ygW8d1eL4z43IfxmRmfCapLAuqIwhoWI?usp=sharing*

It should come as no surprise that Atlas Selene came out on top on account of:
* Accuracy. It was 24% better than GPT4
* Higher precision on 'Relevant' class (1.00 vs 0.56). GPT4 had more False Positives.
* Very clean confusion matrix, with low misclassification rate (False Positive / False Negative both minimal)
* Atla's performance is more balanced between classes, as seen from the identical Macro F1 and Weighted F1

Time and budget permitting, I would have liked to run a comprehensive benchmarking on the full dataset, and pit Atla Selene against Claude, Gemini, Llama, and Mistral across all the metrics.
