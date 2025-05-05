<h2>Evaluating Evals for Retrieval Relevance</h2>

I created this notebook to run a quick comparison **Atla Selene** against Gemini 2.0 Flash and GPT-4o (via the open-source Phoenix Arize), by creating a straightforward comparison of their performances in classifying the relevance or irrelevance of documents retrieved by RAG. To determine relevance to the corresponding query, I evaluated their predictions against a sample of ground-truth labels (n=30) from the Wiki_QA-Train benchmark dataset.

TL;DR it should come as no surprise that **Atla Selene** won this round on account of:
- Accuracy. It was c.30% better than Gemini and GPT.
- Higher precision on 'Relevant' class (1.00 vs c.0.50). Gemini and GPT had substantially more False Positives.
- Very clean confusion matrix, with low misclassification rate (False Positive / False Negative both minimal)
- Atla and Gemini had more balanced performances between classes, as seen from the identical/very close Macro F1 and Weighted F1.
- No material differences were noted in critique quality, though a deeper dive into subjective aspects like cohesiveness, helpfulness, and faithfulness etc may reveal nuances.

Time and budget permitting, I would like to expand the breadth of metrics including thinking critically about custom metrics, and benchmark against Claude, DeepSeek, and Mistral across other use cases apart from RAG.

*BENCHMARKING RESULTS -->*

🥇 **Atla Selene**
	•	Accuracy: 0.97 – highest among all models.
	•	Precision on “True”: 1.00 – perfect, with zero false positives.
	•	Recall on “True”: 0.94 – only one false negative.
	•	Balanced performance: Identical Macro F1 and Weighted F1 of 0.97.
	•	Confusion Matrix: Nearly diagonal – excellent separation of classes.
	•	Verdict: Strongest overall, with reliable and consistent predictions.

🥈 **Gemini 2.0 Flash**
	•	Accuracy: 0.70 – equal to GPT-4o, but with better recall on the “True” class.
	•	Precision / Recall:
	•	“True”: 0.53 / 0.90 – high recall, but weaker precision (many false positives).
	•	“False”: 0.92 / 0.60 – high precision, weaker recall.
	•	Macro F1: 0.75 recall average; F1-score of 0.70, outperforming GPT-4o on balance.
	•	Confusion Matrix: 40% of “False” class mislabeled as “True”, similar to GPT-4o.
	•	Verdict: Slightly better class balance than GPT-4o, though still not ideal.

🥉 **GPT-4o via Arize**
	•	Accuracy: 0.67 – lowest of the three.
	•	Precision / Recall:
	•	“Relevant”: 0.50 / 0.80
	•	“Unrelated”: 0.86 / 0.60
	•	Macro F1: 0.66 – dragged down by inconsistent class treatment.
	•	Confusion Matrix: Shows confusion in distinguishing unrelated docs, with 40% misclassified.
	•	Verdict: Acceptable in simpler use cases, but less dependable than the others.
