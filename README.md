# SemAntoNeg
SemAntoNeg is test dataset designed to analyze how sentence representation models handle semantic similarity in cases involving negation and antonymy. It is created using sentences from Opusparcus ([Creutz, 2018](https://aclanthology.org/L18-1218/)) and filtering for sentences that include an adjective. It includes an input sentence, and three candidate paraphrases. One involves an antonym substitution, one is the input sentence negated, and one is the input sentence rephrased using negated antonymy.

**Note**: the dataset is small in size (3152 examples with 209 unique adjectives), so it is not meant for training models. Rather, it can be used to analyze model sensitivity to similarity in cases that involve negation and antonymy.

## Citation

The dataset is presented in the following paper:

**Teemu Vahtola, Mathias Creutz, and Jörg Tiedemann. 2022. It Is Not Easy To Detect Paraphrases: Analysing Semantic Similarity With Antonyms and Negation Using the New SemAntoNeg Benchmark. In Proceedings of the Fifth BlackboxNLP Workshop on Analyzing and Interpreting Neural Networks for NLP, pages 249–262, Abu Dhabi, United Arab Emirates (Hybrid). Association for Computational Linguistics.**

Please cite this paper if you use the dataset.

## Format

The data is formatted as follows:

| Label | Input                       | Options                                                                                                                                       |
|-------|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| 2     | No, that's true.            | No, that's false.; No, that's not true.; No, that's not false.                                                                               |
| 2     | I'm guilty.                 | I'm innocent.; I'm not guilty.; I'm not innocent.                                                                                            |
| 2     | I'm not sure.               | I'm not uncertain.; I'm sure.; I'm uncertain.                                                                                                |
| 2     | That is good.               | That is bad.; That is not good.; That is not bad.                                                                                            |
| 2     | I know you're not asleep.   | I know you're not awake.; I know you're asleep.; I know you're awake.                                                                        |


The sentence in the **Input** column is the source sentence, and the sentences in the **Options** column are the candidate paraphrases. The dataset is formatted such that the most similar sentence is always the last one in the options. Hence, the correct **label** is always 2.

In the actual data, entries are stored in JSON Lines format (```.jsonl```), including an ```idx``` field. The dataset is sequentially ordered by ```idx```, but the examples below are selected for visualization purposes and do not reflect the first few lines of the dataset:

```jsonl
{"idx": 2758, "label": 2, "input": "No, that's true.", "sentences": ["No, that's false.", "No, that's not true.", "No, that's not false."]}
{"idx": 2368, "label": 2, "input": "I'm guilty.", "sentences": ["I'm innocent.", "I'm not guilty.", "I'm not innocent."]}
{"idx": 33, "label": 2, "input": "I'm not sure.", "sentences": ["I'm not uncertain.", "I'm sure.", "I'm uncertain."]}
{"idx": 2830, "label": 2, "input": "That is good.", "sentences": ["That is bad.", "That is not good.", "That is not bad."]}
{"idx": 547, "label": 2, "input": "I know you're not asleep.", "sentences": ["I know you're not awake.", "I know you're asleep.", "I know you're awake."]}
```

License: Creative Commons Attribution 4.0 International License (CC-BY)
