# Data Manipulation Fundamentals Guide - Weeks 7-8

## Introduction

Welcome to the Data Manipulation phase of your AI Engineering journey! These two weeks will introduce you to the fundamental libraries that form the backbone of data analysis in Python: NumPy, Pandas, and Matplotlib. Think of these tools as your Swiss Army knife for handling data - NumPy for numerical operations, Pandas for structured data manipulation, and Matplotlib for visualization.

## Week 7: NumPy and Basic Data Operations

### Day 1: Getting Started with NumPy

First, let's install NumPy in your conda environment:

```bash
conda activate aienv
conda install numpy
```

#### Introduction to NumPy Arrays

```python
import numpy as np

# Creating arrays
simple_array = np.array([1, 2, 3, 4, 5])
two_d_array = np.array([[1, 2, 3], [4, 5, 6]])

# Array creation functions
zeros = np.zeros(5)                  # Array of zeros: [0. 0. 0. 0. 0.]
ones = np.ones((2, 3))              # 2x3 array of ones
range_array = np.arange(0, 10, 2)   # Array from 0 to 10 with step 2
random_array = np.random.rand(3, 3)  # 3x3 array of random numbers

print("Shape of two_d_array:", two_d_array.shape)
print("Number of dimensions:", two_d_array.ndim)
print("Total elements:", two_d_array.size)
```

### Day 2: NumPy Operations

```python
# Basic array operations
array1 = np.array([1, 2, 3])
array2 = np.array([4, 5, 6])

addition = array1 + array2           # Element-wise addition
multiplication = array1 * array2     # Element-wise multiplication
squared = array1 ** 2               # Element-wise squaring

# Statistical operations
data = np.array([14, 23, 32, 41, 50])
mean = np.mean(data)
median = np.median(data)
std_dev = np.std(data)
max_val = np.max(data)
min_val = np.min(data)

# Array manipulation
reshaped = array1.reshape(3, 1)     # Reshape to 3x1 array
transposed = two_d_array.T          # Transpose array
```

### Day 3: Advanced NumPy Features

```python
# Array indexing and slicing
array3 = np.array([[1, 2, 3, 4],
                   [5, 6, 7, 8],
                   [9, 10, 11, 12]])

# Accessing elements
first_row = array3[0]               # Get first row
specific_element = array3[1, 2]     # Get element at row 1, column 2
subset = array3[0:2, 1:3]          # Get subset of rows 0-1, columns 1-2

# Boolean indexing
greater_than_five = array3[array3 > 5]
```

### Day 4: NumPy Practice Project - Image Processing

```python
import numpy as np
import matplotlib.pyplot as plt

def create_simple_image():
    # Create a 10x10 image (2D array)
    image = np.zeros((10, 10))
    
    # Add a pattern
    image[2:8, 2:8] = 1  # Create a white square
    
    # Add some noise
    noise = np.random.rand(10, 10) * 0.2
    noisy_image = image + noise
    
    # Clip values to be between 0 and 1
    noisy_image = np.clip(noisy_image, 0, 1)
    
    return noisy_image

# Create and display the image
image = create_simple_image()
plt.imshow(image, cmap='gray')
plt.show()
```

## Week 8: Pandas and Data Visualization

### Day 1: Introduction to Pandas

First, install Pandas:

```bash
conda install pandas
```

#### Basic Pandas Operations

```python
import pandas as pd

# Creating a DataFrame
data = {
    'name': ['Alice', 'Bob', 'Charlie', 'David'],
    'age': [25, 30, 35, 28],
    'city': ['New York', 'Paris', 'London', 'Tokyo']
}
df = pd.DataFrame(data)

# Reading and writing data
df.to_csv('people.csv', index=False)  # Save to CSV
read_df = pd.read_csv('people.csv')   # Read from CSV

# Basic information about the DataFrame
print(df.info())        # DataFrame information
print(df.describe())    # Statistical summary
print(df.head())        # First few rows
```

### Day 2: Data Manipulation with Pandas

```python
# Selecting data
names = df['name']                  # Select single column
subset = df[['name', 'age']]       # Select multiple columns
filtered = df[df['age'] > 30]      # Filter rows

# Adding and modifying data
df['country'] = ['USA', 'France', 'UK', 'Japan']  # Add new column
df.loc[4] = ['Eve', 22, 'Berlin', 'Germany']      # Add new row

# Handling missing data
df_with_missing = df.copy()
df_with_missing.loc[2, 'age'] = None
cleaned_df = df_with_missing.dropna()    # Remove rows with missing values
filled_df = df_with_missing.fillna(0)    # Fill missing values with 0
```

### Day 3: Data Analysis with Pandas

```python
# Grouping and aggregation
grouped = df.groupby('country')['age'].mean()  # Average age by country

# Sorting
sorted_df = df.sort_values('age', ascending=False)

# Basic statistics
age_stats = df['age'].agg(['mean', 'median', 'min', 'max'])

# Applying functions
def age_category(age):
    return 'Young' if age < 30 else 'Adult'

df['age_category'] = df['age'].apply(age_category)
```

### Day 4: Introduction to Matplotlib

Install Matplotlib:

```bash
conda install matplotlib
```

#### Basic Plotting

```python
import matplotlib.pyplot as plt

# Line plot
plt.figure(figsize=(10, 6))
plt.plot([1, 2, 3, 4], [1, 4, 2, 3])
plt.title('Simple Line Plot')
plt.xlabel('X axis')
plt.ylabel('Y axis')
plt.show()

# Bar plot
ages = df['age']
names = df['name']
plt.figure(figsize=(10, 6))
plt.bar(names, ages)
plt.title('Age Distribution')
plt.xlabel('Name')
plt.ylabel('Age')
plt.xticks(rotation=45)
plt.show()
```

### Day 5: Advanced Data Visualization

```python
# Multiple plots in one figure
fig, (ax1, ax2) = plt.subplots(1, 2, figsize=(15, 5))

# Scatter plot
ax1.scatter(df['age'], df['name'])
ax1.set_title('Age vs Name')

# Histogram
ax2.hist(df['age'], bins=5)
ax2.set_title('Age Distribution')

plt.tight_layout()
plt.show()

# Combining Pandas with Matplotlib
df['age'].plot(kind='bar')
plt.title('Age Distribution')
plt.show()
```

## Final Project: Data Analysis Report

Create a complete data analysis report using all the tools we've learned. Here's a template:

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

def create_sample_dataset():
    """Create a sample sales dataset"""
    np.random.seed(42)
    dates = pd.date_range(start='2023-01-01', periods=100, freq='D')
    sales = np.random.normal(loc=1000, scale=200, size=100)
    products = np.random.choice(['A', 'B', 'C'], size=100)
    
    return pd.DataFrame({
        'date': dates,
        'sales': sales,
        'product': products
    })

def analyze_sales_data(df):
    """Analyze the sales data and create visualizations"""
    # Basic statistics
    print("Sales Summary:")
    print(df['sales'].describe())
    
    # Daily sales trend
    plt.figure(figsize=(12, 6))
    plt.plot(df['date'], df['sales'])
    plt.title('Daily Sales Trend')
    plt.xlabel('Date')
    plt.ylabel('Sales')
    plt.xticks(rotation=45)
    plt.tight_layout()
    plt.show()
    
    # Sales by product
    product_sales = df.groupby('product')['sales'].agg(['mean', 'count'])
    print("\nSales by Product:")
    print(product_sales)
    
    # Product sales distribution
    plt.figure(figsize=(10, 6))
    df.boxplot(column='sales', by='product')
    plt.title('Sales Distribution by Product')
    plt.suptitle('')  # This removes the automatic suptitle
    plt.show()

# Run the analysis
df = create_sample_dataset()
analyze_sales_data(df)
```

## Practice Exercises

1. Create a NumPy array of random numbers and calculate basic statistics
2. Load a CSV file into a Pandas DataFrame and perform data cleaning
3. Create different types of plots using Matplotlib
4. Combine all three libraries to analyze a real dataset

## Tips for Success

1. Always start by exploring your data using `info()` and `describe()`
2. Keep your visualizations clean and informative
3. Practice with real-world datasets from sources like Kaggle
4. Document your analysis steps using comments and markdown
5. Save intermediate results when working with large datasets

## Additional Resources

- NumPy Documentation: numpy.org/doc
- Pandas Documentation: pandas.pydata.org/docs
- Matplotlib Documentation: matplotlib.org/stable/contents.html
- Kaggle Datasets: kaggle.com/datasets
- Data Analysis YouTube Tutorials

Remember: Data manipulation is a crucial skill in AI engineering. Take time to understand these fundamentals as they'll be essential for preprocessing data for AI models later in your journey.
