import pandas as pd   
df is the dataframe   
col, col_1, col_2 are columns of the dataframe   
`inplace = True`  means the changes will take place in the df itself. No need to assign or create a df.

## Attributes of a dataframe
```python
pd.shape
```
```python
pd.describe
```
## Concatenate
### Concatenate 'col1' and 'col2' (separated by a space)
```combined_col = df.col1.str.cat(df.col2, sep = ' ')```

## Datatypes
`int`, `float`: enables mathematical operations   
`datetime`: enables date-based attributes and methods   
`category`: uses less memory and runs faster    
`bool`: enables logical and mathematical operations 

### Check datatype of all columns in df
```python  
df.dtypes
```

### Check datatype of a single column
```python
df['col'].dtype
```

### To change datatype:
* int to float
* float to int
* object to datetime ```df['dt_col'] = pd.to_datetime(df.['dt_col'])```
* object to category
* object to float       ```df['col'] = df['col'].astype('float')```
                           

## Drop

### Drop columns
### Drop certain columns
```python
df.drop(['col_1', 'col_2'], axis='columns', inplace=True)
```
### Drop rows having missing data in the col column
```df.dropna(subset=['col'], inplace=True)```

### Drop duplicates

## Index
### Set a column as the index of the df
```df.set_index('ind_col', inplace = True)```

## Missing values

### Count missing values in each column
```python
pd.isnull().sum()
```
### Count missing values in the dataframe
```python
pd.isnull().sum().sum()
```