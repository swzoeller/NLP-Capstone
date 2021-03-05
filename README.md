# Can We Detect Political Bias in Tweets?
NLP and Neural Network Project - Flatiron Phase 5
Prepared and Presented by:  **_Sarah Zoeller_**

### Business Case   
Given the recent political context, various organizations are exploring the use of machine learning to fight political bias in text content such as news articles and social media posts. This project aims to explore if a machine learning algorithm or deep learning can distinguish between content from left leaning politicians vs right leaning politicians.

So...can we detect political bias in tweets?

### The Data

- Data was sourced from Twitter using [Twint](https://github.com/twintproject/twint/)
- Included over 400,000 tweets from 500+ congressional members and politicians from January 2016 - January 2020
- Data was labeled as left or right biased based on the political party of the tweeter - **See Limitations**
- 75% of data was class “D” (Democrat), 25% class “R” (Republican)
- Train test split 70/30 train/test

### Exploratory Data Analysis (EDA)
<img src="https://github.com/swzoeller/Movie-Recommendation-System/blob/main/Images/num_v_rating.png" width="400" height="400"/>
- Frequently rated movies were rated higher on average

<img src="https://github.com/swzoeller/Movie-Recommendation-System/blob/main/Images/top_mov.png" width="400" height="400"/>
- Over 6000 movies had less than 5 ratings, while others had upwards of 300, potentially resulting in popularity bias


### Modeling Process
- KNN Basic from the Surprise library was used as a baseline
  - Baseline RMSE: 0.97 
- Final model was SVD model from Surprise library that has been tuned with GridSearch
  - Final RMSE: 0.87
  - Model is off by 0.87 points on average

![Predicted Average Rating per User vs Actual Average Rating per User](https://github.com/swzoeller/Movie-Recommendation-System/blob/main/Images/act_pred.png)

### Recommendation Function
![Recommendation Function Sample](https://github.com/swzoeller/Movie-Recommendation-System/blob/main/Images/recommend_fx.png)

### Conclusions
- The final model is not a perfect fit based on the RMSE (0.87), but is less than the standard deviation of the original ratings dataset (1.05)
- Recommendations appear to be more accurate when genre is specified

### Future Steps and Limitations
- Obtain reviews for movies that do not have a sufficient amount of reviews to be deemed reliable to the dataset or consider removing from model
- Investigate approaches to deal with popularity bias so to increase the representation of less popular movies (considering including weights in model)
- Create a more robust model with LightFM by incorporating movie features into weighting
- Calculate similarity metric between recommended movies and highest rated movies to better validate recommendations

### Additional Sources
- TriageCancer.org [congressional social media handles](https://triagecancer.org/congressional-social-media)
- Stanford NLP Group's [GloVe (Global Vectors for Word Representation)](https://nlp.stanford.edu/projects/glove/)

