# Predicting Readability for Student Text

![Readability Cover Photo](https://github.com/christianmoya/Predicting_LitReadability/blob/main/Pictures/readability_picture.png)

## Introduction 
For my final capstone project, I built a machine learning model that predicts the readability of texts for students grades 3-12. I followed the CRISP-DM methodology and used Natural Language Procession to clean the text data. I tested with 2 vectorizers: TF-IDF and a CountVectorizer, and 3 regression models: LinearRegression, RidgeRegression and RandomForestRegression. I hypothesized that the words in a text have an effect on readability, with the null hypothesis stating that words in a text do not have an effect on readability. 

## Data 
The Data in this text was pulled from the Kaggle competition, "CommonLit Readability Prize". It had over 2,800 texts ranging from grades 3-12. The hardest text had a readabilty score of -3.67 and the easiest text had a score of 1.71, with an average of -0.959. 

![Readability Target Histogram](https://github.com/christianmoya/Predicting_LitReadability/blob/main/Pictures/readability_scores.png)

The most commonly used bigrams are "one day", "united states", and "years ago". In our pre-model EDA, we find that difficult texts have more scientific bigrams like "per cent", "per second", and "experiments made", whereas our easy text have bigrams more related to stories, like "one day", "little girl" and "little boy". 

![Easy Text Bigrams](https://github.com/christianmoya/Predicting_LitReadability/blob/main/Pictures/easy_bigrams.png) ![Difficult Text Bigrams](https://github.com/christianmoya/Predicting_LitReadability/blob/main/Pictures/difficult_bigrams.png)

## Results 
After multiple iterations, I found my score to be the lowest at .698 with a Ridge Regression model and a TF-IDF vectorizer with max features set at 50,000, a score 5% lower than our baseline model. When exploring feature importance, we find that the terms that most increase readability score are "you", "mother", "lived", "girls" and "baby", signifying easier texts are more story-based. Terms that decrease readability scores are more prepositional terms, like "of", "as", and "in", signifying that difficult texts are more passive and lack direct language, making the text harder to comprehend. 

![Negative Coefficient](https://github.com/christianmoya/Predicting_LitReadability/blob/main/Pictures/negative_coef.png)
![Positive_Coefficient](https://github.com/christianmoya/Predicting_LitReadability/blob/main/Pictures/positive_coef.png)

## Conclusions and Recommendations 
Our model shows that terms and words in a text do have an impact on its readability, so teachers and others interested in improving literacy for students can follow the recommendations below. 

For struggling readers: 
* Introduce tougher subjects like science and math through storytelling to provide some sort of access point. 
* Edit the texts to remove unneccsary prepositional phrases to make the text more direct and easy to comprehend. 

For talented readers:
* Provide texts a snudge more difficult than they're comfortable with to continue developing their literacy skills. 
* Challenge more talented readers to write out summary to provide access points to struggling readers as well. 

## Future Work 
Our work continues after this. 
* My first task would be to build out a front-end platform so teachers can detect the readability of assigned texts to see if it's too difficult or too easy for their students. 
* Given text data contains a lot of zeros in our data, I would like to use PCA to possibly create a more accurate model. 
* Lastly, I would like to extend this work to include kindergarten - 2nd grade texts. 
