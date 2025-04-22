#  **NumPy Arrays - Complete Guide**

## 🔹 **What is an Array?**
- Stores data in **sequential manner** (contiguous memory locations)
- All elements must be of the **same data type** (homogeneous)
- More efficient than lists for numerical operations

## 🔄 **Array vs List**
| Feature        | List              | Array               |
|----------------|-------------------|---------------------|
| Data Type      | Heterogeneous     | Homogeneous         |
| Operations     | Limited           | Mathematical        |
| Performance    | Slower for math   | Optimized for math  |
| Memory Usage   | Higher            | More efficient      |

**Key Difference**: 
- Lists can store any data type (`[1, "hello", 3.14]`)
- Arrays require all elements to be of same type (`[1, 2, 3]` or `[1.1, 2.2, 3.3]`)

## 📊 **List Operations (Limitations)**
```python
import numpy

l = [1, 2, 3]
m = [4, 5, 6]

print(l+m)  
# Output: [1, 2, 3, 4, 5, 6] (Concatenation)

# These operations will ERROR with lists:
# print(l-m)  
# print(l*m)  
# print(l/m)
```

**⚠️ Important**: Lists only support concatenation with `+`. For mathematical operations, we need NumPy arrays.

## 🚀 **Introducing NumPy Arrays**
```python
import numpy as np  # Standard convention

a = np.array([1, 2, 3])
print(a)  
# Output: [1 2 3] (Notice no commas - this is a NumPy array)
```

## 💾 **Controlling Data Types**
```python
# Explicitly specifying data type
a = np.array([1, 2, 3], dtype=int)
print(a.dtype)  # Output: int32 or int64 (depends on system)

# Automatic type conversion
mixed = np.array([1, 1.1, 2, 'hello'])
print(mixed)
# Output: ['1' '1.1' '2' 'hello'] (All converted to strings)
```

**Type Conversion Rules**:
1. If any element is float → all integers convert to floats
2. If any element is string → all convert to strings
3. You can force a type using `dtype` parameter

## ➕➖✖️➗ **Array Operations**
```python
l = np.array([1, 2, 3])
m = np.array([4, 5, 6])

print("Addition:", l + m)      # [5 7 9]
print("Subtraction:", l - m)   # [-3 -3 -3]
print("Multiplication:", l * m)# [4 10 18]
print("Division:", l / m)      # [0.25 0.4 0.5]
```

**Element-wise Operations**: 
- All operations are performed element-by-element
- Arrays must be of same shape for these operations

## 🧠 **Why Use NumPy Arrays?**
1. **Speed**: Optimized C backend makes operations faster
2. **Functionality**: Built-in math operations (sin, log, matrix ops)
3. **Memory Efficiency**: Stores data more compactly than lists
4. **Broadcasting**: Special rules for operations between arrays of different shapes

## 📝 **Best Practices**
1. Always specify `dtype` if you know the data type needed
2. Use `np.array()` instead of Python lists for numerical data
3. Remember that operations are element-wise by default

## 🏆 **Key Takeaways**
- NumPy arrays are homogeneous (same data type)
- Enable mathematical operations that lists can't do
- More memory efficient than lists for numerical data
- Automatic type conversion follows strict rules
- Operations are element-wise by default

---

# 🔄 **NumPy Arrays - Part 2: Operations & Features** 🔄

## 🔄 **Array Operations Similar to Lists**
```python
import numpy as np

l = np.array([1, 2, 3, 5])
m = np.array([4, 5, 6])

print(l[::-1])  # Reversing the array
# Output: [5 3 2 1]

print(l[0])     # Indexing
# Output: 1
```

**✅ List-like Features in NumPy:**
- Indexing (`array[0]`)
- Slicing (`array[start:stop:step]`)
- Iteration (using `for` loops)
- Concatenation (`np.concatenate()`)

## 🔢 **Type Conversion & dtype**
```python
# Force conversion to integers (truncates decimals)
l = np.array([1, 2, 3, 5.56], dtype=int)
print(l)
# Output: [1 2 3 5] (5.56 → 5)
```

### 📊 **Explicit Data Type Control**
```python
# Integer array (truncates decimals)
int_arr = np.array([1, 2, 3.9, 5.56], dtype=int)
print("Integer array:", int_arr)
# Output: [1 2 3 5]

# Float array (preserves decimals)
float_arr = np.array([1, 2, 3.9, 5.56], dtype=float)
print("Float array:", float_arr)
# Output: [1.0 2.0 3.9 5.56]

print("dtype of int array:", int_arr.dtype)    # int32/int64
print("dtype of float array:", float_arr.dtype) # float64
```

**💡 Important Notes:**
1. `dtype=int` truncates decimal values (does NOT round)
2. Default float type is `float64` (double precision)
3. Default int type is `int32` or `int64` (platform dependent)

## 🔄 **Common Operations with Lists & Arrays**
| Operation      | List Example        | NumPy Array Example       |
|----------------|---------------------|---------------------------|
| Slicing        | `lst[1:3]`          | `arr[1:3]`                |
| Reversing      | `lst[::-1]`         | `arr[::-1]`               |
| Indexing       | `lst[0]`            | `arr[0]`                  |
| Sorting        | `sorted(lst)`       | `np.sort(arr)`            |
| Length         | `len(lst)`          | `len(arr)` or `arr.size`  |

## 🛠 **Enhanced NumPy Operations**
```python
arr = np.array([3, 1, 4, 2])

# Sorting
print("Sorted array:", np.sort(arr))  # [1 2 3 4]

# Mathematical operations
print("Sum:", np.sum(arr))      # 10
print("Mean:", np.mean(arr))    # 2.5
print("Max:", np.max(arr))      # 4
```

## 🚫 **Common Pitfalls**
1. **Type Conversion Surprises**:
   ```python
   arr = np.array([1, 2, '3'])  # Converts all to strings!
   print(arr)  # ['1' '2' '3']
   ```

2. **Mixed Type Arrays**:
   ```python
   mixed = np.array([1, 2.5, 'hello'])  # All become strings
   print(mixed)  # ['1' '2.5' 'hello']
   ```

3. **Integer Division**:
   ```python
   arr = np.array([1, 2, 3], dtype=int)
   print(arr/2)  # [0.5 1.0 1.5] (becomes float)
   ```

## 🏆 **Best Practices**
1. Always check `dtype` after array creation (`array.dtype`)
2. Be explicit with data types when precision matters
3. Use NumPy's built-in functions (`np.sort()`, `np.sum()`) instead of Python equivalents
4. Remember that slicing returns views (not copies) in NumPy

---

**Example of something we couldn't do with lists:**
```python
# Element-wise trigonometric operations
angles = np.array([0, 30, 45, 90])
print(np.sin(angles * np.pi/180))
# Output: [0. 0.5 0.707 1.] (sin values)
```

---

# 🗺 **NumPy with map() & filter() Functions** 🧮

## 🗺 **Using map() with NumPy Arrays**
```python
import numpy as np

a = np.array([1, 2, 3, 5, 54, 64, 35, 33, 6, 5.56], dtype=float)
print("Original array:\n", a)

def evenOdd(num):
    """Returns 'Even' or 'Odd' based on number"""
    return "Even" if num % 2 == 0 else "Odd"

# Applying map to NumPy array
result = list(map(evenOdd, a))
print("\nMapped result:\n", result)
```

**Output:**
```
Original array:
 [ 1.    2.    3.    5.   54.   64.   35.   33.    6.    5.56]

Mapped result:
 ['Odd', 'Even', 'Odd', 'Odd', 'Even', 'Even', 'Odd', 'Odd', 'Even', 'Odd']
```

### 💡 Key Observations:
1. `map()` works similarly with NumPy arrays as with Python lists
2. The function is applied to **each element** individually
3. Decimal numbers (like 5.56) are checked for even/odd based on their **integer part**

---

## 🚫 **The filter() Function Gotcha**
```python
a = np.array([1, 2, 3, 5, 54, 64, 35, 33, 6, 5.56], dtype=float)
print("Original array:\n", a)

def evenOdd(num):
    """Expected to filter even numbers, but..."""
    return num % 2 == 0

filtered = list(filter(evenOdd, a))
print("\nFiltered result:\n", filtered)
```

**Output:**
```
Original array:
 [ 1.    2.    3.    5.   54.   64.   35.   33.    6.    5.56]

Filtered result:
 [1.0, 2.0, 3.0, 5.0, 54.0, 64.0, 35.0, 33.0, 6.0, 5.56]
```

### 🔍 **Why This Happens:**
1. `filter()` expects the function to return `True/False` for each element
2. NumPy's float dtype causes the `%` operator to return float remainders (e.g., `5.56 % 2 → 1.56`)
3. In Python, **any non-zero number is truthy**, so all elements pass through

### ✅ **Correct Approach:**
```python
# Convert to integers first if you want even/odd check
filtered_correct = a[np.where(a.astype(int) % 2 == 0)]
print("Properly filtered even numbers:\n", filtered_correct)
```
**Output:** `[ 2.  54.  64.   6.]`

---

## 📊 **Statistical Operations in NumPy**
```python
import numpy as np

l = [43, 434, 43, 4343, 645, 64532, 64542, 42345]
a = np.array(l)

print("Original array:\n", a)
print("\nStatistics:")
print("Mean:", np.mean(a))     # Average value
print("Median:", np.median(a)) # Middle value
print("Std Dev:", np.std(a))   # Measure of spread
```

**Output:**
```
Original array:
 [   43   434    43  4343   645 64532 64542 42345]

Statistics:
Mean: 22115.875
Median: 2494.0
Std Dev: 27905.47017359455
```

### 📈 **Statistical Functions Explained:**
| Function | Description | Formula |
|----------|-------------|---------|
| `np.mean()` | Average value | Σxᵢ/n |
| `np.median()` | Middle value | Value at (n+1)/2 position |
| `np.std()` | Standard Deviation | √(Σ(xᵢ-μ)²/n) |

### 🌟 **Why Use NumPy for Statistics?**
1. **Speed**: 10-100x faster than pure Python
2. **Accuracy**: Optimized numerical algorithms
3. **Convenience**: Single function calls
4. **NaN Handling**: Special options for missing data

---

## 🏆 **Best Practices**
1. For element-wise operations, prefer **NumPy's vectorized functions** over `map()`:
   ```python
   # Faster alternative to map
   np.where(a % 2 == 0, "Even", "Odd")
   ```

2. When filtering, use **boolean indexing** instead of `filter()`:
   ```python
   a[a % 2 == 0]  # Gets even numbers
   ```

3. For statistics, always specify `dtype` if working with large numbers:
   ```python
   np.array(l, dtype=np.float64)  # Prevents overflow
   ```

4. Remember that NumPy's `%` operator behaves differently with floats than Python's


---

# 🎲 **NumPy Random Module - Complete Guide** 🎯

## 🌟 **Random Number Generation Basics**

```python
from numpy import random

# Random integer between 0-100
print("Single random integer:", random.randint(100))

# Random float between 0-1
print("Single random float:", random.rand())

# Array of 10 random floats
print("10 random floats:", random.rand(10))

# Array of 10 random integers (0-100)
print("10 random integers:", random.randint(100, size=10))

# Random choice from given list
b = random.choice([10, 23, 1, 19, 4, 7])
print("Random choice:", b)
```

**Output Example:**
```
Single random integer: 52
Single random float: 0.8050100530334096
10 random floats: [0.81027195 0.21537434 ... 0.27142714]
10 random integers: [44 25 52 35 78 83 57 5 34 45]
Random choice: 1
```

### 📊 **Random Function Cheat Sheet**
| Function | Description | Range | Output Shape |
|----------|-------------|-------|--------------|
| `randint(n)` | Random integer | 0 to n-1 | Scalar |
| `rand()` | Random float | [0.0, 1.0) | Scalar |
| `rand(n)` | Random floats | [0.0, 1.0) | (n,) array |
| `randint(n, size=k)` | Random integers | 0 to n-1 | (k,) array |
| `choice(arr)` | Random selection | From input array | Scalar |

---

## 🌱 **Understanding Random Seeds (Reproducibility)**

### ❓ **What is a Seed?**
A seed initializes the random number generator. Using the same seed produces the same sequence of "random" numbers.

```python
from numpy import random

# Set seed for reproducibility
random.seed(55)

# Will always produce same output with seed 55
a = random.randint(500)
print("Seeded random number:", a)  # Always 461 with seed 55
```

**Output:**
```
Seeded random number: 461
```

### 🧪 **Seed Demonstration**
```python
random.seed(100)
print("First run:", random.randint(10, size=3))

random.seed(100)  # Reset seed
print("Second run:", random.randint(10, size=3))  # Same output!
```

**Output:**
```
First run: [8 8 3]
Second run: [8 8 3]
```

---

## 🚀 **Advanced Random Distributions**

### 1. Normal (Gaussian) Distribution
```python
# Mean=0, Std=1 (standard normal)
normal_numbers = random.randn(5)
print("Normal dist:", normal_numbers)
```

### 2. Uniform Distribution
```python
# Between low and high
uniform_numbers = random.uniform(low=5, high=10, size=5)
print("Uniform dist:", uniform_numbers)
```

### 3. Binomial Distribution
```python
# n trials, p probability
coin_flips = random.binomial(n=1, p=0.5, size=10)
print("Coin flips:", coin_flips)
```

---

## 💡 **Why Use Seeds?**
1. **Reproducibility**: Get identical results across runs
2. **Debugging**: Isolate random-number related bugs
3. **Testing**: Verify statistical properties
4. **Comparisons**: Fair algorithm comparisons

---

## 🛠 **Practical Usage Tips**
1. **For production**: Don't set seed (true randomness needed)
2. **For development**: Always set seed for debugging
3. **Multiple seeds**: Test with different seeds to ensure robustness
4. **Global vs Local**: 
   ```python
   # Affects all random operations
   random.seed(42)  

   # Local generator (recommended)
   rng = random.RandomState(42)
   print(rng.randint(10))
   ```

---

## 🏆 **Best Practices**
1. Use `RandomState` for independent streams
2. Document seeds used in research
3. For cryptography, use `secrets` module instead
4. Remember - seeded "randomness" isn't truly random!

---

# 📊 **Pandas Fundamentals - Complete Guide** 🐼

## 🔢 **1. Pandas Series (1D Data Structure)**
### Basic Series Creation
```python
import pandas as pd

# Create Series from list
l = [10, 20, 30, 40, 50]
a = pd.Series(l)
print(a)
```
**Output:**
```
0    10
1    20
2    30
3    40
4    50
dtype: int64
```

### Mixed Data Types
```python
mixed = [10, 20, 30, 40, 50, 'hello']
s = pd.Series(mixed)
print(s.dtype)  # object (parent class for all Python types)
```

### Key Series Features:
- Indexed like a dictionary (default: 0-based integers)
- Homogeneous data preferred (better performance)
- dtype automatically inferred
- Similar to NumPy array but with enhanced functionality

---

## 📈 **2. Pandas DataFrame (2D Data Structure)**
### Basic DataFrame Creation
```python
emp_data = {
    "empid": [1, 2, 3, 4],
    "ename": ["abc", "arya", "rishi", "sagar"],
    "Salary": [20000, 40000, 45000, 50000]
}

df = pd.DataFrame(emp_data)
print(df)
```
**Output:**
```
   empid  ename  Salary
0      1    abc   20000
1      2   arya   40000
2      3  rishi   45000
3      4  sagar   50000
```

### DataFrame Indexing
```python
# Access column
print(df['Salary'])

# Access row by label
print(df.loc[2])  # Access by index label

# Access row by position
print(df.iloc[0])  # Access by integer position
```

### Custom Index
```python
df_indexed = pd.DataFrame(emp_data, index=["one", "two", "three", "four"])
print(df_indexed.loc["three"])
```

---

## 🕰 **3. Time Series Data & Logs**
### What is Time Series Data?
- Data points indexed in time order (timestamps)
- Examples: Stock prices, sensor readings, website visits

### What are Logs?
- Timestamped records of events
- Typically contain: Timestamp, Event Type, Message
- Used for debugging, auditing, and analysis

---

## 📂 **4. Working with CSV Files**
```python
df = pd.read_csv("Survey.csv")

# Essential DataFrame Methods
print(df.head())    # First 5 rows
print(df.tail())    # Last 5 rows  
print(df.info())    # Structure summary
print(df.describe()) # Statistical summary
```

### Key CSV Operations:
- `read_csv()`: Load data from CSV
- `to_csv()`: Save DataFrame to CSV
- Parameters:
  - `index=False` (don't write row numbers)
  - `header=False` (don't write column names)

---

## 🔍 **5. DataFrame Inspection Methods**
| Method | Description | Useful For |
|--------|-------------|------------|
| `head(n)` | First n rows | Quick look |
| `tail(n)` | Last n rows | Recent data |
| `info()` | Data types & memory | Structure overview |
| `describe()` | Statistical summary | Numeric columns |
| `shape` | (rows, columns) | Size check |
| `columns` | Column names | Reference |
| `dtypes` | Data types per column | Type checking |

---

## 💡 **Key Concepts Explained**
### 1. `loc` vs `iloc`
- `loc`: Label-based indexing
- `iloc`: Position-based indexing

### 2. Why `object` dtype?
- Pandas uses `object` for:
  - Strings
  - Mixed data types
  - Python objects

### 3. Handling Missing Data
- Shown as `NaN` in output
- Affects statistical calculations
- Can be handled with:
  - `dropna()`: Remove missing values
  - `fillna()`: Replace missing values

---

## 🏆 **Best Practices**
1. **Specify dtypes** when reading data for better memory usage
2. **Use categoricals** for low-cardinality strings
3. **Set meaningful indexes** for time series data
4. **Always check** `info()` after loading data
5. **Use vectorized operations** instead of loops


---

**Example: Why Pandas Beats Raw Python**
```python
# Calculate average salary by gender (1 line in Pandas)
survey.groupby('Sex')['Salary'].mean()

# Much more complex in pure Python!
```

This shows how Pandas simplifies complex data operations that would require many lines of Python code.

---

# 🔍 **Data Filtering in Pandas**

## **1. Conditional Filtering**
```python
import pandas as pd
df = pd.read_csv("C:/Datasets/Airquality.csv")

# Filter rows where Ozone > 15
print(df[df['Ozone'] > 15].head())
```
**Output:**
```
   Ozone  Solar.R  Wind  Temp  Month  Day
0   41.0    190.0   7.4    67      5    1
1   36.0    118.0   8.0    72      5    2
3   18.0    313.0  11.5    62      5    4
5   28.0      NaN  14.9    66      5    6
6   23.0    299.0   8.6    65      5    7
```

## **Multiple Conditions**
```python
# AND condition: Ozone > 15 AND Temp < 70
print(df[(df['Ozone'] > 15) & (df['Temp'] < 70)].head())

# OR condition: Ozone < 10 OR Solar.R > 300
print(df[(df['Ozone'] < 10) | (df['Solar.R'] > 300)].head())
```

---

# 🤝 **Table Joins in Pandas**
```python
df1 = pd.read_excel("C:/Datasets/Demo.xls", "Sheet1")
df2 = pd.read_excel("C:/Datasets/Demo.xls", "Sheet2")

# Left join on 'deptno'
merged = pd.merge(df1, df2, on="deptno", how="left")
print(merged.head())
```

**Join Types:**
| Join Type | How Parameter | Description |
|-----------|---------------|-------------|
| Inner | `how='inner'` | Only matching rows |
| Left | `how='left'` | All left + matching right |
| Right | `how='right'` | All right + matching left |
| Outer | `how='outer'` | All rows from both |

---

# 📊 **Creating DataFrames**
```python
import pandas as pd
import numpy as np

a = [[1, 2, 3, 4],
     [1, 2, 3, 4],
     [5, 6, 7, 8],
     [9, 10, 11, 12]]

df = pd.DataFrame(a, columns=["col1", "col2", "col3", "col4"])
print(df)
```
**Output:**
```
   col1  col2  col3  col4
0     1     2     3     4
1     1     2     3     4
2     5     6     7     8
3     9    10    11    12
```

---

# 📈 **Data Visualization with Matplotlib**
```python
import matplotlib.pyplot as plt

# Line Plot
x = ["abc", "mno", "pqr", "www", "rrr"]
y = [99, 89, 75, 12, 98]
plt.plot(x, y)
plt.title("Line Plot")
plt.show()

# Box Plot
plt.boxplot(y)
plt.title("Box Plot")
plt.show()

# Scatter Plot
plt.scatter(x, y)
plt.title("Scatter Plot")
plt.show()
```

**Plotting from DataFrame:**
```python
# Scatter plot from DataFrame columns
plt.scatter(df['col1'], df['col2'])
plt.xlabel('Column 1')
plt.ylabel('Column 2')
plt.show()
```

---

# 🧹 **Handling Null Values**
```python
# Drop rows with any null values
cleaned_df = df.dropna()

# Fill nulls with specific value
filled_df = df.fillna(0)

# Fill nulls with column mean
df['Ozone'] = df['Ozone'].fillna(df['Ozone'].mean())

# Forward fill
df.fillna(method='ffill', inplace=True)
```

**Null Handling Methods:**
| Method | Description |
|--------|-------------|
| `dropna()` | Remove missing values |
| `fillna()` | Replace missing values |
| `isna()` | Detect missing values |
| `interpolate()` | Fill values using interpolation |

---

# 🏆 **Key Takeaways**
1. **Filtering**: Use boolean conditions with `df[condition]`
2. **Joins**: `pd.merge()` with different `how` parameters
3. **Visualization**: Start with `plt.plot()`, `plt.scatter()`, `plt.boxplot()`
4. **Null Values**: Always check with `df.isna().sum()` before analysis
5. **DataFrames**: Can be created from lists, dicts, or NumPy arrays

---

# 📊 **Data Visualization & Web Scraping in Python**  

## 🌟 **Seaborn**  

Seaborn is a statistical data visualization library built on Matplotlib. It provides a high-level interface for creating attractive graphs.  

### 🔹 **Installation**  
```bash
pip install seaborn
```

### 🔹 **Basic Plotting**  
```python
import seaborn as sns
import matplotlib.pyplot as plt

# Load built-in dataset
tips = sns.load_dataset("tips")

# Create a scatter plot with regression line
sns.lmplot(x="total_bill", y="tip", data=tips, hue="smoker")
plt.title("Total Bill vs Tip Amount")
plt.show()
```
**Output:**  
![Seaborn Scatter Plot](https://seaborn.pydata.org/_images/regression-1.png)  

### 🔹 **Key Features**  
- **Histograms & KDE Plots:**  
  ```python
  sns.histplot(tips["total_bill"], kde=True)
  plt.title("Distribution of Total Bill")
  plt.show()
  ```
  
- **Box Plots:**  
  ```python
  sns.boxplot(x="day", y="total_bill", data=tips)
  plt.title("Total Bill by Day")
  plt.show()
  ```

- **Heatmaps:**  
  ```python
  corr = tips.corr()
  sns.heatmap(corr, annot=True)
  plt.title("Correlation Heatmap")
  plt.show()
  ```

---

## 📈 **Plotly**  

Plotly is an interactive visualization library that works well in Jupyter notebooks and web apps.  

### 🔹 **Installation**  
```bash
pip install plotly
```

### 🔹 **Basic Interactive Plot**  
```python
import plotly.express as px

df = px.data.iris()  # Load built-in dataset
fig = px.scatter(df, x="sepal_width", y="sepal_length", color="species")
fig.show()
```
**Output:**  
![Plotly Scatter Plot](https://plotly.com/python/static/images/plotly-express-scatter-plot.png)  

### 🔹 **Key Features**  
- **Line Plot:**  
  ```python
  fig = px.line(df, x="sepal_width", y="sepal_length", color="species")
  fig.show()
  ```

- **3D Scatter Plot:**  
  ```python
  fig = px.scatter_3d(df, x="sepal_width", y="sepal_length", z="petal_width", color="species")
  fig.show()
  ```

- **Interactive Dashboards:**  
  Plotly Dash can be used to build web-based dashboards.  

---

## 🌐 **Web Scraping in Python**  

### 🔹 **Requests**  
The `requests` library fetches HTML content from websites.  

#### **Installation**  
```bash
pip install requests
```

#### **Basic Usage**  
```python
import requests

url = "https://example.com"
response = requests.get(url)

print("Status Code:", response.status_code)  # 200 means success
print("HTML Content:", response.text[:200])  # First 200 characters
```
**Output:**  
```
Status Code: 200  
HTML Content: <!doctype html> <html> <head> <title>Example Domain</title> <meta charset="utf-8" /> <meta http-equiv="Content-type" content="text/html; charset=utf-8" /> <meta name="viewport" content="width=device-width, initial-scale=1" /> <sty
```

---

### 🍲 **BeautifulSoup**  
BeautifulSoup parses HTML/XML and extracts data.  

#### **Installation**  
```bash
pip install beautifulsoup4
```

#### **Basic Usage**  
```python
from bs4 import BeautifulSoup
import requests

url = "https://example.com"
response = requests.get(url)
soup = BeautifulSoup(response.text, "html.parser")

# Extract title
title = soup.title.string
print("Page Title:", title)

# Extract all links
links = [a["href"] for a in soup.find_all("a", href=True)]
print("Links:", links[:3])  # First 3 links
```
**Output:**  
```
Page Title: Example Domain  
Links: ['https://www.iana.org/domains/example', 'https://www.iana.org/domains/reserved', 'https://www.iana.org/domains/reserved']  
```

---

### 🕷️ **Scrapy**  
Scrapy is a powerful web scraping framework for large-scale projects.  

#### **Installation**  
```bash
pip install scrapy
```

#### **Creating a Scrapy Spider**  
1. **Create a project:**  
   ```bash
   scrapy startproject myproject
   cd myproject
   ```

2. **Define a spider:**  
   ```python
   import scrapy

   class ExampleSpider(scrapy.Spider):
       name = "example"
       start_urls = ["https://example.com"]

       def parse(self, response):
           title = response.css("title::text").get()
           yield {"title": title}
   ```

3. **Run the spider:**  
   ```bash
   scrapy crawl example -o output.json
   ```
   **Output (output.json):**  
   ```json
   [{"title": "Example Domain"}]
   ```

---

## 🔥 **Key Takeaways**  
| Library | Purpose | Best For |
|---------|---------|----------|
| Seaborn | Statistical Visualization | Quick & elegant plots |
| Plotly | Interactive Visualizations | Dashboards & 3D plots |
| Requests | Fetching Web Pages | Simple HTTP requests |
| BeautifulSoup | HTML Parsing | Small-scale scraping |
| Scrapy | Full Web Scraping Framework | Large-scale projects |

