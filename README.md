# Can We Detect Political Bias in Tweets?
NLP and Neural Network Project - Flatiron Phase 5
Prepared and Presented by:  **_Sarah Zoeller_**

### Business Case   
Given the recent political context, various organizations are exploring the use of machine learning to fight political bias in text content such as news articles and social media posts. This project aims to explore if a machine learning algorithm or deep learning can distinguish between content from left leaning politicians vs right leaning politicians.

So...can we detect political bias in tweets?

### The Data
- Data was sourced from Twitter using [Twint](https://github.com/twintproject/twint/)
- Included over 400,000 tweets from 500+ congressional members and politicians from January 2016 - February 2021
- Data was labeled as left or right biased based on the political party of the tweeter - **See Limitations**
- 75% of data was class “D” (Democrat), 25% class “R” (Republican)
- Train test split 70/30 train/test

### Exploratory Data Analysis (EDA)
<img src="https://github.com/swzoeller/NLP-Capstone/blob/main/Images/wcl.png" width="400" height="200"/>

<img src="https://github.com/swzoeller/NLP-Capstone/blob/main/Images/wcr.png" width="400" height="200"/>
Left wing tweets focused on certain topics, including healthcare and gun violence, and President Trump while Right wing tweets focused on temporal concepts, like today and time, as well as the opposing party (democrat).

### Modeling Process
Machine Learning Models:
- Logistic Regression
- Random Forest
- Naive Bayes

Deep Learning Models:
- RNN
  - GRU  
  - LSTM
 
Final model was LSTM Neural Network tuned with Talos
  - Final Accuracy: 80%
  - Final F1 score: 0.75

![Final Model Stats](https://github.com/swzoeller/NLP-Capstone/blob/main/Images/finalmodel.png)

### Prediction Function
<img src="https://github.com/swzoeller/NLP-Capstone/blob/main/Images/prediction2.png" width="800" height="200"/>

### Conclusions
- While there appears to be a detectable difference in the way right or left leaning politicians tweet, the model does not perfectly distinguish between the two and could use further tuning
- Model could be more accurate with added classes, such as “neutral”, “mild right bias”, “mild left bias”
- If the model were to be used, it could label articles/posts as “May Contain Political Bias” for the content that is  determined to be far right or left (based on their probabilities)
- This would allow readers to at least be aware that there may be bias

### Next Steps
- Expand classes
- Explore removal/inclusion of tweets based on their content
- Explore inclusion of prominent figures into dataset who are not on Twitter
- Set minimum and maximum threshold for tweets to be included in dataset so there is not over/under representation of certain tweeters
- Aggregate word embeddings into document embeddings

### Limitations
- Labeling: Data labeling was based on political party of the tweeter. Party of tweeter does not necessarily serve as a proxy for political bias
- Class distributions: Some politicians who tweet more frequently were more represented in the data than others. This could introduce bias into the dataset if said politicians use a certain rhetoric
- Inclusion/exclusion of political figures: Dataset was restricted to those figures on twitter. Politicians who are not on the platform were not included

### Additional Sources
- TriageCancer.org [congressional social media handles](https://triagecancer.org/congressional-social-media)
- Stanford NLP Group's [GloVe (Global Vectors for Word Representation)](https://nlp.stanford.edu/projects/glove/)

