# OTAM (Offensive Tamazight corpus) v1.0

 The corpus is manually crawled from Facebook social media, by selecting some popular public pages and groups related to political and gouvernmental subjects. Data collection has been done by two native speakers, while the annotation was done by three native speakers. The overall corpus contains 6,250 texts written in Latin script, and some words/texts are written in Arabic script.


 Table 1. OTAM corpus description

 |  | normal | offensive | total |
 | ------------- | ------------- | ------------- | ------------- |
 | #texts | 3,148 | 3,102 | 6,250 |


 Table 2. Inter-disagreement annotation with regards to the final labels

 |  | 1st annotator | 2nd annotator |
 | ------------- | ------------- | ------------- |
 | offensive | 2 | 1 |
 | normal | 29 | 19 |
 | Cohen’s k | 0.9900 | 0.9939 |


 # Evaluation

 We have implemented a naive classifier based on checking the existence of the lexicon words within the input text. Firstly, we check the existence of each offensive/abusive word within the input text, and once it is found, the text is claimed offensive. Otherwise, we compute the similarity between the text words and the lexicon words using Jaro distance. If the distance is greater or equal to 0.92 (tuned experimentally), the words are claimed similar and then the text is considered as offensive.

 Besides the naive classifier, we have used well-known ML and DL classifiers as a baseline. More specifically, we have used SVM and Multinomial Naive Bayes classifiers implemented in scikit-learn with default parameters. In addition, we have used FastText with the default parameters to train the model, as well as CNN and BiLSTM.

 Table 3. Results produced by different classifiers

 | | F-score | Accuracy |
 | ------------- | ------------- | ------------- |
 | LexCheck | 80.77 | 77.95 |
 | ------------- | ------------- | ------------- |
 | FastText | 76.16 | 73.71 |
 | CNN | 74.31 | 71.31 |
 | BiLSTM | 75.33 | 73.71 |
 | ------------- | ------------- | ------------- |
 | NB-tfidf | 76.15 | 70.99 |
 | SVM-tfidf | 74.67 | 68.58 |
 | NB-BOW | 76.36 | 71.63 |
 | SVM-BOW | 74.48 | 67.94 |


 # Citation

 Kheireddine Abainia, Kenza Kara, and Tassadit Hamouni. 2022. A New Corpus and Lexicon for Offensive Tamazight Language Detection. In 7th International Workshop on Social Media World Sensors (Sideways’22), June 28, 2022, Barcelona, Spain. ACM, New York, NY, USA, 10 pages. https://doi.org/10.1145/3544795.3544852


 # ACKNOWLEDGMENTS

 We would like to thank Mr. Salim Koumad for his valuable contribution in annotating the corpus and helping us to fine tune the lexicon.
