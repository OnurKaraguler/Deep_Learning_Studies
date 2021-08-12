## Titanic - Deep Learning from Disaster

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
  (4) Create A Neural Network<br>
      <ul>
        <li>Graphs for Neural Network</li>
        <li>Building Artificial Neural Network (ANN)</li>
            <img height="250" alt="image" src="https://user-images.githubusercontent.com/58983814/129193067-945a6e52-bf64-4f80-b58a-d7149ec95bb3.png">
        <li>Building Convolutional Neural Network (CNN)</li>
            <img height="250" alt="image" src="https://user-images.githubusercontent.com/58983814/129193571-2221b9f1-83db-4070-a832-aab8f4ec2517.png">
        <li>Evaluation of the model</li>
            <img height="250" alt="image" src="https://user-images.githubusercontent.com/58983814/129193725-6793f6e1-a947-4df7-ada4-c3c980f3989d.png"> <img height="250" alt="image" src="https://user-images.githubusercontent.com/58983814/129193827-804b64fe-2f95-4427-9fc8-24d39200c260.png">
      </ul>
  (5) Submission<br>
      <ul>
        <li>[5.1 Results on the Kaggle website](#51)</li>
        <img height="200" alt="image" src="https://user-images.githubusercontent.com/58983814/129194133-0334c9ad-ee6e-4a14-bf3c-8622bea7b8ac.png">
      </ul>
