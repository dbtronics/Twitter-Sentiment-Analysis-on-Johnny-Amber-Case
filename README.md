# Twitter Sentiment Analysis on Johnny-Amber Case

## Purpose of this project
Johnny Depp and Amber Heard case came to the spotlight starting 2016 after the start of their divorce and later this high-profile case started getting more media attention since 2019 and later this resulted to a public open-hearing court where Johnny Depp later wins the case in June 1, 2022. The purpose of this project was the gather and analyze the sentiment of this case since the start of 2022 uptill June 20. This will analyze the sentiment of both pre-post trial case and get better idea of public sentiment on twitter. 

## Data Collection
I decided to collect data from 2022 year and used ***scscrape.module.twitter*** libarary to extract tweets. I decided to cap maximum tweets to 80,000 from each month since January 2022, to get even spread across each month. Although from January to March, the volume of tweets were less than 80k but later on, the volume of tweets started rising as the case start getting more limelight. This resulted in `Johnny Data: 389451` and `Amber Data: 277406` tweets.

## Data Cleaning
It is better to clean the data before I decided to do the analysis. A `preprocess` method was created which will handle the data cleaning. I decided to do small cleaning by lowering all cases and remove URLs using RegEx. Secondly, for simplicity and efficiency, it is better to remove multiple names i.e. for Johnny Depp, only his name should be mentioned and discard all other names mentioned in the `remove_rows` *dictionary*. Lastly, I decided to mention only those tweets which has hashtags mentioned in it. This helps reduce the testing data even more and will be used for hashtag analysis later on. This reuslted in reduced dataset to:
```
Johnny Depp
82019 tweets kept out of 389451 --> 21.06 percent retention
Amber Heard
28076 tweets kept out of 277406 --> 10.12 percent retention
```

## Sentiment Model
For sentiment analysis, I decided to use [roBERTa-base model](https://huggingface.co/cardiffnlp/twitter-roberta-base-sentiment-latest), which has been trained on ~124M tweets. This will help us get better estimate of public sentiment over the case.

## Analysis
After data cleaning, it resulted in 21% and 10% of total dataset for Johnny Depp and Amber Heard tweets respectively. But due to limited resources, I decided to extract only _5k tweets_ from both and run the sentiment analysis. The model takes 35 mins to run total of _**10k tweets**_.
### Sentiments
The visual representation of the analysis for both are given below:

* Johnny Depp Sentiment Analysis

![Johnny Depp Analysis](https://user-images.githubusercontent.com/37752863/176330692-42e05547-0641-4198-b865-f6a2288a4fe8.png)

* Amber Heard Sentiment Analysis

![Amber Heard Analysis](https://user-images.githubusercontent.com/37752863/176330735-5e839511-1f3b-456d-b62b-46aa497d824d.png)


### Hashtags
I decided to compile all the hashtags associated with `Positive` and `Negative` hashtags for both and decided to display the top 5 most used hashtags for both.

#### Positive
<img width="305" alt="Johnny Depp Top 5 Positive Hashtags" src="https://user-images.githubusercontent.com/37752863/176331224-c1645b38-2e78-44b5-8397-04c370fef788.png">
<img width="303" alt="Amber Heard Top 5 Positive Hashtags" src="https://user-images.githubusercontent.com/37752863/176331249-6fcb2fd9-1e20-4fd4-b2a7-bfd639260603.png">

#### Negative
<img width="341" alt="Johnny Depp Top 5 Negative Hashtags" src="https://user-images.githubusercontent.com/37752863/176331525-e0fcf21b-92bc-4420-a16d-f9c133cde3e6.png">
<img width="304" alt="Amber Heard Top 5 Negative Hashtags" src="https://user-images.githubusercontent.com/37752863/176331842-886f66d3-65d2-4cb9-b1f1-88595041d36e.png">

