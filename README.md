### Developed By: Ragavendran A
### Register No: 212222230114
### Date:

# Ex.No: 1B CONVERSION OF NON STATIONARY TO STATIONARY DATA


## AIM:
To analyzing the Summer Olympic Medals dataset is to understand and visualize trends in medal counts by country, year, and sport, and to gain insights into patterns and performance over time.

## ALGORITHM:
```
1.Load the dataset into a DataFrame.
2.Handle missing values and preprocess data.
3.Analyze basic statistics and distributions.
4.Identify trends in medal counts by year and country.
5.Perform the non-stationary convertion into stationary convertion using above three mothods.
6.Create charts to visualize medal counts and trends.
7.Interpret results to derive insights on performance.
```

## PROGRAM:
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose


data = pd.read_csv("/content/Summer_olympic_Medals.csv")

df = pd.DataFrame(data)


df['Regular Difference'] = df['Gold'].diff()


result = seasonal_decompose(df['Gold'], model='additive', period=12)
df['Seasonal Adjustment'] = result.resid

df['Log Transformation'] = np.log(df['Gold'])


plt.figure(figsize=(14, 10))

plt.subplot(4, 1, 1)
plt.plot(df['Gold'], label='Original')
plt.legend(loc='best')
plt.title('Original Data')

plt.subplot(4, 1, 2)
plt.plot(df['Regular Difference'], label='Regular Difference')
plt.legend(loc='best')
plt.title('Regular Differencing')

plt.subplot(4, 1, 3)
plt.plot(df['Seasonal Adjustment'], label='Seasonal Adjustment')
plt.legend(loc='best')
plt.title('Seasonal Adjustment')

plt.subplot(4, 1, 4)
plt.plot(df['Log Transformation'], label='Log Transformation')
plt.legend(loc='best')
plt.title('Log Transformation')

plt.tight_layout()
plt.show()
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/1225e089-aa19-4d37-bdad-ddd4d78a55ef)
![image](https://github.com/user-attachments/assets/88283f98-8762-4c87-ac35-41453a50a676)



# RESULT:
Thus the python code for the conversion of non stationary to stationary data on summer olympic medals is successfully executed.
