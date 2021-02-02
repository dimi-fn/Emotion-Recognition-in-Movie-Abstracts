# Extraction of Emotional Tags from Movie Synopses

### [Guidance through the coding notebooks](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts#guidance-through-the-coding-files)

#### Note:
Due to a Github bug ([issue #3555](https://github.com/jupyter/notebook/issues/3555)), sometimes the notebook files (files with .ipynb) may not render. 

Please reload the page until they do (sometimes it loads after one reload, some other times it might need a persistent refresh of the page until the content can be displayed).

Table of Contents
=======================

* [Summary](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts#summary)
* [Research Problem - Domain](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts#research-problem---domain)
* [Source of Data](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts#source-of-data)
* [Natural Language Processing (NLP)](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts#natural-language-processing-nlp)
* [Models' Production](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts#models-production)
	* [Models](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts#models)
	* [Multi-label Classification Evaluation Metrics](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts#multi-label-classification-evaluation-metrics)
	* [Research Deliverables](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts#research-deliverables)
* [Conclusions](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts#conclusions)
* [Acknowledgments](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts#acknowledgments)
* [Guidance through the coding files](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts#guidance-through-the-coding-files)

## Summary
What makes a movie e.g. suspenseful, dramatic, or sci-fi, and which words hidden in movie plots can predefine this? The answer to that would help extract significant information from narrative texts and build an automatic system that could produce emotional tags.

This project was submitted in partial fulfillment of requirements for the degree of MSc Information Management at Strathclyde University (August 2020), and it was marked with distinction.

The aim was to identify, define, and automatically predict a set of emotions in movies based on their movie abstract and various metadata. This was achieved with various data processing, and machine & deep learning tools, with a core element and focus on Natural Language Processing.

The problem was treated as a multi-label classification one, and the result was the prediction of emotions in 55,577 unlabelled movies, and the identification of a correlation between the predicted emotions and users' ratings and preferences.

Overall, various correlation tests indicated a strong relationship between users' watchlist and their respective emotional tags. It was concluded that the notion of emotion can constitute an important feature in the movie industry with regard to recommender systems and advertising companies for generating, finding, and placing a higher level of personalized content.
## Research Problem - Domain
The production of the model would presuppose the existence of some emotional classes-labels with regard to movies. However and based on the research conducted, there was found no dataset fulfilling that, and therefore, initial manual labeling was necessary, as well the decision of the emotional tags used.
Αfter thorough research, Ekman’s six discrete emotional classes (Ekman, 1992; Lazemi & Ebrahimpour-Komleh, 2016; Tkalčič et al., 2016) were decided to constitute the emotional tags. These classes can be easily linked with facial communication and expressions, and these are (in alphabetical order): anger, disgust, fear, happiness, sadness, and surprise (Ekman, 1992; Farzindar & Inkpen, 2015:p.50).
## Source of Data
The main sources of data originate from:
1)	Secondary Data: They encompass a wide variety of movie metadata provided by the [MovieLenes research dataset](https://grouplens.org/datasets/movielens/).
2)	Primary Data: Fetching the movie overviews for every one of the movies in the above dataset, via a [TMDB API for developers](https://developers.themoviedb.org/3/getting-started/introduction) from the [TMDb website](https://www.themoviedb.org/).
## Natural Language Processing (NLP)
A series of NLP techniques were applied such as: Part of Speech (POS) tags, Sentiment Analysis, Topic Modeling, Non-Negative Matrix Factorization, Named-Entity Recognition (NER).
## Models' Production
The target variables for all models were the six emotions. However, the architecture for the selection of the predictor variables was composed of two kinds. The first type of architecture has as its feature predictors only the movie overviews, while the second type was composed of the movie overviews along with other variables (movie metadata) for a potentially better performance.

After data preprocessing, feature selection and feature engineering the best model was chosen and evaluated.
### Models
* Construction of __*Machine Learning models*__ in [Scikit-Learn](https://scikit-learn.org/stable/):
1)	Logistic Regression as OvR classifier
2)	Multinomial Naive Bayes 
3)	Linear SVClassifier
4)	Random Forest
5)	SGD Classifier
6)	SVC
7)	Neighbors Classifier
8)	SoftMax Classifier
9)	Decision Tree Classifier
10)	XGBClassifier
11)	Multi-layer (MLP) Perception Classifier (shallow network)
12)	Multi-layer (MLP) Perception Classifier (deep network)

* Construction of __*Deep Neural Network models*__ in [TensorFlow](https://www.tensorflow.org/):
A series of a wide variety of Convolutional and Recurrent Neural Network models, with word embeddings, pooling layers, Long Short-Term Memory (LSTM) units; either with single or multiple output layers.
### Multi-label Classification Evaluation Metrics
Micro average F1 score, subset accuracy score, cross-validation score, hamming loss metric, ROC-AUC score.

The final model was also evaluated via the [Scikit-Learn's multi-label confusion matrix report](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.multilabel_confusion_matrix.html).
## Research Deliverables
- Manual Labelling of 300 movies in terms of their represented emotion (the construction of an initial dataset with reference to their emotion was necessary for the models' production).
- Automatic extraction and prediction of emotional tags in 55,577 movies, as well the depiction of the combination of their emotions (e.g. some movies can generate more than one emotion).
- Intensity magnitude in the emotion production procedure: different movies may encompass different emotions and a different number/combination of emotions. But what about their intensity level?
 After proceeding to that initiative, the generated emotion for each one of the six emotions is decided by the researcher to have 3 intensity levels, i.e. low, moderate, and high.
## Conclusions
-	Emotional tags can constitute an additional feature in the movie industry for Recommender Systems (RSs) and advertising companies to integrate. The project can also be useful in the movie industry in the context of film psychology, as well as in the Emotion Aware Recommender Systems (EARSs) helping RSs to scale by recommending new items based on affective item features and users’ emotional reactions.
-	Enhancement of RSs by refining the retrieval of similar movies/TV shows.
-	Movies with law popularity may present few or no tags. Therefore, an automatic prediction of emotional tags can alleviate the problem of incompleteness in tag spaces, the cold start problem, and the data sparsity in RSs.
## Acknowledgments
All respective references of authors and sources can be found inside the dissertation paper, the latter of which is also uploaded in this repository. Additional references with regard to coding can also be found inside the notebooks.
### Guidance through the coding files
#### [*__1_Initial_Datasets.ipynb__*](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts/blob/master/1_Initial_Datasets.ipynb): 
* Data exploration of all six Movielens csv files provided.
* Merging "genome tags" and "genome scores" and the introduction of ten stratums of relevance.
* Introducing a modified genome_scores csv file, keeping only the highest relevance scores and its metadata (relevance score>=0.7).
* Adding a new column "rating_cat" in ratings.csv (values [1,3]).
* Merging movies.csv & links.csv. Creating a new column "overview" in order later to extract data from TMDb.
* Fetching movie plots from TMDb via a tmdb api for developers.
* Several feature engineering.
#### [*__2_NLP_movies_final.ipynb__*](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts/blob/master/2_NLP_movies_final.ipynb):
* NLP techniques applied in movies_final dataframe.
* Tokenization & POS/ Visualization.
* Sentiment Analysis / Compound polarity scores.
* Non-Negative Matrix Factorization & Topic Modelling.
* Name Entity Recognition (NER) & Visualization / introducting the column "entities".
* construction of "movies_final_2.csv" .
#### [*__3_NLP2_movies_final_2_emotion_Labelling.ipynb__*](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts/blob/master/3_NLP2_movies_final_2_emotion_Labelling.ipynb): 
* Fixing entities.
* Choosing genres for the final choice of movie sample for the manual emotion labelling.
* Emotion labelling in 300 movies.
* Construction of "movies_final_3.csv".
#### [*__4a_Models_ML_Overviews.ipynb__*](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts/blob/master/4a_Models_ML_Overviews.ipynb): 
* Application of various Machine Learning models with NLP, using as features the movie overviews.
#### [**__4b_Models_ML_Overviews_&_Metadata.ipynb__**](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts/blob/master/4b_Models_ML_Overviews_%26_Metadata.ipynb):
* Application of various Machine Learning models with NLP, using as features the movie overviews plus various movie metadata via Column Transformer with a pipeline.
* Here is where the final model architecture is located, although it got even more fine-tuned in "4e_Final_Model_&_Predictions.ipynb".
#### [*__4c_Models_DLoverviews&metadata.ipynb__*](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts/blob/master/4c_Models_DLoverviews%26metadata.ipynb): 
* Application of various Deep Learning models with NLP.
* Word Embeddings. 
* Single and multiple output layers.
#### [*__4d_Model_Bert.ipynb__*](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts/blob/master/4d_Model_Bert.ipynb): 
* Making Predictions with BERT via the FastBert Deep Learning library.
#### [**__4e_Final_Model_&_Predictions.ipynb__**](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts/blob/master/4e_Final_Model_%26_Predictions.ipynb):
* Fine-tuning the final model initially created in "4b_Models_ML_Overviews & Metadata.ipynb".
* Making predictions in 55,577 unlabelled movies in terms of emotions.
* Extracting "predictions_decision_scores_df.csv".

#### [*__5_Hypothesis_Tests.ipynb__*](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts/blob/master/5_Hypothesis_Tests.ipynb):
* Normality checks for checking the existence of normal distribution or not in variables used in hypothesis tests.

* 2 sets of hypothesis sets:
	1) ratings vs emotions (in all dataset - non user-centric approach): 4 tests.
	2) user-centric approach:
		a) ratings vs emotions (per user): 4 tests.
		b) emotion scores vs emotion scores in sets of movies in watchlists of users per unique user: 4 tests.
#### 
[*__Dissertation Paper__*](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts/blob/master/Dissertation%20Paper.pdf): The dissertation paper submitted at Strathclyde University for the degree of MSc in Information Management at the Computer & Information Sciences department (August 2020), which contains the theoretical  and practical part of this repository project.
####
[*__Labelling_300_Movies.xlsx__*](https://github.com/dimi-fn/Emotion-Recognition-in-Movie-Abstracts/blob/master/Labelling_300_Movies.xlsx): The excel file containing the manual labelling of 300 movies. Note that they do not have a binary form of 0 and 1. This is because the researcher had in mind to use scores in range [0,3], with values more than 1 implying more intensity. This was not used, however, 1) values that were >=1 were used as "1" and values with 0 as "0", 2) the intensity magnitude of emotions was finally attributed and constructed by the confidence scores of the model's [decision function](https://scikit-learn.org/stable/modules/generated/sklearn.svm.LinearSVC.html#sklearn.svm.LinearSVC.decision_function) (where a higher confidence level score would indicate a higher emotional intensity level).
