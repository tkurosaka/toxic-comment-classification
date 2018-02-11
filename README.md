Data Science Introduction course project

Name of Student: T. *Kuro* Kurosaka <kuro@bhlab.com>

# The Project
My project is to take the [Toxic Comment Classification Challeng](https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge) on Kaggle.

# Write Up No. 1

1. What is the question you hope to answer?
   * Predict if a wikipedia commenent is "toxic" under 6 different cagetories.
1. What data are you planning to use to answer that question?
   * https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge/data
1. What do you know about the data you're using so far?
   * The training data has 159,571 entreies. 
   * The test data has 153,164 entries.
   * The comment tends to ends with some auto-filled text like IP address, use's wikipedia ids, some random strings, or nothing, that probably won't affect the toxic-ness of the comment itself. (But the user-id and IP addresses, if separated into a different, column, might work as a strong signal.)

1. Why did you choose this topic?
   * I don't like those toxic comments and it would make my life better if they can be auto-deleted, although I am also concerned about freedom of expression and removal of my posting by a false identification, which would be very frustrating.
   * I also have some background in NLP and I might be apply some technique for this challenge.
   * There is a chance to win a prize though the change seems less than the chance of winning a lottery. 

# Write Up No.2
To be done by 2/12

1. What data have you gathered, and how did you gather it?
1. How have you explored the data and what insights have you gained as a result?
1. Will you be able to answer your question with this data, or do you need to gather more data (or adjust your question)?
1. What modeling approach are you using to answer your question?

# Notes
* Suggested reading by Trent
   * Tutorial in Scikit Learn: [Working with Text Data](http://scikit-learn.org/stable/tutorial/text_analytics/working_with_text_data.html)
* Toolkit that might help
   * [Gensim: topic modelling for humans](https://radimrehurek.com/gensim/), suggested by Trent
   * [NLTK = Natural Language Toolkit](http://www.nltk.org/), the only Python based NLP library I could find
   
* Top models
   * Top model as of 2/10 [Classifying multi-label comments (0.9741 lb)](https://www.kaggle.com/rhodiumbeng/classifying-multi-label-comments-0-9741-lb)
   * Jereny Howard's popular base line: [Minimal LSTM + NB-SVM baseline ensemble](https://www.kaggle.com/jhoward/minimal-lstm-nb-svm-baseline-ensemble)
