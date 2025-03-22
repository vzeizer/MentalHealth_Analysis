# Sentiment Analysis for Mental Health Status

## About this Dataset:
This comprehensive dataset is a meticulously curated collection of mental health statuses tagged from various statements. The dataset amalgamates raw data from multiple sources, cleaned and compiled to create a robust resource for developing chatbots and performing sentiment analysis.

## Data Source:
The dataset integrates information from the following Kaggle datasets:

- 3k Conversations Dataset for Chatbot
- Depression Reddit Cleaned
- Human Stress Prediction
- Predicting Anxiety in Mental Health Data
- Mental Health Dataset Bipolar
- Reddit Mental Health Data
- Students Anxiety and Depression Dataset
- Suicidal Mental Health Dataset
- Suicidal Tweet Detection Dataset

## Data Overview:
The dataset consists of statements tagged with one of the following seven mental health statuses:

- Normal
- Depression
- Suicidal
- Anxiety
- Stress
- Bi-Polar
- Personality Disorder

## Data Collection:
The data is sourced from diverse platforms including social media posts, Reddit posts, Twitter posts, and more. Each entry is tagged with a specific mental health status, making it an invaluable asset for:

Developing intelligent mental health chatbots.
Performing in-depth sentiment analysis.
Research and studies related to mental health trends.
Features:
unique_id: A unique identifier for each entry.
Statement: The textual data or post.
Mental Health Status: The tagged mental health status of the statement.

Usage:
**This dataset is ideal for training machine learning models aimed at understanding and predicting mental health conditions based on textual data**. It can be used in various applications such as:

1. Chatbot development for mental health support.
2. Sentiment analysis to gauge mental health trends.
3. Academic research on mental health patterns.

## Results

### Number of mental issues detected

The figure below shows a horizontal bar plot addressing the total amount of mental issues detected in the dataset, and also the *"Normal"* mental state. Besides the normal condition, it can be seen that **depression, suicidal, and anxiety** are the most common mental states detected.

![logo](images/1_status_employees.png)


### Length of the text reported

From the figure below it can be noticed that suicidal, personality disorder, and bipolar have more extreme outliers regarding length of the text. Noticeably, te normal mental health state seems to be the "most well behaved", since the length of the text reported seems to be well behaved.   

![logo](images/2_length.png)


### Total number of sentences by status

Here, the number of sentences is studied by mental health conditions, and the suicidal status seems to have the most weird behavior by having an outlier with more than 1200 sentences. **maybe, the high volume of sentences/phrases/unique words in these ilnesses are related to a more desperate mental condition, which could likely result in higher rates of hospitalization or suicidal attempts**.

![logo](images/4_number_sentences_status.png)

### Total number of unique words by Status

The following figure shows the total number of unique words by mental health status, from which one can notice that **bipolar, suicidal, and personality disorder** mental health statuses have the most extreme outliers in this dataset, and normal health status the least.

![logo](images/5_unique_words_status.png)

### Histogram of the length of statements

The following figure shows a histogram of the length of the statements from each patient showing that the greatest amount of length of statements lays between 0-1000, but there are cases where it reaches around 6000!! Therefore, a data treatment and simplication of the text must be implemented.

![logo](images/6_length_statements.png)

### Histogram of the length of statements truncated in 50

The following histogram is a simplification of the previous, **where the sentences have been truncated up to just 50**. This value of 50 was found empirically by testing with values ranging from 20 up to 300, and 50 was found to be present a good trade-off between performance and computing time.


![logo](images/7_length_statements_truncated.png)

### Confusion Matrix: Count Vectorizer model 1

In order to perform **Machine Learning modeling**, the data was split into training and testing datasets, and the **MinMaxScaler** was fitted and applied in the training set, as well this fitted scaler was applied in the testing set. For modeling, the simple yet robust **Logistic Regression** algorithm was used after the **Count Vectorizer** was applied. The results for the confusion matrix for all the classes (mental health entities) are displayed in the figure below.

![logo](images/8_confusionmatrix_1.png)

### Classification Report: Count Vectorizer model 1

The figure below shows the classification report for all the classes for the algorithm applied in the previous part. By regarding precision, recall, and f1-score metrics, **it is noticeable that the normal, anxiety, bipolar, and depression have a good performance in the testing set**, while the other classes are not being so well modeled. This can be explained by regarding the class imbalance presented in this dataset.

![logo](images/9_classificationreport_1.png)

### Top 20 words responsible for the predictions in model 1

In the figure below one can see the top 20 words that have the largest contribution to the model's output.

![logo](images/10_top20words_model1.png)

### Top 20 words responsible for the predictions in model 1 for each mental health status

In the figure below one can see the top 20 words that have the largest contribution to the model's output grouped by each mental health status. For instance, for bipolar episodes the top words are: bipolar, manic, mania, maniac, depress, lithium; and for anxiety: restless, worri(ed), nervous, anxiety, anxiou, cancer. These words can help diagnosize mental health issues for a patient and take preventive actions in order to help them in mental health crisis/episodes. 


![logo](images/11_top20words_model1_illness.png)

### Sentiment analysis by illness

Now, it is going to be performed a sentiment analysis in the statements for the patients. The sentiments can be grouped into positive, neutral, or negative, depending on the results of the algorithmic classification by using **[Text Blob](https://textblob.readthedocs.io/en/dev/quickstart.html)** approach. The figure below shows this for the current dataset, from which one can notice that a normal health status tends to have less negative sentiments

The following figure shows each mental health status discriminated by the kind of sentiment

![logo](images/12_sentimentanalysis_illness.png)

### Length of the sentence by Mental Health Status

The following figure shows the length of the statement whether the patient has a nmental issue or not, discriminated by the kind of sentiment. One can notice that "normal" patients. However, it is noteworthy that ill patients (class 1) that lie in the neutral sentiment category (orange color) also typically write much shorter sentences.

![logo](images/14_lengthstatement_illornotill.png)

### Total number of sentences by sentiment category

In the following figure, one can see the total number of sentences by sentiment by category (negative, neutral, positive), from which it is evident that patients without any mental illness (class 0) typically write much shorter texts than patients that are experiencing a mental issue.

![logo](images/15_totalsentences_sentimentcategory.png)

### Total number of words by sentiment category


In the following figure, it is shown the total number of words categorized by sentiment, from which one can notice that mental ill patients typically have also the largest number of words in a sentence, clearly being outliers. 


![logo](images/16_totalwords_sentimentcategory.png)

### Total number of unique words by sentiment category

In the next figure, it is shown the total number of unique words categorized by sentiment, from which one can notice the mental ill patients (class 1) that have either negative or positive sentiments tend to have a much larger number of unique words used in the sentences.


![logo](images/17_totaluniquewords_sentimentcategory.png)

### Confusion Matrix: Count Vectorizer model 2

The following confusion matrix shows the modeling results for the second approach using a **Count Vectorizer Model**.

![logo](images/18_confusionmatrix_model2.png)

### Classification Report: Count Vectorizer model 2

Now, showing the results of the second modeling approach, but now displaying in the next figure the classification report, one can notice that normal patients are well diagnosed in this approach, as well as the following mental ilnesses: **Bipolar, Anxiety, and Depression**.

![logo](images/19_classificationreport_model2.png)

### Key Findings from Analysis:

1. Mental Health Status Distribution:
Depression, suicidal ideation, and anxiety are the most frequently detected mental health issues.
Suicidal, personality disorder, and bipolar statements often have more extreme text lengths and sentence counts.
2. Text Length Analysis:
Suicidal, personality disorder, and bipolar statements exhibit more extreme text lengths.
Normal statements tend to have more consistent text lengths.
3. Sentence and Word Count:
Suicidal statements show an outlier with a very high sentence count.
Bipolar, suicidal, and personality disorder statements have the most extreme outliers for unique word count.
4. Text Preprocessing:
Statement lengths vary significantly, necessitating text simplification (truncation to 50 words was found to be a good trade off).
5. Machine Learning Modeling (Logistic Regression with Count Vectorizer):
Two models were created.
Normal, anxiety, bipolar, and depression statuses were predicted with good performance.
Class imbalance affected the modeling of the other mental health statuses.
The top 20 words contributing to predictions were identified, both overall and for each mental health status.
6. Sentiment Analysis (TextBlob):
Normal statements tend to have fewer negative sentiments.
Mental ill patients tend to write longer sentences, and use a greater number of total words, and unique words.
- Model 2 improvements:
Model 2 also showed good performance in predicting normal, bipolar, anxiety, and depression.

## Real-World Usage

The findings from this data analysis can be applied in several real-world scenarios to assist patients with mental health issues:

1. **Early Detection and Intervention**:

- *Social Media Monitoring*:
By deploying sentiment analysis and text classification models (like the ones developed in the analysis) on social media platforms, early signs of distress (e.g., suicidal ideation, severe anxiety) can be detected.
This allows for timely intervention by mental health professionals or support services.
**The identified top 20 words associated with specific mental health conditions can be used as keywords for monitoring**.
- *Chatbot Integration*:
Mental health chatbots can be trained using this dataset to identify users expressing symptoms of depression, anxiety, or suicidal thoughts.
These chatbots can provide initial support, offer resources, and guide users towards professional help.
The ability to analyze text length and complexity can help assess the severity of a user's distress.
- *Healthcare System Integration*:
Hospitals and clinics can use these models to analyze patient notes and online interactions, flagging individuals at risk for mental health crises.
This can help prioritize patients for mental health assessments and interventions.


2. **Personalized Support and Treatment**:

- *Sentiment Analysis for Therapy*:
Therapists can use sentiment analysis tools to track changes in a patient's emotional state over time, providing valuable insights into the effectiveness of treatment.
Analyzing the language used by patients can help therapists understand their specific concerns and tailor therapy sessions accordingly.
- *Personalized Content Delivery*:
Based on the identified mental health status and sentiment, apps and online platforms can deliver personalized content, such as coping strategies, mindfulness exercises, or support group recommendations.
The model's identification of key words related to each mental illness can be utilized to provide users with information that is most relevant to their mental health condition.
- *Risk Assessment*:
The finding that certain mental illnesses correlate with very long text outputs, and very high amounts of unique words, can be used as a flag for high risk patients.

3. **Research and Advocacy**:

- *Mental Health Trend Analysis*:
Researchers can use this dataset to study the prevalence and trends of mental health issues in different populations.
This can inform public health campaigns and policies aimed at improving mental health awareness and access to care.
- *Reducing Stigma*:
**By analyzing the language used in online discussions about mental health, researchers can identify and address stigmatizing language and promote more empathetic and supportive communication.**
- *Improving Diagnostic Tools*:
The models developed in this analysis can contribute to the development of more accurate and efficient diagnostic tools for mental health conditions.
In essence, these findings enable the development of tools and systems that can:

- Provide early detection and intervention for mental health issues.
- Offer personalized support and treatment to patients.
Advance research and advocacy efforts to improve mental health care.

## Acknowledgments:

This dataset was created by aggregating and cleaning data from various publicly available datasets on Kaggle. Special thanks to the original dataset creators for their contributions.

## MIT License

### Copyright (c) [2025] [Vagner Zeizer Carvalho Paes]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.


