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
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np

df = pd.read_csv('/content/AirPassengers.csv')

data = df['#Passengers'].values

N = len(data)

lags = range(35)


autocorr_values = []

mean_data = np.mean(data)


variance_data = np.var(data)

for lag in lags:
    if lag == 0:
        autocorr_values.append(1)
    else:
        
        auto_cov = np.sum((data[:-lag] - mean_data) * (data[lag:] - mean_data)) / N
        autocorr_values.append(auto_cov / variance_data) 

plt.figure(figsize=(10, 6))
plt.stem(lags, autocorr_values)
plt.title('Autocorrelation of Air Passengers Data')
plt.xlabel('Lag')
plt.ylabel('Autocorrelation')
plt.grid(True)
plt.show()
```

### OUTPUT:
<img width="657" height="406" alt="Screen Shot 2026-05-11 at 09 09 07" src="https://github.com/user-attachments/assets/347be693-733c-43c9-bce7-ef3739cacf47" />


### RESULT:
Thus we have successfully implemented the auto correlation function in python.
