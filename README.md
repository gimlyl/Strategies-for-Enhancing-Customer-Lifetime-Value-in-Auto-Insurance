# Strategies for Enhancing Customer Lifetime Value in Auto Insurance

### **Context**
**Customer lifetime value**, or **CLV**, is a measure of **how valuable a customer is to a company**. From this value, the company can determine **how much profit is obtained from one passenger and the costs incurred to acquire or retain new customers**. This number is quite important for a company to know if the company wants to target marketing to valuable customers effectively and how the company's customers will change in the future.

### **Problem Statement**

Knowing a customer's true value is crucial for a business. Without this knowledge, resources might be wasted on the wrong customers. It's essential to balance the cost of getting and keeping customers with the revenue they bring. **As the number of customers grows, tools to predict their future value become vital.**

### **Goals**

Given the challenges outlined, a company requires a tool to anticipate the value each customer offers. This understanding can boost profits, streamline marketing resources, and shape strategic business decisions, ensuring customers receive the right attention. **As the number of customers increases, predictive tools become invaluable in determining a customer's worth to the organization.**

### **Analytics Approach**

To enhance our understanding, we'll analyze the data to identify key patterns. Then, we'll build a **regression model to predict the value of any customer, whether new or existing, to the company.**

### **Metrics Evaluation**

    To evaluate the effectiveness of the regression model, we'll utilize three primary metrics: RMSE (Root Mean Square Error), MAE (Mean Absolute Error), and MAPE (Mean Absolute Percentage Error). RMSE provides the square root of the average squared errors, offering insight into the model's accuracy. MAE gives the average of the absolute errors, reflecting the magnitude of errors without direction, while MAPE offers a percentage-based representation of the prediction error. The lower the values for RMSE, MAE, and MAPE, the more accurate our model is in predicting Customer Lifetime Value, given the constraints of the features utilized.


## **Data Understanding**

- Using Customer Lifetime Values as the Dataset
- The Dataset provide Customer Informations

**Attributes Information**

| **Attribute** | **Data Type** | **Description** |
| --- | --- | --- |
| Vehicle Class | Object | The Vehicle Type |
| Coverage | Object | The type of insurance coverage the customer has chosen |
| Renew Offer Type | Object | The type of renewal offer presented to the customer |
| EmploymentStatus | Object | The employment status of the customer |
| Martial Status | Object |  The marital status of the customer, |
| Education | Object | The educational background of the customer |
| Number of Policies | Float | The number of insurance policies the customer holds. |
| Monthly Premium Auto | Float | The monthly premium amount the customer pays for their auto insurance. |
| Total Claim Amount | Float | The total amount claimed by the customer. |
| Income | Float | The income of the customer. |
| Customer Lifetime Value (CLV) | Float | The value of the customer to the business over time. |

<be>

## **CONCLUSION**

In the modeling conducted, the feature `Vehicle Class with SUV and Sport Car` emerged as the most influential factor on `Customer Lifetime Value`.

The evaluation metrics employed for the model included Root Mean Squared Error (RMSE), Mean Absolute Error (MAE), and Mean Absolute Percentage Error (MAPE). If we consider the MAE (as it's more straightforward to interpret) `resulting from hyperparameter tuning, which is 822.31`, we can infer that, in the future, when the model estimates the CLV (Customer Lifetime Value) for an insurance company, within the `model's limitations (maximum CLV value of 16624.75)`, the estimated CLV may deviate by approximately `± 822.31` from the true CLV. Alternatively, considering the MAPE, the estimated CLV may deviate by approximately `± 8.5%` from the actual CLV.

However, it's worth noting that there is a possibility of more substantial deviations in predictions, particularly for CLV `estimates above 8000`, as there appears to be non-uniform variance in the residual plot. Any bias in the model could be attributed to the limited number of features and data in the dataset, which may not adequately represent the diverse range of CLV values.

## **Limitasi Model**

To bring attention to it, this model comes with limitations in predicting CLV (Customer Lifetime Value). When deploying the model, it's important to be aware that its accuracy may diminish when confronted with data exceeding the model's limitations. The model's limitations are as follows:

- `The maximum auto insurance premium cost (Monthly Premium Auto)` it can effectively predict is set at 95% of its value.
- `The maximum total claim amount (Total Claim Amount)` it can accurately handle is restricted to 95% of its value.
- It demonstrates proficiency in `predicting Customer Lifetime Value within a range up to 10,000`. Beyond this threshold, the model tends to introduce bias.

- ## **Recommendation**

`Model Prediction in Machine Learning:`
- This model can only predict customers range up to 10,000. More than that the prediction will not that accurate anymore. Therefore, it's imperative to augment the dataset to enhance the predictive performance of CLV.
- Furthermore, providing a more detailed explanation of the "Renew Offer Type" feature can greatly assist in optimizing the predictive model.
- Consider adding a time-related feature to determine how long a customer has been subscribed to auto insurance.

`Business:`
- Given that "Vehicle Class" emerges as the most influential feature in predicting CLV, it is advisable to create personalized offers for customers based on the type of vehicle they own. Personalized offers can be highly advantageous because the marketing budget can be tailored to individual needs, thereby avoiding overspending on low-value customers and retaining high-value customers.

`Let's assume that we need a months to calculate customer lifetime value. But by using machine learning we can just put the data and let the machine do the works. We can calculate the customer lifetime value just in 1 day or maybe a weeks if there are lots of data that need to calculate.`

Based on this source there are a lots of benefit about why Customer Lifetime Value are Important

[https://blog.hubspot.com/service/how-to-calculate-customer-lifetime-value#:~:text=Customer%20lifetime%20value%20can%20help%20reduce%20costs%20with,it%20can%20also%20reduce%20marketing%20and%20sales%20expenses.]

- Customer lifetime value can help reduce costs with a focus on retaining existing customers. If you can keep a customer happy long-term, then you can improve their value to the business.Using CLV metrics can improve customer loyalty and word-of-mouth referrals — it can also reduce marketing and sales expenses.
- Using the predictive model for customer lifetime value helps you better identify your most valuable customers, the product or service that brings in the most sales, and how you can improve customer retention.
