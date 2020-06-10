# Module 1

## What we will learn in this module

- What is data mining?
- what techniques are available?
- what does each technique do?
- What are the challenges?
- what types of data are available and what operations are applicable to each type?
- why data needs to be cleaned and how it is done
- how data is preprocessed?
- how data proximity is measured?



<u>*Note: exercise 1 due soon*</u>



## Motivations

- Data collection is easy. Companies can collect data on a massive scale by the second. 
- Data storage is cheap.
- knowledge can be extracted from data to improve decision making
- humans are *incapable* of analyzing huge amounts of data **(big data)**

### Examples

- business and industry
  - data collected about customers/purchases
    - bar code scanner
    - smart card
    - logs from websites
    - call center records
  - knowledge extracted by data mining:
    - customer profiling: if the business can answer questions about their customers, they can make smarter decisions
    - targeted marketing
    - store layout
  - data collected by online viewing
    - web browsing
    - messaging
    - social media posts
    - knowledge extracted
      - product recommendation
      - identifying spam
- science, engineering and medicine
  - data collected by
    - devices such as telescopes
    - satellite
    - patient history
  - knowledge extracted
    - exploring galaxies
    - environmental issues
    - finding cause of disease, provide better care





## What is Data Mining?

**Data mining is the process of discovering information, which is not explicitly visible.** Data mining is also able to **extract new information or patterns** which may be potentially useful. This new information may seem inconsequential from a human perspective, but data mining can extract data from seemingly unrelated data points. Data mining is **automated**, or semi-automated.



The process includes:

`understand the business <--> understand the data --> preprocess the data <--> model --> evaluate --> deploy`



### What is *not* data mining?

- searching for a thread in piazza
- finding the average grade received by undergraduate female students
- finding a country in North America, that has more than 30 million people, life expectancy >70, official language is French



**A SQL query can find the answer to all these questions!**



## The origins of data mining

- statistics
  - sampling, estimation, and hypothesis testing 
- AI/ machine learning/ pattern recognition
  - search algorithms, modeling techniques
- database systems
  - indexing and query processing


$$
Data Mining = Statistics \cap AI \cap DatabaseSystems
$$




## Data Mining Techniques

- Predictive methods
  - classification
    - decision trees
    - neural networks
    - support vector machine
    - nearest neighbors
  - regression
  - deviation detection
- Descriptive methods
  - clustering
    - K-means
    - DBSCAN
    - Hierarchical
  - association rule discovery
  - association pattern discovery



## Classification

- **Training set**: contains a set of <u>records</u> (rows) and <u>attributes</u> (columns)
- **Class variable**: an <u>attribute</u> that is to be <u>predicted</u>
- **Test Set**: a set of records, whose class variable is pretended to be unknown



- Goal: create a **model** as a:
  - function of other attributes
  - that can predict the **class variable** for previously unseen record of data



**In a nutshell: The training set is used to create the model, and the test set is used to validate the model.**



### Classification Applications

- Goal: **Fraud detection**
- training set: credit card transactions, account holder's data
- class variable: Fraudulent transaction
- class variable's value: yes or no
- create the model by training it using the training set
- use it to detect fraudulent transactions



Another example:

- Goal: **customer loyalty detection**
- training set: customer financial status, marital status, how often they call, when the call
- class variable: is loyal
- class variable value: yes or no
- create the model by training it using the training set





## Regression

- **Predictive** method
- the model is a linear or nonlinear function of the attribute that predicts the class variable
- class variable is a **continuous variable**
- examples:
  - predicting the sales amounts of new products based on advertising expenditure
  - predicting wind velocities as a function of temperature, humidity, air pressure, etc.
  - time series prediction of stock market indices



## Clustering

- A data set containing a set of attributes is given

- Goal: find clusters such that:

  - the data points in one cluster are the most similar
  - the data points in separate clusters are the most dissimilar

- a measure that is able to compute the similarity between two data points is given

- similarity measures:

  - **Euclidean distance**

    - intracluster distance minimized
    - intercluster distances are maximized

  - other problem-specific measures

    

### Clustering Applications

- goal: group documents based on their subject similarity

- approach:

  - find frequently occurring terms in each document
  - use a similarity measure to find how similar the documents are based on their frequent terms

- example

  - 3204 Articles of LA Times

  - similarity measure: common words in the documents

    - | category  | total articles | correctly placed |
      | --------- | -------------- | ---------------- |
      | financial | 555            | 364              |
      | foreign   | 341            | 260              |
      | national  | 273            | 36               |

  - perfect clustering is not always possible

    

## Association rule analysis

- A data set contains a set of records, each record contains some number of items

- goal: generate a set of dependency rules which will predict occurrence of an item based on occurrences of other items

- example

  | TID  | ITEMS                     |
  | ---- | ------------------------- |
  | 1    | bread, coke, milk         |
  | 2    | bread, beer               |
  | 3    | beer, coke, diaper, milk  |
  | 4    | beer, bread, diaper, milk |
  | 5    | coke, diaper, milk        |

  - **Rules discovered:**

    - {milk} -> {coke} (3/4 occurrences)

    - {diaper, milk} -> {beer} (2/3 occurrences)

      

### Applications

- Marketing and sales promotion
  - assume that {diaper, milk} -> {beer} rule is discovered
  - **consequent**: can be used to determine what should be done to increase its sale
  - **antecedent**: shows which products would be affected if the store stops selling them
  - **consequent and antecedent:** which products should be sold together to boost the sale of the item in the consequent

- supermarket shelf management
  - goal: organize the shelves by placing the items that are bought together by sufficiently many customers



## Deviation/Anomaly Detection

- detect significant deviations from normal behavior
- goal: avoid labeling a normal behavior as anomalous
- applications:
  - credit card fraud detection
  - network intrusion detection
  - unusual pattern of disease



## Data Mining Challenges

- **Scalability**

  Data is generated very fast, and in huge quantities. You don't generally want to wait hours or days for your algorithms to run. We can use various strategies to improve our scalability.

- **Dimensionality**

  It's very common to work with data sets with huge numbers of attributes.

- **Complex and Heterogenous Data**

  In the case of working with the web, we can have images, text, video, audio, etc.

- **data quality**

  Sometimes data sets are full of outliers, and needs to be cleaned.

- **Data ownership and distribution**

  Data access is sometimes an issue. We may have to consider communication costs and privacy issues.

- **Privacy preservation / Ethical issue**

  Data mining has huge ethical consequences. It can be (wrongly) used for:

  - **discrimination**
    - highly unethical and illegal to discriminate based on race, gender, or religion
  - **reidentification**
    - most people can be identified with just a few simple data points (birth date, sex, city, etc.)
  - **personal information**
    - how it is used, what it is used for, how confident it remains
    - should be expressed in **plain language**

