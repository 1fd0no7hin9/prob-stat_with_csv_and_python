

```python
import matplotlib.pyplot as plt
import matplotlib as mpl
import pandas as pd
import seaborn as sns
import numpy as np
```


```python
df = pd.read_csv('airAccs.csv')

times = pd.DataFrame(df, columns=['times'])
dead = pd.DataFrame(df, columns=['Dead'])

mean = dead.mean()
mean = "%.2f"%mean.values
median = dead.median()
median = "%.2f"%median.values
mode = dead.mode()
mode = "%0.2f"%mode.values[0][0]
std = dead.std()
std = "%0.2f"%std.values
```


```python
table = pd.DataFrame(data = {'mean':[mean],
                             'median':[median],
                             'mode':[mode],
                             'std':[std]})
table
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>mean</th>
      <th>median</th>
      <th>mode</th>
      <th>std</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>19.81</td>
      <td>9.00</td>
      <td>2.00</td>
      <td>32.52</td>
    </tr>
  </tbody>
</table>
</div>




```python
dead.plot.box()

dead.plot()
plt.ylabel('some numbers')
plt.xlabel('times')
```




    Text(0.5,0,'times')




![png](output_3_1.png)



![png](output_3_2.png)



```python
plt.scatter(times,dead, data = dead)
plt.ylabel('some numbers')
plt.xlabel('times')
```




    Text(0.5,0,'times')




![png](output_4_1.png)



```python
sns.regplot(x = "times", y = "Dead", data = df, 
           scatter_kws={"color": "blue"}, line_kws={"color": "red"})
```




    <matplotlib.axes._subplots.AxesSubplot at 0x10693550>




![png](output_5_1.png)

