## Coursera DataSet Cleaning
Repository created to improve my knowledge in Data Cleaning using the coursera dataset, which can be obtained on [Kaggle](https://www.kaggle.com/datasets/elvinrustam/coursera-dataset/data).

### Level 0

First, we performed an initial analysis to evaluate the structure of the dataset. This analysis revealed the following dataframe attributes:

- The dataframe has _9,595 rows_ and _13 columns_;
- _900 duplicate_ entries were identified;
- Some columns contained missing values.

Additionally, we look at the data types of each column.

### Level 1
At this stage, data cleaning has already begun. Initially, a graph was generated using the **Plotly** library to visualize the percentage of NaN data in each column.

![NaN Values PCT IMG](https://github.com/Guilherme-PS/Coursera-DataSet-Cleaning/assets/114042039/b0b48700-8682-4748-bae5-8044d4d6780c)

Subsequently, the “What you will learn” column was eliminated due to its high percentage of 48% NaN values. Similarly, the "Programming" column was eliminated because it only contained a single value across all entries, and the "Skill Gain" column was removed because it predominantly stored empty Python lists.

After that, the duplicates in the dataframe were removed. Additionally, the NaN values in the "Rating" and "Review" columns were replaced with 0. This decision was based on the observation that rows with NaN values in both columns implied that no one had taken the course, resulting in a lack of ratings and reviews.

NaN values in the "Level" column have been replaced with "Undefined". Additionally, empty entries in the “Duration” column, which represented 2.7% of NaN values, were removed.

Finally, adjustments were made to the values in the “Level” and “Revision” columns:

- The term “level” has been removed from the entries in the “Level” column;
- In the “Review” column, occurrences of “reviews” and commas were eliminated, and then the data was converted to integers.

### Level 2
In the final phase of data cleaning, the "Duration" column underwent conversion to total hours, accommodating various formats such as:

- X hours (approximately);
- Approx. X hours to complete;
- X months at Y hours a week;
- X hour and Y minutes;
- X week of study, Y hours.

For this transformation, we employed the **re** library, facilitating the use of regular expressions (Regex) to detect patterns.

## Data Cleaning Result
After the data cleansing process was completed, the resulting dataframe exhibited the following characteristics:

- It contained _8,451 rows_ and _10 columns_;
- There were _no duplicates or missing values_;
- _Two columns have had their data types corrected_.

Approximately 11% of the values and three columns were removed during the cleaning process.

[![Kaggle](https://img.shields.io/badge/This_Project_on_Kaggle-3cbce8?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/code/guilhermedepaiva/coursera-dataset-cleaning)
