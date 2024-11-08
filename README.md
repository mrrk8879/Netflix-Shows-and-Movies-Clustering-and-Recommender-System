# **Netflix Shows and Movies Clustering and Recommender System**
This project explores a dataset of TV shows and movies available on Netflix as of 2019. The primary goals were to extract insights through clustering analysis and develop a recommender system to suggest similar shows based on the clustering model.

## **File of Contents**

1. Introduction

2. Dataset

3. Data Preprocessing

4. Clustering Approach

5. Recommender System

6. Hypothesis Testing

7. Conclusion

8. Installation and Usage

## **1. Introduction**

Clustering is an unsupervised learning method to group similar objects based on their characteristics. This technique has many applications, such as market segmentation, anomaly detection, image segmentation, and recommendation systems. In this project, clustering was applied to group similar Netflix shows and movies based on various features, enabling the creation of a recommender system.

## **2. Dataset**

The dataset, sourced from Flixable (a third-party Netflix search engine), consists of 7,787 rows and 12 columns. Key columns include:

1. Show ID: Unique identifier

2. Type: TV show or movie
   
3. Title: Show title
   
4. Director: Director of the show
   
5. Cast: Actors in the show
    
6. Country: Producing nation
    
7. Date Added: Date added to Netflix
    
8. Release Year: Year of release
    
9. Rating: Show rating
    
10. Duration: Length of the show (in minutes for movies, seasons for TV shows)
    
11. Genre: Show genre
    
12. Description: Brief description

    
## **3. Data Preprocessing**

**Data preprocessing included the following steps:**

### **I. Handling Missing Values:**

a. Columns with missing values: Director, Cast, Country, Date Added, and Rating.

b. Imputed missing values in 4 columns by replacing with "unknown."

c. Dropped null values in Date Added (0.09% missing data).

### **II. Data Transformation:**

a. Extracted the number of movies and TV shows each actor appeared in.

b. Created a new DataFrame containing only movie details and converted duration to integer for movies.

c. Processed Country and Genre columns to consider only the first entry.

d. Converted Date Added to datetime format and extracted the year in a new Year Added column.

e. Created a Latest column to indicate if a show was added the same year it was released.

f. Standardized rating values.

### **III. Text Processing:**

a. Used NLP techniques on selected columns (Director, Cast, Country, Genre, Description, and Rating) for clustering.

b. Vectorized text data using TFIDF (Term Frequency-Inverse Document Frequency) for meaningful representation.

c. Scaled data using Standard Scaler and applied PCA (Principal Component Analysis) to reduce dimensionality.

## **4. Clustering Approach**

**Two clustering algorithms were applied:**

### **I. K-Means Clustering:**

a. Optimal value of K was chosen using the elbow method and silhouette scores from 1 to 25.

b. Final model: K = 5, with a variance of 58185 and a silhouette score of 0.458.

### **II. Agglomerative Hierarchical Clustering:**

a. Optimal number of clusters determined by dendrogram analysis.

b. Final model: 11 clusters, achieving a silhouette score of 0.389.

## **Final Choice:**
K-Means was selected due to its higher silhouette score, indicating better-defined clusters.

## **5. Recommender System**

Using the K-Means clustering model, a recommender system was developed to suggest similar shows. The recommender suggests shows based on their position within the clusters, allowing users to find similar content.

## **6. Hypothesis Testing**

**Two hypothesis tests were conducted:**

### **I. Sample Mean and Population Mean of Release Year:**

Tested whether the sample mean equals the population mean. The null hypothesis could not be rejected.

### **II. Normality Test for Movie Duration:**

Tested if the duration of movies is normally distributed. The null hypothesis was rejected, indicating that movie duration is not normally distributed.

## **7. Conclusion**

This project successfully grouped Netflix shows and movies into clusters and developed a recommender system based on these clusters. K-Means clustering outperformed Agglomerative Hierarchical Clustering in this scenario. Insights about clustering show how Netflix's collection can be organized based on various show attributes, making it easier for users to find similar content.

## **8. Installation and Usage**

### **I. Requirements**

a. Python 3.7+

b. Required libraries: pandas, numpy, sklearn, scipy, matplotlib, seaborn, wordcloud, nltk

### **II. Steps to Run**

a. Clone the repository and navigate to the project directory.

b. Install the required libraries.
    
c. Run the Jupyter Notebook or Python scripts to preprocess data, conduct clustering, and run the recommender system.
