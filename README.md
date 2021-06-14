# WP3: Test generation and prioritization for ESG-investment    
The irruption of game-changing innovations and open-source technologies in NLP is changing the way that companies work with text. Unstructured text is being used as input data for many industrial domains (i.e., predicting market trends based on sentiment analysis). Data Analytics companies are curating and collating text information from diverse sources to feed AI models (Figure 1) and provide trends and insights. Its combination with other AI techniques applied to numerical data is fostering the integration of NLP into regular Data Analysis.

![Figure 1](/images/image1.png)

**_Figure 1_** General workflow for NLP-based models to provide trends and insights in finance sector

ESG (Environmental, Social and Governance) investing refers to a class of investing that is also known as “sustainable investing.” This is an umbrella term for investments that seek positive returns and long-term impact on society, environment and the performance of the business. To assess a company (an asset) based on environmental, social, and governance (ESG) criteria, investors look at a broad range of behaviours to set the ESG score for a given asset.

![Figure 2](/images/image2.png)

**_Figure 2_:** Estimates of assets under management with an ESG mandate. Source: Deutsche Bank.

The compilation of these scores is based on the analysis of a vast amount of fast changing alternative data sources, including non-structured information (websites, news, corporate reporting...) that can’t be processed with traditional keyword searches and manual analysis. Since ESG investment is a solid trend that is increasingly impacting the market (Figure 2), the data sources to analyze are growing fast. Given the vast amount of data and information available, that analysis can only be reliably carried out with artificial intelligence. New, powerful AI-based systems are now on scene that can potentially reduce the manual tasks and increase the efficiency. However, new V&V techniques are required:

· The growth of AI-based analysis of sources, has also impacted the way that companies communicate with the external audience, being savvier with their wording. This is causing the appearance of biased content, that must be taken into account before applying NLP-based techniques -heavily relying on sentiment analysis- to get insights and trends. Hence, a systematic and continuous analysis of source credibility and content credibility must be implemented.

· The AI-based systems must continuously adapt to a great variability in sources and content, that are constantly changing. Information sources evolve, mutate and topics related to ESG change over time. Hence, test maintenance and prioritization are challenging.

Added to this, since the outcomes of the evolving systems are insights that may impact investment decisions, these systems are subject to regtech (regulatory technology) constraints that must be taken into account.

## State of the Art      
There are different approaches for test case Reinforcement Learning-based test case prioritization. Zhaolin, et al. \[2\], provides a reference for test case prioritization to save computing resources in Continuous Integration. In \[2\], a novel reward function is proposed, by using partial historical information of test cases effectively for fast feedback and cost reduction. The approach is focusing in reducing the huge cost in terms of time and resource availability defining the Average Percentage of Historical Failure with time Window (APHFW), as a novel reinforcement learning reward function, that utilizes a time window to filter recent historical information to calculate reward value.

## Anticipated Contribution
The main technical contribution is supporting testing based on Reinforcement Learning for NLP-based ESG evolving systems. Specifically, given an ESG-investment-focused ES and a set of rules defined by an expert for scoring securities with respect to ESG criteria, develop masked language models.

![Figure 3](/images/image3.png)

**_Figure 3_:** Templating with masked language models. \[1\]

The RL-based test generation and prioritization is based in a time window-based reward function that will also take into account the most effective Metamorphic Relations for a given case. For the selection of effective Metamorphic Relations, the model will initially interact with the templates generated in WP2 with masked language models (Figure 3), and eventually will control “Plug” operators.

As an outcome, the most effective Metamorphic Relations will be selected to generate the optimal test cases to execute, taking also into account performance.

## System Diagram


![Figure 4](/images/ESP-FIN-WP3-systemDiagram.png)

**_Figure 4_:** ESP-FIN System Diagram.

### WP2 Information Crawler
This component is in charge of automatically crawling information related to ESG. The crawler will get information from online sources. The information will be stored in the Data Manager.  

#### current status:

The information crawler component work in two different phases. In the first phase the crawler search for news urls. For this phase two components have been developed, 

1. News searcher. It Fetches urls using a search term and a time span. It returns basic information such, news title, source, url and publish date.

2. GDelt crawler. (https://www.gdeltproject.org/) The second component downloads the gdelt event database in a daily basis and return the same basic information.

The second phase consists in augmenting the basic information. It uses the url provided and crawls the page looking for additional information such article author, title, and full text. Then a NLP pipeline augments the information again providing, summary and keywords.

A first version of the services has been implemented. 

### WP2 Ground-Truth Manager
This component is in charge of ingesting information related to other sources (i.e. ESG Data from Reuters) and  provides a HIL interface to confirm (and/or enhance data labelling). The information will be stored in the Data Manager. 

#### current status:
Several components have been developed. 

1. Frontend Component: It provides an user interface to retrieve news from the information crawler services and persistsit as nodes in a graph database, communicating with te Data Manager. Then it provides the neccesary tools to annotate the data.

2. Backend Component: It handles all the communication betweenthe user interface, the information crawler and the graph database.

A first version of the services is ready to be used and right know a team is using it to annotate the ground truth data. It is planned to add new services with new use cases to improve the information provided. 

### Data Manager
This component  manageS all the data repositories including the Graph Database Server. 
#### current status:
The current version of de DM is already handling all the articles crawled by the information crawler component and annotations from the ground truth manager.
### WP2 Test Case Manager
This component generate test cases to monitor and validate the performance of the models. 
#### current status:
The development is in early stage. Right know we are experimenting with different text generation pipelines with autoregressive models and getting the first results.
### ESP-FIN Model Validator
This component monitors the models, generating the most efficient test case for every model. 
#### current status:
This component development is in early stage. Its architecture already have been described and the barebone components have been developed and are ready to handle the first models to be tested. It is highly depending on the Test Case Manager. 

### ESP-FIN Model Repository
This component manages the different models being generating and updated. The model will be validated and monitored by the "ESP-FIN Model Validator". Once a version of a model fulfills the KPIs defined, it is set as ready for deployment in the ESP-FIN Server. 
#### current status:
A first version has been generated.
### ESP-FIN Orchestrator
This component is in charge of managing the CI/CD pipeline and coordinate the communication between the rest of components. 
#### current status:
A first version of the component has been released, but in an early stage of development.
### ESP-FIN Server
This component is in charge of hosting the models that will get requests from the front-end.
#### current status:
This component is ready to serve the firsts models whenever they are ready.











## References   
\[1\] [M. Tulio Ribeiro](https://arxiv.org/search/cs?searchtype=author&query=Ribeiro%2C+M+T), [T. Wu](https://arxiv.org/search/cs?searchtype=author&query=Wu%2C+T), [C. Guestrin](https://arxiv.org/search/cs?searchtype=author&query=Guestrin%2C+C), [S. Singh](https://arxiv.org/search/cs?searchtype=author&query=Singh%2C+S), “Beyond Accuracy: Behavioral Testing of NLP Models with CheckList”. arXiv preprint arXiv:2005.04118, 2020.

\[2\] WU, Zhaolin, et al., “A Time Window based Reinforcement Learning Reward for Test Case Prioritization in Continuous Integration”, In Proceedings of the 11th Asia-Pacific Symposium on Internetware, p. 1-6, 2019.


