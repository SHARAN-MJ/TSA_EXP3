### Developed by : SHARAN MJ
### Register No.: 212222240097
### Date :

# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)

### AIM:
To Compute the AutoCorrelation Function (ACF) of the data for The Minimum Price of the amazon stock.

### ALGORITHM:

1. Import the necessary packages

2. Find the mean, variance and then implement normalization for the data.

3. Implement the correlation using necessary logic and obtain the results

4. Store the results in an array

5. Represent the result in graphical representation as given below.

### PROGRAM:

```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

file_path = '/content/drive/MyDrive/time series/AMZN.csv'
data = pd.read_csv(file_path)

# Check for possible typos and correct the column name
Min_data = data['Low'].dropna().values

data_mean = np.mean(Min_data)
print("Mean:", data_mean)

data_var = np.var(Min_data)
print("Variance:", data_var)

normalized_data = (Min_data - data_mean) / np.sqrt(data_var)

acf_result = np.correlate(normalized_data, normalized_data, mode='full')

acf_result = acf_result[len(acf_result)//2:]

plt.figure(figsize=(10, 5))
plt.stem(acf_result[:36], use_line_collection=True)
plt.xlabel('Lag')
plt.ylabel('Autocorrelation')
plt.title('Autocorrelation Function (ACF) of Minimum Price of amazon stock')
plt.show()
```
### OUTPUT:



#### Autocorrelation Function (ACF) of Minimum Price of Onion




### RESULT:

####     Thus auto correlation function in python is successfully implemented.
