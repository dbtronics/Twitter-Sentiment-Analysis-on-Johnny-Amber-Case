# Twitter Sentiment Analysis on Johnny-Amber Case

## Purpose of this project
Johnny Depp and Amber Heard case came to the spotlight starting 2016 after the start of their divorce and later this high-profile case started getting more media attention since 2019 and later this resulted to a public open-hearing court where Johnny Depp later wins the case in June 1, 2022. The purpose of this project was the gather and analyze the sentiment of this case since the start of 2022 uptill June 20. This will analyze the sentiment of both pre-post trial case and get better idea of public sentiment on twitter. 

## Data Collection
I decided to collect data from 2022 year and used ***scscrape.module.twitter*** libarary to extract tweets. I decided to cap maximum tweets to 80,000 from each month since January 2022, to get even spread across each month. Although from January to March, the volume of tweets were less than 80k but later on, the volume of tweets started rising as the case start getting more limelight. This resulted in `Johnny Data: 389451` and `Amber Data: 277406` tweets.

## Data Cleaning
It is better to clean the data before I decided to do the analysis. A ***preprocess*** method was created which will handle the data cleaning. I decided to do small cleaning by lowering all cases and remove URLs using RegEx. Secondly, for simplicity and efficiency, it is better to remove multiple names i.e. for Johnny Depp, only his name should be mentioned and discard all other names mentioned in the ***remove_rows** dictionary*. Lastly, I decided to mention only those tweets which has hashtags mentioned in it. This helps reduce the testing data even more and will be used for hashtag analysis later on. This reuslted in reduced dataset to:
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

* Johnny Depp


* Amber Heard


### Hashtags
