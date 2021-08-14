## Customer Churn Analysis

This data set contains details of a bank's customers and the target variable is a binary variable reflecting the fact whether the customer left the bank (closed his account) or he continues to be a customer.

The study consists of:<br>
  (1) Importing Libraries<br>
  (2) Loading the data<br>
  <ul>
      <li>created dataframes by reading cvs files with Pandas</li>
      <li>checked whether the dependent variable is balanced or imbalanced.</li>
          <img height="100" alt="image" src="https://user-images.githubusercontent.com/58983814/128782908-8fff5875-1094-4754-9e9d-65d7ad01dbd8.png">
      <li>checked for missing values</li>
  </ul>
  
  (3) Data Preprocessing<br>
      <ul>
        <li>[3.1 Functions to be used](#31)</li>
            <ul>
              <li>Visualizations</li>
                  <ul>
                    <li>stacked_bar_chart: plot a stacked bar chart to show how a feature is categorized using the independent feature</li>
                    <img height="100"  alt="image" src="https://user-images.githubusercontent.com/58983814/128782985-610590b2-ede2-403a-b4b7-d479aa5c2e85.png">
                    <li>histogram: plot a histogram to show how a continuous variable is distributed</li>
                    <img height="100" alt="image" src="https://user-images.githubusercontent.com/58983814/128783759-2abbf071-3539-43e0-ae61-028c6279f60d.png">
                    <li>box_plot: plot a boxplot to show how the values in the dataset are spread out</li>
                    <img height="100" alt="image" src="https://user-images.githubusercontent.com/58983814/128783086-d21c7b97-6bc1-474f-964f-631d7634da57.png">
                  </ul>
            </ul>
            <ul>
              <li>Encoding </li>
              <img height="100" alt="image" src="https://user-images.githubusercontent.com/58983814/127749099-7ab7e089-9504-45f9-b4dd-33f9a9103834.png">
                  <ul>
                    <li>ohe_to_df: One Hot Encoding-find the unique values per feature and transform the data to a binary one-hot encoding</li>
                    <li>encode_categorical_column: Convert each value in a categorical column to a number from 0 to the number of items-1 by encoding</li>
                  </ul>
            </ul>
            <ul>
              <li>KBinsDiscretizer </li>
                  <ul>
                    <li>is used to convert a continuous data into categorical data</li>
                  </ul>
            </ul>
            <ul>
              <li>Standardization (StandardScaler)  </li>
                  <ul>
                    <li>transform(scale) the mean of a feature to be 0 and the standard deviation to be 1</li>
                  </ul>
            </ul>
        <li>[3.2 Analyze each feature](#32)</li>
              <ul>
                <li>Each feature examined in depth using related visualization functions</li>
                <li>Encoded</li>
                <li>Dropped outliers and standardised</li>
              </ul>
        <li>[3.3 Feature engineering](#33)</li>
            <img height="100" alt="image" src="https://user-images.githubusercontent.com/58983814/127749043-f5b849f7-1f48-4f5b-bfff-300f6a21aa62.png">
              <ul>
                <li>removed the features that they have at least 99% same value</li>
                <li>removed duplicate features </li>
                <li>dropped highly correlated features using Pearson Correlation</li>
                <li>first feature elimination done with SelectFromModel according to their importance assigned by logistic regression</li>
                <li>best features selected with Univariate feature selection (GenericUnivariateSelect and SelectKBest) based on univariate statistical tests (ANOVA F-value and Mutual Information)</li>
              </ul>
          <li>[3.4 Correlation of the features](#34)</li>
                <img height="100" alt="image" src="https://user-images.githubusercontent.com/58983814/128784061-72c06d3e-5be4-4198-bb5d-bed45bdbf003.png">
      </ul>
  (4) Create A Neural Network<br>
      <ul>
        <li>Graphs for Neural Network</li>
        <li>[4.1 Overcoming Class Imbalance using SMOTE](#41)</li>
          <ul>
            <li>It is an imbalanced data where the target variable, churn has 79.7% customers not churning and 20.3% customers who have churned</li>
            <li>SMOTE: Synthetic Minority Oversampling Technique will be used for creating synthesized data</li>
            <li>A comparative analysis will be done on the dataset using RandomForestClassifier</li>
            <li>The accuracy metric will be ignored to evaluate the performance of the classifier on this imbalanced dataset</li>
            <li>Precision, recall, F1-score metrics will be taken into account</li>
          </ul>
          <img height="150" alt="image" src="https://user-images.githubusercontent.com/58983814/129427889-fbf96b70-1938-490b-a2b2-3ed41b6f29e5.png">
        <li>[4.2 Building DL models](#41)</li>
          <ul>
            <li>Building Artificial Neural Network (ANN)</li>
            <img height="250" alt="image" src="https://user-images.githubusercontent.com/58983814/129428013-c3f455f7-96cd-4514-a803-a97732a0e55d.png">
            <li>Building Convolutional Neural Network (CNN)</li>
            <img height="250" alt="image" src="https://user-images.githubusercontent.com/58983814/129428034-1e56b1b3-d5a0-4fc2-b886-638f4f464f0b.png">
          </ul>
        <li>Evaluation of the model</li>
        <img height="250" alt="image" src="https://user-images.githubusercontent.com/58983814/129428062-e33ee7d0-9c28-40d6-a3c4-9a1c4edbc639.png"> <img height="250" alt="image" src="https://user-images.githubusercontent.com/58983814/129428105-c991a3e3-e7df-489f-9a99-b02b1b1c2d71.png">
      </ul>
