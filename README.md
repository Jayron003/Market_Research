# Market Research
## A Competitive Analysis of Two Financial Products
In Nigeria, lending apps have become a popular choice for individuals in need of short-term loans. Two of such lenders are `Irorun` and `Urgent10k`, both of which offer similar financial products. In this assessment, I conducted a comparative analysis of `Irorun` and `Urgent10K` from the perspective of a typical Nigerian borrower. I gathered information about their loan products, fees, interest rates and other relevant details.
Furthermore, I extracted all customer reviews of both lenders from the Google play store and conducted sentiment analysis to gain insight into the perceptions of their customers. Based on this analysis, I have provided a comprehensive assessment of these lenders, including their strengths, weaknesses, and areas for improvement. The findings of this assessment can be useful for borrowers who are considering using these lenders and can provide insights for the lenders themselves to improve their service.

## OBJECTIVE
The objective of this research is to gain insights and knowledge that can guide decision-making related to product development, pricing, promotion, and distribution strategies. Market research helps businesses understand consumer preferences, market trends, and potential opportunities and risks, enabling them to make informed and data-driven decisions to effectively position and market their product.
 
## METHODOLOGY
In order to successfully meet our business objectives, this assessment was conducted in two part; assessment from the view of typical Nigerian and assessment as Data Analyst

* As a typical Nigerian Borrower:
This aspect simply shows how potential customers view these products for the first time from available online resource such their websites and their apps information.
Step1: Assess the websites of both lenders, and gather their product information.
Step2: Skim through both lenders’ app reviews both on Google playstore and Apple store

### Results

Product                | Irorun  			| Urgent10k
--------------------  |-----------------------|------------------------
Loan amount       | #5000 – #50000    | #5000 - #100,000
Loan term            | 7 – 30 days           | Unknown
Interest rate         | 10% - 15%            | Unknown
Processing fee     | #400                      | Unknown
Sources: Irorun.com and Urgent10k.ng

`Irorun` had a better user friendly interface, their website is more informative than `Urgent10k` and `Irorun` offers loyalty program with zero interest, which promotes customers retention.

Google Play Store
Lenders         | Rating   | Reviews  | Downloads
--------------- |------------|-------------|--------------
Irorun           | 3.6         | 2000         |  100k+
Urgent10k    | 3.8         | 445           |   50k +
 

Apple Store
Lenders         | Rating   | Reviews
--------------- |------------|------------
Irorun           | 3.5         | 331
Urgent10k    | 2.4         | 182



* Data Analyst
Step1: Web scrape all customer reviews from Google playstore
Step2: Conduct Exploratory Data Analysis and gather insight of their customer’s experience
Step3: Provide executive recommendations based on insight obtained. 

### Data Set Information
The data sets was collected using python codes, google_play_scrapper and other libraries to web scrape customer reviews from Google play store. Google url used:
>irorun.ng
>ng.urgent10k

To view the code chunk used in web scraping, click [here]()  

Urgent10k [dataset]()
Irorun [dataset]()

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

### Assumption
The main purpose of a small short-term loan is to provide individuals with quick loan for emergency. Hence, review\comment without a response at the earliest time possible fails to meet customers at their need.
* all `duration` greater than 2 days are considered as `late_reply`
* all `duration` less than equal to 2 days are considered as `early_reply`
* all NaN `repliedAt` are labeled `no_reply`

Summary of Key Findings from EDA of `Urgent10k` dataset
-	We closely examined the most liked reviews `thumbUpCount`, this information gave us insight about reviews which most customers agreed with or had similar experience. We observed that the tops 7 most liked reviews were rated 1 star, which suggests that most customers were dissatisfied. 
-	there was a gradual raise in `urgent10k` app rating from 2021 to till mid-2022 and a decline commenced from 2022 to 2023
-	Statistically, there is a 30% chance of getting an early reply (reply within <=2 days).
-	A high percentage of customer reviews got no response, and a good number had late replies.

Summary of Key Findings from EDA of `Irorun` dataset
-	At a close examination of most liked review `thumbUpCount`, we observed that the most like comment was rated 5 star and it content were commending, thus, inspiring other customers.
-	there was a rapid increase in `Irorun` app rating from 2020 to early 2021, it lost the momentum in 2021 and it has been gradually raising till 2023.
-	Statistically, there is a 50% chance of getting an early reply (reply with <=2 days).
-	A higher percentage of custom




To view the executive recommendations, click [here]()



## Limitation | Challenges
Web scraping of customers’ reviews from Apple store was limited to ten reviews. Hence, no deep analysis was conducted using data from Apple store reviews.
