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
To be done by 2/12 - in complete - sorry. See updates below.

I have tried to follow the Scikit-Learn tutorial [Working with Text Data](http://scikit-learn.org/stable/tutorial/text_analytics/working_with_text_data.html) but it was hard. I might have a grasp of what they are saying but I don't have a very clear idea.

My *kernel* (Kaggle-speak for notebook?) has been created but hasn't been submitted. Not sure if still exploring phase notebook should be submitted: https://www.kaggle.com/tkurosaka/toxic-comment-id-try-1 

Instead of working on Kaggle, I created a local notebook for explortory work, which I intend to push to github at some point.

1. What data have you gathered, and how did you gather it?
1. How have you explored the data and what insights have you gained as a result?
1. Will you be able to answer your question with this data, or do you need to gather more data (or adjust your question)?
1. What modeling approach are you using to answer your question?

# Update 2018-2-16
I made a very basic model, just following [Working with Text Data](http://scikit-learn.org/stable/tutorial/text_analytics/working_with_text_data.html). No bigrams. No stopwords. The result doesn't seem that bad. Please seee [Toxic Comment Data Baseline](https://github.com/tkurosaka/toxic-comment-classification/blob/master/Toxic%20Comment%20Data%20Baseline.ipynb).
To compare, I tried to run [NB-SVM strong linear baseline](https://www.kaggle.com/jhoward/nb-svm-strong-linear-baseline) locally but it timed out. I modified it to use only 1/10th of data, and further splitting it into test and training set. I further had to modify it to produce actual predicitons, not probabilities.  My base line is better for many labels, but that's probably because only 1/10th of the data was used.
I will attempt to copy my notebook to Kaggle and submit just to see my score.
Then I will start feature tuning locally, starting with using word n-grams and perhaps removing random symbols that Jeremy Howard is doing.

# Update 2018-2-17
Published my notebook on Kaggle.

Submitted the resulting data. The score was 0.8360. The top score so far is 0.9873. I'm probably around the bottom. (I could not figure out how to see my rank.)

I then tried ngram_range=(1,3). The resulting score was *lowered* to 0.7892.  It had a negative effect.  

Another experiment with ngram_range=(1,2). There is much difference compared with my baseline. There is a slight gain in the "severe_toxic" labeling.

ToDo: Try min_df. Try exact same setting as Jeremy's. 

# Notes
* Suggested reading by Trent
   * Tutorial in Scikit Learn: [Working with Text Data](http://scikit-learn.org/stable/tutorial/text_analytics/working_with_text_data.html)
* Toolkit that might help
   * [Gensim: topic modelling for humans](https://radimrehurek.com/gensim/), suggested by Trent
   * [NLTK = Natural Language Toolkit](http://www.nltk.org/), the only Python based NLP library I could find
   
* Top models
   * Top model as of 2/10 [Classifying multi-label comments (0.9741 lb)](https://www.kaggle.com/rhodiumbeng/classifying-multi-label-comments-0-9741-lb)
   * ~~Jeremy Howard's popular base line: [Minimal LSTM + NB-SVM baseline ensemble](https://www.kaggle.com/jhoward/minimal-lstm-nb-svm-baseline-ensemble)~~ (This was just combining two models according to the kernels listed below.)
   * Jeremy Howard's [NB-SVM strong linear baseline](https://www.kaggle.com/jhoward/nb-svm-strong-linear-baseline)
   * Jeremy Howard's [Improved LSTM baseline: GloVe + dropout](https://www.kaggle.com/jhoward/improved-lstm-baseline-glove-dropout)
   
