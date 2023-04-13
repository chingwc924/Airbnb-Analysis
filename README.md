# Airbnb Analysis
## Project Introduction
This is a randomized experiment to evaluate the impact of Airbnb’s Plus certification program on user behavio. By doing so, the team can test the effectiveness of the program and optimize the platform to better meet customer needs. Compared to scraping data, a randomized experiment is the gold standard for evaluating interventions. It eliminates bias and helps identify causal effects. It also allows for the control of confounding factors that may influence user behavior, and provides more detailed data on user behavior, including willingness-to-pay and decision-making processes. In conclusion, while scraping data may offer some insights into user behavior, a randomized experiment is a more rigorous and controlled approach for evaluating the impact of the Plus certification program on user behavior.
## Descriptive Analysis
•	In this data set, we have 8880 observations and 8 columns in total

<img width="468" alt="image" src="https://user-images.githubusercontent.com/129904878/231899402-50de6032-4769-4099-a7bf-665cf27a0b82.png">

•	In the overall summary of the dataset, we can take a closer look of the “Price”. The average WIP is $212.4. The minimum WIP is $95, and the maximum is $399. As for the quartile, Q1 is $178, Q2 (median) is $209, and Q3 is $243.5. Besides, range of “Rank” is from 1 to 40. Since other variables are either binary or ordinal, the statistics provided in the chunk don’t appropriately to those variables.

<img width="439" alt="image" src="https://user-images.githubusercontent.com/129904878/231899535-328a3dbb-aa1d-4114-9e61-821d928e1423.png">

•	For “Listing_ID” and “Userid”, there are 47 unique housing and 222 unique users in the experiment.

<img width="463" alt="image" src="https://user-images.githubusercontent.com/129904878/231899567-1ec1a1d8-aa70-4939-ba27-cab5053ed540.png">

•	For “Program”, there are 88 students from the MBA and 134 students from the MSBA.

<img width="473" alt="image" src="https://user-images.githubusercontent.com/129904878/231899604-59c59f16-7a94-4e7d-8563-9c179fb3ff4e.png">

•	For the binary variable “Plus”, randomly assigned 40 out of 47 unique housings to each user, there are 777 housings listed in the Plus Badge, which is 8.75%, matching with the experiment setting of 9%.

<img width="468" alt="image" src="https://user-images.githubusercontent.com/129904878/231899717-0406cc61-8e3a-4560-a4c3-f86b117dd974.png">

•	For the binary variable “Booked”, there are 222 housings successfully got booked, which is 2.5% overall booking rate.

<img width="468" alt="image" src="https://user-images.githubusercontent.com/129904878/231899750-cadb5c94-8ce6-42c1-a35c-6bb99bc562b7.png">

•	For “Price”, we can see from both graphs that group_noplus has a more concentrate price range than group_plus. Both groups have close mean price. Besides, there’s one possible outlier in the group_noplus.

<img width="229" alt="image" src="https://user-images.githubusercontent.com/129904878/231899816-d909017c-5a93-4a22-9341-7763521f37d2.png">
<img width="228" alt="image" src="https://user-images.githubusercontent.com/129904878/231899856-b83d9862-42c8-43b2-aaf0-1adc27c4a3ac.png">

## Exploratory Data Analysis
Before aggregating any data, we can take a look of the correlation of each variable. We can’t see obvious relationship in the graph. However, there are two highlighted parts in it. First, “Booked” and “Plus” have a slightly positive relationship. Second, “Price” and “Rank” have a negative correlation. Both findings can be used for the further analysis.

<img width="178" alt="image" src="https://user-images.githubusercontent.com/129904878/231900129-53f4e5a8-0f50-4d20-8cf9-61b8695ef352.png">

•	To analyze the effect for Plus on Booked, I used the Pearson’s Chi-Squared to test whether there’s significant association between two variables. Here’s the hypotheses:

***H0: there's no significant association between the two binary variables 'Plus' and 'Booked'***

***Ha: there is a significant association between these variables.***

<img width="430" alt="image" src="https://user-images.githubusercontent.com/129904878/231900305-b433a488-6d8f-43c5-af4f-14bafc2379c8.png">

The result rejects H0, meaning that there’s a significant association between two variables. Following is the visualization of booking rate in terms of receiving the Plus Badge or not.

As we can see in the graph, the booking rate of having the Plus is 1.3% higher than without the Plus. With both statically and visually evidence, the Plus Badge does help to improve the booking rate in Airbnb.

<img width="438" alt="image" src="https://user-images.githubusercontent.com/129904878/231900346-4717c259-be4a-4d3c-bec0-baf0dcb01593.png">

•	To analyze the effect for Price on Booked, I used the Welch two sample t-test to test whether there’s significant association between two variables. Here’s the hypotheses:

***H0: The mean of the Price of No-Booked = The mean of the Price Booked***

***Ha: The mean of the Price of No-Booked != The mean of the Price Booked***

<img width="442" alt="image" src="https://user-images.githubusercontent.com/129904878/231900430-5a094701-633b-4322-a470-c97cbefeff5b.png">

The result rejects H0, meaning that there's a significant association between two variables. Following is the visualization of mean Price in terms of booking the room or not.

As we can see in the first graph, the mean Price of booking is $4 lower than not booking the room. We can imply that pricing affects people's final choice of booking a room or not. The lower the price, the more likely to book the room. 

<img width="329" alt="image" src="https://user-images.githubusercontent.com/129904878/231900481-6a130d80-c729-4856-a1be-8b3b418f7759.png">

To further strengthen our thought of the price, I separate the housing based on the price to see the difference between each group. As you can see in the second graph, group 1 (94~178) has the highest booking rate, suggesting that people do take price as one of the factor when booking a room on the Airbnb.

<img width="345" alt="image" src="https://user-images.githubusercontent.com/129904878/231900519-0c3747c8-5ed5-453d-8092-a17f1d01b87b.png">

What we can learn from the third graph is that even group 4 has the highest price among all groups, having a plus or not will somehow elevate the booking rate, strengthening our first analysis that having a plus badge will have a positive effect on booking.

<img width="327" alt="image" src="https://user-images.githubusercontent.com/129904878/231900567-aa60b518-a32b-4315-80fd-47aae2ce37c9.png">

As we look at the last graph of this section, for those housings are not chosen, the mean price has no obvious difference from having a Plus or not. However, the interesting part is that the price of gap of booking a room between having a Plus or not is $13.13, suggesting that hosts with a Plus Badge are willing to offer their properties at a lower price than hosts without a Plus Badge.

There could be a few possible reasons for this. One possibility is that hosts with a Plus Badge may be trying to compensate for any perceived disadvantage or stigma associated with their properties, and thus may be willing to offer them at a lower price. Alternatively, hosts with a Plus Badge may be more price-sensitive or focused on providing value to renters and may be more willing to set a lower price point in order to attract renters.

<img width="327" alt="image" src="https://user-images.githubusercontent.com/129904878/231900599-7399be01-085e-4670-9d9b-06b6a0a173ad.png">

•	To analyze the effect for Rank on Booked, I used the Wilcoxon rank sum test to test whether there's significant association between two variables. Here's the hypotheses:

***H0: there's no significant association between the two binary variables 'Rank' and 'Booked'***

***Ha: there is a significant association between these variables.***

<img width="468" alt="image" src="https://user-images.githubusercontent.com/129904878/231900651-ce2029c0-14dd-4d1a-b642-0499b5346348.png">

The result rejects H0, meaning that there's a significant association between two variables. Following is the visualization of booking rate in terms of each rank.

As we can see in the first graph, the booking is highly concentrated within top 20, with rank 8 has the highest booking rate. One thing we can notice is that rank 29 has the second highest booking rate, which is quite unusual because people usually prefer things with higher ranking. Thus, I do an analysis on the price by each rank to see if there's any clue explaining the situation.

<img width="328" alt="image" src="https://user-images.githubusercontent.com/129904878/231900703-cba73c0a-02f1-4c21-baa7-9ed6ff65fc89.png">

From the second graph, we can see that rank 49 has the lowest average price, aligning with our previous thought that lower price leads to a higher booking rate. Since all participants in the experiment are students who are more sensitive to the price, making it a more affordable option for those on a budget. This could make it a popular choice for people looking for a bargain.

<img width="352" alt="image" src="https://user-images.githubusercontent.com/129904878/231900739-9324a8ce-7874-4754-b405-6fb34df59bbe.png">

## Logistic Regression
Through the application of logistic regression analysis, we can see every independent variable is significant. Receiving a Plus Badge will have a positive effect on the booking. However, if one's price and rank increase, they will decrease the booking.

<img width="470" alt="image" src="https://user-images.githubusercontent.com/129904878/231900791-5389b2ec-f1cc-4f06-811c-f783480b918a.png">

In a logistic regression the response being modeled is the log(odds) that Y = 1 (Booked the room).
•	Plus: The odds of booking a room will increase by around 53.7% (exp of 0.43) if the room received a Plus Badge.
•	lnPrice: 1% increase in Price is associated with a 1.12% decrease in odds
•	lnRank: 1% increase in Rank is associated with a 0.21% decrease in odds

<img width="468" alt="image" src="https://user-images.githubusercontent.com/129904878/231900820-3c4722f8-c3fd-4708-a59c-e0454638dad4.png">

Holding other variables consistent, getting a Plus Badge increases the probability of booking by 0.12%.

<img width="444" alt="image" src="https://user-images.githubusercontent.com/129904878/231900844-f28f2fe5-48fa-47bc-9b63-d33eb8cf9c75.png">

## Conclusion
The results of the experiment suggest that price does have an important impact on booking at every stage of the analysis. In addition, the Plus Program was found to be a crucial factor in the decision-making process when booking higher-priced housing. Overall, the Plus Program had a positive effect on the booking rate, indicating that it may be a valuable feature for Airbnb hosts to consider when looking to increase their bookings. These findings provide important insights for both Airbnb hosts and users, and highlight the benefits of using randomized experiments to understand the causal relationships between different factors in the platform.






