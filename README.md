<h2 style='text-align: center; font-size: 40px;'> Churn Analysis </h2>

<font size="5">**Authors**</font>
* Navya Chalamalasetty 
* Saketh Reddy Dodda
* Pavan Kumar Malasani 
* Kundan Sai Chowdary Sannapaneni
* Sai Preetham Vinnakota

<h2 style="margin-bottom: 20px;">Introduction</h2>

<div style="text-align: justify">
Customer churn is an important business indicator, especially in industries where it is more expensive to acquire new customers than it is to retain existing ones.It simply measures the loss of customers, which can occur for a number of reasons, from dissatisfaction with services to better deals from competitors. In the era of digital transformation, when customer preferences and choices are constantly changing, businesses need to be more adaptive and attentive to these changes.They run the danger of seeing their churn rate rise if they don't. Churn not only affects the company's financial performance, but it may also be a sign of more serious problems with the company's business strategy, customer support, or product line.
</div>

<h2 style="margin-bottom: 20px;">Goal</h2>

<div style="text-align: justify">
Perform a thorough analysis of our current customer dataset to identify the main factors causing churn. By identifying these patterns and contributing causes, we hope to get actionable insights that will guide and improve our customer retention tactics, resulting in increased customer satisfaction and a decrease in the churn rate in subsequent quarters.
</div>

<h2 style="margin-bottom: 20px;">About Dataset</h2>


**Link to Data Set:** https://huggingface.co/datasets/scikit-learn/churn-prediction 

<div style="text-align: justify">
The data meticulously describes the demographics, chosen services, and billing patterns of 7043 customers, illuminating their nuanced interactions with a telecommunications entity. Its central component is the Churn column, which identifies clients who have chosen to leave or remain. A balanced gender representation, a sizeable senior citizen population, and a range of service preferences for PhoneService, InternetService, and related offerings are among the key characteristics. The data is also further enhanced by financial touchpoints like MonthlyCharges and contractual commitments, as shown by the types and duration of contracts. Through the prism of this thorough tableau, we can understand the underlying drivers of a customer's loyalty or choice to depart.
</div>

* Churn is the name of the column that lists customers who have left in the past month.
* Services that each customer has signed up for: a phone, multiple lines, an internet connection, online backup and security, device protection, tech support, and on-demand TV and movie streaming.
* Customer account information: the duration of their contract, payment method, paperless billing, monthly charges, and overall charges.
* Demographic info about customers: Gender, age range, and whether they are married or have children.


## Potential Sources of Bias in the Data Set

1. **Representation Bias**:
   - Underrepresentation of some customer demographics, such as those without phone service.
   - About 70% of customers are single, which may not accurately reflect the customer base.
   
2. **Data Quality Bias**:
   - "TotalCharges" column contains 11 empty strings in place of missing data, which may induce bias if the missingness is not random.

3. **Outcome Bias**:
   - Features like "MonthlyCharges," "PaperlessBilling," and "SeniorCitizen" are significantly correlated with churn. Models trained on this dataset may inherit any inherent biases in these features.

To achieve a more balanced and representative sample, addressing these biases necessitates domain expertise and perhaps extra data.

## Understanding and Cleaning of Data

<div style="text-align: justify">
The data is then organized into groups according to the <code>InternetService (DSL or Fiber optic)</code> type and further divided according to the <code>res</code> (Above created Data Frame for visulation) values. The distribution of positive comments for each internet service type is shown by this aggregated data, which is kept as counts.</div> <br>

<div style="text-align: justify">
To illustrate the distribution of responses for each internet service, a horizontal stacked bar chart is plotted as a final step. Based on the customer's choice of internet service, this visualization helps to understand how engaged they are with the company's services.
</div> <br>

<div style="text-align: justify">A stacked bar plot was chosen for this insight because it provides both a broad and segmented view. It layers categories, like <code>res</code> values, within more inclusive groups, like <code>InternetService</code>, making it easier to make direct comparisons. This structure highlights differences in positive responses across service types and clarifies individual and combined totals. Its small size and adaptable construction also allow for future analyses' potential expansions.</div>


<div style="text-align: justify">
From the visualized data, we can see from the data that the churn rates for male and female customers are essentially the same, with a few minor exceptions. Customers who did not churn are slightly more likely to exist in both genders than those who did. The visualization's color choices—red and blue for male customers, and gold and lime green for female customers—clearly separate the two sexes, making comparisons between the two groups simpler. By displaying the churn and retention rates side by side, the overlapping donut structure further enables a concise yet detailed representation. Businesses can better understand customer behavior patterns across demographics with the help of this type of visualization, which in this instance focuses on gender. </div>

<div style="text-align: justify">From the stacked bar chart visualization of customer churn across various monthly charge ranges, it's clear that there are differences in the levels of customer retention and churn in each charge bracket. The graph provides a thorough overview of the factors that might affect a customer's choice to keep or stop using a service on a monthly basis. It would indicate that price sensitivity plays a role in customer retention if, for example, higher monthly charge brackets consistently showed a more significant proportion of churn. On the other hand, if churn is consistent across all charge brackets, it may be due to other factors. The visualization highlights the value of comprehending customer behavior within various pricing segments, enabling businesses to adjust their strategies, whether through price changes, targeted offers, or improved services, to address specific pain points and enhance customer loyalty.</div> <br>

<div style="text-align: justify">This data is best visualized using a stacked bar chart because it makes it possible to compare two related parts of a whole (in this case, churned vs. non-churned customers) for each category (the monthly charge ranges). By stacking the bars, we can determine the proportion of churned customers versus non-churned customers, as well as the total number of customers in each monthly charge range. When it's important to comprehend both the relative distributions within each category as well as the absolute counts for each, this visualization is especially helpful. Understanding how churn behavior varies across various monthly charge ranges for the dataset in question can offer insights into pricing strategies and customer retention initiatives.</div>

<div style="text-align: justify">Insightful trends can be seen in the pie charts showing the distribution of churn over various contract lengths. Customers on month-to-month contracts experience the highest customer churn, indicating that the short-term nature of these contracts makes it simpler for customers to leave. On the other hand, individuals with one-year contracts exhibit a moderate rate of churn, indicating a reasonable level of satisfaction and commitment. Most significantly, two-year contracts, which have the lowest churn rate, show a strong sense of customer loyalty, perhaps motivated by the value or benefits they receive. Collectively, these findings highlight the importance of fostering long-term relationships with clients in order to increase retention.</div>

<div style="text-align: justify">Several conclusions can be drawn from the stacked bar chart showing the churn rates for senior citizens and non-senior citizens. Notably, compared to their younger counterparts, seniors show a significantly higher tendency to churn. While almost half (46.15%) of senior citizens chose to churn, only about a quarter (27.52%) of non-senior citizens did the same. This significant difference suggests that factors affecting customer retention may differ between these demographic groups. To improve their retention rates, service providers may need to use different tactics or provide customized services to address the special preferences and needs of senior citizens.</div>

## Detailed Analysis

<div style="text-align: justify">In this comprehensive analysis, we examine patterns of customer churn, looking at how tenure and service subscriptions affect retention. By examining the tenure distribution against churn rates and assessing the impact of key add-on services, we unveil pivotal insights that shed light on customer behavior and the underlying factors driving their loyalty.</div>

**The Significance of Tenure in Churn Dynamics:**<br></br>

<div style="text-align: justify">The relationship between tenure distribution and churn reveals a compelling story about consumer behavior. An important finding is that there is a noticeable churn rate in the first few months of a customer's engagement with the service. This early departure can be explained by a number of reasonable factors. The expectations that new customers have when using a service are frequently influenced by marketing initiatives, word-of-mouth recommendations, or personal aspirations. If the initial customer service experience falls short of these expectations, it may cause disillusionment and subsequent churn. Additionally, customers who are just beginning to use a service may still be evaluating it and contrasting its offerings with those of other providers. A more attractive proposition from a competitor, be it in terms of pricing, features, or quality, might lure them away. The absence of effective engagement strategies, like onboarding processes or introductory promotions, can further exacerbate this early churn. Customers who have been a part of a business for a long time, however, tend to be loyal. They frequently become more accustomed to the service as they use it more frequently, personalizing it to their preferences, devoting time and occasionally additional resources, and figuring out its quirks. They frequently develop a sense of attachment as a result of this familiarity, which reduces their likelihood of jumping ship.</div>

**The Role of Add-On Services in Shaping Customer Loyalty:**<br></br>

<div style="text-align: justify">Insights into a customer's priorities and level of satisfaction can be gained by looking more closely at the services they subscribe to. Two stand out among the many services because of their notable effects on client retention: Technical assistance and online security. There is no denying the allure of online safety. The importance of protecting one's data and online activities grows in a world that is becoming more and more digital. Customers who subscribe to online security services can feel secure knowing that potential threats to their digital footprint are prevented. This not only increases the perceived usefulness of the service but also fosters trust. The availability of technical support also becomes apparent as a key element in customer satisfaction. Regardless of how well a service is done, problems will always arise. The availability of quick and helpful tech support in these circumstances can mean the difference between a minor irritation and a deal-breaker. By ensuring that customers spend as little time wrangling with problems as possible, it promotes a seamless experience. For entertainment services like streaming TV and streaming movies, it is impossible to make the same claim. Despite being well-liked, they don't appear to anchor clients in the same way. Similar content is available on numerous platforms, which reduces its exclusivity and appeal.</div>

## Conclusion

<div style="text-align: justify">In our in-depth analysis of customer churn patterns, we've highlighted the profound impact of tenure and service type on customer retention. Early tenure was found to be a vulnerable time, with a sizeable percentage of customers quitting in the first few months, perhaps as a result of unmet expectations or the allure of rivals. The importance of encouraging early engagement to improve retention, on the other hand, was suggested by the stronger loyalty long-term customers showed to the service. When examining service subscriptions, it became clear that Online Security's protective barrier and Tech Support's safety net were crucial in promoting client loyalty. Although they were very popular, entertainment-focused services didn't anchor users in the same way, indicating that this type of content is available on many different platforms. Additional factors included payment methods, with electronic checks showing a concerning correlation with higher churn rates. Despite the fact that the data offered priceless insights, it's critical to be aware of any potential biases that might affect the outcome. The company may be able to increase retention and improve customer satisfaction by addressing early customer engagement, emphasizing core services, and streamlining payment procedures.</div>

