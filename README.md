# Alternus Vera

Course code : **CMPE-257**

Group name : **SAY**

Name: **Yuhua He 013803959**
      **Yuanzhe Li 013637754**
-----

GitHub URL: https://github.com/three-cobbler/AlternusVera


### Liar Liar Pants on Fire Dataset Description
- It has 3 files test, training and valid.
- Each file has 14 columns

    Column 1: the ID of the statement ([ID].json).

    Column 2: the label.

    Column 3: the statement.

    Column 4: the subject(s).

    Column 5: the speaker.

    Column 6: the speaker's job title.

    Column 7: the state info.

    Column 8: the party affiliation.

    Column 9-13: the total credit history count, including the current statement.

    Column 14: the context (venue / location of the speech or statement).
    
### Credbank-data Dataset Description

Datalink: http://compsocial.github.io/CREDBANK-data/
The CREDBANK corpus was collected between mid October 2014 and end of February 2015. It is a collection of streaming tweets tracked over this period, topics in this tweet stream,topics classified as events or non events, events annotated with credibility ratings. The data is spread across four files. In this project, I selected Credibility Annotation File for the project's data enrichment.
This file contains more than 1300 events and their corresponding credibility ratings and reasons behind the ratings entered by Turkers. It contains 4 fields:

topic_key : This is a combination of the time_key and topic_terms from the (2). Topic File. The entries in the Topic File which were marked as event (isEvent = 1) have credibility ratings in the credibility annotation file.
topic_terms : A list of 3 terms corresponding to the top 3 terms in each topic.
Cred_Ratings: A list of 30 credibility ratings entered by Turkers. The ratings are based on a 5-point Likert scale ranging from [-2 to +2]:
[-2] Certainly Inaccurate
[-1] Probably Inaccurate
[0] Uncertain (Doubtful)
[+1] Probably Accurate
[+2] Certainly Accurate
Reasons: A list of 30 reasons corresponding to the ratings entered by the Turkers.

A snippet:

topic_key   topic_terms Cred_Ratings    Reasons
louis_ebola_nurse-20141024_170629-20141024_181626       [u'louis', u'ebola', u'nurse']  ['1', '-1', '2', '-2', '0', '2', '0',....]    ['Nurses union describes the procedures taken by nurse who now has Ebola from treating a patient., .....]

### Process of My Approach
- Load the Data
- Distillation Process
    - Data Cleaning and Text Preprocessing
    - Visualization
- **Feature 1 :** Corpus Structure
- Vector Classification Modeling
- Ranking and Importance
- Merge all features and individual contributions
- Form Polynomial Equation

For the Stance feature.
Transform enrichment dataset to the same form of Liar Liar dataset.
Extract useful features from both dataset.
Use a innovative formula for labeling data. the formula is 'log(mean of viewpoints, standard deviation)' where mean of viewpoints represents the topic tending towards, standard deviation represent conflicts in a topic, the more the false.
Build a keras model for training mode.

### Feature Selection
**List top Features Selected based on research articles**



### Team Contributions example:

|Features  |  Member |
|-----|-----|
| Corpus Structure                         |  Yuhua He |  
| Feature name(s)                          |  Samuel Yang |
| Stance                                   |  Yuanzhe Li  |   


#### Enrichment Dataset Details

- Real news data from published articles (https://www.kaggle.com/snapcrack/all-the-news --- articles1)
- Fake news data from Kaggle (https://www.kaggle.com/mrisdal/fake-news)
- CredBank http://compsocial.github.io/CREDBANK-data/
#### Existing data source
word2vec-GoogleNews-vectors (https://drive.google.com/file/d/0B7XkCwpI5KDYNlNUTTlSS21pQmM/edit)

https://github.com/BuzzFeedNews/2016-10-facebookfact-check/tree/master/data

https://www.cs.ucsb.edu/william/data/liardataset.zip

https://www.kaggle.com/mrisdal/fake-news

https://github.com/bs-detector/bs-detector

http://compsocial.github.io/CREDBANK-data/

http://www.politifact.com/

#### Libraries Used

- NLTK
- Gensim
- Numpy
- Pandas
- CSV
- WordCloud
- Seaborn
- Scipy
- Regualr Expression
- Matplotlib
- Sklearn
- Math
- Keras

#### What did I try and What worked?

> For Corpus structure feature, I tried applying unigram, bigrams, 3-grams, etc from cleaned content, vectorizing the documents with TF-IDF, then apply multiple classification algorithms such as Logistic Regression, Random Forest, etc. Comparing the F1 scores for each. Vectorizing each document based on ngrams do give me the the improvements on the accuracy model provides, I also played around with the C values passed in LogisticRegression class, which also gives me slight improvements on the accuracy score.
> For Stance feature, I tried different CNN models, especially in activation factions and units in hidden layers. Because data points from Liar Liar I choosed. have a lot of zeros, easily causing an gradient vanishing during training phase. Finally I found that tanh works like a charm on choosen dataset. 
Another one is threshold for labeling data from CredBanK, after multiple attempts, I found that 75/100 is a good threshhold.

#### What did not work?

> Even though ngrams gave the difference on the model accuracy, but with orignal liar-liar dataset, the model accuracy didn't have too much diffence, it ranges between 50% - 58%, even though I applied different classification algorithms, the model accuracy still not improved that much.
> Some common activation function could not working here, like ReLu, like no matter how to set labeling threshold, ReLu will cause a gradient vanish problem.

#### What alternatives did you try?

> I tried data enrichment by getting additional real news data and fake news data from kaggle, cleaned the feature content and text columns by applying and similar cleanning logic used in the original data set, enriched with the orignal dataset and feed into the same model again, and got significant improvement on the model accuracy, it goes up to 87%(logistic regression), 89%(random forest) with unigram.
> Once solved vanishing problem, I trid different hyper-parameters on training model, finally found one words well.
----
