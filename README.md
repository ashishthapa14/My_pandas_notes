# Pandas:

+ Pandas is a powerful python data analysis Toolkit.
+ Open Source

## Data Structure:

+ Series *lablled Homogenous*
+ DataFrame *Hetrogenous tabular*
+ Panel *3d labelled Array*


```python
import pandas as pd
import numpy as np
```

### Series:


```python
#short method of creating Series:
series_1 = pd.Series([1,2,3,4]) 
series_1
```




    0    1
    1    2
    2    3
    3    4
    dtype: int64




```python
#changing index:
series_2 = pd.Series([1,2,3,4],index = ['a','b','c','d']) #index should be equal to data values:
series_2
```




    a    1
    b    2
    c    3
    d    4
    dtype: int64




```python
#changing datatype: (optional)
series_2 = pd.Series([30, 35, 40], index=['2015 Sales', '2016 Sales', '2017 Sales'], name='Product A')
series_2
```




    2015 Sales    30
    2016 Sales    35
    2017 Sales    40
    Name: Product A, dtype: int64




```python
#creating series with dict:
people = {'a' : 1,'b':2,'c':3}
series_3 = pd.Series(people)
series_3
```




    a    1
    b    2
    c    3
    dtype: int64



#### access the value of series:


```python
#slicing series:
series_2[0:2]
```




    2015 Sales    30
    2016 Sales    35
    Name: Product A, dtype: int64



##### aggregate function applicable on Series:

### DataFrame:

A DataFrame is a table. It contains an array of individual entries, each of which has a certain value. Each entry corresponds to a row (or record) and a column.

#### Creating DataFrame:


```python
#creating dataframe:
pd.DataFrame({'Yes': [50, 21], 'No': [131, 2]})
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
      <th>Yes</th>
      <th>No</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>50</td>
      <td>131</td>
    </tr>
    <tr>
      <th>1</th>
      <td>21</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.DataFrame({'Bob': ['I liked it.', 'It was awful.'], 'Sue': ['Pretty good.', 'Bland.']})
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
      <th>Bob</th>
      <th>Sue</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>I liked it.</td>
      <td>Pretty good.</td>
    </tr>
    <tr>
      <th>1</th>
      <td>It was awful.</td>
      <td>Bland.</td>
    </tr>
  </tbody>
</table>
</div>



+ Row labels used in a DataFrame is known as an **Index**.
+ We can assign values to it by using an index parameter


```python
pd.DataFrame({'Bob': ['I liked it.', 'It was awful.'], 
              'Sue': ['Pretty good.', 'Bland.']},
             index=['Product A', 'Product B'])
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
      <th>Bob</th>
      <th>Sue</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Product A</th>
      <td>I liked it.</td>
      <td>Pretty good.</td>
    </tr>
    <tr>
      <th>Product B</th>
      <td>It was awful.</td>
      <td>Bland.</td>
    </tr>
  </tbody>
</table>
</div>



#### Reading DataFiles:


```python
df = pd.read_csv("D:\\Dataset_ash\\SQL Case Study\\athlete_events.csv")
df.head()
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
      <th>ID</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>A Dijiang</td>
      <td>M</td>
      <td>24.0</td>
      <td>180.0</td>
      <td>80.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>1992 Summer</td>
      <td>1992</td>
      <td>Summer</td>
      <td>Barcelona</td>
      <td>Basketball</td>
      <td>Basketball Men's Basketball</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>A Lamusi</td>
      <td>M</td>
      <td>23.0</td>
      <td>170.0</td>
      <td>60.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>2012 Summer</td>
      <td>2012</td>
      <td>Summer</td>
      <td>London</td>
      <td>Judo</td>
      <td>Judo Men's Extra-Lightweight</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Gunnar Nielsen Aaby</td>
      <td>M</td>
      <td>24.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark</td>
      <td>DEN</td>
      <td>1920 Summer</td>
      <td>1920</td>
      <td>Summer</td>
      <td>Antwerpen</td>
      <td>Football</td>
      <td>Football Men's Football</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Edgar Lindenau Aabye</td>
      <td>M</td>
      <td>34.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark/Sweden</td>
      <td>DEN</td>
      <td>1900 Summer</td>
      <td>1900</td>
      <td>Summer</td>
      <td>Paris</td>
      <td>Tug-Of-War</td>
      <td>Tug-Of-War Men's Tug-Of-War</td>
      <td>Gold</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Christine Jacoba Aaftink</td>
      <td>F</td>
      <td>21.0</td>
      <td>185.0</td>
      <td>82.0</td>
      <td>Netherlands</td>
      <td>NED</td>
      <td>1988 Winter</td>
      <td>1988</td>
      <td>Winter</td>
      <td>Calgary</td>
      <td>Speed Skating</td>
      <td>Speed Skating Women's 500 metres</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
#in read_csv you can specify your own index:
pd.read_csv("D:\\Dataset_ash\\SQL Case Study\\athlete_events.csv",index_col = 'ID').tail()
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
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
    </tr>
    <tr>
      <th>ID</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>135569</th>
      <td>Andrzej ya</td>
      <td>M</td>
      <td>29.0</td>
      <td>179.0</td>
      <td>89.0</td>
      <td>Poland-1</td>
      <td>POL</td>
      <td>1976 Winter</td>
      <td>1976</td>
      <td>Winter</td>
      <td>Innsbruck</td>
      <td>Luge</td>
      <td>Luge Mixed (Men)'s Doubles</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>135570</th>
      <td>Piotr ya</td>
      <td>M</td>
      <td>27.0</td>
      <td>176.0</td>
      <td>59.0</td>
      <td>Poland</td>
      <td>POL</td>
      <td>2014 Winter</td>
      <td>2014</td>
      <td>Winter</td>
      <td>Sochi</td>
      <td>Ski Jumping</td>
      <td>Ski Jumping Men's Large Hill, Individual</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>135570</th>
      <td>Piotr ya</td>
      <td>M</td>
      <td>27.0</td>
      <td>176.0</td>
      <td>59.0</td>
      <td>Poland</td>
      <td>POL</td>
      <td>2014 Winter</td>
      <td>2014</td>
      <td>Winter</td>
      <td>Sochi</td>
      <td>Ski Jumping</td>
      <td>Ski Jumping Men's Large Hill, Team</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>135571</th>
      <td>Tomasz Ireneusz ya</td>
      <td>M</td>
      <td>30.0</td>
      <td>185.0</td>
      <td>96.0</td>
      <td>Poland</td>
      <td>POL</td>
      <td>1998 Winter</td>
      <td>1998</td>
      <td>Winter</td>
      <td>Nagano</td>
      <td>Bobsleigh</td>
      <td>Bobsleigh Men's Four</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>135571</th>
      <td>Tomasz Ireneusz ya</td>
      <td>M</td>
      <td>34.0</td>
      <td>185.0</td>
      <td>96.0</td>
      <td>Poland</td>
      <td>POL</td>
      <td>2002 Winter</td>
      <td>2002</td>
      <td>Winter</td>
      <td>Salt Lake City</td>
      <td>Bobsleigh</td>
      <td>Bobsleigh Men's Four</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
#shape attribute to check the dimension of dataframe:
df.shape
```




    (271116, 15)



##### if you want to see full  dataframe:
+ pd.set_option('display.max_rows' , 'number_of_rows')
+ pd.set_option('display.max_columns', 'number_of_columns')


```python
#head() command, which grabs the first five rows:
df.head()
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
      <th>ID</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>A Dijiang</td>
      <td>M</td>
      <td>24.0</td>
      <td>180.0</td>
      <td>80.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>1992 Summer</td>
      <td>1992</td>
      <td>Summer</td>
      <td>Barcelona</td>
      <td>Basketball</td>
      <td>Basketball Men's Basketball</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>A Lamusi</td>
      <td>M</td>
      <td>23.0</td>
      <td>170.0</td>
      <td>60.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>2012 Summer</td>
      <td>2012</td>
      <td>Summer</td>
      <td>London</td>
      <td>Judo</td>
      <td>Judo Men's Extra-Lightweight</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Gunnar Nielsen Aaby</td>
      <td>M</td>
      <td>24.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark</td>
      <td>DEN</td>
      <td>1920 Summer</td>
      <td>1920</td>
      <td>Summer</td>
      <td>Antwerpen</td>
      <td>Football</td>
      <td>Football Men's Football</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Edgar Lindenau Aabye</td>
      <td>M</td>
      <td>34.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark/Sweden</td>
      <td>DEN</td>
      <td>1900 Summer</td>
      <td>1900</td>
      <td>Summer</td>
      <td>Paris</td>
      <td>Tug-Of-War</td>
      <td>Tug-Of-War Men's Tug-Of-War</td>
      <td>Gold</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Christine Jacoba Aaftink</td>
      <td>F</td>
      <td>21.0</td>
      <td>185.0</td>
      <td>82.0</td>
      <td>Netherlands</td>
      <td>NED</td>
      <td>1988 Winter</td>
      <td>1988</td>
      <td>Winter</td>
      <td>Calgary</td>
      <td>Speed Skating</td>
      <td>Speed Skating Women's 500 metres</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



##### Native accessors:
In Python, we can access the property of an object by accessing it as an attribute. 


```python
#method 1
df.City
```




    0              Barcelona
    1                 London
    2              Antwerpen
    3                  Paris
    4                Calgary
                   ...      
    271111         Innsbruck
    271112             Sochi
    271113             Sochi
    271114            Nagano
    271115    Salt Lake City
    Name: City, Length: 271116, dtype: object




```python
#method 2
df['City'] 
```




    0              Barcelona
    1                 London
    2              Antwerpen
    3                  Paris
    4                Calgary
                   ...      
    271111         Innsbruck
    271112             Sochi
    271113             Sochi
    271114            Nagano
    271115    Salt Lake City
    Name: City, Length: 271116, dtype: object



**Always use second method**

##### Indexing in Pandas: 

The indexing operator and attribute selection are nice because they work just like they do in the rest of the Python ecosystem. As a novice, this makes them easy to pick up and use. However, pandas has its own accessor operators, loc and iloc.


```python
#both loc and iloc is row first and column second:
from IPython import display
display.Image("C:\\Users\\thapa\\Downloads\\Pandas-selections-and-indexing.png")
```




    
![png](output_32_0.png)
    



###### Index based selection: 
The first is index-based selection: selecting data based on its numerical position in the data.


```python
#To select the first row of data in a DataFrame:
df.iloc[0]
```




    ID                                  1
    Name                        A Dijiang
    Sex                                 M
    Age                                24
    Height                            180
    Weight                             80
    Team                            China
    NOC                               CHN
    Games                     1992 Summer
    Year                             1992
    Season                         Summer
    City                        Barcelona
    Sport                      Basketball
    Event     Basketball Men's Basketball
    Medal                             NaN
    Name: 0, dtype: object




```python
#methods of rows retrieving:
df.iloc[:,0]
```




    0              1
    1              2
    2              3
    3              4
    4              5
               ...  
    271111    135569
    271112    135570
    271113    135570
    271114    135571
    271115    135571
    Name: ID, Length: 271116, dtype: int64




```python
df.iloc[:3,0]
```




    0    1
    1    2
    2    3
    Name: ID, dtype: int64




```python
df.iloc[1:3,0]
```




    1    2
    2    3
    Name: ID, dtype: int64




```python
df.iloc[[1,2,5],0] #selective rows:
```




    1    2
    2    3
    5    5
    Name: ID, dtype: int64




```python
df.iloc[-5:]
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
      <th>ID</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>271111</th>
      <td>135569</td>
      <td>Andrzej ya</td>
      <td>M</td>
      <td>29.0</td>
      <td>179.0</td>
      <td>89.0</td>
      <td>Poland-1</td>
      <td>POL</td>
      <td>1976 Winter</td>
      <td>1976</td>
      <td>Winter</td>
      <td>Innsbruck</td>
      <td>Luge</td>
      <td>Luge Mixed (Men)'s Doubles</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>271112</th>
      <td>135570</td>
      <td>Piotr ya</td>
      <td>M</td>
      <td>27.0</td>
      <td>176.0</td>
      <td>59.0</td>
      <td>Poland</td>
      <td>POL</td>
      <td>2014 Winter</td>
      <td>2014</td>
      <td>Winter</td>
      <td>Sochi</td>
      <td>Ski Jumping</td>
      <td>Ski Jumping Men's Large Hill, Individual</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>271113</th>
      <td>135570</td>
      <td>Piotr ya</td>
      <td>M</td>
      <td>27.0</td>
      <td>176.0</td>
      <td>59.0</td>
      <td>Poland</td>
      <td>POL</td>
      <td>2014 Winter</td>
      <td>2014</td>
      <td>Winter</td>
      <td>Sochi</td>
      <td>Ski Jumping</td>
      <td>Ski Jumping Men's Large Hill, Team</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>271114</th>
      <td>135571</td>
      <td>Tomasz Ireneusz ya</td>
      <td>M</td>
      <td>30.0</td>
      <td>185.0</td>
      <td>96.0</td>
      <td>Poland</td>
      <td>POL</td>
      <td>1998 Winter</td>
      <td>1998</td>
      <td>Winter</td>
      <td>Nagano</td>
      <td>Bobsleigh</td>
      <td>Bobsleigh Men's Four</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>271115</th>
      <td>135571</td>
      <td>Tomasz Ireneusz ya</td>
      <td>M</td>
      <td>34.0</td>
      <td>185.0</td>
      <td>96.0</td>
      <td>Poland</td>
      <td>POL</td>
      <td>2002 Winter</td>
      <td>2002</td>
      <td>Winter</td>
      <td>Salt Lake City</td>
      <td>Bobsleigh</td>
      <td>Bobsleigh Men's Four</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



###### Label based selection:  
In this paradigm, it's the data index value, not its position, which matters.


```python
df.loc[0,'City']
```




    'Barcelona'




```python
df.loc[:,['Season','City','Sport']].head() #all rows but selective columns, it's way to create subtable of data:
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
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Summer</td>
      <td>Barcelona</td>
      <td>Basketball</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Summer</td>
      <td>London</td>
      <td>Judo</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Summer</td>
      <td>Antwerpen</td>
      <td>Football</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Summer</td>
      <td>Paris</td>
      <td>Tug-Of-War</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Winter</td>
      <td>Calgary</td>
      <td>Speed Skating</td>
    </tr>
  </tbody>
</table>
</div>



##### Manipulating the index:
Label-based selection derives its power from the labels in the index. Critically, the index we use is not immutable. We can manipulate the index in any way we see fit.

The set_index() method can be used to do the job. Here is what happens when we set_index to the title field:


```python
df.set_index('City').head()
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
      <th>ID</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
    </tr>
    <tr>
      <th>City</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Barcelona</th>
      <td>1</td>
      <td>A Dijiang</td>
      <td>M</td>
      <td>24.0</td>
      <td>180.0</td>
      <td>80.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>1992 Summer</td>
      <td>1992</td>
      <td>Summer</td>
      <td>Basketball</td>
      <td>Basketball Men's Basketball</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>London</th>
      <td>2</td>
      <td>A Lamusi</td>
      <td>M</td>
      <td>23.0</td>
      <td>170.0</td>
      <td>60.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>2012 Summer</td>
      <td>2012</td>
      <td>Summer</td>
      <td>Judo</td>
      <td>Judo Men's Extra-Lightweight</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Antwerpen</th>
      <td>3</td>
      <td>Gunnar Nielsen Aaby</td>
      <td>M</td>
      <td>24.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark</td>
      <td>DEN</td>
      <td>1920 Summer</td>
      <td>1920</td>
      <td>Summer</td>
      <td>Football</td>
      <td>Football Men's Football</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Paris</th>
      <td>4</td>
      <td>Edgar Lindenau Aabye</td>
      <td>M</td>
      <td>34.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark/Sweden</td>
      <td>DEN</td>
      <td>1900 Summer</td>
      <td>1900</td>
      <td>Summer</td>
      <td>Tug-Of-War</td>
      <td>Tug-Of-War Men's Tug-Of-War</td>
      <td>Gold</td>
    </tr>
    <tr>
      <th>Calgary</th>
      <td>5</td>
      <td>Christine Jacoba Aaftink</td>
      <td>F</td>
      <td>21.0</td>
      <td>185.0</td>
      <td>82.0</td>
      <td>Netherlands</td>
      <td>NED</td>
      <td>1988 Winter</td>
      <td>1988</td>
      <td>Winter</td>
      <td>Speed Skating</td>
      <td>Speed Skating Women's 500 metres</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



#### Conditional Selection(filter):


```python
#filter by specific Medal:
filt = (df['Medal'] == 'Gold')
```


```python
df.loc[filt].head()
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
      <th>ID</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Edgar Lindenau Aabye</td>
      <td>M</td>
      <td>34.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark/Sweden</td>
      <td>DEN</td>
      <td>1900 Summer</td>
      <td>1900</td>
      <td>Summer</td>
      <td>Paris</td>
      <td>Tug-Of-War</td>
      <td>Tug-Of-War Men's Tug-Of-War</td>
      <td>Gold</td>
    </tr>
    <tr>
      <th>42</th>
      <td>17</td>
      <td>Paavo Johannes Aaltonen</td>
      <td>M</td>
      <td>28.0</td>
      <td>175.0</td>
      <td>64.0</td>
      <td>Finland</td>
      <td>FIN</td>
      <td>1948 Summer</td>
      <td>1948</td>
      <td>Summer</td>
      <td>London</td>
      <td>Gymnastics</td>
      <td>Gymnastics Men's Team All-Around</td>
      <td>Gold</td>
    </tr>
    <tr>
      <th>44</th>
      <td>17</td>
      <td>Paavo Johannes Aaltonen</td>
      <td>M</td>
      <td>28.0</td>
      <td>175.0</td>
      <td>64.0</td>
      <td>Finland</td>
      <td>FIN</td>
      <td>1948 Summer</td>
      <td>1948</td>
      <td>Summer</td>
      <td>London</td>
      <td>Gymnastics</td>
      <td>Gymnastics Men's Horse Vault</td>
      <td>Gold</td>
    </tr>
    <tr>
      <th>48</th>
      <td>17</td>
      <td>Paavo Johannes Aaltonen</td>
      <td>M</td>
      <td>28.0</td>
      <td>175.0</td>
      <td>64.0</td>
      <td>Finland</td>
      <td>FIN</td>
      <td>1948 Summer</td>
      <td>1948</td>
      <td>Summer</td>
      <td>London</td>
      <td>Gymnastics</td>
      <td>Gymnastics Men's Pommelled Horse</td>
      <td>Gold</td>
    </tr>
    <tr>
      <th>60</th>
      <td>20</td>
      <td>Kjetil Andr Aamodt</td>
      <td>M</td>
      <td>20.0</td>
      <td>176.0</td>
      <td>85.0</td>
      <td>Norway</td>
      <td>NOR</td>
      <td>1992 Winter</td>
      <td>1992</td>
      <td>Winter</td>
      <td>Albertville</td>
      <td>Alpine Skiing</td>
      <td>Alpine Skiing Men's Super G</td>
      <td>Gold</td>
    </tr>
  </tbody>
</table>
</div>




```python
#filter by Boolean operators:
filt = (df['Season'] == 'Summer') | (df['City'] == 'London')  # & = and , | = or , ~ = negation 
```


```python
df.loc[~filt].head()
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
      <th>ID</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Christine Jacoba Aaftink</td>
      <td>F</td>
      <td>21.0</td>
      <td>185.0</td>
      <td>82.0</td>
      <td>Netherlands</td>
      <td>NED</td>
      <td>1988 Winter</td>
      <td>1988</td>
      <td>Winter</td>
      <td>Calgary</td>
      <td>Speed Skating</td>
      <td>Speed Skating Women's 500 metres</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5</th>
      <td>5</td>
      <td>Christine Jacoba Aaftink</td>
      <td>F</td>
      <td>21.0</td>
      <td>185.0</td>
      <td>82.0</td>
      <td>Netherlands</td>
      <td>NED</td>
      <td>1988 Winter</td>
      <td>1988</td>
      <td>Winter</td>
      <td>Calgary</td>
      <td>Speed Skating</td>
      <td>Speed Skating Women's 1,000 metres</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6</th>
      <td>5</td>
      <td>Christine Jacoba Aaftink</td>
      <td>F</td>
      <td>25.0</td>
      <td>185.0</td>
      <td>82.0</td>
      <td>Netherlands</td>
      <td>NED</td>
      <td>1992 Winter</td>
      <td>1992</td>
      <td>Winter</td>
      <td>Albertville</td>
      <td>Speed Skating</td>
      <td>Speed Skating Women's 500 metres</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>7</th>
      <td>5</td>
      <td>Christine Jacoba Aaftink</td>
      <td>F</td>
      <td>25.0</td>
      <td>185.0</td>
      <td>82.0</td>
      <td>Netherlands</td>
      <td>NED</td>
      <td>1992 Winter</td>
      <td>1992</td>
      <td>Winter</td>
      <td>Albertville</td>
      <td>Speed Skating</td>
      <td>Speed Skating Women's 1,000 metres</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>8</th>
      <td>5</td>
      <td>Christine Jacoba Aaftink</td>
      <td>F</td>
      <td>27.0</td>
      <td>185.0</td>
      <td>82.0</td>
      <td>Netherlands</td>
      <td>NED</td>
      <td>1994 Winter</td>
      <td>1994</td>
      <td>Winter</td>
      <td>Lillehammer</td>
      <td>Speed Skating</td>
      <td>Speed Skating Women's 500 metres</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
#creating filter by highest fare:
filt = (df['Height'] < df['Height'].median())
```


```python
df.loc[filt,['Age','Height','Weight','Team']].head()
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
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>23.0</td>
      <td>170.0</td>
      <td>60.0</td>
      <td>China</td>
    </tr>
    <tr>
      <th>26</th>
      <td>18.0</td>
      <td>168.0</td>
      <td>NaN</td>
      <td>Netherlands</td>
    </tr>
    <tr>
      <th>27</th>
      <td>18.0</td>
      <td>168.0</td>
      <td>NaN</td>
      <td>Netherlands</td>
    </tr>
    <tr>
      <th>31</th>
      <td>31.0</td>
      <td>172.0</td>
      <td>70.0</td>
      <td>Finland</td>
    </tr>
    <tr>
      <th>32</th>
      <td>30.0</td>
      <td>159.0</td>
      <td>55.5</td>
      <td>Finland</td>
    </tr>
  </tbody>
</table>
</div>



**Pandas comes with a few built-in conditional selectors, two of which we will highlight here.**
+ **isin is lets you select data whose value "is in" a list of values.**


```python
#filter by isin():
team_filt = ['China','India','Australia']
filt = df['Team'].isin(team_filt)
```


```python
df.loc[filt,['Age','Height','Weight','Team']].head()
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
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>24.0</td>
      <td>180.0</td>
      <td>80.0</td>
      <td>China</td>
    </tr>
    <tr>
      <th>1</th>
      <td>23.0</td>
      <td>170.0</td>
      <td>60.0</td>
      <td>China</td>
    </tr>
    <tr>
      <th>274</th>
      <td>21.0</td>
      <td>184.0</td>
      <td>87.0</td>
      <td>Australia</td>
    </tr>
    <tr>
      <th>453</th>
      <td>30.0</td>
      <td>178.0</td>
      <td>66.0</td>
      <td>Australia</td>
    </tr>
    <tr>
      <th>454</th>
      <td>34.0</td>
      <td>178.0</td>
      <td>66.0</td>
      <td>Australia</td>
    </tr>
  </tbody>
</table>
</div>



+ **The second is isnull (and its companion notnull)**


```python
filt = df.Age.notnull()
```


```python
df.loc[filt].head()
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
      <th>ID</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>A Dijiang</td>
      <td>M</td>
      <td>24.0</td>
      <td>180.0</td>
      <td>80.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>1992 Summer</td>
      <td>1992</td>
      <td>Summer</td>
      <td>Barcelona</td>
      <td>Basketball</td>
      <td>Basketball Men's Basketball</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>A Lamusi</td>
      <td>M</td>
      <td>23.0</td>
      <td>170.0</td>
      <td>60.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>2012 Summer</td>
      <td>2012</td>
      <td>Summer</td>
      <td>London</td>
      <td>Judo</td>
      <td>Judo Men's Extra-Lightweight</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Gunnar Nielsen Aaby</td>
      <td>M</td>
      <td>24.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark</td>
      <td>DEN</td>
      <td>1920 Summer</td>
      <td>1920</td>
      <td>Summer</td>
      <td>Antwerpen</td>
      <td>Football</td>
      <td>Football Men's Football</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Edgar Lindenau Aabye</td>
      <td>M</td>
      <td>34.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark/Sweden</td>
      <td>DEN</td>
      <td>1900 Summer</td>
      <td>1900</td>
      <td>Summer</td>
      <td>Paris</td>
      <td>Tug-Of-War</td>
      <td>Tug-Of-War Men's Tug-Of-War</td>
      <td>Gold</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Christine Jacoba Aaftink</td>
      <td>F</td>
      <td>21.0</td>
      <td>185.0</td>
      <td>82.0</td>
      <td>Netherlands</td>
      <td>NED</td>
      <td>1988 Winter</td>
      <td>1988</td>
      <td>Winter</td>
      <td>Calgary</td>
      <td>Speed Skating</td>
      <td>Speed Skating Women's 500 metres</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
#filter by specific string contains:
filt = df.Event.str.contains("Men's",na=False)
```


```python
df.loc[filt].head()
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
      <th>ID</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>A Dijiang</td>
      <td>M</td>
      <td>24.0</td>
      <td>180.0</td>
      <td>80.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>1992 Summer</td>
      <td>1992</td>
      <td>Summer</td>
      <td>Barcelona</td>
      <td>Basketball</td>
      <td>Basketball Men's Basketball</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>A Lamusi</td>
      <td>M</td>
      <td>23.0</td>
      <td>170.0</td>
      <td>60.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>2012 Summer</td>
      <td>2012</td>
      <td>Summer</td>
      <td>London</td>
      <td>Judo</td>
      <td>Judo Men's Extra-Lightweight</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Gunnar Nielsen Aaby</td>
      <td>M</td>
      <td>24.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark</td>
      <td>DEN</td>
      <td>1920 Summer</td>
      <td>1920</td>
      <td>Summer</td>
      <td>Antwerpen</td>
      <td>Football</td>
      <td>Football Men's Football</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Edgar Lindenau Aabye</td>
      <td>M</td>
      <td>34.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark/Sweden</td>
      <td>DEN</td>
      <td>1900 Summer</td>
      <td>1900</td>
      <td>Summer</td>
      <td>Paris</td>
      <td>Tug-Of-War</td>
      <td>Tug-Of-War Men's Tug-Of-War</td>
      <td>Gold</td>
    </tr>
    <tr>
      <th>10</th>
      <td>6</td>
      <td>Per Knut Aaland</td>
      <td>M</td>
      <td>31.0</td>
      <td>188.0</td>
      <td>75.0</td>
      <td>United States</td>
      <td>USA</td>
      <td>1992 Winter</td>
      <td>1992</td>
      <td>Winter</td>
      <td>Albertville</td>
      <td>Cross Country Skiing</td>
      <td>Cross Country Skiing Men's 10 kilometres</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



#### Sorting:


```python
df.sort_values(by = 'Age',ascending=True).head() #ascending order:
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
      <th>ID</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>142882</th>
      <td>71691</td>
      <td>Dimitrios Loundras</td>
      <td>M</td>
      <td>10.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Ethnikos Gymnastikos Syllogos</td>
      <td>GRE</td>
      <td>1896 Summer</td>
      <td>1896</td>
      <td>Summer</td>
      <td>Athina</td>
      <td>Gymnastics</td>
      <td>Gymnastics Men's Parallel Bars, Teams</td>
      <td>Bronze</td>
    </tr>
    <tr>
      <th>252231</th>
      <td>126307</td>
      <td>Liana Vicens</td>
      <td>F</td>
      <td>11.0</td>
      <td>158.0</td>
      <td>50.0</td>
      <td>Puerto Rico</td>
      <td>PUR</td>
      <td>1968 Summer</td>
      <td>1968</td>
      <td>Summer</td>
      <td>Mexico City</td>
      <td>Swimming</td>
      <td>Swimming Women's 200 metres Breaststroke</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>101378</th>
      <td>51268</td>
      <td>Beatrice Hutiu</td>
      <td>F</td>
      <td>11.0</td>
      <td>151.0</td>
      <td>38.0</td>
      <td>Romania</td>
      <td>ROU</td>
      <td>1968 Winter</td>
      <td>1968</td>
      <td>Winter</td>
      <td>Grenoble</td>
      <td>Figure Skating</td>
      <td>Figure Skating Women's Singles</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>140650</th>
      <td>70616</td>
      <td>Liu Luyang</td>
      <td>F</td>
      <td>11.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>China</td>
      <td>CHN</td>
      <td>1988 Winter</td>
      <td>1988</td>
      <td>Winter</td>
      <td>Calgary</td>
      <td>Figure Skating</td>
      <td>Figure Skating Mixed Ice Dancing</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>237141</th>
      <td>118925</td>
      <td>Megan Olwen Devenish Taylor (-Mandeville-Ellis)</td>
      <td>F</td>
      <td>11.0</td>
      <td>157.0</td>
      <td>NaN</td>
      <td>Great Britain</td>
      <td>GBR</td>
      <td>1932 Winter</td>
      <td>1932</td>
      <td>Winter</td>
      <td>Lake Placid</td>
      <td>Figure Skating</td>
      <td>Figure Skating Women's Singles</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
#descending order sort:
df.sort_values(by = 'Age' , ascending = False).head()
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
      <th>ID</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>257054</th>
      <td>128719</td>
      <td>John Quincy Adams Ward</td>
      <td>M</td>
      <td>97.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>United States</td>
      <td>USA</td>
      <td>1928 Summer</td>
      <td>1928</td>
      <td>Summer</td>
      <td>Amsterdam</td>
      <td>Art Competitions</td>
      <td>Art Competitions Mixed Sculpturing, Statues</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>98118</th>
      <td>49663</td>
      <td>Winslow Homer</td>
      <td>M</td>
      <td>96.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>United States</td>
      <td>USA</td>
      <td>1932 Summer</td>
      <td>1932</td>
      <td>Summer</td>
      <td>Los Angeles</td>
      <td>Art Competitions</td>
      <td>Art Competitions Mixed Painting, Unknown Event</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>60863</th>
      <td>31173</td>
      <td>Thomas Cowperthwait Eakins</td>
      <td>M</td>
      <td>88.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>United States</td>
      <td>USA</td>
      <td>1932 Summer</td>
      <td>1932</td>
      <td>Summer</td>
      <td>Los Angeles</td>
      <td>Art Competitions</td>
      <td>Art Competitions Mixed Painting, Unknown Event</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>60861</th>
      <td>31173</td>
      <td>Thomas Cowperthwait Eakins</td>
      <td>M</td>
      <td>88.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>United States</td>
      <td>USA</td>
      <td>1932 Summer</td>
      <td>1932</td>
      <td>Summer</td>
      <td>Los Angeles</td>
      <td>Art Competitions</td>
      <td>Art Competitions Mixed Painting, Unknown Event</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>60862</th>
      <td>31173</td>
      <td>Thomas Cowperthwait Eakins</td>
      <td>M</td>
      <td>88.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>United States</td>
      <td>USA</td>
      <td>1932 Summer</td>
      <td>1932</td>
      <td>Summer</td>
      <td>Los Angeles</td>
      <td>Art Competitions</td>
      <td>Art Competitions Mixed Painting, Unknown Event</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
#can sort on multiple column:
df.sort_values(['Height','Weight']).head()
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
      <th>ID</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>29333</th>
      <td>15150</td>
      <td>Rosario Briones</td>
      <td>F</td>
      <td>15.0</td>
      <td>127.0</td>
      <td>42.0</td>
      <td>Mexico</td>
      <td>MEX</td>
      <td>1968 Summer</td>
      <td>1968</td>
      <td>Summer</td>
      <td>Mexico City</td>
      <td>Gymnastics</td>
      <td>Gymnastics Women's Individual All-Around</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>29334</th>
      <td>15150</td>
      <td>Rosario Briones</td>
      <td>F</td>
      <td>15.0</td>
      <td>127.0</td>
      <td>42.0</td>
      <td>Mexico</td>
      <td>MEX</td>
      <td>1968 Summer</td>
      <td>1968</td>
      <td>Summer</td>
      <td>Mexico City</td>
      <td>Gymnastics</td>
      <td>Gymnastics Women's Team All-Around</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>29335</th>
      <td>15150</td>
      <td>Rosario Briones</td>
      <td>F</td>
      <td>15.0</td>
      <td>127.0</td>
      <td>42.0</td>
      <td>Mexico</td>
      <td>MEX</td>
      <td>1968 Summer</td>
      <td>1968</td>
      <td>Summer</td>
      <td>Mexico City</td>
      <td>Gymnastics</td>
      <td>Gymnastics Women's Floor Exercise</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>29336</th>
      <td>15150</td>
      <td>Rosario Briones</td>
      <td>F</td>
      <td>15.0</td>
      <td>127.0</td>
      <td>42.0</td>
      <td>Mexico</td>
      <td>MEX</td>
      <td>1968 Summer</td>
      <td>1968</td>
      <td>Summer</td>
      <td>Mexico City</td>
      <td>Gymnastics</td>
      <td>Gymnastics Women's Horse Vault</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>29337</th>
      <td>15150</td>
      <td>Rosario Briones</td>
      <td>F</td>
      <td>15.0</td>
      <td>127.0</td>
      <td>42.0</td>
      <td>Mexico</td>
      <td>MEX</td>
      <td>1968 Summer</td>
      <td>1968</td>
      <td>Summer</td>
      <td>Mexico City</td>
      <td>Gymnastics</td>
      <td>Gymnastics Women's Uneven Bars</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
#sort asc and desc different by parsing boolean 
df.sort_values(by = ['Height','Weight'],ascending=[False,True]).head()
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
      <th>ID</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>265040</th>
      <td>132627</td>
      <td>Yao Ming</td>
      <td>M</td>
      <td>20.0</td>
      <td>226.0</td>
      <td>141.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>2000 Summer</td>
      <td>2000</td>
      <td>Summer</td>
      <td>Sydney</td>
      <td>Basketball</td>
      <td>Basketball Men's Basketball</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>265041</th>
      <td>132627</td>
      <td>Yao Ming</td>
      <td>M</td>
      <td>23.0</td>
      <td>226.0</td>
      <td>141.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>2004 Summer</td>
      <td>2004</td>
      <td>Summer</td>
      <td>Athina</td>
      <td>Basketball</td>
      <td>Basketball Men's Basketball</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>265042</th>
      <td>132627</td>
      <td>Yao Ming</td>
      <td>M</td>
      <td>27.0</td>
      <td>226.0</td>
      <td>141.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>2008 Summer</td>
      <td>2008</td>
      <td>Summer</td>
      <td>Beijing</td>
      <td>Basketball</td>
      <td>Basketball Men's Basketball</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>32376</th>
      <td>16639</td>
      <td>Tommy Loren Burleson</td>
      <td>M</td>
      <td>20.0</td>
      <td>223.0</td>
      <td>102.0</td>
      <td>United States</td>
      <td>USA</td>
      <td>1972 Summer</td>
      <td>1972</td>
      <td>Summer</td>
      <td>Munich</td>
      <td>Basketball</td>
      <td>Basketball Men's Basketball</td>
      <td>Silver</td>
    </tr>
    <tr>
      <th>207373</th>
      <td>104059</td>
      <td>Arvydas Romas Sabonis</td>
      <td>M</td>
      <td>23.0</td>
      <td>223.0</td>
      <td>122.0</td>
      <td>Soviet Union</td>
      <td>URS</td>
      <td>1988 Summer</td>
      <td>1988</td>
      <td>Summer</td>
      <td>Seoul</td>
      <td>Basketball</td>
      <td>Basketball Men's Basketball</td>
      <td>Gold</td>
    </tr>
  </tbody>
</table>
</div>




```python
#sort_index: 
df.sort_index().head()
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
      <th>ID</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>A Dijiang</td>
      <td>M</td>
      <td>24.0</td>
      <td>180.0</td>
      <td>80.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>1992 Summer</td>
      <td>1992</td>
      <td>Summer</td>
      <td>Barcelona</td>
      <td>Basketball</td>
      <td>Basketball Men's Basketball</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>A Lamusi</td>
      <td>M</td>
      <td>23.0</td>
      <td>170.0</td>
      <td>60.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>2012 Summer</td>
      <td>2012</td>
      <td>Summer</td>
      <td>London</td>
      <td>Judo</td>
      <td>Judo Men's Extra-Lightweight</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Gunnar Nielsen Aaby</td>
      <td>M</td>
      <td>24.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark</td>
      <td>DEN</td>
      <td>1920 Summer</td>
      <td>1920</td>
      <td>Summer</td>
      <td>Antwerpen</td>
      <td>Football</td>
      <td>Football Men's Football</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Edgar Lindenau Aabye</td>
      <td>M</td>
      <td>34.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark/Sweden</td>
      <td>DEN</td>
      <td>1900 Summer</td>
      <td>1900</td>
      <td>Summer</td>
      <td>Paris</td>
      <td>Tug-Of-War</td>
      <td>Tug-Of-War Men's Tug-Of-War</td>
      <td>Gold</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Christine Jacoba Aaftink</td>
      <td>F</td>
      <td>21.0</td>
      <td>185.0</td>
      <td>82.0</td>
      <td>Netherlands</td>
      <td>NED</td>
      <td>1988 Winter</td>
      <td>1988</td>
      <td>Winter</td>
      <td>Calgary</td>
      <td>Speed Skating</td>
      <td>Speed Skating Women's 500 metres</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
#nsmallest value
df.nsmallest(5,'Age')
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
      <th>ID</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>142882</th>
      <td>71691</td>
      <td>Dimitrios Loundras</td>
      <td>M</td>
      <td>10.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Ethnikos Gymnastikos Syllogos</td>
      <td>GRE</td>
      <td>1896 Summer</td>
      <td>1896</td>
      <td>Summer</td>
      <td>Athina</td>
      <td>Gymnastics</td>
      <td>Gymnastics Men's Parallel Bars, Teams</td>
      <td>Bronze</td>
    </tr>
    <tr>
      <th>43468</th>
      <td>22411</td>
      <td>Magdalena Cecilia Colledge</td>
      <td>F</td>
      <td>11.0</td>
      <td>152.0</td>
      <td>NaN</td>
      <td>Great Britain</td>
      <td>GBR</td>
      <td>1932 Winter</td>
      <td>1932</td>
      <td>Winter</td>
      <td>Lake Placid</td>
      <td>Figure Skating</td>
      <td>Figure Skating Women's Singles</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>73461</th>
      <td>37333</td>
      <td>Carlos Bienvenido Front Barrera</td>
      <td>M</td>
      <td>11.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Spain</td>
      <td>ESP</td>
      <td>1992 Summer</td>
      <td>1992</td>
      <td>Summer</td>
      <td>Barcelona</td>
      <td>Rowing</td>
      <td>Rowing Men's Coxed Eights</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>79024</th>
      <td>40129</td>
      <td>Luigina Giavotti</td>
      <td>F</td>
      <td>11.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Italy</td>
      <td>ITA</td>
      <td>1928 Summer</td>
      <td>1928</td>
      <td>Summer</td>
      <td>Amsterdam</td>
      <td>Gymnastics</td>
      <td>Gymnastics Women's Team All-Around</td>
      <td>Silver</td>
    </tr>
    <tr>
      <th>94058</th>
      <td>47618</td>
      <td>Sonja Henie (-Topping, -Gardiner, -Onstad)</td>
      <td>F</td>
      <td>11.0</td>
      <td>155.0</td>
      <td>45.0</td>
      <td>Norway</td>
      <td>NOR</td>
      <td>1924 Winter</td>
      <td>1924</td>
      <td>Winter</td>
      <td>Chamonix</td>
      <td>Figure Skating</td>
      <td>Figure Skating Women's Singles</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
#nlargest value:
df.nlargest(7,'Age')
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
      <th>ID</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>257054</th>
      <td>128719</td>
      <td>John Quincy Adams Ward</td>
      <td>M</td>
      <td>97.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>United States</td>
      <td>USA</td>
      <td>1928 Summer</td>
      <td>1928</td>
      <td>Summer</td>
      <td>Amsterdam</td>
      <td>Art Competitions</td>
      <td>Art Competitions Mixed Sculpturing, Statues</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>98118</th>
      <td>49663</td>
      <td>Winslow Homer</td>
      <td>M</td>
      <td>96.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>United States</td>
      <td>USA</td>
      <td>1932 Summer</td>
      <td>1932</td>
      <td>Summer</td>
      <td>Los Angeles</td>
      <td>Art Competitions</td>
      <td>Art Competitions Mixed Painting, Unknown Event</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>60861</th>
      <td>31173</td>
      <td>Thomas Cowperthwait Eakins</td>
      <td>M</td>
      <td>88.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>United States</td>
      <td>USA</td>
      <td>1932 Summer</td>
      <td>1932</td>
      <td>Summer</td>
      <td>Los Angeles</td>
      <td>Art Competitions</td>
      <td>Art Competitions Mixed Painting, Unknown Event</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>60862</th>
      <td>31173</td>
      <td>Thomas Cowperthwait Eakins</td>
      <td>M</td>
      <td>88.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>United States</td>
      <td>USA</td>
      <td>1932 Summer</td>
      <td>1932</td>
      <td>Summer</td>
      <td>Los Angeles</td>
      <td>Art Competitions</td>
      <td>Art Competitions Mixed Painting, Unknown Event</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>60863</th>
      <td>31173</td>
      <td>Thomas Cowperthwait Eakins</td>
      <td>M</td>
      <td>88.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>United States</td>
      <td>USA</td>
      <td>1932 Summer</td>
      <td>1932</td>
      <td>Summer</td>
      <td>Los Angeles</td>
      <td>Art Competitions</td>
      <td>Art Competitions Mixed Painting, Unknown Event</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>9371</th>
      <td>5146</td>
      <td>George Denholm Armour</td>
      <td>M</td>
      <td>84.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Great Britain</td>
      <td>GBR</td>
      <td>1948 Summer</td>
      <td>1948</td>
      <td>Summer</td>
      <td>London</td>
      <td>Art Competitions</td>
      <td>Art Competitions Mixed Painting, Unknown Event</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>154855</th>
      <td>77710</td>
      <td>Robert Tait McKenzie</td>
      <td>M</td>
      <td>81.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Canada</td>
      <td>CAN</td>
      <td>1948 Summer</td>
      <td>1948</td>
      <td>Summer</td>
      <td>London</td>
      <td>Art Competitions</td>
      <td>Art Competitions Mixed Sculpturing, Unknown Event</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



#### Summary and Aggregate Function:

Pandas provides many simple "summary functions" which restructure the data in some useful way.


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
      <th>ID</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>271116.000000</td>
      <td>261642.000000</td>
      <td>210945.000000</td>
      <td>208241.000000</td>
      <td>271116.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>68248.954396</td>
      <td>25.556898</td>
      <td>175.338970</td>
      <td>70.702393</td>
      <td>1978.378480</td>
    </tr>
    <tr>
      <th>std</th>
      <td>39022.286345</td>
      <td>6.393561</td>
      <td>10.518462</td>
      <td>14.348020</td>
      <td>29.877632</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
      <td>10.000000</td>
      <td>127.000000</td>
      <td>25.000000</td>
      <td>1896.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>34643.000000</td>
      <td>21.000000</td>
      <td>168.000000</td>
      <td>60.000000</td>
      <td>1960.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>68205.000000</td>
      <td>24.000000</td>
      <td>175.000000</td>
      <td>70.000000</td>
      <td>1988.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>102097.250000</td>
      <td>28.000000</td>
      <td>183.000000</td>
      <td>79.000000</td>
      <td>2002.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>135571.000000</td>
      <td>97.000000</td>
      <td>226.000000</td>
      <td>214.000000</td>
      <td>2016.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
df['Age'].describe()
```




    count    261642.000000
    mean         25.556898
    std           6.393561
    min          10.000000
    25%          21.000000
    50%          24.000000
    75%          28.000000
    max          97.000000
    Name: Age, dtype: float64




```python
df.count()
```




    ID        271116
    Name      271116
    Sex       271116
    Age       261642
    Height    210945
    Weight    208241
    Team      271116
    NOC       271116
    Games     271116
    Year      271116
    Season    271116
    City      271116
    Sport     271116
    Event     271116
    Medal      39783
    dtype: int64




```python
df['Age'].count()
```




    261642




```python
df['NOC'].value_counts()
```




    USA    18853
    FRA    12758
    GBR    12256
    ITA    10715
    GER     9830
           ...  
    YMD        5
    SSD        3
    NBO        2
    UNK        2
    NFL        1
    Name: NOC, Length: 230, dtype: int64




```python
df['NOC'].value_counts(normalize=True)  #it gives percentage of data
```




    USA    0.069539
    FRA    0.047057
    GBR    0.045206
    ITA    0.039522
    GER    0.036258
             ...   
    YMD    0.000018
    SSD    0.000011
    NBO    0.000007
    UNK    0.000007
    NFL    0.000004
    Name: NOC, Length: 230, dtype: float64




```python
df['NOC'].unique()
```




    array(['CHN', 'DEN', 'NED', 'USA', 'FIN', 'NOR', 'ROU', 'EST', 'FRA',
           'MAR', 'ESP', 'EGY', 'IRI', 'BUL', 'ITA', 'CHA', 'AZE', 'SUD',
           'RUS', 'ARG', 'CUB', 'BLR', 'GRE', 'CMR', 'TUR', 'CHI', 'MEX',
           'URS', 'NCA', 'HUN', 'NGR', 'ALG', 'KUW', 'BRN', 'PAK', 'IRQ',
           'UAR', 'LIB', 'QAT', 'MAS', 'GER', 'CAN', 'IRL', 'AUS', 'RSA',
           'ERI', 'TAN', 'JOR', 'TUN', 'LBA', 'BEL', 'DJI', 'PLE', 'COM',
           'KAZ', 'BRU', 'IND', 'KSA', 'SYR', 'MDV', 'ETH', 'UAE', 'YAR',
           'INA', 'PHI', 'SGP', 'UZB', 'KGZ', 'TJK', 'EUN', 'JPN', 'CGO',
           'SUI', 'BRA', 'FRG', 'GDR', 'MON', 'ISR', 'URU', 'SWE', 'ISV',
           'SRI', 'ARM', 'CIV', 'KEN', 'BEN', 'UKR', 'GBR', 'GHA', 'SOM',
           'LAT', 'NIG', 'MLI', 'AFG', 'POL', 'CRC', 'PAN', 'GEO', 'SLO',
           'CRO', 'GUY', 'NZL', 'POR', 'PAR', 'ANG', 'VEN', 'COL', 'BAN',
           'PER', 'ESA', 'PUR', 'UGA', 'HON', 'ECU', 'TKM', 'MRI', 'SEY',
           'TCH', 'LUX', 'MTN', 'CZE', 'SKN', 'TTO', 'DOM', 'VIN', 'JAM',
           'LBR', 'SUR', 'NEP', 'MGL', 'AUT', 'PLW', 'LTU', 'TOG', 'NAM',
           'AHO', 'ISL', 'ASA', 'SAM', 'RWA', 'DMA', 'HAI', 'MLT', 'CYP',
           'GUI', 'BIZ', 'YMD', 'KOR', 'THA', 'BER', 'ANZ', 'SCG', 'SLE',
           'PNG', 'YEM', 'IOA', 'OMA', 'FIJ', 'VAN', 'MDA', 'YUG', 'BAH',
           'GUA', 'SRB', 'IVB', 'MOZ', 'CAF', 'MAD', 'MAL', 'BIH', 'GUM',
           'CAY', 'SVK', 'BAR', 'GBS', 'TLS', 'COD', 'GAB', 'SMR', 'LAO',
           'BOT', 'ROT', 'CAM', 'PRK', 'SOL', 'SEN', 'CPV', 'CRT', 'GEQ',
           'BOL', 'SAA', 'AND', 'ANT', 'ZIM', 'GRN', 'HKG', 'LCA', 'FSM',
           'MYA', 'MAW', 'ZAM', 'RHO', 'TPE', 'STP', 'MKD', 'BOH', 'TGA',
           'LIE', 'MNE', 'GAM', 'COK', 'ALB', 'WIF', 'SWZ', 'BUR', 'NBO',
           'BDI', 'ARU', 'NRU', 'VNM', 'VIE', 'BHU', 'MHL', 'KIR', 'UNK',
           'TUV', 'NFL', 'KOS', 'SSD', 'LES'], dtype=object)



#### Updating rows and columns:


```python
#for this we will use this code snippet:
people = { 'first name' : ['Keshav','Ashish','Nadeem'],
           'last name' : ['Choudhary','Thapa','Khan'],
           'email' : ['choudharykeshav@gmail.com','thapa.ashishkumar3@gmail.com','khanNadeem@gmail.com']
}
```


```python
df_2 = pd.DataFrame(people)
df_2
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
      <th>first name</th>
      <th>last name</th>
      <th>email</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Keshav</td>
      <td>Choudhary</td>
      <td>choudharykeshav@gmail.com</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ashish</td>
      <td>Thapa</td>
      <td>thapa.ashishkumar3@gmail.com</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nadeem</td>
      <td>Khan</td>
      <td>khanNadeem@gmail.com</td>
    </tr>
  </tbody>
</table>
</div>



##### Update columns:


```python
df_2.columns = [x.upper() for x in df_2.columns]
```


```python
df_2
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
      <th>FIRST NAME</th>
      <th>LAST NAME</th>
      <th>EMAIL</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Keshav</td>
      <td>Choudhary</td>
      <td>choudharykeshav@gmail.com</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ashish</td>
      <td>Thapa</td>
      <td>thapa.ashishkumar3@gmail.com</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nadeem</td>
      <td>Khan</td>
      <td>khanNadeem@gmail.com</td>
    </tr>
  </tbody>
</table>
</div>




```python
df_2.columns = df_2.columns.str.replace(' ', '_')
df_2
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
      <th>FIRST_NAME</th>
      <th>LAST_NAME</th>
      <th>EMAIL</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Keshav</td>
      <td>Choudhary</td>
      <td>choudharykeshav@gmail.com</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ashish</td>
      <td>Thapa</td>
      <td>thapa.ashishkumar3@gmail.com</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nadeem</td>
      <td>Khan</td>
      <td>khanNadeem@gmail.com</td>
    </tr>
  </tbody>
</table>
</div>



##### Renaming
+ it lets you change index names and/or column names. 
+ lets you rename index or column values by specifying a index or column keyword parameter, respectively. It supports a variety of input formats, but usually a Python dictionary is the most convenient.


```python
df_2.rename(columns={'FIRST_NAME':'first_name','LAST_NAME':'last_name','EMAIL':'email'},inplace=True)
df_2
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
      <th>first_name</th>
      <th>last_name</th>
      <th>email</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Keshav</td>
      <td>Choudhary</td>
      <td>choudharykeshav@gmail.com</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ashish</td>
      <td>Thapa</td>
      <td>thapa.ashishkumar3@gmail.com</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nadeem</td>
      <td>Khan</td>
      <td>khanNadeem@gmail.com</td>
    </tr>
  </tbody>
</table>
</div>




```python
df_2.rename(index={0: 'firstEntry', 1: 'secondEntry',2:'thirdEntry'})
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
      <th>first_name</th>
      <th>last_name</th>
      <th>email</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>firstEntry</th>
      <td>Keshav</td>
      <td>Choudhary</td>
      <td>choudharykeshav@gmail.com</td>
    </tr>
    <tr>
      <th>secondEntry</th>
      <td>Ashish</td>
      <td>Thapa</td>
      <td>thapa.ashishkumar3@gmail.com</td>
    </tr>
    <tr>
      <th>thirdEntry</th>
      <td>Nadeem</td>
      <td>Khan</td>
      <td>khanNadeem@gmail.com</td>
    </tr>
  </tbody>
</table>
</div>




```python
#this is rare: (optional)
df_2.rename_axis("Entry", axis='rows').rename_axis("Col", axis='columns')
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
      <th>Col</th>
      <th>first_name</th>
      <th>last_name</th>
      <th>email</th>
    </tr>
    <tr>
      <th>Entry</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Keshav</td>
      <td>Choudhary</td>
      <td>choudharykeshav@gmail.com</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ashish</td>
      <td>Thapa</td>
      <td>thapa.ashishkumar3@gmail.com</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nadeem</td>
      <td>Khan</td>
      <td>khanNadeem@gmail.com</td>
    </tr>
  </tbody>
</table>
</div>




```python
#whole column update:
df_2['email'] = df_2['email'].str.upper()
df_2
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
      <th>first_name</th>
      <th>last_name</th>
      <th>email</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Keshav</td>
      <td>Choudhary</td>
      <td>CHOUDHARYKESHAV@GMAIL.COM</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ashish</td>
      <td>Thapa</td>
      <td>THAPA.ASHISHKUMAR3@GMAIL.COM</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nadeem</td>
      <td>Khan</td>
      <td>KHANNADEEM@GMAIL.COM</td>
    </tr>
  </tbody>
</table>
</div>




```python
df_2['email'] = df_2['email'].str.lower()
df_2
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
      <th>first_name</th>
      <th>last_name</th>
      <th>email</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Keshav</td>
      <td>Choudhary</td>
      <td>choudharykeshav@gmail.com</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ashish</td>
      <td>Thapa</td>
      <td>thapa.ashishkumar3@gmail.com</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nadeem</td>
      <td>Khan</td>
      <td>khannadeem@gmail.com</td>
    </tr>
  </tbody>
</table>
</div>



##### Update rows


```python
#updating whole row
df_2.loc[2] = ['John','Smith','johnsmith@gmail.com']
df_2
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
      <th>first_name</th>
      <th>last_name</th>
      <th>email</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Keshav</td>
      <td>Choudhary</td>
      <td>choudharykeshav@gmail.com</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ashish</td>
      <td>Thapa</td>
      <td>thapa.ashishkumar3@gmail.com</td>
    </tr>
    <tr>
      <th>2</th>
      <td>John</td>
      <td>Smith</td>
      <td>johnsmith@gmail.com</td>
    </tr>
  </tbody>
</table>
</div>




```python
#updating specific data point
df_2.iloc[2 , 0] = 'Aakash'
df_2
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
      <th>first_name</th>
      <th>last_name</th>
      <th>email</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Keshav</td>
      <td>Choudhary</td>
      <td>choudharykeshav@gmail.com</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ashish</td>
      <td>Thapa</td>
      <td>thapa.ashishkumar3@gmail.com</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Aakash</td>
      <td>Smith</td>
      <td>johnsmith@gmail.com</td>
    </tr>
  </tbody>
</table>
</div>




```python
df_2.loc[2,['last_name','email']] = ['thapa','thapa.aakashkumar3@gmail.com']
df_2
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
      <th>first_name</th>
      <th>last_name</th>
      <th>email</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Keshav</td>
      <td>Choudhary</td>
      <td>choudharykeshav@gmail.com</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ashish</td>
      <td>Thapa</td>
      <td>thapa.ashishkumar3@gmail.com</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Aakash</td>
      <td>thapa</td>
      <td>thapa.aakashkumar3@gmail.com</td>
    </tr>
  </tbody>
</table>
</div>



*The four method to update rows*
+ apply
+ map
+ applymap
+ replace



```python
#apply can be applicable to both series and dataframes: it help to update and apply function.
df_2['email'].apply(len) 
```




    0    25
    1    28
    2    28
    Name: email, dtype: int64




```python
df_2['first_name'].apply(lambda x: x.lower())
```




    0    keshav
    1    ashish
    2    aakash
    Name: first_name, dtype: object




```python
#applymap is only applicable to dataframe.
df_2.applymap(str.lower)
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
      <th>first_name</th>
      <th>last_name</th>
      <th>email</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>keshav</td>
      <td>choudhary</td>
      <td>choudharykeshav@gmail.com</td>
    </tr>
    <tr>
      <th>1</th>
      <td>ashish</td>
      <td>thapa</td>
      <td>thapa.ashishkumar3@gmail.com</td>
    </tr>
    <tr>
      <th>2</th>
      <td>aakash</td>
      <td>thapa</td>
      <td>thapa.aakashkumar3@gmail.com</td>
    </tr>
  </tbody>
</table>
</div>




```python
#map only works in series:
df_2['first_name'].map({'Ashish': 'nadeem' ,'Aakash' :'kashif' }) 
```




    0       NaN
    1    nadeem
    2    kashif
    Name: first_name, dtype: object




```python
#use replace if you don't want nan:
df_2['first_name'].replace({'Ashish': 'nadeem' ,'Aakash' :'kashif' })
```




    0    Keshav
    1    nadeem
    2    kashif
    Name: first_name, dtype: object



#### Add/Remove Rows and Columns:


```python
#add a column:
df_2['full_name'] = df_2['first_name'] + ' ' + df_2['last_name']
df_2
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
      <th>first_name</th>
      <th>last_name</th>
      <th>email</th>
      <th>full_name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Keshav</td>
      <td>Choudhary</td>
      <td>choudharykeshav@gmail.com</td>
      <td>Keshav Choudhary</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ashish</td>
      <td>Thapa</td>
      <td>thapa.ashishkumar3@gmail.com</td>
      <td>Ashish Thapa</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Aakash</td>
      <td>thapa</td>
      <td>thapa.aakashkumar3@gmail.com</td>
      <td>Aakash thapa</td>
    </tr>
  </tbody>
</table>
</div>




```python
#remove columns:
df_2.drop(columns = ['first_name','last_name'],inplace = True)
```


```python
df_2[['first','last']] = df_2['full_name'].str.split(' ',expand =True)
df_2
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
      <th>email</th>
      <th>full_name</th>
      <th>first</th>
      <th>last</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>choudharykeshav@gmail.com</td>
      <td>Keshav Choudhary</td>
      <td>Keshav</td>
      <td>Choudhary</td>
    </tr>
    <tr>
      <th>1</th>
      <td>thapa.ashishkumar3@gmail.com</td>
      <td>Ashish Thapa</td>
      <td>Ashish</td>
      <td>Thapa</td>
    </tr>
    <tr>
      <th>2</th>
      <td>thapa.aakashkumar3@gmail.com</td>
      <td>Aakash thapa</td>
      <td>Aakash</td>
      <td>thapa</td>
    </tr>
  </tbody>
</table>
</div>




```python
df_2 = df_2.loc[:,['first','last','full_name','email']]
```


```python
#add a row:
x = {'first' : 'Teshav', 'last': 'Ahoudhary','full_name' : 'Teshav_Ahoudhary' , 'email' : ['xyz@gmail.com'] }
```


```python
df_2 = df_2.append(x,ignore_index=True)
df_2
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
      <th>first</th>
      <th>last</th>
      <th>full_name</th>
      <th>email</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Keshav</td>
      <td>Choudhary</td>
      <td>Keshav Choudhary</td>
      <td>choudharykeshav@gmail.com</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ashish</td>
      <td>Thapa</td>
      <td>Ashish Thapa</td>
      <td>thapa.ashishkumar3@gmail.com</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Aakash</td>
      <td>thapa</td>
      <td>Aakash thapa</td>
      <td>thapa.aakashkumar3@gmail.com</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Teshav</td>
      <td>Ahoudhary</td>
      <td>Teshav_Ahoudhary</td>
      <td>[xyz@gmail.com]</td>
    </tr>
  </tbody>
</table>
</div>




```python
#remove a row:
df_2.drop(index = 3)
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
      <th>first</th>
      <th>last</th>
      <th>full_name</th>
      <th>email</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Keshav</td>
      <td>Choudhary</td>
      <td>Keshav Choudhary</td>
      <td>choudharykeshav@gmail.com</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ashish</td>
      <td>Thapa</td>
      <td>Ashish Thapa</td>
      <td>thapa.ashishkumar3@gmail.com</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Aakash</td>
      <td>thapa</td>
      <td>Aakash thapa</td>
      <td>thapa.aakashkumar3@gmail.com</td>
    </tr>
  </tbody>
</table>
</div>




```python
#dropping with condition:
drop_filt = df_2['last'] == 'thapa'
```


```python
df_2.drop(index= df_2[drop_filt].index)
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
      <th>first</th>
      <th>last</th>
      <th>full_name</th>
      <th>email</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Keshav</td>
      <td>Choudhary</td>
      <td>Keshav Choudhary</td>
      <td>choudharykeshav@gmail.com</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ashish</td>
      <td>Thapa</td>
      <td>Ashish Thapa</td>
      <td>thapa.ashishkumar3@gmail.com</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Teshav</td>
      <td>Ahoudhary</td>
      <td>Teshav_Ahoudhary</td>
      <td>[xyz@gmail.com]</td>
    </tr>
  </tbody>
</table>
</div>



#### Group by:


```python
embarked_grp = df.groupby(['Embarked'])
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-79-8a5541432bdc> in <module>
    ----> 1 embarked_grp = df.groupby(['Embarked'])
    

    ~\anaconda3\lib\site-packages\pandas\core\frame.py in groupby(self, by, axis, level, as_index, sort, group_keys, squeeze, observed, dropna)
       6509         axis = self._get_axis_number(axis)
       6510 
    -> 6511         return DataFrameGroupBy(
       6512             obj=self,
       6513             keys=by,
    

    ~\anaconda3\lib\site-packages\pandas\core\groupby\groupby.py in __init__(self, obj, keys, axis, level, grouper, exclusions, selection, as_index, sort, group_keys, squeeze, observed, mutated, dropna)
        523             from pandas.core.groupby.grouper import get_grouper
        524 
    --> 525             grouper, exclusions, obj = get_grouper(
        526                 obj,
        527                 keys,
    

    ~\anaconda3\lib\site-packages\pandas\core\groupby\grouper.py in get_grouper(obj, key, axis, level, sort, observed, mutated, validate, dropna)
        779                 in_axis, name, level, gpr = False, None, gpr, None
        780             else:
    --> 781                 raise KeyError(gpr)
        782         elif isinstance(gpr, Grouper) and gpr.key is not None:
        783             # Add key to exclusions
    

    KeyError: 'Embarked'



```python
embarked_grp['Embarked'].count()
```


```python
embarked_grp.get_group('C') #only c embarked
```

**Above method can also be done by filter**


```python
#group by embarked and in specific selective columns value_counts()
embarked_grp['Cabin'].value_counts()
```


```python
embarked_grp['Cabin'].value_counts(normalize = True).loc['S'].head()  #specific group data
```


```python
#group by aggregate:
embarked_grp['Fare'].mean()
```


```python
#applying more aggregate method
embarked_grp['Fare'].agg(['mean','median'])
```

###### Advance group by method:

**In group by df i am selecting specific column and applying a function which gives me sum of specific string within group:**

country_uses_python = country_grp['LanguageWorkedWith'].apply(lambda x : x.str.contains('Python').sum())

country_uses_python

**multi-index: - A multi-index differs from a regular index in that it has multiple levels.**

survey_public.groupby(['Country','SocialMedia']).Employment.agg([len])

#### Handling missing Data:


```python
#code snippet:
ppl = {
    'first' : ['corey','jane','john','chris',np.nan,None,'NA'],
    'last' : ['schafer','doe','doe','schafer',np.nan,np.nan,'Missing'],
    'email' : ['coreymscha@gmail.com','JaneDoe@email.com','Johndoe@email.com',None,np.nan,'anonympus@gmail.com','NA'],
    'age' : ['33','55','63','36',None,None,'Missing']
}
```


```python
datafram = pd.DataFrame(ppl)

datafram.replace(['NA','Missing'],np.nan,inplace= True)
datafram
```


```python
#dropping all na values:
datafram.dropna()
```


```python
#any deletes all the row which having Nan values.
#all deletes those rows only which have all rows missing value.
#axis = 'index' always us all.
#axis  = 'columns' use all
datafram.dropna(axis = 'index' , how = 'all') 
```


```python
#dropping for specific column:
datafram.dropna(how = 'any', subset = ['email'])
```


```python
datafram.isnull()
```

#### casting:


```python
datafram['age'].dtype
```


```python
#nan values can't be converted into int:
#nan is float

datafram['age'] = datafram['age'].astype('float')
datafram['age'].dtype
```

###### Fill na:


```python
#filling with scaler data:
datafram.fillna(0)
```


```python
#filling with specific column using dict:
datafram.fillna({'first':'Missing','age':0})
```


```python
#filling with forward value:
datafram.fillna(method = 'ffill')
```


```python
#filling with backward fill:
datafram.fillna(method = 'bfill')
```

###### Interpolate

Pandas interpolate() function is basically used to fill nan values in dataframes or series.
+ very powerful function
+ uses various technique.


```python
#only in numeric value:
datafram.interpolate(method = 'linear')
```


```python
#fill with nearest
datafram.interpolate(method = 'nearest')
```

**fill with time**

method == time: 

if column time is not in data time format it will throw an error.

datafram.interpolate(method= 'time')

**fill with polynomial:**
    
datafram.interpolate(method = 'polynomial',order = 2)




```python
datafram.interpolate(limit_direction = 'both')
```

### Merge, Concat and Join

**Merge**

Pandas merge connects columns or index in dataframe based on one or more keys.


```python
df2 = pd.read_csv("D:\\Dataset_ash\\SQL Case Study\\noc_regions.csv")
df2.head()
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
      <th>NOC</th>
      <th>region</th>
      <th>notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>AFG</td>
      <td>Afghanistan</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>AHO</td>
      <td>Curacao</td>
      <td>Netherlands Antilles</td>
    </tr>
    <tr>
      <th>2</th>
      <td>ALB</td>
      <td>Albania</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>ALG</td>
      <td>Algeria</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>AND</td>
      <td>Andorra</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 'on' should be same on both the dataframe. 
# if NOC is not common then only upto same part it gonna print.
pd.merge(df,df2,on = 'NOC',how = 'inner').head()   #left join, right join, inner and outer.
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
      <th>ID</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
      <th>region</th>
      <th>notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>A Dijiang</td>
      <td>M</td>
      <td>24.0</td>
      <td>180.0</td>
      <td>80.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>1992 Summer</td>
      <td>1992</td>
      <td>Summer</td>
      <td>Barcelona</td>
      <td>Basketball</td>
      <td>Basketball Men's Basketball</td>
      <td>NaN</td>
      <td>China</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>A Lamusi</td>
      <td>M</td>
      <td>23.0</td>
      <td>170.0</td>
      <td>60.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>2012 Summer</td>
      <td>2012</td>
      <td>Summer</td>
      <td>London</td>
      <td>Judo</td>
      <td>Judo Men's Extra-Lightweight</td>
      <td>NaN</td>
      <td>China</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>602</td>
      <td>Abudoureheman</td>
      <td>M</td>
      <td>22.0</td>
      <td>182.0</td>
      <td>75.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>2000 Summer</td>
      <td>2000</td>
      <td>Summer</td>
      <td>Sydney</td>
      <td>Boxing</td>
      <td>Boxing Men's Middleweight</td>
      <td>NaN</td>
      <td>China</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1463</td>
      <td>Ai Linuer</td>
      <td>M</td>
      <td>25.0</td>
      <td>160.0</td>
      <td>62.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>2004 Summer</td>
      <td>2004</td>
      <td>Summer</td>
      <td>Athina</td>
      <td>Wrestling</td>
      <td>Wrestling Men's Lightweight, Greco-Roman</td>
      <td>NaN</td>
      <td>China</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1464</td>
      <td>Ai Yanhan</td>
      <td>F</td>
      <td>14.0</td>
      <td>168.0</td>
      <td>54.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>2016 Summer</td>
      <td>2016</td>
      <td>Summer</td>
      <td>Rio de Janeiro</td>
      <td>Swimming</td>
      <td>Swimming Women's 200 metres Freestyle</td>
      <td>NaN</td>
      <td>China</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



**CONCAT**

Pandas provides various facilities for easily combining together series, DataFrame and Panel objects


```python
pd.concat([df,df2],axis =1,join = 'inner').head()
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
      <th>ID</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
      <th>NOC</th>
      <th>region</th>
      <th>notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>A Dijiang</td>
      <td>M</td>
      <td>24.0</td>
      <td>180.0</td>
      <td>80.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>1992 Summer</td>
      <td>1992</td>
      <td>Summer</td>
      <td>Barcelona</td>
      <td>Basketball</td>
      <td>Basketball Men's Basketball</td>
      <td>NaN</td>
      <td>AFG</td>
      <td>Afghanistan</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>A Lamusi</td>
      <td>M</td>
      <td>23.0</td>
      <td>170.0</td>
      <td>60.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>2012 Summer</td>
      <td>2012</td>
      <td>Summer</td>
      <td>London</td>
      <td>Judo</td>
      <td>Judo Men's Extra-Lightweight</td>
      <td>NaN</td>
      <td>AHO</td>
      <td>Curacao</td>
      <td>Netherlands Antilles</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Gunnar Nielsen Aaby</td>
      <td>M</td>
      <td>24.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark</td>
      <td>DEN</td>
      <td>1920 Summer</td>
      <td>1920</td>
      <td>Summer</td>
      <td>Antwerpen</td>
      <td>Football</td>
      <td>Football Men's Football</td>
      <td>NaN</td>
      <td>ALB</td>
      <td>Albania</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Edgar Lindenau Aabye</td>
      <td>M</td>
      <td>34.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark/Sweden</td>
      <td>DEN</td>
      <td>1900 Summer</td>
      <td>1900</td>
      <td>Summer</td>
      <td>Paris</td>
      <td>Tug-Of-War</td>
      <td>Tug-Of-War Men's Tug-Of-War</td>
      <td>Gold</td>
      <td>ALG</td>
      <td>Algeria</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Christine Jacoba Aaftink</td>
      <td>F</td>
      <td>21.0</td>
      <td>185.0</td>
      <td>82.0</td>
      <td>Netherlands</td>
      <td>NED</td>
      <td>1988 Winter</td>
      <td>1988</td>
      <td>Winter</td>
      <td>Calgary</td>
      <td>Speed Skating</td>
      <td>Speed Skating Women's 500 metres</td>
      <td>NaN</td>
      <td>AND</td>
      <td>Andorra</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



**JOIN**

DataFrame join is a convenient method for combining the columns of two potentially differently indexed.


```python
#if dataframe has same column then we have to provide a suffix.
df.join(df2,lsuffix= '-1').head()
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
      <th>ID</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC-1</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
      <th>NOC</th>
      <th>region</th>
      <th>notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>A Dijiang</td>
      <td>M</td>
      <td>24.0</td>
      <td>180.0</td>
      <td>80.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>1992 Summer</td>
      <td>1992</td>
      <td>Summer</td>
      <td>Barcelona</td>
      <td>Basketball</td>
      <td>Basketball Men's Basketball</td>
      <td>NaN</td>
      <td>AFG</td>
      <td>Afghanistan</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>A Lamusi</td>
      <td>M</td>
      <td>23.0</td>
      <td>170.0</td>
      <td>60.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>2012 Summer</td>
      <td>2012</td>
      <td>Summer</td>
      <td>London</td>
      <td>Judo</td>
      <td>Judo Men's Extra-Lightweight</td>
      <td>NaN</td>
      <td>AHO</td>
      <td>Curacao</td>
      <td>Netherlands Antilles</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Gunnar Nielsen Aaby</td>
      <td>M</td>
      <td>24.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark</td>
      <td>DEN</td>
      <td>1920 Summer</td>
      <td>1920</td>
      <td>Summer</td>
      <td>Antwerpen</td>
      <td>Football</td>
      <td>Football Men's Football</td>
      <td>NaN</td>
      <td>ALB</td>
      <td>Albania</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Edgar Lindenau Aabye</td>
      <td>M</td>
      <td>34.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark/Sweden</td>
      <td>DEN</td>
      <td>1900 Summer</td>
      <td>1900</td>
      <td>Summer</td>
      <td>Paris</td>
      <td>Tug-Of-War</td>
      <td>Tug-Of-War Men's Tug-Of-War</td>
      <td>Gold</td>
      <td>ALG</td>
      <td>Algeria</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Christine Jacoba Aaftink</td>
      <td>F</td>
      <td>21.0</td>
      <td>185.0</td>
      <td>82.0</td>
      <td>Netherlands</td>
      <td>NED</td>
      <td>1988 Winter</td>
      <td>1988</td>
      <td>Winter</td>
      <td>Calgary</td>
      <td>Speed Skating</td>
      <td>Speed Skating Women's 500 metres</td>
      <td>NaN</td>
      <td>AND</td>
      <td>Andorra</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



#### Pandas Pivot Table:

The levels in the pivot table will be stored in multiindex objects(hierarchical indexes) on the index and columns of the result DataFrame


```python
df.pivot_table(index = 'NOC').head()
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
      <th>Age</th>
      <th>Height</th>
      <th>ID</th>
      <th>Weight</th>
      <th>Year</th>
    </tr>
    <tr>
      <th>NOC</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>AFG</th>
      <td>23.538462</td>
      <td>170.592593</td>
      <td>70778.373016</td>
      <td>65.901639</td>
      <td>1966.031746</td>
    </tr>
    <tr>
      <th>AHO</th>
      <td>26.589744</td>
      <td>177.294118</td>
      <td>56438.518987</td>
      <td>76.176471</td>
      <td>1980.911392</td>
    </tr>
    <tr>
      <th>ALB</th>
      <td>25.342857</td>
      <td>173.000000</td>
      <td>76332.300000</td>
      <td>71.491803</td>
      <td>2002.257143</td>
    </tr>
    <tr>
      <th>ALG</th>
      <td>24.370642</td>
      <td>174.702869</td>
      <td>49394.666062</td>
      <td>68.693252</td>
      <td>1997.851180</td>
    </tr>
    <tr>
      <th>AND</th>
      <td>23.065089</td>
      <td>173.703704</td>
      <td>64885.218935</td>
      <td>70.644444</td>
      <td>1997.029586</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.pivot_table(index = 'NOC',columns = 'Year',aggfunc='count',fill_value = 0).head()
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
      <th colspan="10" halign="left">Age</th>
      <th>...</th>
      <th colspan="10" halign="left">Weight</th>
    </tr>
    <tr>
      <th>Year</th>
      <th>1896</th>
      <th>1900</th>
      <th>1904</th>
      <th>1906</th>
      <th>1908</th>
      <th>1912</th>
      <th>1920</th>
      <th>1924</th>
      <th>1928</th>
      <th>1932</th>
      <th>...</th>
      <th>1998</th>
      <th>2000</th>
      <th>2002</th>
      <th>2004</th>
      <th>2006</th>
      <th>2008</th>
      <th>2010</th>
      <th>2012</th>
      <th>2014</th>
      <th>2016</th>
    </tr>
    <tr>
      <th>NOC</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>AFG</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>4</td>
      <td>0</td>
      <td>4</td>
      <td>0</td>
      <td>6</td>
      <td>0</td>
      <td>3</td>
    </tr>
    <tr>
      <th>AHO</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>8</td>
      <td>0</td>
      <td>3</td>
      <td>0</td>
      <td>4</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>ALB</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>5</td>
      <td>0</td>
      <td>7</td>
      <td>3</td>
      <td>12</td>
      <td>2</td>
      <td>10</td>
      <td>2</td>
      <td>6</td>
    </tr>
    <tr>
      <th>ALG</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>51</td>
      <td>0</td>
      <td>69</td>
      <td>3</td>
      <td>56</td>
      <td>1</td>
      <td>35</td>
      <td>0</td>
      <td>74</td>
    </tr>
    <tr>
      <th>AND</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>7</td>
      <td>5</td>
      <td>5</td>
      <td>6</td>
      <td>10</td>
      <td>5</td>
      <td>20</td>
      <td>5</td>
      <td>12</td>
      <td>4</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 455 columns</p>
</div>



#### unpivot:

A dataframe turn it from  a wide format (many columns) to a long format (few columns but many rows)

#### Melt function

Pandas melt function is used to transform or reshape data.


```python
pd.melt(df, id_vars = ['Medal'])
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
      <th>Medal</th>
      <th>variable</th>
      <th>value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>NaN</td>
      <td>ID</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>NaN</td>
      <td>ID</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>NaN</td>
      <td>ID</td>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Gold</td>
      <td>ID</td>
      <td>4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>NaN</td>
      <td>ID</td>
      <td>5</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>3795619</th>
      <td>NaN</td>
      <td>Event</td>
      <td>Luge Mixed (Men)'s Doubles</td>
    </tr>
    <tr>
      <th>3795620</th>
      <td>NaN</td>
      <td>Event</td>
      <td>Ski Jumping Men's Large Hill, Individual</td>
    </tr>
    <tr>
      <th>3795621</th>
      <td>NaN</td>
      <td>Event</td>
      <td>Ski Jumping Men's Large Hill, Team</td>
    </tr>
    <tr>
      <th>3795622</th>
      <td>NaN</td>
      <td>Event</td>
      <td>Bobsleigh Men's Four</td>
    </tr>
    <tr>
      <th>3795623</th>
      <td>NaN</td>
      <td>Event</td>
      <td>Bobsleigh Men's Four</td>
    </tr>
  </tbody>
</table>
<p>3795624 rows × 3 columns</p>
</div>




```python

```
