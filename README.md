# K-Means-Segmentation-Project

# Context
This project applies K-Means clustering, an unsupervised machine learning algorithm, to segment customers based on their demographic and behavioral data. The dataset, Mall_Customers.csv, contains information such as Customer ID, Gender, Age, Annual Income, and Spending Score. The primary goal is to identify distinct customer groups within a retail context to enable targeted marketing strategies, personalized product recommendations, and improved customer relationship management.

# Actions & Techniques Applied
Data Acquisition and Initial Inspection:

The Mall_Customers.csv dataset was loaded into a pandas DataFrame.

Initial data exploration included viewing the first few rows (df.head()), generating descriptive statistics (df.describe()), and checking for null values (df.isnull().sum()) and data types (df.info()).

Data Cleaning & Preprocessing:

Column Renaming: Columns with less user-friendly names (Annual Income (k$) and Spending Score (1-100)) were renamed to Annual Income and SpendingScore for clarity and easier access.

Missing Value Check: Confirmed that there were no missing values in the dataset, ensuring data completeness for clustering.

# Exploratory Data Analysis (EDA) & Visualization:

Pair Plots: seaborn.pairplot was used to visualize the relationships and distributions of key numerical features (Age, Annual Income, SpendingScore). This helped in understanding potential correlations and identifying initial patterns.

Scatter Plots:

A scatter plot of Annual Income vs. Spending Score was generated to visually inspect the distribution of customers and identify any natural groupings before clustering. This plot clearly showed distinct clusters.

A similar scatter plot of Age vs. Spending Score was also created to explore other potential segmentation dimensions.

# K-Means Clustering Model Development:

Feature Selection: Two main sets of features were used for clustering:

X = df[['Annual Income', 'SpendingScore']] for income-spending based segmentation.

X = df[['Age', 'SpendingScore']] for age-spending based segmentation.

Determining Optimal Number of Clusters (Elbow Method):

The Within-Cluster Sum of Squares (WCSS) was calculated for a range of cluster numbers (1 to 10).

The "Elbow Method" was applied by plotting WCSS against the number of clusters. The "elbow point" in the plot indicated the optimal number of clusters. For Annual Income and SpendingScore, the elbow was clearly at 5 clusters.

The elbow method was also applied for Age and SpendingScore, suggesting 4 clusters as optimal.

Model Training: KMeans from sklearn.cluster was used to train the clustering models with the identified optimal number of clusters (n_clusters=5 for income/spending and n_clusters=4 for age/spending), using k-means++ initialization for robust centroid selection.

# Cluster Assignment and Visualization:

The fit_predict() method was used to assign each customer to a specific cluster.

New columns (Cluster and ClusterAge) were added to the DataFrame to store the assigned cluster labels.

Cluster Visualization: Scatter plots were generated, coloring data points by their assigned cluster and marking the cluster centroids with 'X's. This provided a clear visual representation of the segmented customer groups.

Customer segments based on Annual Income and Spending Score (5 clusters).

Customer segments based on Age and Spending Score (4 clusters).

# Results
Identified Customer Segments: The project successfully identified distinct customer segments based on their annual income, spending score, and age. For instance, the income-spending analysis revealed groups like "high income, high spending" and "low income, low spending," among others.

Actionable Insights for Marketing: The derived customer segments provide actionable insights for businesses to tailor marketing campaigns, product offerings, and customer service strategies to specific groups, maximizing effectiveness and ROI.

Optimal Cluster Determination: The effective use of the Elbow Method demonstrated a data-driven approach to determine the most appropriate number of clusters, ensuring meaningful and stable segmentation.

Enhanced Understanding of Customer Behavior: By visualizing the clusters, the project offers a clear understanding of customer behavioral patterns, allowing businesses to cater to diverse customer needs more effectively.

Proficiency in Unsupervised Learning: The project showcases strong skills in applying K-Means clustering, a fundamental unsupervised learning technique, for real-world business problems like customer segmentation.
