# Twitter Sentiment Analysis on Johnny-Amber Case

## Purpose of this project
Johnny Depp and Amber Heard case came to the spotlight starting 2016 after the start of their divorce and later this high-profile case started getting more media attention since 2019 and later this resulted to a public open-hearing court where Johnny Depp later wins the case in June 1, 2022. The purpose of this project was the gather and analyze the sentiment of this case since the start of 2022 uptill June 20. This will analyze the sentiment of both pre-post trial case and get better idea of public sentiment on twitter. 

## Data Collection
I decided to collect data from 2022 year and used ***scscrape.module.twitter*** libarary to extract tweets. I decided to cap maximum tweets to 80,000 from each month since January 2022, to get even spread across each month. Although from January to March, the volume of tweets were less than 80k but later on, the volume of tweets started rising as the case start getting more limelight.

## Data Cleaning
It is better to clean the data before I decided to do the analysis. A ***preprocess*** method was created which will handle the data cleaning. I decided to do small cleaning by lowering all cases and remove URLs using RegEx. Secondly, for simplicity and efficiency, it is better to remove multiple names i.e. for Johnny Depp, only his name should be mentioned and discard all other names mentioned in the ***remove_rows** dictionary*. Lastly, I decided to mention only those tweets which has hashtags mentioned in it. This helps reduce the testing data even more and will be used for hashtag analysis later on.

## Sentiment Model


## Analysis
### Sentiments

### Hashtags
