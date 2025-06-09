# InternshipTask05


Exploratory Data Analysis (EDA) performed on the Titanic dataset:

Step 1: Initial Data Loading and Inspection

Action: Loaded the train.csv dataset into a pandas DataFrame.
Information Gathered:
Checked basic dataset information (.info()) to understand data types and non-null counts for each column.
Obtained descriptive statistics (.describe()) for numerical columns (mean, std, min, max, quartiles).
Analyzed value counts (.value_counts()) for key categorical columns like 'Survived', 'Pclass', 'Sex', and 'Embarked' to understand their distribution.
Identified the number of missing values (.isnull().sum()) in each column, noting significant missing data in 'Age', 'Cabin', and 'Embarked'.
Step 2: Missing Value Handling

Action:
Imputed missing 'Age' values with the median age to handle numerical missing data robustly.
Imputed missing 'Embarked' values with the mode (most frequent port) as it's a categorical feature.
Dropped the 'Cabin' column entirely due to its high percentage of missing values (over 70%), which would make reliable imputation or direct use challenging for a basic EDA.
Step 3: Visual Exploration - Histograms of Numerical Features

Action: Generated histograms for 'Age', 'Fare', 'SibSp', and 'Parch'.
Observations:
'Age' showed a slightly right-skewed distribution, peaking around 20-30 years, with a notable number of children.
'Fare' was highly right-skewed, indicating most passengers paid low fares, with a few paying very high fares.
'SibSp' and 'Parch' distributions revealed that the majority of passengers traveled alone or with very few family members.
Step 4: Visual Exploration - Boxplots for Numerical Features by Survival

Action: Created boxplots comparing 'Age' and 'Fare' distributions against 'Survived' status.
Observations:
Age vs. Survival: The median age for non-survivors was slightly higher, with a slightly wider age range for those who perished.
Fare vs. Survival: Survivors generally paid significantly higher fares, indicating a strong correlation between fare (and thus class) and survival chances.
Step 5: Visual Exploration - Countplots for Categorical Features

Action: Produced countplots for 'Survived', 'Pclass', 'Sex', and 'Embarked'.
Observations:
Overall Survival: More passengers did not survive than survived.
Passenger Class: 3rd class had the most passengers, followed by 1st and 2nd.
Gender: There were more male passengers than female passengers.
Port of Embarkation: Southampton ('S') was the most common embarkation port.
Step 6: Visual Exploration - Countplots for Categorical Features vs. Survived

Action: Generated countplots to show survival rates across 'Pclass', 'Sex', and 'Embarked'.
Observations:
Survival by Pclass: 1st class had the highest survival rate, 3rd class the lowest.
Survival by Sex: Females had a significantly higher survival rate than males (strongest factor).
Survival by Embarked: Passengers from Cherbourg ('C') showed a relatively higher survival rate.
Step 7: Visual Exploration - Pairplot of Numerical Features by Survival

Action: Created a pairplot for selected numerical features ('Age', 'Fare', 'SibSp', 'Parch', 'Survived') to visualize their pairwise relationships and distributions, colored by survival status.
Observations: This plot visually confirmed that higher fares correlate with survival and highlighted that larger family sizes (higher SibSp/Parch) were associated with lower survival rates.
Step 8: Visual Exploration - Correlation Heatmap of Numerical Features

Action: Generated a heatmap showing the correlation matrix of all numerical features.
Observations:
Fare had a positive correlation with Survived, and Pclass had a negative correlation (meaning 1st class correlates with survival).
SibSp and Parch were positively correlated with each other.
Age showed a very weak correlation with Survived.
Step 9: Visual Exploration - Scatterplots

Action: Created scatterplots for 'Age vs. Fare', 'Age vs. Pclass', and 'SibSp vs. Parch', colored by 'Survived' status.
Observations:
Age vs. Fare by Survival: Reinforced that high-fare passengers predominantly survived.
Age vs. Pclass by Survival: Clearly showed the age distribution within each class and how survival varied across classes.
SibSp vs. Parch by Survival: Suggested that very large families had lower survival rates.
Summary of Findings:
The EDA concluded that gender (female) and passenger class (1st class, linked to higher fares) were the most significant predictors of survival on the Titanic. While age was less impactful overall, very young children showed better survival rates, and larger family sizes seemed to hinder escape. The embarkation port also showed a subtle correlation, likely due to class demographics.
