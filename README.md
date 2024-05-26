# Multilingual BERT for Textual Entailment in Vietnamese and English

**Introduction**

This model is designed to address the Natural Language Inference (NLI) task using a pre-trained multilingual model. The goal is to predict the semantic relationship between two sentences (synonymous, antonymous, or semantically unrelated).

**Requirements**

* Python 3.6+
* TensorFlow 2.0+
* Transformers library
* Sentencepiece library

**Dataset**

The datasets contain two columns for sentence pairs (`sentence_1`, `sentence_2`) and one column for the label (`label`). `sentence_1` can be an English or Vietnamese sentence, `sentence_2` is a Vietnamese sentence, and `label` has three values: "agree", "disagree", and "neutral".

**Model**

I use the infoXLM-Large model from Hugging Face. The model is fine-tuned for the NLI task using TensorFlow Keras with additional layers for classification.

**Experiments**

To find the most suitable model for the task, I experimented with various multilingual models: mBERT, XLM-R, and infoXLM with their variations. The table below shows the experimental results with these models.

| Model | Train acc | Val acc | Test acc |
| --- | --- | --- | --- |
| [mBERT](https://huggingface.co/google-bert/bert-base-multilingual-cased) | 0.95 | 0.86 | 0.85 |
| [XLM-RoBERTa-base](https://huggingface.co/FacebookAI/xlm-roberta-base) | 0.96 | 0.9 | 0.9 |
| [XLM-RoBERTa-large](https://huggingface.co/joeddav/xlm-roberta-large-xnli) | 0.99 | 0.95 | 0.96 |
| [InfoXLM-base](https://huggingface.co/microsoft/infoxlm-base) | 0.85 | 0.88 | 0.87 |
| [InfoXLM-large](https://huggingface.co/microsoft/infoxlm-large) | 0.99 | 0.96 | 0.96 |

The two models, XLM-R-large and InfoXLM-large, yielded nearly identical results. Ultimately, I chose the InfoXLM-large model to address this task.

**Acknowledgements**

Thank you to the authors of the mBERT, XLM-R, and infoXLM models.
