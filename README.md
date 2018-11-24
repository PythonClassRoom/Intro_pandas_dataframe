

```python
import json
```


```python
# load json file from /data folder
with open('monthlySalesbyCategoryMultiple.json') as json_data:
    d = json.load(json_data)
```


```python
d['contents'][0]
```


```python
d
```




    {'contents': [{'category': 'Furniture',
       'region': 'West',
       'monthlySales': [{'month': 20130101, 'sales': 38},
        {'month': 20130201, 'sales': 35},
        {'month': 20130301, 'sales': 41},
        {'month': 20130401, 'sales': 55},
        {'month': 20130501, 'sales': 58},
        {'month': 20130601, 'sales': 66},
        {'month': 20130701, 'sales': 74},
        {'month': 20130801, 'sales': 78},
        {'month': 20130901, 'sales': 38},
        {'month': 20131001, 'sales': 30},
        {'month': 20131101, 'sales': 26},
        {'month': 20131201, 'sales': 29}]},
      {'category': 'Technology',
       'region': 'West',
       'monthlySales': [{'month': 20130101, 'sales': 54},
        {'month': 20130201, 'sales': 66},
        {'month': 20130301, 'sales': 77},
        {'month': 20130401, 'sales': 70},
        {'month': 20130501, 'sales': 60},
        {'month': 20130601, 'sales': 63},
        {'month': 20130701, 'sales': 55},
        {'month': 20130801, 'sales': 47},
        {'month': 20130901, 'sales': 55},
        {'month': 20131001, 'sales': 30},
        {'month': 20131101, 'sales': 22},
        {'month': 20131201, 'sales': 77}]}]}




```python
#intro pandas
```


```python
import pandas as pd
```


```python
my_df = pd.DataFrame([1,2,3,4])
```


```python
my_df.empty
```




    False




```python
my_df.head()
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
      <th>0</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>




```python
my_df.tail(1)
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
      <th>0</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3</th>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>




```python
my_df.columns
```




    Index(['numeros'], dtype='object')




```python
my_df.columns = ['numeros']
```


```python
my_df.rename(columns={'numeros':'nombre_col'}, inplace=True)
```


```python
my_df.head()
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
      <th>nombre_col</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>




```python
my_df.index
```




    RangeIndex(start=0, stop=4, step=1)




```python
#datos por columna
```


```python
my_df.nombre_col.values.tolist()
```




    [1, 2, 3, 4]




```python
my_df['nombre_col'].values.tolist()
```




    [1, 2, 3, 4]




```python
#filtrado
```


```python
s = my_df['nombre_col'] >= 2
```


```python
type(s)
```




    pandas.core.series.Series




```python
my_df[my_df['nombre_col'] >= 2]
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
      <th>nombre_col</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>




```python
my_df.loc[my_df['nombre_col'] >= 2]
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
      <th>nombre_col</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>




```python
my_df.iloc[1:5]
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
      <th>nombre_col</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>




```python
my_df.to_pickle('mi_primer_df.p')
```


```python
my_df.to_csv('mi_csv.csv')
```


```python
df = pd.DataFrame([{'a':1,'b':2, 'c':3, 'nombre': 'juan'},
             {'a':6, 'b': 7, 'c': 0, 'nombre': 'andres'}])
```


```python
df.set_index(['nombre'], inplace=True)
```


```python
df.reset_index(inplace=True)
```


```python
df
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
      <th>nombre</th>
      <th>a</th>
      <th>b</th>
      <th>c</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>juan</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
    </tr>
    <tr>
      <th>1</th>
      <td>andres</td>
      <td>6</td>
      <td>7</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df['resultado'] = (df.a + df.b) / df.c
```


```python
df.a.sum()
```




    7




```python
df.replace(0, 0.001, inplace=True)
```


```python
df
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
      <th>nombre</th>
      <th>a</th>
      <th>b</th>
      <th>c</th>
      <th>resultado</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>juan</td>
      <td>1</td>
      <td>2</td>
      <td>3.000</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>1</th>
      <td>andres</td>
      <td>6</td>
      <td>7</td>
      <td>0.001</td>
      <td>inf</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.describe()
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
      <th>a</th>
      <th>b</th>
      <th>c</th>
      <th>resultado</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>3.500000</td>
      <td>4.500000</td>
      <td>1.500500</td>
      <td>6500.500000</td>
    </tr>
    <tr>
      <th>std</th>
      <td>3.535534</td>
      <td>3.535534</td>
      <td>2.120613</td>
      <td>9191.681049</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
      <td>2.000000</td>
      <td>0.001000</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>2.250000</td>
      <td>3.250000</td>
      <td>0.750750</td>
      <td>3250.750000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>3.500000</td>
      <td>4.500000</td>
      <td>1.500500</td>
      <td>6500.500000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>4.750000</td>
      <td>5.750000</td>
      <td>2.250250</td>
      <td>9750.250000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>6.000000</td>
      <td>7.000000</td>
      <td>3.000000</td>
      <td>13000.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
df = df.append(df*2)
```


```python
df.replace('juan'*2, 'juan',inplace=True)
```


```python
df.replace('andres'*2, 'andres',inplace=True)
```


```python
df.reset_index(drop=True, inplace=True)
```


```python
help(df.reset_index)
```


```python
#agregacion
```


```python
df
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
      <th>nombre</th>
      <th>a</th>
      <th>b</th>
      <th>c</th>
      <th>resultado</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>juan</td>
      <td>1</td>
      <td>2</td>
      <td>3.000</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>andres</td>
      <td>6</td>
      <td>7</td>
      <td>0.001</td>
      <td>13000.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>juan</td>
      <td>2</td>
      <td>4</td>
      <td>6.000</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>andres</td>
      <td>12</td>
      <td>14</td>
      <td>0.002</td>
      <td>26000.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby('nombre').agg({'a': [sum, 'count'], 'b': lambda x: x.values.tolist()})
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead tr th {
        text-align: left;
    }

    .dataframe thead tr:last-of-type th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th colspan="2" halign="left">a</th>
      <th>b</th>
    </tr>
    <tr>
      <th></th>
      <th>sum</th>
      <th>count</th>
      <th>&lt;lambda&gt;</th>
    </tr>
    <tr>
      <th>nombre</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>andres</th>
      <td>18</td>
      <td>2</td>
      <td>[7, 14]</td>
    </tr>
    <tr>
      <th>juan</th>
      <td>3</td>
      <td>2</td>
      <td>[2, 4]</td>
    </tr>
  </tbody>
</table>
</div>




```python
df_1 = pd.DataFrame(d['contents'])
```


```python
list_dict_0 = df_1.monthlySales.iloc[0]
```


```python
list_dict_1 = df_1.monthlySales.iloc[1]
```


```python
df_0_0 = pd.DataFrame(list_dict_0)
```


```python
summary =df_0_0.describe()
```


```python
summary.loc['50%'].sales
```




    39.5




```python
df_0_0.sort_values('sales', inplace=True)
```


```python
df_0_0.shape
```




    (12, 2)




```python
df_0_0.reset_index(drop=True, inplace=True)
```


```python
df_0_0.iloc[5:7]
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
      <th>month</th>
      <th>sales</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>5</th>
      <td>20130901</td>
      <td>38</td>
    </tr>
    <tr>
      <th>6</th>
      <td>20130301</td>
      <td>41</td>
    </tr>
  </tbody>
</table>
</div>




```python
df_0_0.sales.max()
```




    78




```python
df_0_0.sales.mean()
```




    47.333333333333336




```python
np.isclose(df_0_0.sales , df_0_0.sales.mean(), 0.2)
```




    array([False, False, False, False,  True,  True,  True,  True, False,
           False, False, False])




```python
df_0_0[np.isclose(df_0_0.sales , df_0_0.sales.mean(), rtol =0.15)]
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
      <th>month</th>
      <th>sales</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>6</th>
      <td>20130301</td>
      <td>41</td>
    </tr>
  </tbody>
</table>
</div>




```python
import numpy as np
```


```python
np.isclose(3.14, 3.141,0.0001 )
```




    False




```python
rng = pd.date_range('1/1/2011', periods=72, freq='H')
```


```python
my_df.set_index(rng[:len(my_df)])
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
      <th>nombre_col</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2011-01-01 00:00:00</th>
      <td>1</td>
    </tr>
    <tr>
      <th>2011-01-01 01:00:00</th>
      <td>2</td>
    </tr>
    <tr>
      <th>2011-01-01 02:00:00</th>
      <td>3</td>
    </tr>
    <tr>
      <th>2011-01-01 03:00:00</th>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>


