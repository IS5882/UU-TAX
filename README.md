# UU-Tax
## UU-Tax at SemEval-2022 Task 3: Towards improving the generalizability of language models for taxonomy classification through data augmentation.


[![SemEval](https://img.shields.io/badge/SemEval-PreTENS-blue)](https://sites.google.com/view/semeval2022-pretens/home-page)
[![Paper](https://img.shields.io/badge/Paper-UU--Tax-red)](add link)


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

For dataset files please refer to the SemEval-2022: PreTENS Git-Hub ([page](https://github.com/shammur/SemEval2022Task3))

### Code:

#### Dependencies

* Compatible with Python 3.x
* Dependencies can be installed as specified in Block 1 in the respective notebooks. 
* All the code was implemented on Google Colab using GPU. Please ensure that you are using the version as specified in the "Ïnstallion and Drives" block.

		
**For more details on the how the exact process was carried out and the final hyper-parameters used; please refer to UU-Tax paper.**

### Citing:
Please cite UU-Tax if you use any of this material in your work.

[Add citation]


#### Implementation Refrences:
* Hugging face link of all pretrained models https://huggingface.co/transformers/v2.3.0/pretrained_models.html 
* [NLPAug](https://nlpaug.readthedocs.io/en/latest/) was used to for data-augmentation for experminets in both sub-tasks. (https://arxiv.org/pdf/1409.0473.pdf). Towards Data Science 
* Translation was obtained from GoogleTranslation API (made on Google-Sheets, as the GoogleTranslate Python API limits the translation to 10K chars / 24 hrs.


*Please cite the appropriate reference(s) in your work*

