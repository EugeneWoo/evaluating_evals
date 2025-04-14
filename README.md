<h2>Evaluating Evals for Retrieval Relevance</h2>

I created this notebook to compare **Atla Selene** against GPT4 via Phoenix Arize (I omitted GPT4o due to technical reasons), by creating a straightforward evaluation of the models' performance when classifying the relevance or irrelevance of documents retrieved by RAG. To determine relevance to the corresponding query, I compared their predictions against ground-truth labels from the Wiki_QA-Train benchmark dataset.

It should come as no surprise that Atlas Selene came out on top on account of:
* Accuracy. It was 24% better than GPT4
* Higher precision on 'Relevant' class (1.00 vs 0.56). GPT4 had more False Positives.
* Very clean confusion matrix, with low misclassification rate (False Positive / False Negative both minimal)
* Atla's performance is more balanced between classes, as seen from the identical Macro F1 and Weighted F1

Time and budget permitting, I would have liked to run a comprehensive benchmarking on the full dataset, and pit Atla Selene against Claude, Gemini, Llama, and Mistral across all the metrics.
