# Market Research
![](display.jpeg)
image [source](https://www.inventiva.co.in/trends/top-15-market-research-india/)
## A Competitive Analysis
In Nigeria, lending apps have become a popular choice for individuals in need of short-term loans. Two of such lenders are `Irorun` and `Urgent10k`, both of which offer similar financial products. In this assessment, I conducted a comparative analysis of `Irorun` and `Urgent10K` from the perspective of a typical Nigerian borrower. I gathered information about their loan products, fees, interest rates and other relevant details.

Furthermore, I extracted all customer reviews of both lenders from the Google play store and conducted sentiment analysis to gain insight into the perceptions of their customers. Based on this analysis, I have provided a comprehensive assessment of these lenders, including their strengths, weaknesses, and areas for improvement. The findings of this assessment can be useful for borrowers who are considering using these lenders and can provide insights for the lenders themselves to improve their service.

## OBJECTIVE
The objective of this research is to gain insights and knowledge that can guide decision-making related to product development, pricing, promotion, and distribution strategies. Market research helps businesses understand consumer preferences, market trends, and potential opportunities and risks, enabling them to make informed and data-driven decisions to effectively position and market their product.
 
## METHODOLOGY
To effectively achieve our business objectives, this assessment was conducted in two parts: an evaluation from the perspective of a typical Nigerian borrower and an assessment as a data Analyst. 

**As a typical Nigerian Borrower**, this aspect focuses on how potential customers perceive these products when encountering them for the first time through online resources such as their websites and app information. Here are the steps involved:

Step 1: Evaluate the websites of both lenders and gather information about their products.
Step 2: Review the app ratings and feedback on both Google Play Store and Apple App Store for both lenders.


## RESULTS AND DISCUSSION

Product             | Irorun  		        	| Urgent10k
--------------------|--------------------|------------------------
Loan amount         | #5000 – #50000     | #5000 - #100,000
Loan term           | 7 – 30 days        | Unknown
Interest rate       | 10% - 15%          | Unknown
Processing fee      | #400               | Unknown

Source: 
>Irorun.com & Urgent10k.ng

Based on the assessment, it was found that Irorun has a better user-friendly interface compared to Urgent10k. Their website is more informative and provides a comprehensive understanding of their products. Additionally, `Irorun` offers a loyalty program with zero interest, which promotes customer retention.

Google Play Store
Lenders         | Rating   | Reviews  | Downloads
--------------- |----------|----------|--------------
Irorun          | 3.6      | 2000     |  100k+
Urgent10k       | 3.8      | 445      |   50k +
 

Apple Store
Lenders         | Rating   | Reviews
--------------- |----------|------------
Irorun          | 3.5      | 331
Urgent10k       | 2.4      | 182


From the data, it can be observed that Urgent10k has a higher rating on Google Play Store but a significantly lower rating on the Apple App Store compared to Irorun. Irorun has a relatively lower rating on both platforms but has more reviews and higher downloads on Google Play Store, indicating a larger user base. It is important to consider both the ratings and the number of reviews to get a more comprehensive understanding of customer satisfaction and app popularity.

**As a Data Analyst**, the following steps were taken to analyze the customer reviews from Google Play Store for Irorun.ng and ng.urgent10k:

Step 1: Data Collection ([Web Scraping]( Webscraping_Googleplay_Customers_Reviews.ipynb))
Python code, including the Google Play Scraper library, was utilized to scrape all customer reviews from the Google Play Store. The targeted URLs for scraping were:
- For Irorun: [Irorun.ng](https://play.google.com/store/apps/details?id=com.irorun)
- For urgent10k: [ng.urgent10k](https://play.google.com/store/apps/details?id=ng.urgent10k)

Step 2: Exploratory Data Analysis (EDA)
The scraped customer reviews dataset was subjected to exploratory data analysis. Various analytical techniques were applied to gain insights into customers' experiences. This involved analyzing the text data, sentiment analysis, and extracting key themes or patterns from the reviews. EDA helped in understanding the strengths and weaknesses of both lenders based on customer feedback.

Step 3: Executive Recommendations
Based on the insights obtained from the EDA, executive recommendations were formulated. These recommendations are aimed at addressing the identified issues, improving customer experience, and maximizing the potential for business growth.

By following these steps, I was able to analyze the customer reviews from the Google Play Store for Irorun and urgent10k, gain valuable insights into customers' experiences, and provide executive recommendations for further improvement.

To view the code chunk used in web scraping, click [here]( Webscraping_Googleplay_Customers_Reviews.ipynb)  
The scrapped datasets can be found below
•	Urgent10k [dataset]( Urgent10k_scraped_reviews.csv)
•	Irorun [dataset]( Irorun_scraped_reviews.csv)

### Feature Information
- `reviewId`- Unique identification key per review
- `userName`- customer username
- `userImage`- customer display picture url
- `reviews`- customer review content
- `score`- customer star rating
- `thumbsUpCount`- total number of like per reviews
- `reviewCreatedVersion`- customer app version as of the time of review
- `at`- date and time review was created.
- `replyContent`- reply content per customer review
- `repliedAt`- date and time of reply content per customer review

### Data Manipulation \ Cleaning
-  converted `at` and `repliedAt` to datetime data type 

### Feature Engineering
-	Created a new feature `duration`, which is the difference between `repliedAt` and `at` (in days) 
-	Also created a new feature `year`, it consist of the year each review was created

### Assumption made
The main objective of a small short-term loan is to offer individuals fast access to emergency funds. Therefore, reviews or comments that remain unanswered for an extended period of time fail to meet customers' urgent needs.

To categorize the response times for reviews, the following labels can be applied:
1. `Duration` less than or equal to 2 days: These responses are considered as "early_reply" as they were provided within a reasonable timeframe.
2. `Duration` greater than 2 days: These responses are considered as "late_reply" since they took longer than the expected timeframe.
3. NaN values in the `repliedAt` column: These instances indicate that no reply was provided and can be labeled as "no_reply."

By categorizing the response times in this manner, it becomes easier to identify cases where customers' needs were not met promptly and areas for improvement in response time can be identified.

## RESULTS  AND DISCUSSION
Key findings from the [EDA of the Urgent10k](EDA_of_Urgent10k_Dataset.ipynb) dataset:

1. Dissatisfaction among customers: The top 7 most liked reviews, based on `thumbUpCount`, were all rated 1 star, indicating that a majority of customers were dissatisfied with their experience.

2. App rating trend: The Urgent10k app rating showed a gradual increase from 2021 to mid-2022, followed by a decline from 2022 to 2023. This suggests a shift in customer perception and satisfaction over time.

3. Response time: Statistically, there is a 30% chance of receiving an early reply (within <=2 days). This indicates that a significant portion of customers had to wait longer for a response.

4. No response and late replies: A high percentage of customer reviews did not receive any response, while a considerable number of reviews experienced late replies. This indicates a need for improvement in timely customer support.

Key findings from the [EDA of the Irorun](EDA_of_Irorun_Dataset.ipynb) dataset:

1. Positive customer feedback: The most liked comment, based on `thumbUpCount`, was rated 5 stars and contained commendations. This positive feedback inspired other customers and contributed to a favorable perception of the app.

2. App rating trend: The Irorun app rating showed a rapid increase from 2020 to early 2021, followed by a slight decline in momentum during 2021. However, the rating has been gradually rising since then, suggesting overall customer satisfaction and positive experiences.

3. Response time: Statistically, there is a 50% chance of receiving an early reply (within <=2 days). This indicates that the majority of customers received timely responses, which is a positive aspect of customer support.

These findings highlight the differing customer experiences and satisfaction levels between Urgent10k and Irorun. Urgent10k had a higher proportion of dissatisfied customers, longer response times, and a higher percentage of no responses or late replies. On the other hand, Irorun received positive customer feedback, shorter response times, and a higher chance of receiving early replies. These insights can inform the respective companies' strategies for improving customer satisfaction and response times.

To view the python code used for Exploratory Data Analysis for:
-	Irorun click [here](EDA_of_Irorun_Dataset.ipynb)
-	Urgent10k click [here](EDA_of_Urgent10k_Dataset.ipynb)

# RECOMMENDATIONS
•	Increase Transparency: As "scam" is in the top 20 frequent words, it suggests that some customers may feel that they are being deceived by the lending apps. Both Irorun and Urgent10k should ensure that all terms and conditions are clear and transparent, and that customers are aware of all fees and charges associated with their loans. In addition, assure the customers that their personal data and card details are secured.
•	Enhance Customer Service: customers value good customer service. Irorun and Urgent10k should prioritize responding promptly to customer inquiries and complaints and provide excellent service to improve customer satisfaction.
•	Improve the App: As "app" is the most frequent word, it indicates that most customers are interacting with the app frequently. To ensure customer satisfaction, Irorun and Urgent10k should prioritize improving the user interface, fixing bugs, and adding new features.

>To view the PowerPoint recommendations, click [here]( Market_Research_Report.pptx)

## Limitation | Challenges
Web scraping of customers’ reviews from Apple store was limited to ten reviews. Hence, no further analysis was conducted using data from Apple App Store reviews. This limitation restricted the depth of analysis and insights that could be derived from the Apple Store reviews.



