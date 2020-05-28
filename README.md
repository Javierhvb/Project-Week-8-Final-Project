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


## Model Training and Evaluation
My next step was to start using a machine learning algorithm. In order to do so and not lose all the data from the previous days, which is what is going to determine the output of the algorithm, I decided to create new columns for the features with higher correlation (eventhough later I found a better way to do so) containing the values of the 14 previous days on each of the features (1 colum per day). After trying to train a random forest classifier, I found that there was barely no way to predict if the stock was going to be higher or lower. I tried different models without more luck. I had some hope por the SVM, but the result was pretty simmilar to the other ones.
Not being satisfied with not being able to predict in a way the stock market, I centered my research on finding which would be the best algorithm to predict stock values. And I came across many articles talking about Long Short-Term Memory (LSTM), which I found really interesting how it focuses on analysing the previous 60 (or X) days of the stock value in order predict the next (or X) target. Therefore, I decided to build a LSTM model an fit the data of the previous companies. It resulted in a great success, if you want to see the results you will find them in the file 03 analysing_data.


## Conclusion
I took many conclusions from this project which I value a lot. First of all, it is very important to be a good at managing expectations whne you are working in a data project. Sometimes you are so inmersed in the project that can only think that everything is going to be perfect, but when trying to find new inshights it is extremely difficult to actually make it. Nevertheless, it is very important to keep trying to make it, sometimes it is just a matter of consistency. The biggest insight I take from this project is that you need to love the process if you want to be a data scientist and I definately loved all of it, from gathering the data to cleaning it to trying to find hidden patterns etc. If you love the process you will never get bored and if you never get bored you are going to learn a lot! The more you learn the more thing you will be able to do and the more things you are able to do the more you will like what you are doing! Do what you love!


## Future Work
I am still convinced that there is correlation between what it is being said about a company in twitter and it's stock value. Having more time and resources I would love to dig deeper into this matter as well as on analysing better the peaks in google trends and the companies stock data.
Regarding the LSTM algorithm, I would like to keep improving the rsme and to keep improving the algorithm, maybe even start using it to make some money trading myself. Always bearing in mind that it is a risky play.


## Workflow
The workflow for the project was really straigth forward, eventhough some problems came up (as always) but I clearly knew where to gather the data from and I had crystal clear that I wanted to do a sentiment anlysis on the tweets (giving them an score) and merging all the data into one dataframe to see if I could find the hidden partern. There 


## Organization
The repository is organised into 4 different files. One with the files used to gather the data, for each data source I used a different file. Another file to saving the csv files, also divided per category and one extra file for the definitive data used for analysing and training the algorithm. There is also a file for the data analysis where you will find the jupyter notebooks for the two analyses.
All the tasks can be found on the trello I used to organise this project.


## Links
[Repository](https://github.com/Javierhvb/Stock-Predictor)  
[Slides](https://docs.google.com/presentation/d/1ekQ55ymflhcRIxlxnbWMWz8-Xeuy26LavG8EqqdZn5o/edit?usp=sharing)  
[Trello](https://trello.com/b/xIqnHxqJ/stock-predictor)  
