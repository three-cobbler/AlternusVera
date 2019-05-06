# Alternus Vera

Course code : **CMPE-257**

Group name : **SAY**

Name: **Yuhua He 013803959**

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


### Feature Selection
**List top Features Selected based on research articles**



### Team Contributions example:

|Features  |  Member |
|-----|-----|
| Corpus Structure                         |  Yuhua He |  
| Feature name(s)                 |  Samuel Yang |
| Feature name(s)                   |  Yuanzhe Li  |   


#### Enrichment Dataset Details

- Real news data from published articles (https://www.kaggle.com/snapcrack/all-the-news --- articles1)
- Fake news data from Kaggle (https://www.kaggle.com/mrisdal/fake-news)

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


#### What did I try and What worked?

> For Corpus structure feature, I tried applying unigram, bigrams, 3-grams, etc from cleaned content, vectorizing the documents with TF-IDF, then apply multiple classification algorithms such as Logistic Regression, Random Forest, etc. Comparing the F1 scores for each. Vectorizing each document based on ngrams do give me the the improvements on the accuracy model provides, I also played around with the C values passed in LogisticRegression class, which also gives me slight improvements on the accuracy score.

#### What did not work?

> Even though ngrams gave the difference on the model accuracy, but with orignal liar-liar dataset, the model accuracy didn't have too much diffence, it ranges between 50% - 58%, even though I applied different classification algorithms, the model accuracy still not improved that much.


#### What alternatives did you try?

> I tried data enrichment by getting additional real news data and fake news data from kaggle, cleaned the feature content and text columns by applying and similar cleanning logic used in the original data set, enriched with the orignal dataset and feed into the same model again, and got significant improvement on the model accuracy, it goes up to 87%(logistic regression), 89%(random forest) with unigram.

----
