# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 11-03-2025
```
Name : Guttha Keerthana
Register number : 212223240045
```

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:

### Import the necessary Packages
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```
### Load the dataset
```
df=pd.read_csv('FINAL_USO.csv')
```
### PLot the data without Conversion

```
x=data['Date']
y=data['Volume']
plt.xlabel('Date')
plt.ylabel('Volume')
plt.plot(x,y)
```
### REGULAR DIFFERENCING
```
data1=data
data1['diff']=data1['Volume'].diff()
data1=data1.dropna()
x=data1['Date']
y=data1['Volume']
plt.xlabel('Date')
plt.ylabel('diff')
plt.plot(x,y)
```

### SEASONAL ADJUSTMENT
```
data2=data
data2['SeasonalAdjustment']=data2['Volume'].rolling(window=12).mean()
data2['SeasonalAdjustment'].dropna()
x=data2['Date']
y=data2['SeasonalAdjustment']
plt.xlabel('Date')
plt.ylabel('SeasonalAdjustment')
plt.plot(x,y)
```
### LOG TRANSFORMATION
```
data3=data
data['log']=np.log(data3['diff']).dropna()
data3=data3.dropna()
x=data3['Date']
y=data3['log']
plt.xlabel('Date')
plt.ylabel('Volume')
plt.plot(x,y)
```

### OUTPUT:

### WITHOUT CONVERSION:

![image](https://github.com/user-attachments/assets/b47f9915-af07-4857-9ac7-546ca3338508)

### REGULAR DIFFERENCING:

![image](https://github.com/user-attachments/assets/62e590c4-836d-4c9b-b893-1c32f2e3a567)

### SEASONAL ADJUSTMENT:

![image](https://github.com/user-attachments/assets/58cd2b2c-72d2-4be7-9b25-a0e4b3b8b302)

### LOG TRANSFORMATION:

![image](https://github.com/user-attachments/assets/f0e97029-d52a-4b16-a118-75e769068f62)


### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
