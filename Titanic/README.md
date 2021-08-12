## Titanic - Machine Learning from Disaster

The purpose of the study is to build a predictive model that answers the question: “what sorts of people were more likely to survive?” using passenger data (ie name, age, gender, socio-economic class, etc).

The study consists of:<br>
  (1) Importing Libraries<br>
  (2) Loading the data<br>
  <ul>
      <li>created dataframes by reading cvs files with Pandas</li>
      <li>checked whether the dependent variable is balanced or imbalanced.</li>
      <img height="100" alt="image" src="https://user-images.githubusercontent.com/58983814/127742868-d63b26e4-8af7-4929-9e36-f36559ab3549.png">
      <li>checked for missing values</li>
  </ul>
  
  (3) Data Preprocessing<br>
      <ul>
        <li>[3.1 Functions to be used](#31)</li>
            <ul>
              <li>Visualizations</li>
                  <ul>
                    <li>stacked_bar_chart: plot a stacked bar chart to show how a feature is categorized using the independent feature</li>
                    <img height="100" alt="image" src="https://user-images.githubusercontent.com/58983814/127743327-a5b9656e-bed2-477f-b48a-16069a10d907.png">
                    <li>box_plot: plot a boxplot to show how the values in the dataset are spread out</li>
                    <img height="100" alt="image" src="https://user-images.githubusercontent.com/58983814/127743417-dc07ef52-4904-45b0-b3ad-32fea92ce181.png">
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
            <ul>
              <li>Missing value imputation  </li>
                  <ul>
                    <li>imputing_missing_values: replace missing values in data with substitute values</li>
                  </ul>
            </ul>
        <li>[3.2 Analyze each feature](#32)</li>
              <ul>
                <li>Each feature examined in depth using related visualization functions</li>
                <li>Encoded</li>
                <li>Dropped outliers and standardised</li>
              </ul>
        <li>[3.3 Feature Engineering](#33)</li>
            <img height="100" alt="image" src="https://user-images.githubusercontent.com/58983814/127749043-f5b849f7-1f48-4f5b-bfff-300f6a21aa62.png">
              <ul>
                <li>removed the features that they have at least 99% same value</li>
                <li>removed duplicate features </li>
                <li>dropped highly correlated features using Pearson Correlation</li>
                <li>first feature elimination done with SelectFromModel according to their importance assigned by logistic regression</li>
                <li>best features selected with Univariate feature selection (GenericUnivariateSelect and SelectKBest) based on univariate statistical tests (ANOVA F-value and Mutual Information)</li>
              </ul>
          <li>[3.4 Correlation of the features](#34)</li>
              <ul>
                <li>plot the correlation of the features where the correlation with the dependent feature is greater than 0.2</li>
                <img height="100" alt="image" src="https://user-images.githubusercontent.com/58983814/127752709-ba5d253b-6af5-4164-ae80-d247493e473a.png">
              </ul>
      </ul>
  (4) Machine Learning Algorithms and Results<br>
      <ul>
        <li>[4.1 Building ML models](#41)</li>
            <ul>
              <li>Logistic, Random Forest, Naive Bayes, Support Vector Classification, k-Nearest Neighbours, Stochastic Gradient Descent, Gradient Boosting Trees, xgboost -> XGBClassifier</li>
            </ul>
        <li>[4.2 Model selection - final](#42)</li>
              <ul>
              <li>best model selected according to the accuracy</li>
                <img height="150" alt="image" src="https://user-images.githubusercontent.com/58983814/128779894-627ea6e5-c8b4-4000-8748-e5bb31aa0edf.png">
            </ul>
        <li>[4.3 Evalueation of the selected model](#43)</li>
              <ul>
              <li>finally, feature engineering has been done again with SequentialFeatureSelector. SequentialFeatureSelector chooses the best features based on the cross-validation score of an estimator (the selected best model) to form a feature subset.</li>
              <li>computed and visually represented confusion matrix to evaluate the accuracy of a classification</li>
                <img height="150" alt="image" src="https://user-images.githubusercontent.com/58983814/128780166-4e265e4d-9e06-42b7-906d-de27d080136d.png"> <img height="150" alt="image" src="https://user-images.githubusercontent.com/58983814/128780232-e38aa92e-7fec-4062-90da-c4d4b95d70fa.png">
              <li>Graphs for threshold determination</li>
                    <ul>
                      <li>ROC & AUC</li>
                      <img height="150" alt="image" src="https://user-images.githubusercontent.com/58983814/128780798-20e6e6d4-13c8-4255-af1e-5a9e36e9210c.png">
                      <li>TPR & TNR - Threshold </li>
                      <img height="150" alt="image" src="https://user-images.githubusercontent.com/58983814/128780875-188cf512-aa49-4fde-81b0-bba2be5aec4f.png">
                      <li>Precision(PPV) & NPV - Recall</li>
                      <img height="150" alt="image" src="https://user-images.githubusercontent.com/58983814/128780964-7d8a095a-cdfb-4927-81d7-dfc9034693b2.png">
                      <li>Accuracy - Threshold</li>
                      <img height="150" alt="image" src="https://user-images.githubusercontent.com/58983814/128781082-f2fc47ee-aa96-41c0-93f2-14fbb4f1bf7f.png">
                    </ul>
                <li>final Confusion Matrix with the new Threshold</li>
                <img height="150" alt="image" src="https://user-images.githubusercontent.com/58983814/128781233-3c009afb-3c51-4341-b7dd-258a4b6f621e.png"> <img height="150" alt="image" src="https://user-images.githubusercontent.com/58983814/128781270-d81ed766-61b3-4120-bc2a-3762eb0f08ec.png">
            </ul>
      </ul>
  (5) Submission<br>
      <ul>
        <li>[5.1 Results on the Kaggle website](#51)</li>
              <img height="150" alt="image" src="https://user-images.githubusercontent.com/58983814/127753765-de7d0ee9-8a94-479c-8d67-556523b0adbb.png"> <img height="150" alt="image" src="https://user-images.githubusercontent.com/58983814/128781345-7c6aa925-e377-4bd6-8911-d31b4437edc7.png">
      </ul>

