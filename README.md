## Using text classifcation to detect fake news

**Partho Ghosh**

### Executive summary
**Project overview and goals:** The goal of the project is to figure out a model which can predict whether a news / article is fake or not accurately. This is a classification problem and we will thus use classfication algorithms to train our data. We will evaluate 4 algorithms which are as follows:
* Naive Bayes
* Logisitc Regression
* Decision Trees
* Passive Aggressive Classifier

Based on our results, we would choose the best model which can help us with accurate prediction for future news articles.

**Findings:** The best model which our analysis revealed for predicting whether a news is fake or not is PAC (Passive Aggressive Classifier.) The scores for the model are as follows:
* **Accuracy score:** 99.5
* **Precision score:** 99.5
* **Recall score:** 99.5
* **F1 score:** 99.5

The runtime of the model to train and evaulate our dataset was 419 s which was pretty decent compared to other models. Although, the runtime was slower than NB and Logistic Regression, the performance is way better. In other words, PAC turned out to be a good mix of speed and performance.

**Results and conclusion:** As a result, we can use PAC to train our dataset and predict whether a news is fake or not. We also tested on 2 random news samples (fake and true) and found out our model was able to correctly predict them.

**Future research and development:** Although we were able to come up with a model which is able to classify a news article as fake or not using binary classification. The problem is, fake news is not mere a body of text. It has other attributes such as source, medium via which it is getting shared and it should be cross-referenced against some fact corpus.

**Next steps and recommendations:** Next steps are as follows:
* Deep anaylysis of the model in hand by using debugging and feature importance techniques to figure out which words has more weightage in determining news is fake or not.
* Try out other techniques like Deep learning (especially, RNN and LSTM) and see how they perform against PAC.
* As discussed in future R&D, consider other aspects too for training the dataset to increase the accuracy.

### Rationale
Fake news by nature is very destructive, harmful and has many ill effects. A small example of it's ill impact can be found in this [article](https://www.marketwatch.com/press-release/the-impact-of-fake-news-on-the-economy-2023-06-08).

As per the above article, University of Baltimore did a study in 2019 which revealed that fake news caused an economic damage worth $78 billion in one single year. And this was before the covid era.

This is just one example. Like above, fake news not just do financial and economical damage but also damage societies in general.

Fake news mongers might be difficult to deal with but the news/article itself can be dealt with AI if we choose to put some efforts. 

### Research Question
The question we are trying to answer here is that which classification model can help us accurately determine a fake news given a dataset to train on.

### Data Sources
We are sourcing the data from [kaggle](https://www.kaggle.com/datasets/clmentbisaillon/fake-and-real-news-dataset?resource=download)

The data contains around 23k fake news and 21k true news with 0 non-null data. The original dataset contained features like title, text (actual article), subject and date.

We additionally added another feature to our data set (which becomes the target feature) called class. We then initalized this feature with 0 (fake) or 1 (true) based on the text.

Then, we merged the 2 datasets to create one single dataset to work upon.

### Methodology
**Preprocessing:** Post cleanup of the data, we pre-processed it in following order:
* Tokenization: Splitting of the text using TweetTokenizer.
* Stop words: Stop words for stop words removal in english.
* Punctuation: Made punctuation list for removal.
* Stemmer: Used Porter stemmer to stem.
* Lemmatizer: Used WordNetLemmatizer to lemmatize.

**Modeling:** As mentioned in the above sections, this is a classification problem and thus we chose bunch of classification algorithms to train and compare performance. We decided to go ahead with RandomizedGridSearch for the purpose of cross-validation of each algorithm to figure out the best versions of those.

For each classifcation algorithm, we followed the below steps:
* Cross-validation using RandomizedGridSearch.
* Used TF-IDF vectorizer for data standardization which was followed with the actual model implementation.
* Generated Confusion matrix to checkout their peformance.


### Results
We chose below classification algorithms to train our model and compare against each other:

* Naive Bayes
* Logistic Regression
* Decision Tree
* Passive Aggressive Classifier

Passive Aggressive Classifer (PAC) seem to have perfomed the best with accuracy score of 99% compared to others with a decent average runtime of 450 sec.


### Next steps
* Deep anaylysis of the model in hand by using debugging and feature importance techniques to figure out which words has more weightage in determining news is fake or not.
* Try out other techniques like Deep learning (especially, RNN and LSTM) and see how they perform against PAC.
* As discussed in future R&D, consider other aspects too for training the dataset to increase the accuracy.

### Outline of project

- [Link to notebook](https://github.com/parthoghosh24/fake_news_detection/blob/main/fake_new_detection.ipynb)


### Contact and Further Information
* Partho Ghosh
* Linkedin: https://ca.linkedin.com/in/parthog24
