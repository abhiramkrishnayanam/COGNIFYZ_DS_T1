# COGNIFYZ_DS_T1
# Task 1 : Data Exploration and Preprocessing:
## Understanding the Data
The dataset appears to contain detailed information about restaurants, likely from a restaurant review or food delivery platform. 
##### Dataset Use Cases
This dataset is likely about restaurant reviews, ratings, and delivery services and can be used for:

* Customer Analysis: Understanding preferences, ratings, and feedback.
* Geospatial Insights: Mapping restaurant locations and analyzing city/locality-based trends.
* Price and Cuisine Trends: Exploring how price ranges and cuisines vary across regions.
* Rating and Popularity Trends: Identifying highly-rated or popular restaurants.
* Business Opportunities: Spotting gaps in services, like areas lacking table booking or online delivery.


### Problem Statement(Task 1) :
Explore the dataset and identify the number
of rows and columns.<br>
Check for missing values in each column and
handle them accordingly.<br>
Perform data type conversion if necessary.<br>
Analyze the distribution of the target variable
("Aggregate rating") and identify any class
imbalances.<br>

### This repository focuses on the exploration and cleaning of a dataset. The main objective is to:

* Identify the structure of the dataset (number of rows and columns).
* Check for missing values in each column.
* Handle missing values appropriately.
### Steps Involved
#### 1. Dataset Exploration

* Rows and Columns: Determine the number of rows and columns in the dataset to understand its dimensionality.
* Column Overview: Review column names, data types, and a brief summary of the data.

#### 2. Missing Values

##### Missing Value Check: Identify columns with missing data.
##### Handling Missing Values: Apply suitable strategies to manage missing values, such as:
* Filling with statistical measures (mean, median, mode).
* Forward or backward filling.
* Removing rows or columns with excessive missing data.

#### Finding Imbalance in target variable ie; Aggregate rating
For that a histogram is plotted using seaborn.
```
sns.histplot(df['Aggregate rating'],bins=7)
plt.title('Distribution of Aggregate rating')
plt.xlabel('Aggregate rating')
plt.ylabel('Frequency')
plt.show()
```
![image](https://github.com/user-attachments/assets/6751672e-0bad-418f-be08-6a05d01f351e)

##### I found the proportion percentage for each rating to find the imbalance.
For that :<br>
* Find the total:
```
#we need total as a single value
agre_data["count"] = pd.to_numeric(agre_data["count"], errors="coerce")# ensure the 'Count' data contains only numerical value.
total = agre_data["count"].sum()
print(total)
```

* Then found the Proportion percentage for each value of Aggregate rating.
  ```
  # Calculate the Proportion (%)
agre_data["Proportion (%)"] = (agre_data["count"] / total) * 100
```
* A bar chart showing the relation between 'Proportion percetage' with 'Aggregate rating' is plotted.

![image](https://github.com/user-attachments/assets/e4b658a1-2c4e-43dc-a6d4-a9100fdf7e78)

![image](https://github.com/user-attachments/assets/b10baaef-2941-414f-89c5-06e6f0c86b89)

##### Ensured that zero rating is the main imbalance in the Aggregate rating , as it shows high 'Proportion percentage' (22.489792)
### Observations:
* Most Overrepresented Rating:<br>

The rating 0.0 Aggregate rating for 22.49% of the total ratings, significantly higher than any other rating. This indicates a strong concentration at the lowest rating level, which creates an imbalance.



