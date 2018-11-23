```python
Code
```

# Data Science Cheatsheet

## Numpy

### Import

```python
import numpy as np
```


### Create array

```python
data = [1,2,3] # list
arr1 = np.array(data) # 1d array
arr2 = np.array(range(10)) # 2d array
# arr2.tolist() # convert array back to list
```

### Create array with a function

```python
np.zeros((10,10))
```

### Slicing

```python
arr2[0:3]
```

### Selection

```python
arr = np.arange(10, dtype=float).reshape( (2,5) )
arr[0,3]
```

```python
a = arr[:, [1,2,3]] # return a copie
a[0, 0] = 33. # affectation
``` 

```python
a = arr[ arr > 5]
```

### Details of an array

```python
a1.dtype # type of array
a1.ndim # dimension
a1.shape # nb of row and column
```

### Transpose

```python
a1.T
```

### Flat the array

```python
a1.flatten()
```

## Pandas

### Import

```python
import pandas as pd
```

### Create dataframe

```python
columns = ['name', 'age', 'gender', 'job']
user1 = pd.DataFrame([['alice', 19, "F", "student"],
                    ['john', 26, "M", "student"]],
                    columns=columns)
user2 = pd.DataFrame([['eric', 22, "M", "student"],
                    ['paul', 58, "F", "manager"]],
                    columns=columns)
user3 = pd.DataFrame(dict(name=['peter', 'julie'],
                    age=[33, 44], gender=['M', 'F'],
                    job=['engineer', 'scientist']))```
```                    

### Import csv

```python
df = pd.read_csv('path/toyourfile.csv')
```  

### Selection loc - by label/index or indices

```python
user1.loc[0]
user1.loc[0, 'age']
```  

### Selection iloc - by indices

```python
user1.iloc[0, 1]
```

### Counting occurences of missing values

```python
user1.isna().sum()
```


### Concatenate

```python
users = pd.concat([user1, user2, user3])
```

### Reset index

```python
users = users.reset_index()
```

### Delete by index

```python
users.drop('index', axis=1) 
```

### Return number of unique elements in the object

```python
users.nunique
users.unique # Return unique values of Series object
```




               


