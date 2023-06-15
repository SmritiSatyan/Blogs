# How Fraud Detection with Machine Learning Works

Fraud involves exploiting vulnerabilities in a system to steal sensitive data and money. Fraud is a primary concern in all industries and [costs the global economy trillions of dollars](https://www.khaleejtimes.com/business/cybercrime-corporate-fraud-cost-global-economy-11tr) every year. 

Online transactions are a common target for fraud, as they often contain sensitive data such as credit card information and bank details that can easily be exploited. Many companies have incorporated machine learning in their products to increase the effectiveness of fraud detection and prevention. 

A simple fraud detection example in machine learning is email spam filtering, which helps eliminate irrelevant data. Users can focus on credible emails and safely ignore those in the spam folder, without worrying about missing important correspondence. Along the same lines, machine learning helps identify and avoid fraudulent transactions by notifying users about suspicious activity.

Classifying transactions as fraudulent or non-fraudulent is challenging because there are far more genuine transactions than fraudulent ones. However, machine learning can achieve this classification by training a model on large amounts of transaction data, deploying the model to production, analyzing the transaction data, and identifying trends and patterns.

This article explains why machine learning is important in fraud detection and how fraud detection algorithms work.

**Note:** Within this article, *transaction* refers to any communication between the user and the web. It could be a bank transaction, submission of identification forms, anything mimicking consumer behavior, logins, or any activity that may impersonate the consumer's identity/information/money without their knowledge.

## Why Is Machine Learning Important for Fraud Detection?

Organizations have historically used rule-based systems to detect fraud. These systems would help uncover suspicious or fraudulent trends and patterns based on set rules. However, these systems proved somewhat limited as they weren’t adaptable. They were unable to identify hidden or new patterns and had to be constantly updated, exposing organizations’ vulnerabilities to fraudsters. 

Machine learning was introduced into fraud detection to supplement this traditional system and to provide solutions that are more adaptable to the dynamic nature of modern fraud. The synergy between traditional systems and machine learning makes today's fraud detection systems more reliable: it provides the manual inference required in certain transactions and uncovers hidden patterns in data that traditional systems alone could not.

## What Is Fraud Detection Using Machine Learning?

Fraud detection using machine learning refers to self-learning systems that detect patterns and flag fraudulent transactions, which is achieved using features in data that help distinguish fraudulent transactions from legitimate ones. 

These systems uncover, learn, and adapt to patterns using transaction data without explicitly being instructed to do so. The process is quick, scalable, efficient, accurate, and cost effective. It eliminates the need for organizations to constantly update their systems in response to new schemes and patterns of vulnerabilities.

Some common examples of fraudulent transactions that can be flagged include:

* Multiple payment cards with the same shipping address
* Suspicious email addresses with a name mismatch
* A customer placing an unusually high number of orders of high value
* Suspicious shipping locations that don’t match up to residential addresses

### Fraud Detection Use Cases

Fraud not only affects customers, but organizations and entire countries too. Detecting and preventing fraud is an integral part of avoiding economic harm. Machine learning uses previous transactions to learn patterns (about suspicious and fraudulent transactions), and uses this knowledge to detect fraud in ongoing transactions. 

In this way, organizations and countries can detect and prevent fraud before it occurs. This results in less time spent investigating such fraud, thereby reducing the friction associated with fraudulent transactions. Fraud detection using machine learning can:

- Prevent business losses
- Reduce losses to the global economy 
- Reduce fraud investigation time and labor
- Ensure safe and smooth transactions
- Eliminate the constant need for manual intervention during transactions

## How Does Fraud Detection with Machine Learning Work?

The standard machine learning steps, including data collection, pre-processing, choosing a model, and training remain the same when using machine learning for fraud detection. However, before diving into these, you should familiarize yourself with two important elements of fraud detection: the risk score and the risk score threshold.

### Understanding the Risk Score

The *risk score* is an important parameter defined when building the model. It’s a numeric value that lies between one and a hundred, which is the deciding factor in whether or not to classify the transaction as fraudulent. 

After deploying a model into production, the risk score is calculated when a transaction is initiated, which helps identify if a transaction is fraudulent or genuine. The determined risk score reflects the probability of fraud in the transaction, with a higher score indicating that fraud is more likely.

The risk score is calculated by providing risk rules and determining how many rules the transaction adheres to. The more risk rules a transaction adheres to, the safer the transaction. 

For example, if you have a risk rule that states that the transaction shouldn’t be more than $500 USD and the transaction is valued at $480 USD, then the transaction adheres to the rule. Hence, it has a better chance of being flagged as genuine. 

### Setting a Risk Score Threshold

The *risk score threshold* is a limit set to compare it with the risk score. This comparison helps decide whether a transaction is fraudulent or genuine. Based on your product, you should provide a threshold for the risk score that ensures minimal genuine transactions are flagged in the process of reviewing transactions. However, It’s better to flag a small number of genuine transactions as fraud rather than flagging fraudulent transactions as genuine. 

Businesses determine their risk score threshold using two metrics: precision and recall. 

*Precision* determines the proportion of transactions that are flagged as fraudulent, while *recall* determines the proportion of prevented fraudulent transactions out of all the fraudulent transactions. These metrics are inversely proportional; as one increases, the other decreases.

With a high precision score, a small number of fraudulent transactions will be flagged, but, as a consequence, some fraudulent transactions with a precision score lower than the threshold will probably not be identified. The right balance between precision and recall is important for finding an optimal value for the risk score threshold.

This threshold is then compared with the risk score of every transaction. If the risk score is lower than the threshold value, it’s flagged as a genuine transaction and a fraudulent transaction otherwise. 

Instead of creating and deploying a machine learning model that considers the risk score and all of the above features, an already available framework might be more convenient and practical.

This is where Rapyd comes into the picture. [Rapyd Protect](https://docs.rapyd.net/client-portal/docs/rapyd-protect-overview) is a management system that uses AI modeling to detect and flag fraudulent transactions and also lets you write [customized risk rules](https://docs.rapyd.net/client-portal/docs/creating-a-fraud-rule).

The next section explains how the risk score is determined as a part of the machine learning pipeline.

### Typical Steps in Fraud Detection Using Machine Learning

A machine learning pipeline consists of the common steps involved in building a model, along with an additional step to calculate the risk score and compare it to a risk threshold to see if the transaction is genuine or not. 

1. **Input data processing:** This involves collecting large amounts of data (the more data, the better the accuracy of results), cleaning it, and pre-processing it. An example is labeled data that indicates genuine and fraudulent transactions (this is supervised training; unsupervised training would contain unlabelled data). 

2. **Feature extraction:** You extract features from the labeled data that describe customer behavior, such as:
 - Number of orders placed
 - Customer’s location
 - Customer's network 
 - Payment methods used
 - Shipping locations
 - Time spent on the page
 - Amount of time between adding a payment card and placing an order

**Note:** Adopting a platform that has already identified problematic features can be a good idea. For example, Rapyd provides a list of known fraudsters, dubious IP addresses, blocked countries, and high-risk BINs and their ranges.

3. **Choose or devise a learning algorithm:** Apply the data on different algorithms, analyze the accuracy, and determine how the algorithm responds to new data. Sometimes, a hybrid model (a combination of two or more algorithms) may give better results. For example, Rapyd builds finely tuned models using unique data sets to identify new trends in fraud and to keep your business safe. 

4. **Split data into training and validation sets:** Split the data into training and validation sets to determine how the model performs on new data.

5. **Model training:** Use the training set to train the algorithm on the collected data.

6. **Determine risk score:** The model determines the risk score (predictions) by reviewing the risk rules that the transaction adheres to (using the features in the data set). Rapyd uses a model that allows you to set up manual reviews for high-risk transactions, thereby greatly reducing the probability of fraud. 

7. **Determine accuracy:** Use the validation set to determine how accurate the risk score is and how well the model classifies data into fraudulent and genuine transactions.

8. **Retrain if necessary:** If the model performs well and classifies most or all the transactions correctly, you can deploy it to production. Otherwise, you can retrain the model with a different set of hyperparameters to better determine the risk score or choose a different model.

Assume that your risk score threshold is eighty-six. The transaction is considered legitimate if the calculated risk score is lower than eighty-six. The transaction is flagged as fraudulent if the calculated risk score is equal to or higher than eighty-six. The data from such transactions are further accumulated to train the model.

**Note:** It’s essential to constantly provide new data to the training algorithm and ensure that the results are accurate because fraudsters frequently come up with new schemes to exploit transactions.

The fraud detection using machine learning workflow can be seen below and you can find a visualization of this process [here](https://mermaid.live/view#pako:eNp9k9tu4jAQhl9llGt4AbTainJo6ZFC92LX4cK1h8SqYyMfQFXEu-8kNlWQVstVMvON___Hk7YQVmIxKfbankTNXYD329IA_Xz8qBw_1PBMhIaPqLRUpkrNP2wbCN7BePwTpmxmtUYRQPLAd4mY9q1btnY4Pjgr0Pth-x-NfmDGZrW1HkEjdyQHXFfWqVA3eXDGtgetwmDklb07rgyEGqHpvGbyte-u2RwDukYZBKf8J3hhHWZk3SObdrUHLkR0PAyhc4I2BMFv9D37RscdtP1KShAsUAYZRVDW7Ab8i4URUMLQW-ttpi4amR7mbGVUUJ0kQcbzdEbPPrFf_jrMU19fsBnXIuprnxlZkDWhJII1qRlqh762WqZDl-3mewR-wOYKyVnfknx6WQ6D37E7NLH7FwduRyCsCcrEi4dlzt5NrNp7VdVw5DqSJyfR3WSV1YB6HJQuWg_tMzeRa1CGru6IptPKsw8dSPdFQam8VyiBe6iyt97p_8C941FGTaWkzpaaV9eNHOWxm59KOczbb1136eF64-BEGwoGT9-AamgvjjhA8g6UoRgVDS0kV5K-u7YTKwvCGiyLCT1K7j7LojRn4uKBzsOFVMG6YhJcxFHBY7DbLyMu74mZK05fa5OK578czzuC).

```
flowchart TB
    subgraph Model building
    Z[Start] --> A[Collect data]
    A --> B[Pre-process data]
    B[Pre-process data] --> C[Choose learning algorithm]
    C[Split data] --> O[Train the model]
    O --> P[Determine risk score]
    P --> R{If accurate risk score}
    R -- Yes --> Q[Deploy model to production]
    R -- No , retrain --> O
    end
    D[Initiate transaction] --> L[Use model]
    L --> E[Calculate risk score]
    E[Decide on risk threshold] --> F{Risk score < Risk threshold}
    Q --> L
    F -- Yes --> G[Genuine transaction, continue]
    F -- No --> I{High value order?}
    I -- No --> K
    I -- Yes --> J{Manual intervention}
    J -- If identified as genuine --> G
    J -- If identified as fraudulent --> K[Flag as fraudulent]
    K -- Add transaction data to train the model with new data to improve the model --> O
```

## Conclusion

In this article, you learned about how machine learning can detect fraud, how risk scores determine the probability of fraud, and factors to keep in mind while deciding on a threshold for the risk score. 

Throughout the article, [Rapyd](https://www.rapyd.net/) served as an example of a payment solution that helps detect fraud for hundreds of [payment methods](https://docs.rapyd.net/build-with-rapyd/docs/payment-methods) and [business models](https://docs.rapyd.net/build-with-rapyd/docs/payment-features). Using sophisticated AI models, Rapyd provides unique insights into transactions and identifies fraud before it occurs.

On top of these features, Rapyd has a dedicated fraud protection platform, Rapyd Protect. It’s embedded with Rapyd and is available at no additional cost or coding. It provides a seamless shopping experience by reducing the risks associated with card payments.

