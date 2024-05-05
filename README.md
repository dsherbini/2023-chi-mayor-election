# 2023 Chicago Mayoral Election Analysis

### This project explores the results of the 2023 Chicago mayor's election, including:
1. Sentiment Analysis: A sentiment analysis of headlines related to the election, producing polarity and subjectivity scores (using spaCy and NLTK packages). Headlines are web-scraped from Wikipedia.
2. Plotting: A shiny app featuring correlation plots of ward-level election results against other ward characteristics, such as percent of housholdes who are rent burdened.
3. Prediction: A prediction algorithm using k nearest neighbors to predict the winning candidate per ward.

### Data sets used:
1. Mayoral Election Results by Ward (Source: Chicago Board of Election Commissioners)
2. Chicago Ward Maps (Source: chicago.gov)
3. Demographic data: voting age, rent burden, and race/ethnicity (Source: U.S. Census API)
4. Election-related article headlines (Source: Wikipedia)

### Sentiment Analysis Results:

Johnson:
- Mean Subjectivity: 0.0733. This suggests that the text associated with Johnson is objective or non-subjective.
- Mean Polarity: 0.0505. There is a slightly positive sentiment, but the value is close to 0, meaning that the sentiment is mostly neutral.

Vallas:
- Mean Subjectivity: 0.1214. On average, the text associated with Vallas is more subjective compared to Johnson.
- Mean Polarity: 0.016. This suggests a slightly positive sentiment, but the value is close to 0 again, indicating a relatively neutral sentiment.

### Prediction Results: 

For the nearest neighbors prediction algorithm, I first determine the optimal number of neighbors (k). The optimal value of k is defined as the one that yields the lowest misclassification rate among the testing data. A ward is misclassified if its predicted winner does not match its actual winner. After considering all values of k from 2-10, we find the optimal value to be 4.

I then train the nearest neighbors model with k = 4 and use the standard euclidean distance as the distance metric. I use the model to output the predicted probability that Johnson will win a ward and the predicted probability that Vallas will win a ward. The ward winner is the candidate who has a higher predicted probability. I then compare the predicted winner to the actual winner from the original data and find that the model correctly predicts 13 out of 15 wards in the testing data – an 86% accuracy rate.
