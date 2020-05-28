<img src="https://bit.ly/2VnXWr2" alt="Ironhack Logo" width="100"/>

# Stock Predictor
*[Javier Hita Vallet-Barceló]*

*[Data Analytics, Barcelona & March 2020]*

## Content
- [Project Description](#project-description)
- [Hypotheses / Questions](#hypotheses-questions)
- [Dataset](#dataset)
- [Cleaning](#cleaning)
- [Analysis](#analysis)
- [Model Training and Evaluation](#model-training-and-evaluation)
- [Conclusion](#conclusion)
- [Future Work](#future-work)
- [Workflow](#workflow)
- [Organization](#organization)
- [Links](#links)

## Project Description
The final intention of this project, as the title indicates, is trying to predict the stock market. Who hasn't thought about being able to make money without working? I, obviously, know that it is a nearly impossible thing to do, but not completely. If you want to know more about people who have made it possible, read about Jim Simons (The man who solved the market). Extremely interesting read. Nevertheless, my approach is going to be different, I'm going to gather data from twitter (tweets) regarding a company and it's google trends evolution, mix all with stock data and see what happens.

## Hypotheses / Questions
* Can twitter give a hint on whether the stock market of a company is going to increase or decrease? 
* Will an increase of 10% in the google trends of a company imply an increase or decrease on the companies stock value?
* Can a peak in google trends mean that the company is doing something noticeable? If yes, can a sentiment analysis on twitter data tell me if the stock will increase or decrease?
* Which is the best algorithm to predict the stock market changes?

## Dataset

I used three different data sources:
* To gather the data related to stocks, I used an API call alpha advantage, which I highly recommend to anyone interested in this type of data.
* The data related to twitter, I gathered thanks to a library I installed (twitterscraper). Also highly recommendable to gather twitters passed data. The only inconvenient is that you will have to be patient if you want to gather large amounts of tweets.
* Pytrends was the non-official google API I found to gather all the data related to google trends. Again, very usefull and easy to use.


## Cleaning
Regarding the cleaning of the data, the stock data was already cleaned and ready to be used. I had more troubels with the Google trends and twitter. Twitter because sometimes, it would only gather 100 tweets from a day, instead of 1.000 (which was the supposed value) and since it took so long I had to predefine it which days to gather the data. At the end of the day, I decised to conduct the analysis and drop the tweets with neutral sentiment analysis and do the mean between the remaining tweets. Giving values according to te polarity of the tweet, ranging from -1 to 1. The dates without tweets data were filled with 0 and in other cases ignored. Regarding the google data, it was all scaled according to the dataframe requested. Since the API had a limit of total calls per minute, in some occasion it was not possible to gather the last 5 years of a company. Therefore, in some cases the data missing was dropped or in some other cases making a rescaling approximation.

## Analysis
Clearly, my first steps once all the different datasets were merged into one dataframe was to look for the basic indicators. At plain sight there was no correlation. Therefore, I had to start plotting the data to try to look for hidden patterns. I started plotting with matplolib and seaborn but in order to explore the data Tableau has no rival. Therefore, I opened the merged csv in Tableau and started playing with the different features. After a while, it became clear that there was no apparent relationship between the three datapoints.

My next step was to start using a machine learning algorithm. In order to do so and not lose all the data from the previous days, which is what is going to determine the output of the algorithm

## Model Training and Evaluation
*Include this section only if you chose to include ML in your project.*
* Describe how you trained your model, the results you obtained, and how you evaluated those results.

## Conclusion
* Summarize your results. What do they mean?
* What can you say about your hypotheses?
* Interpret your findings in terms of the questions you try to answer.

## Future Work
Address any questions you were unable to answer, or any next steps or future extensions to your project.

## Workflow
Outline the workflow you used in your project. What were the steps?
How did you test the accuracy of your analysis and/or machine learning algorithm?

## Organization
How did you organize your work? Did you use any tools like a trello or kanban board?

What does your repository look like? Explain your folder and file structure.

## Links


[Repository](https://github.com/Javierhvb/Stock-Predictor)  
[Slides](https://docs.google.com/presentation/d/1ekQ55ymflhcRIxlxnbWMWz8-Xeuy26LavG8EqqdZn5o/edit?usp=sharing)  
[Trello](https://trello.com/b/xIqnHxqJ/stock-predictor)  
