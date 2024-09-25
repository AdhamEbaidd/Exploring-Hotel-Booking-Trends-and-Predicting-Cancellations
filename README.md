
# Exploring Hotel Booking Trends and Predicting Cancellations
## Author
**Name:** Adham Sherif Hussein Ebaid  
**Email:** adhamebaid1@gmail.com 
## Description
This project undertakes a comprehensive exploratory data analysis (EDA) of hotel reservation data, focusing on understanding guest behavior, reservation trends, and the factors influencing cancellation rates. It aims to understand the underlying factors that could help anticipate a guest cancelling their reservation beforehand.
![JW Marriott Hotel Cairo](https://cache.marriott.com/content/dam/marriott-renditions/CAIJW/caijw-golf-0233-hor-feat.jpg?output-quality=70&interpolation=progressive-bilinear&downsize=1920px:* "JW Marriott Hotel Cairo")  
![Renaissance Hotel Cairo](https://cf.bstatic.com/xdata/images/hotel/max1024x768/470657601.jpg?k=b9b8d001aee86a4cf5213866e6b367992e98fa31532284356ec8815e3dde5fad&o=&hp=1* "Renaissance Hotel Cairo")

## Appendix

1. [Data Source](#data-source)
2. [Technologies](#technologies)
3. [Skills](#skills)
4. [About the Dataset](#about-the-dataset)
5. [Key Findings](#key-findings)  
    5.1 [Revenue Analysis and General Facts](#revenue-analysis-and-general-facts)  
    5.2 [Cancellation Relations and Trends](#cancellation-relations-and-trends)
6. [Predictive Models](#predictive-models) 
7. [Future Work](#future-work)


## Data Source
This project uses the "Egypt Hotel Bookings" Dataset From Kaggle 
https://www.kaggle.com/datasets/sarynasser/egypt-hotel-bookings


## Technologies
- Python  
- Pandas , NumPy
- Matplotlib
- Seaborn
- SQL , sqlite3
- Sklearn , Keras
## Skills
Python, Data Visualization, SQL , Machine Learning , Deep Learning, Data Analysis
## About The Dataset
This Dataset contains the data for around 200,000 diffrent Hotel Reservations/Bookings from 2017 to 2019 for the JW Marriott and the Renaissance Hotels in Egypt. Each entry has information like the date of the booking , lead time , customer type, distribution channel , the number of nights booked and wether the booking was cancelled or not.
## Key Findings
### Revenue Analysis and General Facts  
Summertime in Egypt is really special and vistors from all over the world come to Egypt to enjoy it's sunny beaches or the vibrant city life of Cairo. This is evident when analyzing the months with the most reservations across both hotels in this dataset.

![number-of-reservations-per-month](https://i.postimg.cc/85vvs37G/number-of-reservations-per-month.png "number-of-reservations-per-month")  
The month of August is by far the busiest month in the year.   
It is also the month where hotels make the most revenue (total revenue across both hotels)
| Month      | Total Revenue |
|------------|---------------|
| August     | 4,912,010.0   |
| July       | 3,746,992.0   |
| September  | 1,845,626.0   |
| June       | 1,695,346.0   |
| April      | 1,597,693.0   |
| May        | 1,240,437.0   |
| March      | 1,165,028.0   |
| October    | 1,118,890.0   |
| February   | 722,494.0     |
| December   | 721,252.0     |
| November   | 517,412.0     |
| January    | 461,566.0     |

But when anlyzing the revenue each hotel makes across each month we can see an intresting insight.  

![Average-Revenue-per-Month](https://i.postimg.cc/0jfbwqxT/Average-Revenue-per-Month.png"Average-Revenue-per-Month")  

While **Renaissance Hotel** is achieving fairly consistent revenue throughout the year with a slight peak during the summer , **JW Marriott Hotel** achieves margianlly higher revenue during the summer peaking during August. This may come down to various factors including Brand Perception, Facilities and Amenities & Marketing and Promotions.  

Analyzing the geographical distribution of the hotel's customer base particularly the top 10 nationalities with the most reservations we can see the following.  
| Country         | Number of Reservations |
|-----------------|------------------------|
| Portugal        | 22,759                 |
| United Kingdom  | 6,654                  |
| Spain           | 4,895                  |
| France          | 2,419                  |
| Ireland         | 2,221                  |
| Germany         | 1,637                  |
| Italy           | 1,019                  |
| China           | 724                    |
| Netherlands     | 624                    |
| Brazil          | 591                    |  

 The majority of the hotel's guests come from Portugal followed by The United Kingdom and Spain suggesting that the hotel is popular among travelers from these countries. This information could be used to tailor marketing strategies and services to these key markets to further boost reservations.  

 When Looking at the most popular Type of Meal booked for every customer type we observe the following:  

 | Customer Type     | Meal       | Frequency |
|-------------------|------------|-----------|
| Contract          | Self-Catering (SC) | 183       |
| Group             | Self-Catering (SC) | 38        |
| Transient         | Self-Catering (SC) | 9,928     |
| Transient-Party   | Self-Catering (SC) | 451       |  

There is a consensus on choosing **Self-Catring** as it is the most popular choice for all customer types largely due to it's low cost and high flexibility.
  

 ### Cancellation Relations and Trends  
 In todays world Hotel Cancellations have become a common occurence. Wether it's due to a change in travel plans or unforseen circumstances Hotel booking cancellations can lead to revenue loss. This project aim to analyze diffrent factors that could be related to Booking Cancellations and could help us understand more the reasons that might be behind such cancellations and hopefully forsee and prevent these cancellations.  
 Let's start by answering a simple question , **are people with a history of previous cancellations more likely to cancel an upcoming reservation?**  

 ![Cancellation_Rate_by_Previous_Cancellations](https://i.postimg.cc/c4LQBFjR/Cancellation-Rate-by-Previous-Cancellations-1.png"Cancellation_Rate_by_Previous_Cancellations")  
 As expected people who canceled a reseravtion before are much more likely to cancel another reservation  

 ![Cancellation_Rate_vs_Previous_Cancellations](https://i.postimg.cc/bJRtQn9V/Cancellation-Rate-by-Previous-Cancellations.png"Cancellation_Rate_vs_Previous_Cancellations")   
 Furthermore it appears that people who have cancelled 14 or more times before are almost certain to cancel their reservation again.   

   **Let's analyze more relations present in the data.**  

 ![Cancellation-Rate-by-Repeated-Guests-Vs-First-Time-Guests](https://i.postimg.cc/X7qCCpGx/Cancellation-Rate-by-Repeated-Guests-Vs-First-Time-Guests.png"Cancellation-Rate-by-Repeated-Guests-Vs-First-Time-Guests")  
 As evident by this chart , First time guests are more likely to cancel a reservation than repeated guests. This could be because repeated guests know the experience they are going to get and they liked it enough to book again making the likelyhood that the guest changes their mind last minute very little. 

   ![Cancellation-Rate-by-Customer-Type](https://i.postimg.cc/QCwx5Nwn/Cancellation-Rate-by-Customer-Type.png"Cancellation-Rate-by-Customer-Type")  
   We can see that **Transient** guests are the most likely to cancel a reservation. This could be due to the nature of their bookings, which are typically short-term and often made without solid plans.On the other hand, **Group** customers have the lowest cancellation rate. This could be attributed to the fact that group bookings are often planned and coordinated in advance, making them less likely to be cancelled. This insight suggests that the hotel could focus on strategies to reduce cancellations among **Transient** customers, such as offering flexible booking options. For **Group** customers, the hotel could offer benefits for early booking or long-term stays to maintain the low cancellation rate.

![Cancellation-Rate-by-Distribution-Channel](https://i.postimg.cc/g2NcqKCZ/Cancellation-Rate-by-Distribution-Channel.png"Cancellation-Rate-by-Distribution-Channel")  

Bookings made through **Travel Agents/Tour Operators** has the highest cancellation rate. This could be lack of direct communication between the hotel and the customer or the ease of cancellation provided by these platforms. On the other hand the **Direct** Distribution channel has the lowest cancellation rate as the direct interaction between the hotel and the customer allows for better understanding of the booking conditions and there is a bigger feeling of commitment when bookings are made directly with the hotel as opposed to bookings made through a third party. To reduce the cancellations made by guests who book through a **Travel Agents/Tour Operators** the hotel could work closely with these partners to ensure clear communication of booking conditions and cancellation policies to the customers.  

![Cancellation-Rate-by-Deposit-Type](https://i.postimg.cc/gkpGC5dh/Cancellation-Rate-by-Deposit-Type.png"Cancellation-Rate-by-Deposit-Type")  

There is a very strange pattern here were guests with deposit type **Non Refund** are the most likely to cancel. This seems very counter-intuitive and confusing but perhaps further investigation might reveal the reason behind this pattern.  
## Predictive Models  
Predecting Booking Cancellations is the main goal for this project so a handful of classification models were developed to see which one would produce the best results (Note Accuracy displayed is a 5-fold Cross-Validation Accuracy).

| Model Type                            | Accuracy (%) | Std Dev (%) |
|---------------------------------------|--------------|-------------|
| Logistic Regression                   | 77.61        | 0.21        |
| Decision Trees                        | 79.94        | 0.32        |
| **Random Forest**                         | **84.70**        | **0.15**        |
| K-Nearest Neighbors (KNN)            | 80.31        | 0.15        |
| Naive Bayes                           | 76.40        | 0.21        |
| XGBoost Classifier                              | 82.92        | 0.29        |
| Multi-Layer Perceptron (MLP) Neural  | 82.47        | 38.02       |

 The **Random Forest Classifier** is the best model as it achieves a 5-fold Cross-Validation Accuracy of about 84.70 % with a Standard Deviation of only 0.21 %.  

 ## Future Work
 This project provided a comprehensive analysis of hotel reservation data focusing on analyzing customer behavior and underlying patterns and trends relationg to booking cancellations.  
 There remains potential for further exploration and improvement. Future work could focus on several key areas:  
 - Discovering and analyzing more patterns and relations in the data. 
 - Further understanding the reason behind certain patterns and findings discussed above
 - Collecting more recent data from diffeent hotels and expanding the dataset. 
 - Improving the accuracy of the Classifier.  
 


