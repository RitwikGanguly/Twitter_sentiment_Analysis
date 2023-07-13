# Twitter Sentiment Analysis
---

## Sentiment Analysis
Sentiment analysis, also known as opinion mining, is the process of determining and extracting the sentiment or emotional tone expressed in a piece of text data. It aims to understand the subjective information conveyed by the text, whether it is positive, negative, or neutral.

#### The sentiment analysis of text data is performed using various techniques, including:
1) **Rule-based approach:** In this approach, a set of predefined rules or patterns is used to classify the sentiment of the text. These rules can be based on the presence of specific words, phrases, or linguistic patterns associated with positive or negative sentiment. Rule-based approaches often involve the use of sentiment lexicons or dictionaries that map words to sentiment scores.

2) **Machine learning approach:** This approach involves training a machine learning model on a labeled dataset of text samples, where each sample is annotated with its corresponding sentiment (positive, negative, or neutral). The model learns patterns and relationships between textual features (such as words, n-grams, or syntactic structures) and their associated sentiments. Once trained, the model can be used to predict the sentiment of new, unseen text data.

3) **Hybrid approach:** Some sentiment analysis techniques combine rule-based and machine learning methods to benefit from the strengths of both. They may use rule-based methods for initial sentiment classification and then employ machine learning techniques to refine the results or handle more complex cases.

#### The process of performing sentiment analysis on text data typically involves the following steps:
1) **Text preprocessing:** This step involves cleaning and preparing the text data for analysis. It may include tasks such as removing special characters, punctuation, and irrelevant information, converting text to lowercase, and tokenizing the text into individual words or sentences.

2) **Feature extraction:** In this step, relevant features are extracted from the text data. Features can include words, n-grams (sequences of multiple words), parts of speech, or other linguistic or contextual information that may be indicative of sentiment.

3) **Sentiment classification:** This is the core step where sentiment analysis techniques are applied to classify the sentiment of the text. Depending on the chosen approach (rule-based or machine learning), the sentiment of the text is determined based on predefined rules, sentiment lexicons, or by using a trained model.

4) **Result interpretation:** Once the sentiment classification is performed, the results are interpreted and analyzed. This can involve aggregating sentiment scores over multiple text samples, calculating sentiment proportions, or generating visualizations to understand the sentiment distribution.

---

> - **The Sentiment Analysis is a UnSupervised Technique**
> - **So can either use any one of the clustering technique(i.e. KMeans or DBSCAN) or else we have to use any ML lexical analysis technique.**
> - **If we will choose the sentiment analysis of any social media platform (i.e Twitter, Instragram etc) then the lexical analysis technique is easy to impliment and understand**
> - **The Most Important Sentiment analysis techniques are - TextBlob, Vader**
> - **In this Twitter Sentiment Analysis I used TextBlob Technique**

## TextBlob Technique: 

TextBlob's sentiment analysis technique is based on a combination of pattern-based and machine learning approaches. It provides a simple and intuitive API to analyze the sentiment of text data, classifying it as positive, negative, or neutral.

#### The sentiment analysis in TextBlob involves the following steps:

1) **TextBlob object creation:** You start by creating a TextBlob object, which represents a piece of text that you want to analyze for sentiment. This could be a sentence, paragraph, document, or even a collection of text documents.

2) **Pre-processing:** TextBlob performs pre-processing steps on the input text, such as tokenization (splitting the text into individual words or sentences), word normalization (converting words to their base or root form), and removing stop words (commonly occurring words that do not carry much meaning for sentiment analysis, such as "the," "is," "and," etc.).

3) **Sentiment polarity calculation:** TextBlob employs a pre-trained sentiment classifier to assess the sentiment polarity of the processed text. The sentiment polarity score is a real-valued number that ranges from -1 to +1, where -1 represents negative sentiment, +1 represents positive sentiment, and 0 represents neutral sentiment.

4) **Subjectivity calculation:** TextBlob also calculates the subjectivity score, which indicates the degree of objectivity or subjectivity in the text. The subjectivity score ranges from 0 to 1, where 0 represents highly objective (factual) text, and 1 represents highly subjective (opinionated) text.

5) **Result interpretation:** Based on the sentiment polarity score, the text is classified as positive, negative, or neutral. The magnitude of the polarity score indicates the strength or intensity of the sentiment.

TextBlob's sentiment analysis technique is trained on a large dataset containing labeled text data for sentiment classification. This enables it to generalize well to unseen text and provide reasonably accurate sentiment analysis results.

To use TextBlob for sentiment analysis, one would typically follow these steps:

``` python

from textblob import TextBlob

# Create a TextBlob object
text = "I love this movie!"
blob = TextBlob(text)

# Perform sentiment analysis
sentiment = blob.sentiment

# Access polarity and subjectivity scores
polarity = sentiment.polarity
subjectivity = sentiment.subjectivity

# Classify sentiment
if polarity > 0:
    sentiment_label = "Positive"
elif polarity < 0:
    sentiment_label = "Negative"
else:
    sentiment_label = "Neutral"

# Print results
print("Sentiment: ", sentiment_label)
print("Polarity: ", polarity)
print("Subjectivity: ", subjectivity)

```

**Output:**

Sentiment: Positive
Polarity: 0.5
Subjectivity: 0.6


**TextBlob's sentiment analysis is a helpful tool for getting quick insights into the sentiment of text data, making it useful for applications such as social media monitoring, customer feedback analysis, and opinion mining.**
