# Sensors User Log Data Analysis
> Objective: Understand why users did not convert and how to opitmize the funnel flow to increase conversion rate

## Analysis Structure
1. Understand Rows & Columns
2. Data Processing
3. EDA
4. Baseline Model & Inference
5. Feature Engineering & Refined Model
6. Finding & Summary

## Analysis Details

### 1. Understand Rows & Columns

* Identify number of unique users
* Identify types of events
* Find missing values and why they are missing


### 2. Data Processing

* Upack JSON dictionary
* Filter out irrelevant users for unbiased analysis
* Generate two tables (event-level based & user-level based)

### 3. EDA

* Generate questions and use data to answer them
	1. What is average users activity level?
		> Most of users has around **lower than 5 events** with the website
	2. In which page did user click the request button for demo?
		> Most of people who click the button for demo in **landing page**. Some of them click the button on demo page.
	3. How long does the user take to convert?
		> The plot shows that most of the users click the submit button after first visit in **around 1-4 minutes**. Did they actually look into the about, demo, video pages? Or they just request demo without reading information
	4. Find conversion rate and visualize the funnel for conversion.
		> Out of all users who view the page, only 20% of them click the request button for demo, and **only 5% users** who decide to sign up for demo.
	5. Do mobile users have lower conversion rate than pc users?
		> Most of users who are using PC or laptop tend to be more likely to sign up for demo.
	6. Is referrer source helpful?
		> **Baidu** appears to be the reference soruce that has the highest conversion rate.
	7. If user interact with website more times, more likely to sign up.
		> Prior to conversion, a significant amount of users interact with product, b-round, demo and manual pages. **40% of user who convert see the demo page**. However, in the population, only 15% user see the demo page. We probably need to think about expose our demo page to the users to increase the chance of converting.

### 4. Baseline Model & Inference

* Logitstic Regression model with limited amount of features (around 4)
* Logistic Regression model with more features (around 15)
* Logistic Regression model with bootstrap sampling technique to control class balance
* Random Forest model for better performance

### 5. Feature Engineering & Refined Model

* Extensive Feature Engineering
* Refined Random Forest Model

### 6. Finding & Summary

* Findings:
	1. Compare to user activity information, the Effect of Reference Source, Mobile, Browser is pretty minimal
	2. Most of users who converted spend reasonable time between pages 8 - 20 seconds per page
	3. People who viewed demo page are more likely to be converted
	4. Almost 50% people who converted, directly clicked the request button for demo request on the landing page without exploring other pages.
	5. The lifetime for most converted users is around 2 minutes.
	6. Around 100+ churn users has very low value in effective btn click feature.


* Recommendations:
	1. We may need to find a better way to do the marketing strategies. From the finding, **we did not see difference among marketing campaign** in terms of conversion performance. The likehood of conversion is highly depend on users' interaction with the website.
	2. Optimize the content of the web page. Control the reading time in **8 - 20 seconds** per page range.
	3. **Made the demo page button standout** in the landing page so that user are more likely to view the demo page because people who virewed the demo page are more likely to convert.
	4. 50% of converted users submit demo request directly from the landing page. This means that landing page is attractive enough for user to click the convert button. However, a considerable amount of users who did not request demo on the landing page. This might due to the fact that they need more information about the product. Therefore, we still need to **optimize other pages to provide additional information**.
	5. We need to made our **website easier to interact and faster to response**.
	6. Low value in effective btn click feature indicates that these users are **experiencing response lantancy** from the website. So we need to do some adjsutment on the server sides to optimize user experience.
