# UU-Tax
## UU-Tax at SemEval-2022 Task 3: Improving the generalizability of language models for taxonomy classification through data augmentation.


[![SemEval](https://img.shields.io/badge/SemEval-PreTENS-blue)](https://sites.google.com/view/semeval2022-pretens/home-page)
[![Paper](https://img.shields.io/badge/Paper-UU--TAX-red)](https://aclanthology.org/2022.semeval-1.35/)
[![Google Scholar](https://img.shields.io/badge/Google%20Scholar-Injy%20Sarhan-yellow)](https://scholar.google.nl/citations?user=Otq5vX0AAAAJ&hl=nl)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Injy%20Sarhan-brightgreen)](https://linkedin.com/in/injy-sarhan-03294295)

### Model Description
<p align="center">
 
  <img src="https://github.com/IS5882/UU-TAX/blob/main/SemEvalDiagram-Electra.drawio.png" width="550" title="UU-Tax Framework for sub-task 1">


</p>


### Sub-task 1:
In Subtask 1 in all 3 languages, we used the pre-trained ELECTRA language model and fine-tuned the discriminator part of the transformer on our downstream task. The fine-tuning was a 2-stage process as follows.

**In the first stage**: We fine-tuned the language model on an augmented version of the training data using NLPAug. We used 2 variants of the NLPAug tool: insertion and substitution, both were carried out using BERT.

**In the second stage:** We fine-tuned the model on the original training data and its translation from the 2 other two languages. In other words, for English, we translated the French training dataset and the Italian dataset to English, concatenated them with the original English training dataset, and used the concatenated data for our 2nd stage of fine-tuning.

The same process was carried out for all the 3 languages independently.



### Sub-task 2:
In subtask 2, we relied on the sentence embedding features generated by multilingual Universal Sentence Encoder (USE) to train a classifier.

**English:** SVM was used as the classifier.

**Italian:** Linear Regression used as the classifier.

**French:** Decision Tree used as a classifier.


A model was trained for each language.


### Datasets

For the original training dataset files please refer to the SemEval-2022: PreTENS [GitHub](https://github.com/shammur/SemEval2022Task3).

NLPAug data that was used for sub-task 1 for all 3 languages is uploaded in the 'NLPAug Data' folder.

Translated data for sub-tasks 1 and 2 is uploaded in the 'Translation Data' folder for all 3 languages.

### Code:

#### Dependencies

* Compatible with Python 3.x
* Dependencies can be installed as specified in Block 1 in the respective notebooks. 
* All the code was implemented on Google Colab using GPU. Please ensure that you are using the version as specified in the "Ïnstallion and Drives" block.

		
**For more details on the how the exact process was carried out and the final hyper-parameters used; please refer to UU-Tax paper.**

### Citing:
Please cite UU-Tax if you use any of this material in your work.


```
@inproceedings{sarhan-etal-2022-uu,
    title = "{UU}-Tax at {S}em{E}val-2022 Task 3: Improving the generalizability of language models for taxonomy classification through data augmentation",
    author = "Sarhan, Injy  and
      Mosteiro, Pablo  and
      Spruit, Marco",
    booktitle = "Proceedings of the 16th International Workshop on Semantic Evaluation (SemEval-2022)",
    month = jul,
    year = "2022",
    address = "Seattle, United States",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2022.semeval-1.35",
    pages = "271--281",
    abstract = "This paper presents our strategy to address the SemEval-2022 Task 3 PreTENS: Presupposed Taxonomies Evaluating Neural Network Semantics. The goal of the task is to identify if a sentence is deemed acceptable or not, depending on the taxonomic relationship that holds between a noun pair contained in the sentence. For sub-task 1{---}binary classification{---}we propose an effective way to enhance the robustness and the generalizability of language models for better classification on this downstream task. We design a two-stage fine-tuning procedure on the ELECTRA language model using data augmentation techniques. Rigorous experiments are carried out using multi-task learning and data-enriched fine-tuning. Experimental results demonstrate that our proposed model, UU-Tax, is indeed able to generalize well for our downstream task. For sub-task 2 {---}regression{---}we propose a simple classifier that trains on features obtained from Universal Sentence Encoder (USE). In addition to describing the submitted systems, we discuss other experiments that employ pre-trained language models and data augmentation techniques. For both sub-tasks, we perform error analysis to further understand the behaviour of the proposed models. We achieved a global F1{\$}Binary{\$} score of 91.25{\%} in sub-task 1 and a rho score of 0.221 in sub-task 2.",
}

```

#### Implementation Refrences:
* Hugging face link of all pretrained models https://huggingface.co/transformers/v2.3.0/pretrained_models.html 
* [NLPAug](https://nlpaug.readthedocs.io/en/latest/) was used to for data-augmentation for experminets in both sub-tasks. 
* Translation was obtained from GoogleTranslation API (made on Google-Sheets, as the GoogleTranslate Python API limits the translation to 10K chars / 24 hrs.


*Please cite the appropriate reference(s) in your work*

