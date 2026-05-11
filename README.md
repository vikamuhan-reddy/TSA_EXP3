# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)
Date: 11/05/2026

### AIM:
To Compute the AutoCorrelation Function (ACF) of the data for the first 35 lags to determine the model
type to fit the data.

### ALGORITHM:
1. Import the necessary packages
2. Find the mean, variance and then implement normalization for the data.
3. Implement the correlation using necessary logic and obtain the results
4. Store the results in an array
5. Represent the result in graphical representation as given below.
   
### PROGRAM:

```py
import matplotlib.pyplot as plt
import numpy as np
data = np.array([3, 16, 156, 47, 246, 176, 233, 140, 130, 101, 166, 201, 200, 116, 118,
                 52, 153, 232, 128, 27, 192, 168, 208, 187, 228, 86, 30, 151, 18, 254, 76, 112, 6])
N = len(data)
lags = range(35)
autocorr_values = []
mean_data = np.mean(data)
variance_data = np.var(data)
normalized_data = (data - mean_data) / np.sqrt(variance_data)
for lag in lags:
    if lag == 0:
        autocorr_values.append(1)
    else:
        auto_cov = np.sum((data[:-lag] - mean_data) * (data[lag:] - mean_data)) / N
        autocorr_values.append(auto_cov / variance_data) 
plt.figure(figsize=(10, 6))
plt.stem(lags, autocorr_values)
plt.title('Autocorrelation of Data')
plt.xlabel('Lag')
plt.ylabel('Autocorrelation')
plt.grid(True)
plt.show()
```

### OUTPUT:
<img width="655" height="413" alt="Screen Shot 2026-05-11 at 09 16 16" src="https://github.com/user-attachments/assets/e983b530-5a67-4742-9a75-3a4df4632a5c" />


### RESULT:
Thus we have successfully implemented the auto correlation function in python.
