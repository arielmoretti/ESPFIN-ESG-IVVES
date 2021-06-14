# Test generation and prioritization for ESG-investment    
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

## Claimed novelty
The novelty relies in the dynamic metamorphic testing for NLP-based ESG evolving systems based on templates and Knowledge Graphs combined with approaches for test prioritization based on performance.

## References   
\[1\] [M. Tulio Ribeiro](https://arxiv.org/search/cs?searchtype=author&query=Ribeiro%2C+M+T), [T. Wu](https://arxiv.org/search/cs?searchtype=author&query=Wu%2C+T), [C. Guestrin](https://arxiv.org/search/cs?searchtype=author&query=Guestrin%2C+C), [S. Singh](https://arxiv.org/search/cs?searchtype=author&query=Singh%2C+S), “Beyond Accuracy: Behavioral Testing of NLP Models with CheckList”. arXiv preprint arXiv:2005.04118, 2020.

\[2\] WU, Zhaolin, et al., “A Time Window based Reinforcement Learning Reward for Test Case Prioritization in Continuous Integration”, In Proceedings of the 11th Asia-Pacific Symposium on Internetware, p. 1-6, 2019.
