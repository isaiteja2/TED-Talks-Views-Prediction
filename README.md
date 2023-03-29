# **Project Name**    - **TED Talks Views Prediction**

##### **Project Type**    - Supervised Learning (Regression)
##### **Contribution**    - Individual
##### **Name**          - Saiteja Ch

# **All the what(s) and why(s)**

Here are some basic understandings that could be helpful to include before jumping into the TED Talks views prediction regression project:


**1. What is TED?**  
    TED (Technology, Entertainment, Design) is a nonprofit organization devoted to spreading ideas in the form of short, powerful talks. TED began in 1984 as a conference where Technology, Entertainment and Design converged, and today covers almost all topics — from science to business to global issues — in more than 100 languages.


**2. Why predict views for TED Talks?**         
    Predicting the number of views for TED Talks can provide valuable insights for the TED organization and help them make data-driven decisions about which talks to promote and how to allocate their marketing resources. By accurately predicting which talks are likely to receive a high number of views, the model could help increase the visibility and reach of these talks, leading to more engagement from the audience.


**3. What is data-driven decision making?**           
    Using data and predictive models to guide decision making can help organizations make more informed choices and allocate their resources more effectively. In the case of the TED organization, using a regression model to predict the number of views for their talks could provide valuable insights into which talks are likely to be popular with their audience and how they can best promote their content.
    

**4. Why this project?**            
    The purpose of this project is to develop a regression model that can accurately predict the number of views for TED Talks based on various features such as speaker characteristics, talk topic, and talk length. The goal is to provide valuable insights for the TED organization and help them make data-driven decisions about how to promote their content and engage with their audience.
    
# **Project Summary -**

TED is devoted to spreading powerful ideas on just about any topic. These datasets contain over 4,000 TED talks including transcripts in many languages. Founded in 1984 by Richard Salman as a nonprofit organization that aimed at bringing experts from the fields of Technology, Entertainment, and Design together, TED Conferences have gone on to become the Mecca of ideas from virtually all walks of life. As of 2015, TED and its sister TEDx chapters have published more than 2000 talks for free consumption by the masses and its speaker list boasts of the likes of Al Gore, Jimmy Wales, Shahrukh Khan, and Bill Gates. The main objective is to build a predictive model, which could help in predicting the views of the videos uploaded on the TEDx website.

# **GitHub Link -**

GitHub Link - https://github.com/isaiteja2/TED-Talks-Views-Prediction

# **Problem Statement**

The TED organization aims to maximize the visibility and reach of its talks to engage with a wide audience and promote the spread of ideas. However, with a large number of talks available on their platform, it can be challenging to determine which talks to promote and how to allocate marketing resources effectively.

To address this challenge, we propose developing a regression model that can accurately predict the number of views for TED Talks based on various features such as speakers, talk topic, and talk length. The model’s predictions could be used to prioritize promoting talks that are likely to receive a high number of views and guide the TED organization’s content strategy and selection process.

The goal of this project is to provide valuable insights for the TED organization and help them make data-driven decisions about how to promote their content and engage with their audience.

# **Bussiness Context**

A regression project predicting the number of views for TED Talks could provide valuable insights for the TED organization and help them make more informed decisions about how to promote their content and engage with their audience.

By accurately predicting which talks are likely to receive a high number of views, the model could help the TED organization prioritize promoting these talks on their website and social media channels. This could increase the visibility and reach of these talks, leading to more views and engagement from the audience.

Additionally, by identifying which features (e.g., speaker average views, talk topics, duration) are most strongly associated with a high number of views, the model could guide the TED organization’s content strategy and selection process. 

Overall, using a regression model to predict the number of views for TED Talks could be a helpful tool for the TED organization in making data-driven decisions about which talks to promote and how to allocate their marketing resources.

# **Project Workflow:**


1. Know Your Data.

2. Understanding Your Variables.
3. Data Wrangling.
4. Visualizasion and Operations.
5. Feature Selection
6. Removing Multicollinearlity.
7. Final dataset for Modeling.
8. Splitting the Data.
9. ML Model Implimentation. 
10. Conclusion.

### What did you know about your dataset?

**Observations:**


1. Dataset has 4005 rows and 19 columns.
2. There are null values in 5 columns. They are comments, about_speakers, occupations, all_speakers, and recorded_date.
3. There are no duplicate values.

### Variables Description 

Comming to the dataset there are 19 columns which explains details about the talk and its description along with speaker and all. They are:

* **talk_id:** A unique identification number assigned to 
each TED talk.
* **title:** The title of the TED talk.
* **speaker_1:** The name of the first speaker in TED's speaker list.
* **all_speakers:** The names of all the speakers in the talk.
* **occupations:** The occupations of the speakers.
* **about_speakers:** A brief description about each speaker.
* **recorded_date:** The date on which the talk was recorded.
* **published_date:** The date on which the talk was published to TED.com.
* **event:** The event or medium in which the talk was given.
* **native_lang:** The language in which the talk was given.
* **available_lang:** The list of all available languages for a talk.
* **comments:** The count of comments received for the talk.
* **duration:** The duration of the talk in seconds.
* **topics:** Related tags or topics for the talk.
* **related_talks:** A list of related talks with their talk ID and title.
* **url:** The URL of the talk.
* **description:** A brief description of the talk.
* **transcript:** The full transcript of the talk.
* **views:** The count of views for the talk.


Q. How we dealt with null values? 


*   **Comments:** Since this is a numerical variable we dealt the null values by filling them with median instead of mean so that it shows a little to no effect while removing outliers.
*   **occupations & about_speakers:** We filled them with unknown cuz they are of categorical variables.
*   **recorded_date:** We removed since it is only one record.

Q. What is IQR?

**Explaination:** IQR (Interquartile Range) is a measure of statistical dispersion and is used to identify outliers in a dataset by calculating the difference between the 75th percentile (Q3) and the 25th percentile (Q1) of the data.

Q. What do you know about top 5 speakers w.r.t overall comments, duration and views?

**Obseravtions:** (not single video but overall)   

1. According to comments ***Richard Dawkins*** is the top speaker with ***28.8%***
2. According to duration ***Alex Gendler*** is the top speaker with ***34.6***
3. According to views ***Alex Gendler*** is the top speaker with ***59.2%***

Q. What are the reasons behind selected columns?

***Reasons:*** The selected are relevant features that could influence the number of views a TED Talk receives. 
* The **‘comments’** column could indicate the level of engagement and interest in the talk. 
* The **‘duration’** column could affect how likely people are to watch it. 
* The date it was published **(‘published_year’, ‘published_month’, ‘published_day’, ‘published_daynumber’, ‘published_months_ago’)** and the event it was associated with **(‘ted_event_type’)** could also play a role in its popularity. 
* Average views of other talks by the same speaker **(‘speaker_avg_views’)** or from the same event **(‘event_avg_views’)** could provide useful context for predicting views. 
* The number of available languages **(‘available_languages’),(‘time_since_published’)** and **(‘daily_views’)** may also be relevant factors in predicting the number of **views**(dependent variable) a TED Talk receives.

### Important Questions regarding multicollinearity:

**1. What is VIF?**

  **Variance Inflation Factor (VIF)** is a measure used to **detect the severity of multicollinearity** in regression analysis. Multicollinearity occurs when two or more independent variables in a regression model are highly correlated with each other. This can inflate the variance of the estimated regression coefficients and make them unreliable.

**2. What is multicollinearity?**

  ***Multicollinearity*** is the occurrence of high intercorrelations among two or more independent variables in a multiple regression model.

**3. How is VIF calculated?**

  VIF is calculated by regressing each independent variable against all other independent variables and then using the R-squared value from that regression to calculate VIF.

**4. What happens if there is high VIF?**

  A high VIF value indicates that an independent variable is highly correlated with other independent variables in the model, which can be problematic for interpreting the individual effects of each variable on the dependent variable.

### Questions regarding skewness:

***1. What is skewness? And its types?***

Skewness is a measure of the asymmetry of a distribution. It gives an idea about the shape of the curve obtained by frequency distribution or frequency curve of data. A distribution can have right (or positive), left (or negative), or zero skewness. A right-skewed distribution has a longer tail on its right side, while a left-skewed distribution has a longer tail on its left side.

***2. How is it used?***

Skewness can be used to describe the distribution of a variable alongside other descriptive statistics and to determine if a variable is normally distributed. A normal distribution has zero skewness and is an assumption of many statistical procedures.

# Questions regarding transformations?

***1. What is Transformation?***

Transformation in machine learning refers to the process of converting data from one format or structure to another. This is often done to improve the performance of a model by making the data more suitable for analysis.

***2. Why we Transform data?***

Transforming data can improve the accuracy of certain statistical tests and models. For example, transforming skewed data to make it more normally distributed can improve the accuracy of certain statistical tests and models. Additionally, transforming categorical variables into numerical values can make them easier to use in certain algorithms.

***3) What is PowerTransformer? And its use?***

**PowerTransformer** is a preprocessing method used to transform features to a normal distribution. It applies a power transformation to each feature to make the data more Gaussian-like. 

This can be useful when features have skewed distributions, as it can help improve the performance of some machine learning algorithms.

***4) What is Log Transformer?***

**LogTransformer** is a preprocessing method used to transform features by taking their logarithm. It can be useful when features have skewed distributions, as it can help reduce skewness and make the data more Gaussian-like. This can help improve the performance of some machine learning algorithms.

### Questions regarding scaling and Encoding?

**1) What is StandardScalar? And its use?**

**StandardScaler** is a preprocessing method used to standardize features by removing the mean and scaling to unit variance. It scales each feature such that its mean is 0 and its standard deviation is 1. 

This can be useful when features have different scales and units, as it can help improve the performance of some machine learning algorithms.

**2) What is ordinal and one hot encoding?**

***Ordinal encoding*** is a method for encoding categorical variables as integers where the order of the integers represents the order of the categories.

***One hot encoding*** is a method for encoding categorical variables as binary vectors where each category is represented by a separate binary feature.

## Observations after applying all ML models:

**Observations:**

1. The highest R2 scores were achieved by the Random Forest and XGBoost models after cross-validation (CV) and hyperparameter tuning with 86%.

2. The lowest R2 scores were achieved by the linear regression (LR), Lasso, and Ridge models with 66%.

3. Cross-validation and hyperparameter tuning improved the performance of the Decision Tree model, increasing its R2 score from 73 to 80.

4. Cross-validation and hyperparameter tuning had a smaller effect on the performance of the Random Forest model, increasing its R2 score from 83 to 85.

5. The Gradient Boosting model achieved an R2 score of 84, which is the same as the Random Forest model before CV and hyperparameter tuning.

6. The XGBoost model achieved the highest R2 score of all models, with a score of 86 along with Random Forest.

7. Overall, tree-based models (Decision Tree, Random Forest, Gradient Boosting, XGBoost) performed better than linear models (LR, Lasso, Ridge) in predicting TED talk views.

8. Cross-validation and hyperparameter tuning can improve model performance, as seen with the Decision Tree and Random Forest models.

9. The choice of model can have a significant impact on prediction performance, as seen by the differences in R2 scores between the different models.

## Final Conclusion:

By performing all appropriate testings and trainings we conclude that the ***XGBoost Regressor*** model and ***Random Forest Regressor*** is the best choice for predicting TED talk views with R-Square value of 86% and 85.6%. 
