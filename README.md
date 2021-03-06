# Credit_Card__User_Segmentation

## Background
I am a data scientist at a credit card company whose current objective is to reduce costs associated with signup incentives by carefully targeting benefits that will attract new cardholders.
## Tasks:
* Examine 6 months of cardhoulder data to understand the types of uses
* Which benefits are most relevant to each new card offering (user segment)

## Data: 
Cardholder data collected over the last 6 months. Especially interested in getting an idea of which benefits to associate with each new card offering.

## Metric:
* New cardholder signups
* Downstream, the company makes money off of the interest paid on the balance
* To maximize revenue, encourage behavior that results in large month-to-month balances

## EDA (Exploratory Data Analysis)
* Descriptive statistics
* Check for data type
* Check for missing or duplicated data
* Vasulize data
![vasulize data](https://github.com/stemgene/Credit_Card__User_Segmentation/blob/main/imgs/visualize_data.png)
* Shapiro-Wilk Test for normality on original data
* Unskew data

## K-Means Clustering
### Determine k using the elbow method
k = 5 appears to be optimum
![elbow](https://github.com/stemgene/Credit_Card__User_Segmentation/blob/main/imgs/elbow.png)
### Run Kmeans for Tenure
![kmeans](https://github.com/stemgene/Credit_Card__User_Segmentation/blob/main/imgs/kmeans.png)

### Assign cluster number to the original dataset

### RFM-type categorization by equal binning on K-Means Clusters
Assign meaningful values to the clusters

## Agglomerative hierarchical clustering
![Dendrogram](https://github.com/stemgene/Credit_Card__User_Segmentation/blob/main/imgs/dendrogram.png)
### RFM-type categorization by equal binning on hierarchical clusters

## Output
* User segments, each with a target benefit to maximize new cardholder signups
* Any promotions to acquire new cardholders need to be profitable and sustainable
  * I want to target customer segments and discourage those customers who would prove to be less valuable
  * A program that is 'self-selecting' and 'individually correcting'.
  * Does the program align with company capabilities?
  * Will customers value the program?
  * Can competitors offer a more desirable alternative? Would partnering make the program more competitive?
  * Should take into account cash value, choice of redemption options, aspirational value, relevance, convenience
  * Motivate customers to consolidate all their spending onto a single card.
* Avoid promotions with only short-term benefits
  * Startup bonuses which encourage 'chronic switcher' behavior
  * "Miles" programs that cost the company to acquire a bank of "miles" from other companies (airlines)
  * One-time promotions increase signups but not loyalty once the promotional period is over
  * Lotteries and "chances to win"

## Customer Segments

![customer segments](https://github.com/stemgene/Credit_Card__User_Segmentation/blob/main/imgs/user_seg.png)

### Average user - Target with simplicity and transparency in fees, rates, and terms.
* Type 1 - Many one-off purchases
* Type 2 - multiple purchases per transaction
* High credit limit
* Multiple minimum payments
* Does not take out cash advances often
* Average purchase value
* Carries an average daily balance

### Responsible high-volume user - Target with premium network incentives, no foreign transaction fees, low APR
* Mostly one-off and multiple purchases with high value
* Carries a high balance and has a high credit limit
* Responsible for multiple minimum payments but is good at paying them off monthly.
* Occasionally takes out cash advances

### Responsible everyday user - Target with simplicity and transparency in fees, rates, and terms.
* Makes moderate to high value purchases with multiple purchases per transaction
* Occasionally takes out cash advances
* Has an average credit limit with few minimum payments
* Carries a relatively low balance but is not always good at paying the full amount each month

### High volume, Financially Stressed user - Target with simplicity and transparency in fees, rates, and terms, rewards for responsible spending.
* High frequency user that makes high-value purchases frequently, both as single and multiple purchases per transaction
* Maintains a high balance but with many minimum payments
* Average credit limit
* Does not always pay the full balance

### Inactive user - Target with low (or no) balance transfer fees. Avoid sign-on bonuses.
* Carries a high balance with multiple minimum payments
* Not likely to take out cash advances
* Makes few purchases of any value or type
* Not likely to pay the full balance each month

### Cash advancer - Target with low APR, the same APR for cash advances as purchases, and no fees for cash advances.
* More likely to make cash advances than purchases
* Carries a very low balance, if any
* Makes small-to-moderate value purchases with multiple purchases per transaction
* Is not likely to pay the balance in full each month

## Summary and Actionable Insights
Based on information from the Harvard Business Review and McKinsey Financial Services, these customer segments above align with standard credit card customer segments with well-documented behaviors, including response to incentives.
* Average Users are most similar to the established "Self-Aware Avoiders" category of cardholder. They tend to avoid using credit cards, but still carry a moderate-to-high balance and are not likely to pay it off every month. They respond well to simplicity and transparency in fees, rates, and terms. They tend to use credit cards for short-term borrowing and respond well when they see the payoff horizon for major purchases, for example, cards that instantly calculate the scale and duration of monthly payments for a given purchase at the point of sale.

* Target the Responsible High-Value user by offering convenience, premium network incentives through partner businesses and services, no foreign transaction fee, and low interest rates. They are willing to pay annual fees if they find the added convenience or status worthwhile.

* The High Volume, Finanacially Stressed user is likely either a spendthrift or in a situation that requires credit card borrowing to pay for essentials. They value simplicity and transparency in fees, rates, and terms. McKinsey suggests a new type of reward for this group, rewards for imposing spending limits. This would encourage one-off purchase behavior rather than multiple, higher-value purchases so that they can pay down their debt.

* Target Inactive users carefully. If they carry a high balance without making purchases, they could be a "deal chaser" that moves their balances to take advantage of the best transfer rates for their existing balances without making new purchases. For these, make sure they feel they are getting the best deal. Alternatively, they could be recovering credit and paying down past expenditures, in which case, they are not likely to make purchases or cash advances. Big signup bonuses should be avoided** because they are not likely to spend the bonus using the new card, but low balance transfer rates would be attractive.

* Target the cash advancer with promotions offering no cash advance fees, low APR, the same APR for cash advances as for purchases.
