# ES-LTR-Implicit-Explicit-Correlation
-----------------------------------------------------------------------------------

Contact: Obscured  <!--dalyc24@tcd.ie-->

-----------------------------------------------------------------------------------

## Analysis & Experiment
This project analyses the relationship between explicit & implicit ranking and how this impacts the ranking performance of a ’real world’ Enterprise Search (ES) service of a large organisation.

###  Correlation Analysis
We investigate the correlation between a) human relevance judgements and b) clickthrough rate (CTR) in a learning to rank dataset.

The click-through rate (CTR) is generally defined as the percentage of the number of clicks to the number of impressions.  For the purposes of this study, we calculate the CTR for document, d, and query, q, as follows: - 

$$ CTR_{(q,d)} = {\frac{ clicks_{(q,d)}}{impressions_{(q,d)}}} $$

where impressions is the sum of clicks for all documents returned for q.  A high CTR indicates that users find the document within the listings as helpful and relevant for the given query.  For example, a document with a CTR value of 0.26 means that 26% of the end-users selected that document for the given query.

The metric used to calculate the correlation is the Spearman correlation coefficient. 

### Experiment :  Comparison of Ranking Performance using alternative ground truths
We use the CTR values in place of human relevance judgements are recreate our learning to rank model.   This involves subsitiuting the CTR values into the first column of the LTR dataset.   The nDCG values are calculated using 
- human relevance judgements and 
- clickthrough rate.

# Dataset
We generate and publish a small manually annotated LTR dataset (ENTRP-SRCH.txt) that includes both kinds of feedback as well as a number of features used for learning to rank.  The LTR dataset is formatted as follows: -
![LETOR_format_diagram-with-clickthroughrate](https://user-images.githubusercontent.com/51714656/184387570-87e33de2-a985-4d8f-8a71-4cd7f43bb87a.png)

# How to Run
The attached dataset and code were used to perform correlation and ranking performance tests.  To reproduce, simply download the code (python ipynb files) and LTR dataset (txt file).  It was compliled using python 3 and requires the installation (pip3) of datapane,jinja2 and scipy packages.
The two scripts can be run independently, but the logical order is 
1. ES-LTR-explicit-implicit-correlation.ipynb
2. ES-LTR-ranking-performance.ipynb  (simply change the judgements variable to 'HUMAN' or 'CTR')

# Acknowledgements
Temporarily obscured pending double-blind journal submission.
<!--This research was usertaken by Colin Daly and has been partially funded by the ADAPT Centre and Trinity College Dublin -->
