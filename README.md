# Cars Data Analysis Using Pandas

## (A part of Big Data Analysis)

## About Cars Dataset
### Here, 
### The data of different cars is given with their specifications. This data is available as a CSV file. I'm going to analyze this data set using the Pandas DataFrame.

 ``` python
car.shape
```

## 1) - Find all Null Values in the dataset. If there is any null value in any column, then fill it with the mean of that column. 
```python
car.isnull().sum()

car['Cylinders'].fillna(car['Cylinders'].mean(), inplace = True)
```

## 2) - Check what are the different types of Make are there in our dataset. And, what is the count (occurrence) of each Make in the data ?
```python
car['Make'].value_counts()
```

## 3) - Show all the records where Origin is Asia or Europe.
``` python
car[car['Origin'].isin(['Asia', 'Europe'])]
car['Origin'].value_counts()
```


## 4) - Remove all the records where Weight is above 4000.
```python
[~(car['Weight'] > 4000)]
```


## 5) - Increase all the values of 'MPG_City' column by 3.
```python
car['MPG_City'] =  car['MPG_City'].apply(lambda x:x+3)
```


# Findings

### 1. Missing Values: Some columns had null values. These were successfully handled by filling them with the column-wise mean, ensuring no data loss.
### 2. Make Distribution: The dataset contains multiple car manufacturers. The frequency count showed which makes dominate the dataset and which are rare.
### 3. Regional Insights: Cars from Asia and Europe were filtered, highlighting regional representation and making it easy to compare design and performance trends.
### 4. Weight Constraint: Cars with a weight greater than 4000 lbs were removed to focus on more commonly used passenger cars rather than unusually heavy vehicles.
### 5. Fuel Efficiency Update: The MPG_City values were adjusted upward by 3, reflecting an improved mileage scenario and allowing for comparative analysis under updated assumptions.



# Conclusion

### The project successfully demonstrated the application of data cleaning, filtering, and transformation techniques in Pandas. By addressing missing values, exploring categorical distributions, applying conditional filters, and adjusting numerical columns, the dataset was transformed into a more reliable and interpretable form.
### Overall, the analysis improved data quality, uncovered manufacturer distribution patterns, and highlighted regional variations, making the dataset ready for deeper exploration such as performance comparison, trend analysis, or predictive modeling.
