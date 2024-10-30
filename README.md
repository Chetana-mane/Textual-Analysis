

---

# Advanced Journal Analysis of Academic Papers (2000-2022)

This project offers a comprehensive analysis of 4,385 academic papers, using a range of machine learning techniques to extract trends, classify research areas, and predict influential factors across multiple journals over a 22-year period. The repository provides both the methodologies and insights derived from the dataset, serving as a powerful tool for understanding the evolving landscape of academic publishing in mathematical sciences.

## Table of Contents
- [Project Overview](#project-overview)
- [Objectives and Hypotheses](#objectives-and-hypotheses)
- [Dataset Overview](#dataset-overview)
- [Data Processing and Cleaning](#data-processing-and-cleaning)
- [Methodologies and Techniques](#methodologies-and-techniques)
  - [Textual Feature Extraction (BoW & TF-IDF)](#textual-feature-extraction-bow--tf-idf)
  - [Classification Models](#classification-models)
  - [Topic Modeling with LDA](#topic-modeling-with-lda)
  - [Regression for Citation Prediction](#regression-for-citation-prediction)
  - [Clustering Analysis](#clustering-analysis)
- [Key Findings and Results](#key-findings-and-results)
- [Conclusion and Future Directions](#conclusion-and-future-directions)
- [References and Libraries](#references-and-libraries)

## Project Overview
This project delves into data from high-impact academic journals, applying sophisticated analytical techniques to identify latent patterns, temporal trends, and influential factors within academic research. By leveraging this analysis, we aim to offer insights that can help researchers and policymakers understand research popularity, impact factors, and evolving themes in mathematical sciences from 2000 to 2022.

## Objectives and Hypotheses
The analysis explores the following core objectives:
1. **Trend and Content Analysis**: Examine temporal trends in views, citations, and altmetric scores, and analyze abstract characteristics for patterns across journals.
   ![image](https://github.com/user-attachments/assets/98c32f6c-2fda-4568-9158-6b4428b7b95a)

2. **Predictive and Clustering Modeling**:
   - Build a regression model to predict citation counts based on abstract content and other features.
   - Apply clustering to assess the popularity of topics and identify common research areas.

   ![image](https://github.com/user-attachments/assets/120afee0-1312-4f22-9cfb-404d0a305a01)

## Dataset Overview
The primary dataset (`journal_data.csv`) encompasses 4,385 academic papers, with key variables including:
- **Title**: Paper title
- **Journal**: Journal name
- **Year**: Publication year
- **Authors, Views, Citations, Altmetric Score**: Engagement and impact metrics
- **Abstract**: Textual content for topic and trend analysis

The dataset’s broad scope allows for multi-dimensional analysis of research trends and topics.

## Data Processing and Cleaning
Significant preprocessing steps were undertaken to standardize and prepare the data:
1. **Handling Missing Values**: Rows with empty `abstract` or `views` fields were removed, impacting approximately 5% of entries.
2. **Outlier Detection**: Views and citations were capped at the 95th percentile to mitigate skewness.
3. **Text Processing**: Abstracts were cleaned through tokenization, stop-word removal, and other preprocessing techniques.
4. **Categorical Encoding**: One-hot encoding was applied to classify journals for downstream analysis.

## Methodologies and Techniques

### Textual Feature Extraction (BoW & TF-IDF)
Using the `clean_abstract` column, Bag of Words (BoW) and Term Frequency-Inverse Document Frequency (TF-IDF) were calculated to quantify word importance. These features were integrated into the dataset as `dtm_bow` and `dtm_tfidf`, facilitating further analysis.

![image](https://github.com/user-attachments/assets/e559dcc0-cd0e-47f0-87ea-1965d4e80310)

### Classification Models
To classify papers into journals, we employed the Naïve Bayes algorithm, utilizing features like TF-IDF scores, publication year, and dominant topic. This approach achieved a 95% classification accuracy, supporting reliable journal categorization.
![image](https://github.com/user-attachments/assets/522d8540-6a59-47c9-b9db-52c2513835f6)

### Topic Modeling with LDA
Latent Dirichlet Allocation (LDA) was applied to the abstracts, revealing ten prominent topics across the corpus. These include Statistical Modeling, Healthcare Services, Decision Analysis, and more. Each document's dominant topic was identified, providing a deeper understanding of content themes and shifts over time.

![image](https://github.com/user-attachments/assets/b1b7012a-24d3-4a30-a9d8-164b572e8d72)

### Regression for Citation Prediction
A regression model was implemented to predict citation counts, achieving 99% accuracy. Key predictors included TF-IDF features and year of publication. Using Elastic Net regularization, the model demonstrates strong predictive power, identifying critical factors influencing citation frequency.

![image](https://github.com/user-attachments/assets/08aed476-6a01-4d3e-97d3-c9328f92abff)

### Clustering Analysis
Two clustering methods, DBSCAN and K-means, were applied to categorize papers based on views and dominant topics:
- **DBSCAN** helped visualize dense clusters, representing the concentration of similar research papers.

![image](https://github.com/user-attachments/assets/e8b0f7a8-f152-42d3-a9d0-2d795a9b0838)

- **K-means** enabled grouping based on topic popularity, assigning clusters based on engagement metrics.

![image](https://github.com/user-attachments/assets/cf6c93a2-fd85-44e1-99f3-fa5301e634c0)

## Key Findings and Results
1. **Temporal Insights**: The analysis reveals changing patterns in citation and view counts, highlighting evolving research interests over the years.
2. **Journal Classification**: Classification models successfully identified unique characteristics of each journal, providing a structured view of research areas.
3. **Citation Prediction Accuracy**: With a 99% citation prediction accuracy, the regression model offers robust insight into factors that drive academic influence.
4. **Topic Popularity**: Clustering indicates topic-based view trends, allowing for insights into research relevance and audience engagement.

## Conclusion and Future Directions
This project validates the formulated hypotheses, offering actionable insights into academic publishing patterns. Future work may include:
1. Testing the regression model on external datasets to improve generalizability.
2. Extending temporal analysis beyond 2022 to predict future research trends.
3. Integrating external factors, such as funding information, to enhance citation prediction accuracy.
4. Applying these methodologies to datasets from other academic fields to understand broader trends and influence patterns.

## References and Libraries
The analysis utilized a range of R libraries for data processing, visualization, and machine learning, including:
- **Quanteda, TidyText, and Wordcloud** for text analysis
- **Topicmodels and LDA** for topic modeling
- **Caret and glmnet** for regression and regularization
- **Arules and arulesViz** for association rule mining
- **Dbscan and factoextra** for clustering and dimensionality reduction

