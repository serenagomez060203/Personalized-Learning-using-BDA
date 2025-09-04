# Personalized Learning using Big Data Analytics

## Abstract

This project leverages PySpark to develop a personalized learning system based on student performance data. The dataset includes variables such as student ID, gender, study time, and grades (G1, G2, G3). Using Spark’s capabilities, the dataset is first cleaned and processed, with missing values handled through imputation. Feature engineering is applied to calculate an average grade and encode categorical features like gender and study time.

KMeans clustering is utilized to group students into clusters based on their performance. These clusters are then used to provide personalized learning resource recommendations. The project concludes with a visual analysis of the clustering results, demonstrating patterns in student performance and offering tailored learning materials for each group. This approach showcases the potential of data-driven, personalized educational experiences aimed at improving student outcomes.

---

## Tools & Technologies Used

- **PySpark**: Distributed data processing, data cleaning, and feature engineering.
- **KMeans Clustering**: Grouping students based on grades and study time.
- **Seaborn & Matplotlib**: Data visualization and scatter plots.
- **Pandas**: DataFrame conversion for easier manipulation and plotting.
- **Jupyter Notebook / Google Colab**: Interactive execution environment.

---

## Dataset

The dataset contains the following key columns:

- `student_id`: Unique identifier for each student.
- `gender`: Gender of the student (categorical).
- `study_time`: Study time categorized into ranges (e.g., "<2 hours").
- `G1`, `G2`, `G3`: Grades from three assessment periods.

Additional transformations:
- Created `average_grade` from G1, G2, G3.
- Encoded categorical features (gender, study_time) into numeric format.
- Handled null values by filling with 0.

---

## Sample Data & Clustering Results

### Schema Preview:
|-- student_id: string (nullable = true)
|-- gender: string (nullable = true)
|-- study_time: string (nullable = true)
|-- G1: integer (nullable = true)
|-- G2: integer (nullable = true)
|-- G3: integer (nullable = true)


### Clustering Output (Top 20 Rows):

| student_id | study_time    | features           | prediction |
|------------|---------------|--------------------|------------|
| STUDENT_1  | 5-10 hours    | [3.0,16.0,18.0,10.0] | 2          |
| STUDENT_2  | <2 hours      | [0.0,8.0,9.0,12.0]   | 1          |
| STUDENT_3  | <2 hours      | (4,[2],[14.0])       | 1          |
| STUDENT_4  | >10 hours     | [1.0,20.0,7.0,5.0]   | 0          |
| STUDENT_5  | 5-10 hours    | [3.0,19.0,1.0,8.0]   | 0          |

### Personalized Recommendations:

| student_id | recommended_resources                          |
|------------|-----------------------------------------------|
| STUDENT_1  | [Statistics Course, Data Analysis Video]      |
| STUDENT_2  | [Advanced Calculus Book, Calculus Quiz]       |
| STUDENT_3  | [Advanced Calculus Book, Calculus Quiz]       |
| STUDENT_4  | [Basic Algebra Book, Introductory Algebra Video] |
| STUDENT_5  | [Basic Algebra Book, Introductory Algebra Video] |

---

## Visualization

![KMeans Clustering Visualization](clustering_plot.png)

*Scatter plot showing student clusters based on grades (G1 vs G2).*

---

## Conclusion

This project demonstrates the application of PySpark for analyzing and clustering student performance data. By utilizing KMeans clustering, students are grouped based on their study habits and grades, allowing for personalized learning recommendations. The results offer valuable insights into patterns of student performance, with recommendations tailored to each cluster. The use of distributed computing with PySpark ensures scalability for larger datasets, while the visualizations provide a clear understanding of the clustering results. This approach highlights the potential of data-driven educational tools for enhancing personalized learning experiences.

---

## Tags

#PySpark #BigData #DataAnalytics #MachineLearning #KMeans #PersonalizedLearning #Education #Clustering #DataVisualization #Python #Jupyter #Colab #StudentPerformance #FeatureEngineering #DistributedComputing
