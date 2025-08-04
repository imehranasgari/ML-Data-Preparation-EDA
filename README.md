# Google Play Store Apps Analysis

## Project Title
Mini Project  - Google Play Store Apps

## Problem Statement  
This project is an exploratory data analysis (EDA) of the Google Play Store apps dataset, with the goal of visually exploring trends and uncovering relationships between app categories, features, and user demographics. Emphasis is placed on understanding data distributions and demonstrating the capabilities of popular Python data science libraries.

## Solution Approach  
By conducting comprehensive data preprocessing and a range of insightful visualizations, the project demonstrates how EDA can reveal meaningful patterns, connections between categories and audience, and key characteristics of applications—while also showcasing the functionality of libraries like pandas, numpy, matplotlib, seaborn, and scikit-learn.

**Data Loading and Initial Inspection:**
- The dataset `googleplaystore.csv` is loaded into a pandas DataFrame.
- Initial information about the DataFrame, including data types and non-null counts, is displayed using `df.info()`.
- Column names are inspected.

**Exploratory Data Analysis (EDA):**
- Descriptive statistics of the numerical columns are generated using `df.describe()`.
- The number of unique values in each column is counted to understand data diversity.
- The shape (number of rows and columns) of the DataFrame is determined.
- Applications with the highest ratings are identified and displayed.

**Data Preprocessing:**
- **Missing Values:**
    - The number of missing values in each column is identified.
    - Rows with missing 'Rating' values are inspected to understand their characteristics (e.g., low reviews, specific categories like BEAUTY and BOOKS_AND_REFERENCE, and being free).
    - Missing values in the 'Rating' column are filled using the median.
    - Any remaining rows with missing values are dropped.
- **Feature Transformation:**
    - The 'Type' column (Free/Paid) is converted into numerical representation (0 for Free, 1 for Paid) using `LabelEncoder`.
    - The 'Installs' column is cleaned by removing non-numeric characters (like '+' and ',') and converted to an integer type.
    - The 'Price' column is cleaned by removing the '$' sign and converted to a numeric (float) type.
    - The 'Reviews' column is converted to a numeric (integer) type.
- **'Content Rating' and 'Category' Analysis:**
    - Value counts for 'Content Rating' and 'Category' columns are inspected.
    - Missing values in 'Content Rating' are handled by dropping them and then filling with the mode (though the code shows dropping and then filling, the `dropna` earlier would have removed them).
- **'Size' Column Transformation:**
    - The 'Size' column, which contains 'M' (megabytes), 'k' (kilobytes), and 'Varies with device' values, is converted to a uniform numerical format (megabytes).
    - 'M' values are converted to kilobytes and then to megabytes.
    - 'k' values are converted to megabytes.
    - 'Varies with device' values are replaced with the mean of the 'Size' column.
    - The 'Size' values are rounded to two decimal places.

**Visualization:**
- Histograms of all numerical columns are plotted to visualize their distributions.
- A histogram showing the distribution of 'Rating' colored by 'Content Rating' is generated to understand rating patterns.
- A count plot is created to show the number of apps in each 'Category', differentiated by 'Type' (Free/Paid).
- A bar plot is generated to visualize the total number of installations for each 'Category', also differentiated by 'Type'.

## Technologies & Libraries
- **Python**: The primary programming language used.
- **NumPy**: For numerical operations.
- **Matplotlib**: For creating static, interactive, and animated visualizations.
- **Seaborn**: For statistical data visualization based on Matplotlib.
- **Pandas**: For data manipulation and analysis.
- **Scikit-learn (sklearn.preprocessing.LabelEncoder)**: For encoding categorical labels into numerical format.

## Key Results / Performance
**Data Overview:**
- The dataset contains 10841 rows and 13 columns.
- After preprocessing, 10829 rows remain.

**Rating Distribution:**
- The mean rating is approximately 4.19.
- Most apps have high ratings (around 4.0 to 4.5).
- There are very few programs with low ratings, suggesting users might prefer not to rate unsuitable apps.
- The majority of apps are rated for "Everyone".

**App Categories and Type:**
- The most common app categories are 'FAMILY', 'GAME', and 'TOOLS'.
- Free programs are significantly more numerous than paid programs.
- Free programs have a much higher number of installations compared to paid programs.
- 'COMMUNICATION', 'SOCIAL', 'VIDEO_PLAYERS', and 'PRODUCTIVITY' categories have the highest number of installations, predominantly for free apps.

**Data Cleaning and Transformation:**
- Missing 'Rating' values were successfully imputed using the median.
- Categorical 'Type' data was converted to numerical (0 for Free, 1 for Paid).
- 'Installs' and 'Price' columns were successfully converted to numerical types by removing special characters.
- The 'Size' column was standardized to megabytes, with 'Varies with device' values replaced by the mean size.


**My Insight:**
- Free, small-sized apps (around 20MB) in categories like Communication, Social, Video, Games, Travel, and Photography attract the most users on Google Play.
---

# **Author:** mehran Asgari
## **Email:** [imehranasgari@gmail.com](mailto:imehranasgari@gmail.com).
## **GitHub:** [https://github.com/imehranasgari](https://github.com/imehranasgari).

---

## 📄 License

This project is licensed under the MIT License – see the `LICENSE` file for details.