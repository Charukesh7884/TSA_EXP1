# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 13/10/26

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:
```

import matplotlib.pyplot as plt
import pandas as pd

df = pd.read_csv("NVIDIA_STOCK.csv", skiprows=3, header=None)

df.columns = ['Date', 'Adj Close', 'Close', 'High', 'Low', 'Open', 'Volume']

df.head()

df['Date'] = pd.to_datetime(df['Date'], format='%Y-%m-%d')

df.dtypes

df.set_index('Date', inplace=True)

df_resampled = df['Close'].resample('D').interpolate()

df_resampled.plot(kind='line', label='NVIDIA Stock Price', color='black')

plt.title('Time Series Plot of NVIDIA Stock Price Each Day')
plt.xlabel('Day')
plt.ylabel('Stock Closing Price')
plt.legend()
plt.grid(True)
plt.show()
```
# OUTPUT:
<img width="575" height="460" alt="image" src="https://github.com/user-attachments/assets/797814b6-3179-4342-a157-9b1700ca296b" />

# RESULT:
Thus we have created the python code for plotting the time series of given data.




# RESULT:
Thus we have created the python code for plotting the time series of given data.
