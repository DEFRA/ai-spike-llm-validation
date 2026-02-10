# AI LLM Validation Spike

Status: Completed

## Need
AI is increasingly used across Defra.  There will be times when users need to decide which of two competing models to use for a particular task or whether to update an existing model to a later version, and development of AI tools and patterns should be guided by an independent evaluation of performance.  We therefore need a validation framework to measure the performance of LLMs in various tasks.

## Hypothesis

LLMs have an intrinsic, consistent performance for each of a number of different tasks which we can measure using public datasets.

## What we aim to discover
- Whether it is feasible to reliably validate performance
- Which tasks can be validated
- Which publicly available datasets can be used for validation
- The method by which the LLM response can be compared to the ground-truth

## Assumptions
- The public datasets we use were not used in the training of any of the LLMs we test
- The public datasets include a compreshensive coverage of use-cases.

## Outcomes
 We succesfully validated the peformance of 7 LLMs included in AWS Bedrock Production against two tasks - answering questions and summarising documents.  Both DeepEval (LLM-As-A-Judge) and Bert-Score (Semantic Similarity) provided a realistic comparison of the LLM response to the ground-truth examples.  Bigger and newer models generally out-performed smaller and older models as expected.

### Key Findings
- It is possible to validate the ability of LLMs to answer questions and summarise documents.
- This can be done with publicly available datasets
- DeepEval (LLM-As-A-Judge) seems to provide more believable comparison results than a semantic evaluation using Bert-Score
- Bigger and newer models generally out-performed smaller and older models as expected.



## Shortcomings

- Validation was run on a laptop and only 20 prompts per model were used.  More prompts should be used to improve significance.
- We dont know for sure whether the public test datasets were used in training the models and therefore whether the results are biased.