# The performance of different approaches on SSI/SSDI
Conclusion:

![A bar chart of scores on test cases]()

## Scenario test cases (ROUGE)
|Approach   |rouge1             |rouge2              |rougeL             |rougeLsum          |
|-----------|-------------------|--------------------|-------------------|-------------------|
|NaiveRAG   |0.10638972974600375|0.03332123277906021 |0.07092772930309406|0.09179419033228833|
|AdvancedRAG|0.22694791192729363|0.0610002691993031  |0.14573577658754394|0.14553024242745344|
|GraphRAG   |0.1262765092746989 |0.033861502970296505|0.08621287227334787|0.10267322829949359|
|KB-RAG     |0.09550044274878426|0.018672250657445558|0.06790505095745589|0.08147286797283657|

# Approaches
Would be great if we can also add the baseline of `Policy Engine`, `RAPTOR` and other approaches.

> 💡 Add prompt `Answer the question with yes or no.` before question will simplify the benchmark task.  

## Naive RAG
Basic RAG, question is used to query vector storage of POMS document and get top 25 chunks to be used as a part of context for LLM to answer the question.
## AdvancedRAG
We used [PaperQA implementation](https://github.com/Future-House/paper-qa).
## GraphRAG
We used [Microsoft GraphRAG implementation](https://github.com/microsoft/graphrag).

# Test method
Single round Q&A, compare to human response.

* Metric 1 compare if prediction and target in same category `yes`, `no`, `maybe`.
* Metric 2 `ROUGE`.

# Test dataset
- [test-cases.jsonl](test-cases.jsonl)
- [scenario-test-cases.jsonl](scenario-test-cases.jsonl)
