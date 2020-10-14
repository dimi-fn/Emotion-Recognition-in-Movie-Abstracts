# Extraction of Emotional Tags from Movie Synopses

## Summary
What makes a movie e.g. suspenseful, dramatic, or sci-fi, and which words hidden in movie plots can predefine this? The answer to that would help extract significant information from narrative texts and build an automatic system that could produce emotional tags.

This project was submitted in partial fulfillment of requirements for the degree of MSc Information Management at Strathclyde University (August 2020), and it was marked with distinction.

The aim was to identify, define, and automatically predict a set of emotions in movies based on their movie abstract and various metadata. This was achieved with various data processing, and machine & deep learning tools, with a core element and focus on Natural Language Processing.

The problem was treated as a *multi-label classification* one, and the result was the prediction of emotions in 55,577 unlabelled movies, and the identification of a correlation between the predicted emotions and users' ratings and preferences.

Overall, various correlation tests indicated a strong relationship among users' watchlist and the respective emotional tags. It was concluded that the notion of emotion can constitute an important feature in the movie industry with regard to recommender systems and advertising companies for generating, finding, and placing a higher level of personalized content.
## Research Problem - Domain
The production of the model would presuppose the existence of some emotional classes-labels with regard to movies. However and based on the research conducted, there was found no dataset fulfilling that, and therefore, initial manual labeling was necessary, as well the decision of the emotional tags used.
Αfter thorough research, Ekman’s six discrete emotional classes (Ekman, 1992; Lazemi & Ebrahimpour-Komleh, 2016; Tkalčič et al., 2016) were decided to constitute the emotional tags. These classes can be easily linked with facial communication and expressions, and these are (in alphabetical order): anger, disgust, fear, happiness, sadness, and surprise (Ekman, 1992; Farzindar & Inkpen, 2015:p.50).
## Source of Data
The main sources of data originate from:
1)	Secondary Data: They encompass a wide variety of movie metadata provided by the [MovieLenes research dataset](https://grouplens.org/datasets/movielens/)
2)	Primary Data: Fetching the movie overviews for every one of the movies in the above dataset, via a [TMDB API for developers](https://developers.themoviedb.org/3/getting-started/introduction) from the [TDDb website](https://www.themoviedb.org/)
## Natural Language Processing (NLP)
A series of NLP techniques were applied such as: Part of Speech (POS) tags, Sentiment Analysis, Topic Modeling, and Named-Entity Recognition (NER).
## Models' Production
The target variables for all models were the six emotions. However, the architecture for the selection of the predictor variables was composed of two kinds. The first type of architecture has as its feature predictors only the movie overviews, while the second type was composed of the movie overviews along with other variables (movie metadata) for a potentially better performance.

After data preprocessing, feature selection and feature engineering the best model was chosen and evaluated.
### Models
Construction of __*Machine Learning models*__ in [Scikit-Learn](https://scikit-learn.org/stable/):
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

Construction of __*Deep Neural Network models__* in [TensorFlow](https://www.tensorflow.org/):
A series of a wide variety of Convolutional and Recurrent Neural Network models, with word embeddings, pooling layers, Long Short-Term Memory (LSTM) units, either with single or multiple output layers.
### Multi-label Classification Evaluation Metrics
Micro average F1 score, subset accuracy score, cross-validation score, hamming loss metric, ROC-AUC score.

The final model was also evaluated via the [Scikit-Learn's multi-label confusion matrix report](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.multilabel_confusion_matrix.html).
## Research Deliverables
- Manual Labelling of 300 movies in terms of their represented emotion (the construction of an initial dataset with reference to their emotion was necessary for the models' production).
- Prediction of emotion in 55,577 movies, as well the combination of their emotions (e.g. some movies can generate more than one emotion).
- Intensity magnitude in the emotion production: different movies have different emotions and a different number/combination of emotions. But what about their intensity level?
 After proceeding to that initiative, the generated emotion for each one of the six emotions is decided by the researcher to have 3 intensity levels, i.e. low, moderate, and high.
## Conclusions
-	Emotional tags can constitute an additional feature in the movie industry for Recommender Systems (RSs) and advertising companies to integrate.
-	Enhancement of RSs by refining the retrieval of similar movies/TV shows.
-	Movies with law popularity may present few or no tags. Therefore, an automatic prediction of emotional tags can alleviate the problem of incompleteness in tag spaces, cold start problem, and data sparsity in RSs.
## Acknowledgments
All respective references can be found inside the dissertation paper.

