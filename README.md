# Natural-Language-Processing-movie-sentiment-analysis-part-I

# Introduction
Text is usually just a string in your dataset, but not all string features should be treated as text. A string feature can sometimes represent categorical variables. There is no way to know how to treat a string feature before looking at the data.
There are four kinds of string data you might see:
• Categorical data
• Free strings that can be semantically mapped to categories
• Structured string data
• Text data

![image](https://user-images.githubusercontent.com/53411455/145695978-c2824cda-bb8d-4878-9223-10b3bafedaae.png)


# Data source

We will use a dataset of movie reviews from the IMDb (Internet Movie Database) website collected by Stanford researcher Andrew Maas.3 This dataset contains the text of the reviews, together with a label that indicates whether a review is “positive” or “negative.” The IMDb website itself contains ratings from 1 to 10. To simplify the modeling, this annotation is summarized as a two-class classification dataset where reviews with a score of 6 or higher are labeled as positive, and the rest as negative. The data can be found in this repository as 'aclImdb_v1.tar.gz'. The notebook containg the codes for the project can be found in this repository as ' Untitled.iypnb'.

# Data loading as train and test

text_train and text_test are a list of length 25,000, where each entry is a string containing a review. We printed the review with index 1. You can also see that the review contains some HTML line breaks (<br />). While these are unlikely to have a large impact on our machine learning models.

# Data Wranglong

Involves data cleaning and preprocessing i.e. Bage of Words, by CountVectorizer.

One of the most simple but effective and commonly used ways to represent text for machine learning is using the bag-of-words representation. When using this representation, we discard most of the structure of the input text, like chapters, paragraphs, sentences, and formatting, and only count how often each word appears in each text in the corpus. Discarding the structure and counting only word occurrences leads to the mental image of representing text as a “bag.”

# Evaluating using Logistic regression

We obtain a mean cross-validation score of 88%, which indicates reasonable performance for a balanced binary classification task.

## Optimization

This simple mechanism works quite well in practice, but as we saw earlier, we get many uninformative features (like the numbers). One way to cut back on these is to only use tokens that appear in at least two documents (or at least five documents, and so on). A token that appears only in a single document is unlikely to appear in the test set and is therefore not helpful. We can set the minimum number of documents a token needs to appear in with the min_df parameter.

# Conclusion

The best validation accuracy of the grid search is still 89%, unchanged from before. We didn’t improve our model, but having fewer features to deal with speeds up processing and throwing away useless features might make the model more interpretable.
See you in part II to check more optimization to increase the performance of our model.



