# The-Python-Pandas-Tutorial

- https://www.youtube.com/watch?v=LJTm8_IJGNY
- https://raw.githubusercontent.com/RodrigoMvs123/The-Python-Pandas-Tutorial/main/README.md
- https://github.com/RodrigoMvs123/The-Python-Pandas-Tutorial/blame/main/README.md

## Pandas

- https://pandas.pydata.org/

Is a software library written for the python programming language for data manipulation and analysis

- https://jupyter.org/install
- https://jupyter.org/try-jupyter/lab/?path=notebooks%2FIntro.ipynb

## Intro to Pandas and Series

```python
In: import numpy as np
In: sales = [1402, 548, 1122]
In: sales
Out: [1402, 548, 1122]
In: sales_arr = np.array(sales)
In: sales_arr
Out: array([1402,  548, 1122])
In: sales_arr[1]
Out: 548
In: import pandas as pd
In: sales_series = pd.Series(sales_arr)
In: sales_series
Out: 
0    1402
1     548
2    1122
dtype: int32
In: sales_series[1]
Out: 548
In: names = ["Ellie", "Tom", "Mike"]
In: sales_series = pd.Series(sales_arr, names)
In: sales_series
Out: 
Ellie    1402
Tom       548
Mike     1122
dtype: int32
In: sales_series ["Tom"]
Out: 548
In: sales_series = [1]
Out: 548
In: sales = {"Ellie":1402, "Tom": 548, "Mike": 1122}
In: pd.Series(sales)
Out: 
Ellie    1402
Tom       548
Mike     1122
dtype: int64
```

## Series Operations

```python
In: sales_series
Out: 
Ellie    1402
Tom       548
Mike     1122
dtype: int64
In: sales_series * 0.7
Out:
Ellie    981.4 
Tom    386.3 
Mike    785.4
dtype: float64
In: april_sales = {c, "Tom": 548, "Mike": 1122}
In: may_sales = {"Ellie": 704, "Tom": 433, "Ted": 255}
In: april_Sales = pd.Series(april_sales)
In: may_Sales =pd.Series(may_sales)
In: april_Sales
Out:
Ellie    1402
Tom       548
Mike     1122
dtype: int64
In: may_Sales
Out: 
Ellie    704
Tom      433
Ted      255
dtype: int64
In: april_Sales + may_Sales
Out: 
Ellie    2106.0
Mike        NaN
Ted         NaN
Tom       981.0
dtype: float64
In: april_Sales.add(may_Sales)
Out:
Ellie    2106.0
Mike        NaN
Ted         NaN
Tom       981.0
dtype: float64
In: april_Sales.add(may_Sales, fill_value=0)
Out: 
Ellie    2106.0
Mike     1122.0
Ted       255.0
Tom       981.0
dtype: float64
```

## Dataframes

```python
In: sales = np.random.randint(200, 2001, (4, 3))
In: sales
Out:
array([[ 836, 1671,  288],
       [1534, 1477, 1385],
       [ 252, 1471, 1148],
       [ 581, 1775, 1447]])
In: names = ["Ellie", "Mike", "Ted", "Tom"]
In: months = ["April", "May", "June"]
In: df = pd.DataFrame(sales, index=names, columns=months)
In: df
Out:
```

|       | April | May  | June |
|-------|-------|------|------|
| Ellie | 1686  | 1333 | 1498 |
| Mike  | 820   | 426  | 1589 |
| Ted   | 362   | 1691 | 1814 |
| Tom   | 783   | 1215 | 1526 |

```python
In: ls
NumPy/ Pandas/ Untitled.ipynb
In: ls Pandas
Padas copy.ipynb Pandas.ipynb data/
In: ls Pandas/data
Out: cars.csv
In: df = pd.read_csv('./Pandas/data/cars.csv')
In:df
Out:
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

| # | car | type | year | price | finance | day | dealer | customer | social_security | sex |
|---|-----|------|------|-------|---------|-----|--------|----------|-----------------|-----|
| 0 | Mercedes-Benz A-Class | sedan | 2019 | 39000 | no | Sun | Mike | Stanley | 555342396 | M |
| 1 | Audi A6 | sedan | 2021 | 67800 | yes | Mon | Sam | Brittany | 887766234 | F |
| 2 | Nissan Altima | sedan | 2015 | 17500 | no | Sun | Mike | Todd | 998573477 | M |
| 3 | Chevrolet Equinox | SUV | 2013 | 9600 | no | Wed | Turner | Jasime | 342234563 | F |
| 4 | Hyundai Accent | hatchback | 2017 | 23000 | yes | Thur | Maddy | Sam | 570566354 | M |
| 5 | Porsche Cayenne | coupe | 2021 | 82000 | yes | Fri | Mike | Morgan | 968258639 | F |
| 6 | Volkswagen Jetta | sedan | 2000 | 3500 | no | Tue | Turner | Aaron | 557275923 | M |
| 7 | Audi A6 | sedan | 2020 | 78444 | no | Sat | Brittany | Shelby | 223955366 | F |
| 8 | Jeep Wrangler | SUV | 2017 | 33553 | yes | Fri | Mike | Sam | 877425852 | M |
| 9 | Volkswagen Jetta | sedan | 2012 | 9855 | no | Tue | Sam | Jessie | 885354544 | F |
| 10 | Hyundai Accent | hatchback | 2014 | 17434 | no | Mon | Maddy | Taylor | 870566354 | F |
| 11 | Hyundai Accent | hatchback | 2011 | 7434 | no | Wed | Maddy | Monte | 870066354 | M |
| 12 | Mercedes-Benz A-Class | hatchback | 2015 | 25453 | yes | Tue | Mike | Alyssa | 579521683 | F |
| 13 | Nissan Altima | sedan | 2010 | 10983 | no | Mon | Turner | Felix | 994853335 | M |
| 14 | Chevrolet Equinox | SUV | 2016 | 23998 | yes | Fri | Mike | Kyle | 947577792 | M |
| 15 | BMW M8 | coupe | 2021 | 158000 | yes | Wed | Maddy | Nicole | 338559922 | F |
| 16 | Toyota 4Runner | SUV | 2022 | 54000 | no | Thur | Mike | Jan | 462375343 | F |
| 17 | Audi A6 | sedan | 2015 | 58444 | yes | Sat | Brittany | Qatava | 223855366 | M |
| 18 | Jaguar XF | sedan | 2019 | 57744 | yes | Sun | Turner | Taylor | 884352886 | F |
| 19 | Volkswagen Jetta | sedan | 2004 | 2235 | no | Tue | Turner | Git | 995358322 | M |
| 20 | Honda Civic | sedan | 2018 | 22333 | no | Fri | Mike | Jon | 334642443 | M |
| 21 | BMW M8 | coupe | 2020 | 140553 | no | Wed | Maddy | Sal | 326234886 | M |
| 22 | Ford Maverick | pickup | 2018 | 27433 | no | Mon | Sam | Murry | 588845355 | M |
| 23 | Jeep Wrangler | SUV | 2021 | 43553 | yes | Fri | Mike | Don | 277425852 | M |
| 24 | Audi A6 | sedan | 2021 | 78444 | no | Thur | Brittany | Qatava | 223855366 | M |
| 25 | Genesis GV80 | SUV | 2021 | 80444 | yes | Mon | Mike | Selena | 994447745 | F |
| 26 | Porsche Cayenne | coupe | 2015 | 52000 | no | Thur | Turner | Emily | 958258639 | F |
| 27 | Volkswagen Jetta | sedan | 2014 | 25356 | no | Wed | Sam | Pam | 995538822 | F |
| 28 | Maserati Levante | SUV | 2020 | 104325 | yes | Mon | Mike | Cam | 452685274 | M |
| 29 | Hyundai Accent | hatchback | 2017 | 17434 | no | Thurs | Maddy | Bob | 70066354 | M |
| 30 | Honda Civic | sedan | 2000 | 2333 | no | Sat | Brittany | Allen | 134642443 | M |
| 31 | Chevrolet Camaro | coupe | 2018 | 76550 | yes | Wed | Turner | Sarah | 552422222 | F |
| 32 | Maserati Levante | SUV | 2020 | 134325 | yes | Sun | Mike | Todd | 952685274 | M |
| 33 | Mercedes-Benz A-Class | sedan | 2021 | 44032 | yes | Mon | Turner | Jon | 996435345 | M |
| 34 | Ford Maverick | pickup | 2013 | 36033 | yes | Sun | Turner | Bailey | 508845355 | F |
| 35 | Jeep Wrangler | SUV | 2021 | 43553 | yes | Fri | Mike | Don | 277425852 | M |
| 36 | Porsche 911 | coupe | 2021 | 185543 | yes | Mon | Sam | Cam | 452685274 | M |
| 37 | Hyundai Accent | hatchback | 2015 | 13434 | yes | Thurs | Brittany | Don | 277425852 | M |
| 38 | Hyundai Accent | hatchback | 2015 | 13434 | yes | Thurs | Brittany | Don | 277425852 | M |
| 39 | Cadillac Escalade | sedan | 2017 | 85474 | no | Tue | Mike | Harris | 885437455 | M |
| 40 | Genesis GV80 | SUV | 2020 | 78422 | yes | Mon | Sam | Rachel | 995943645 | F |
| 41 | Jeep Wrangler | SUV | 2002 | 3553 | no | Sun | Brittany | Porsche | 277425858 | F |
| 42 | Genesis GV80 | SUV | 2020 | 77842 | yes | Sat | Mike | Edward | 885352535 | M |
| 43 | Cadillac Escalade | sedan | 2020 | 48422 | yes | Mon | Sam | Rachel | 995943645 | F |
| 44 | Bentley Bentayga | SUV | 2020 | 232000 | no | Wed | Mike | Gabrielle | 885353455 | F |

```python
In: df.head()
Out:
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

| # | car | type | year | price | finance | day | dealer | customer | social_security | sex |
|---|-----|------|------|-------|---------|-----|--------|----------|-----------------|-----|
| 0 | Mercedes-Benz A-Class | sedan | 2019 | 39000 | no | Sun | Mike | Stanley | 555342396 | M |
| 1 | Audi A6 | sedan | 2021 | 67800 | yes | Mon | Sam | Brittany | 887766234 | F |
| 2 | Nissan Altima | sedan | 2015 | 17500 | no | Sun | Mike | Todd | 998573477 | M |
| 3 | Chevrolet Equinox | SUV | 2013 | 9600 | no | Wed | Turner | Jasime | 342234563 | F |
| 4 | Hyundai Accent | hatchback | 2017 | 23000 | yes | Thur | Maddy | Sam | 570566354 | M |

## Conditional Selection

```python
In: df["year"]
Out:
0     2019
1     2021
2     2015
3     2013
4     2017
5     2021
6     2000
7     2020
8     2017
9     2012
10    2014
11    2011
12    2015
13    2010
14    2016
15    2021
16    2022
17    2015
18    2019
19    2004
20    2018
21    2020
22    2018
23    2021
24    2021
25    2021
26    2015
27    2014
28    2020
29    2017
30    2000
31    2018
32    2020
33    2021
34    2013
35    2021
36    2021
37    2015
38    2015
39    2017
40    2020
41    2002
42    2020
43    2020
44    2020
Name: year, dtype: int64
In: type(df["year"])
Out: padas.core.series.Series
In: df["year"] > 2015
Out:
0      True
1      True
2     False
3     False
4      True
5      True
6     False
7      True
8      True
9     False
10    False
11    False
12    False
13    False
14     True
15     True
16     True
17    False
18     True
19    False
20     True
21     True
22     True
23     True
24     True
25     True
26    False
27    False
28     True
29     True
30    False
31     True
32     True
33     True
34    False
35     True
36     True
37    False
38    False
39     True
40     True
41    False
42     True
43     True
44     True
Name: year, dtype: bool
In: bool_series = df["year"] > 2015
In: df[bool_series]
Out:
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

| # | car | type | year | price | finance | day | dealer | customer | social_security | sex |
|---|-----|------|------|-------|---------|-----|--------|----------|-----------------|-----|
| 1 | Audi A6 | sedan | 2021 | 67800 | yes | Mon | Sam | Brittany | 887766234 | F |
| 5 | Porsche Cayenne | coupe | 2021 | 82000 | yes | Fri | Mike | Morgan | 968258639 | F |
| 15 | BMW M8 | coupe | 2021 | 158000 | yes | Wed | Maddy | Nicole | 338559922 | F |
| 16 | Toyota 4Runner | SUV | 2022 | 54000 | no | Thur | Mike | Jan | 462375343 | F |
| 23 | Jeep Wrangler | SUV | 2021 | 43553 | yes | Fri | Mike | Don | 277425852 | M |
| 24 | Audi A6 | sedan | 2021 | 78444 | no | Thur | Brittany | Qatava | 223855366 | M |
| 25 | Genesis GV80 | SUV | 2021 | 80444 | yes | Mon | Mike | Selena | 994447745 | F |
| 33 | Mercedes-Benz A-Class | sedan | 2021 | 44032 | yes | Mon | Turner | Jon | 996435345 | M |
| 35 | Jeep Wrangler | SUV | 2021 | 43553 | yes | Fri | Mike | Don | 277425852 | M |
| 36 | Porsche 911 | coupe | 2021 | 185543 | yes | Mon | Sam | Cam | 452685274 | M |

```python
In: df[df['year'] > 2020]
Out:
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

| # | car | type | year | price | finance | day | dealer | customer | social_security | sex |
|---|-----|------|------|-------|---------|-----|--------|----------|-----------------|-----|
| 1 | Audi A6 | sedan | 2021 | 67800 | yes | Mon | Sam | Brittany | 887766234 | F |
| 5 | Porsche Cayenne | coupe | 2021 | 82000 | yes | Fri | Mike | Morgan | 968258639 | F |
| 15 | BMW M8 | coupe | 2021 | 158000 | yes | Wed | Maddy | Nicole | 338559922 | F |
| 16 | Toyota 4Runner | SUV | 2022 | 54000 | no | Thur | Mike | Jan | 462375343 | F |
| 23 | Jeep Wrangler | SUV | 2021 | 43553 | yes | Fri | Mike | Don | 277425852 | M |
| 24 | Audi A6 | sedan | 2021 | 78444 | no | Thur | Brittany | Qatava | 223855366 | M |
| 25 | Genesis GV80 | SUV | 2021 | 80444 | yes | Mon | Mike | Selena | 994447745 | F |
| 33 | Mercedes-Benz A-Class | sedan | 2021 | 44032 | yes | Mon | Turner | Jon | 996435345 | M |
| 35 | Jeep Wrangler | SUV | 2021 | 43553 | yes | Fri | Mike | Don | 277425852 | M |
| 36 | Porsche 911 | coupe | 2021 | 185543 | yes | Mon | Sam | Cam | 452685274 | M |

```python
In: df[df["finance"] == "yes"]
Out:
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

…

```python
In: df[(df["year"] >= 2020) & (df["price"] .>= 100000)]
Out:
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

| # | car | type | year | price | finance | day | dealer | customer | social_security | sex |
|---|-----|------|------|-------|---------|-----|--------|----------|-----------------|-----|
| 15 | BMW M8 | coupe | 2021 | 158000 | yes | Wed | Maddy | Nicole | 338559922 | F |
| 21 | BMW M8 | coupe | 2020 | 140553 | no | Wed | Maddy | Sal | 326234886 | M |
| 28 | Maserati Levante | SUV | 2020 | 104325 | yes | Mon | Mike | Cam | 452685274 | M |
| 32 | Maserati Levante | SUV | 2020 | 134325 | yes | Sun | Mike | Todd | 952685274 | M |
| 36 | Porsche 911 | coupe | 2021 | 185543 | yes | Mon | Sam | Cam | 452685274 | M |
| 44 | Bentley Bentayga | SUV | 2020 | 232000 | no | Wed | Mike | Gabrielle | 885353455 | F |

```python
In: df[(df["year"] >= 2020) | (df["price"] .>= 100000)]
Out:
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

…

```python
In:df[(df["day"] == "Sat")] | df(df["day"] == "Sun")]
Out:
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

| # | car | type | year | price | finance | day | dealer | customer | social_security | sex |
|---|-----|------|------|-------|---------|-----|--------|----------|-----------------|-----|
| 0 | Mercedes-Benz A-Class | sedan | 2019 | 39000 | no | Sun | Mike | Stanley | 555342396 | M |
| 2 | Nissan Altima | sedan | 2015 | 17500 | no | Sun | Mike | Todd | 998573477 | M |
| 7 | Audi A6 | sedan | 2020 | 78444 | no | Sat | Brittany | Shelby | 223955366 | F |
| 17 | Audi A6 | sedan | 2015 | 58444 | yes | Sat | Brittany | Qatava | 223855366 | M |
| 18 | Jaguar XF | sedan | 2019 | 57744 | yes | Sun | Turner | Taylor | 884352886 | F |
| 30 | Honda Civic | sedan | 2000 | 2333 | no | Sat | Brittany | Allen | 134642443 | M |
| 32 | Maserati Levante | SUV | 2020 | 134325 | yes | Sun | Mike | Todd | 952685274 | M |
| 34 | Ford Maverick | pickup | 2013 | 36033 | yes | Sun | Turner | Bailey | 508845355 | F |
| 41 | Jeep Wrangler | SUV | 2002 | 3553 | no | Sun | Brittany | Porsche | 277425858 | F |
| 42 | Genesis GV80 | SUV | 2020 | 77842 | yes | Sat | Mike | Edward | 885352535 | M |

```python
In: df[df["day"].isin(["Mon", "Tue", "Wed", "Thur", "Fri"])]
Out:
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

| # | car | type | year | price | finance | day | dealer | customer | social_security | sex |
|---|-----|------|------|-------|---------|-----|--------|----------|-----------------|-----|
| 1 | Audi A6 | sedan | 2021 | 67800 | yes | Mon | Sam | Brittany | 887766234 | F |
| 3 | Chevrolet Equinox | SUV | 2013 | 9600 | no | Wed | Turner | Jasime | 342234563 | F |
| 4 | Hyundai Accent | hatchback | 2017 | 23000 | yes | Thur | Maddy | Sam | 570566354 | M |
| 5 | Porsche Cayenne | coupe | 2021 | 82000 | yes | Fri | Mike | Morgan | 968258639 | F |
| 6 | Volkswagen Jetta | sedan | 2000 | 3500 | no | Tue | Turner | Aaron | 557275923 | M |
| 8 | Jeep Wrangler | SUV | 2017 | 33553 | yes | Fri | Mike | Sam | 877425852 | M |
| 9 | Volkswagen Jetta | sedan | 2012 | 9855 | no | Tue | Sam | Jessie | 885354544 | F |
| 10 | Hyundai Accent | hatchback | 2014 | 17434 | no | Mon | Maddy | Taylor | 870566354 | F |
| 11 | Hyundai Accent | hatchback | 2011 | 7434 | no | Wed | Maddy | Monte | 870066354 | M |
| 12 | Mercedes-Benz A-Class | hatchback | 2015 | 25453 | yes | Tue | Mike | Alyssa | 579521683 | F |
| 13 | Nissan Altima | sedan | 2010 | 10983 | no | Mon | Turner | Felix | 994853335 | M |
| 14 | Chevrolet Equinox | SUV | 2016 | 23998 | yes | Fri | Mike | Kyle | 947577792 | M |
| 15 | BMW M8 | coupe | 2021 | 158000 | yes | Wed | Maddy | Nicole | 338559922 | F |
| 16 | Toyota 4Runner | SUV | 2022 | 54000 | no | Thur | Mike | Jan | 462375343 | F |
| 19 | Volkswagen Jetta | sedan | 2004 | 2235 | no | Tue | Turner | Git | 995358322 | M |
| 20 | Honda Civic | sedan | 2018 | 22333 | no | Fri | Mike | Jon | 334642443 | M |
| 21 | BMW M8 | coupe | 2020 | 140553 | no | Wed | Maddy | Sal | 326234886 | M |
| 22 | Ford Maverick | pickup | 2018 | 27433 | no | Mon | Sam | Murry | 588845355 | M |
| 23 | Jeep Wrangler | SUV | 2021 | 43553 | yes | Fri | Mike | Don | 277425852 | M |
| 24 | Audi A6 | sedan | 2021 | 78444 | no | Thur | Brittany | Qatava | 223855366 | M |
| 25 | Genesis GV80 | SUV | 2021 | 80444 | yes | Mon | Mike | Selena | 994447745 | F |
| 26 | Porsche Cayenne | coupe | 2015 | 52000 | no | Thur | Turner | Emily | 958258639 | F |
| 27 | Volkswagen Jetta | sedan | 2014 | 25356 | no | Wed | Sam | Pam | 995538822 | F |
| 28 | Maserati Levante | SUV | 2020 | 104325 | yes | Mon | Mike | Cam | 452685274 | M |
| 31 | Chevrolet Camaro | coupe | 2018 | 76550 | yes | Wed | Turner | Sarah | 552422222 | F |
| 33 | Mercedes-Benz A-Class | sedan | 2021 | 44032 | yes | Mon | Turner | Jon | 996435345 | M |
| 35 | Jeep Wrangler | SUV | 2021 | 43553 | yes | Fri | Mike | Don | 277425852 | M |
| 36 | Porsche 911 | coupe | 2021 | 185543 | yes | Mon | Sam | Cam | 452685274 | M |
| 39 | Cadillac Escalade | sedan | 2017 | 85474 | no | Tue | Mike | Harris | 885437455 | M |
| 40 | Genesis GV80 | SUV | 2020 | 78422 | yes | Mon | Sam | Rachel | 995943645 | F |
| 43 | Cadillac Escalade | sedan | 2020 | 48422 | yes | Mon | Sam | Rachel | 995943645 | F |
| 44 | Bentley Bentayga | SUV | 2020 | 232000 | no | Wed | Mike | Gabrielle | 885353455 | F |

## Pandas Methods

### .apply()

```python
In: def price_after_tax(price):
       return round(price * 1.13, 0)
In: tax_after_price(df["price"][2])
Out: 19775.0
In: df["total_price"] = df["price"].apply(price_after_tax) 
In: df 
Out: 
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

| # | car | type | year | price | finance | day | dealer | customer | social_security | sex | price_after_tax |
|---|-----|------|------|-------|---------|-----|--------|----------|-----------------|-----|-----------------|
| 0 | Mercedes-Benz A-Class | sedan | 2019 | 39000 | no | Sun | Mike | Stanley | 555342396 | M | 44070.0 |
| 1 | Audi A6 | sedan | 2021 | 67800 | yes | Mon | Sam | Brittany | 887766234 | F | 76614.0 |
| 2 | Nissan Altima | sedan | 2015 | 17500 | no | Sun | Mike | Todd | 998573477 | M | 19775.0 |
| 3 | Chevrolet Equinox | SUV | 2013 | 9600 | no | Wed | Turner | Jasime | 342234563 | F | 10848.0 |
| 4 | Hyundai Accent | hatchback | 2017 | 23000 | yes | Thur | Maddy | Sam | 570566354 | M | 25990.0 |
| 5 | Porsche Cayenne | coupe | 2021 | 82000 | yes | Fri | Mike | Morgan | 968258639 | F | 92660.0 |
| 6 | Volkswagen Jetta | sedan | 2000 | 3500 | no | Tue | Turner | Aaron | 557275923 | M | 3955.0 |
| 7 | Audi A6 | sedan | 2020 | 78444 | no | Sat | Brittany | Shelby | 223955366 | F | 88642.0 |
| 8 | Jeep Wrangler | SUV | 2017 | 33553 | yes | Fri | Mike | Sam | 877425852 | M | 37915.0 |
| 9 | Volkswagen Jetta | sedan | 2012 | 9855 | no | Tue | Sam | Jessie | 885354544 | F | 11136.0 |
| 10 | Hyundai Accent | hatchback | 2014 | 17434 | no | Mon | Maddy | Taylor | 870566354 | F | 19700.0 |
| 11 | Hyundai Accent | hatchback | 2011 | 7434 | no | Wed | Maddy | Monte | 870066354 | M | 8400.0 |
| 12 | Mercedes-Benz A-Class | hatchback | 2015 | 25453 | yes | Tue | Mike | Alyssa | 579521683 | F | 28762.0 |
| 13 | Nissan Altima | sedan | 2010 | 10983 | no | Mon | Turner | Felix | 994853335 | M | 12411.0 |
| 14 | Chevrolet Equinox | SUV | 2016 | 23998 | yes | Fri | Mike | Kyle | 947577792 | M | 27118.0 |
| 15 | BMW M8 | coupe | 2021 | 158000 | yes | Wed | Maddy | Nicole | 338559922 | F | 178540.0 |
| 16 | Toyota 4Runner | SUV | 2022 | 54000 | no | Thur | Mike | Jan | 462375343 | F | 61020.0 |
| 17 | Audi A6 | sedan | 2015 | 58444 | yes | Sat | Brittany | Qatava | 223855366 | M | 66042.0 |
| 18 | Jaguar XF | sedan | 2019 | 57744 | yes | Sun | Turner | Taylor | 884352886 | F | 65251.0 |
| 19 | Volkswagen Jetta | sedan | 2004 | 2235 | no | Tue | Turner | Git | 995358322 | M | 2526.0 |
| 20 | Honda Civic | sedan | 2018 | 22333 | no | Fri | Mike | Jon | 334642443 | M | 25236.0 |
| 21 | BMW M8 | coupe | 2020 | 140553 | no | Wed | Maddy | Sal | 326234886 | M | 158825.0 |
| 22 | Ford Maverick | pickup | 2018 | 27433 | no | Mon | Sam | Murry | 588845355 | M | 30999.0 |
| 23 | Jeep Wrangler | SUV | 2021 | 43553 | yes | Fri | Mike | Don | 277425852 | M | 49215.0 |
| 24 | Audi A6 | sedan | 2021 | 78444 | no | Thur | Brittany | Qatava | 223855366 | M | 88642.0 |
| 25 | Genesis GV80 | SUV | 2021 | 80444 | yes | Mon | Mike | Selena | 994447745 | F | 90902.0 |
| 26 | Porsche Cayenne | coupe | 2015 | 52000 | no | Thur | Turner | Emily | 958258639 | F | 58760.0 |
| 27 | Volkswagen Jetta | sedan | 2014 | 25356 | no | Wed | Sam | Pam | 995538822 | F | 28652.0 |
| 28 | Maserati Levante | SUV | 2020 | 104325 | yes | Mon | Mike | Cam | 452685274 | M | 117887.0 |
| 29 | Hyundai Accent | hatchback | 2017 | 17434 | no | Thurs | Maddy | Bob | 70066354 | M | 19700.0 |
| 30 | Honda Civic | sedan | 2000 | 2333 | no | Sat | Brittany | Allen | 134642443 | M | 2636.0 |
| 31 | Chevrolet Camaro | coupe | 2018 | 76550 | yes | Wed | Turner | Sarah | 552422222 | F | 86501.0 |
| 32 | Maserati Levante | SUV | 2020 | 134325 | yes | Sun | Mike | Todd | 952685274 | M | 151787.0 |
| 33 | Mercedes-Benz A-Class | sedan | 2021 | 44032 | yes | Mon | Turner | Jon | 996435345 | M | 49756.0 |
| 34 | Ford Maverick | pickup | 2013 | 36033 | yes | Sun | Turner | Bailey | 508845355 | F | 40717.0 |
| 35 | Jeep Wrangler | SUV | 2021 | 43553 | yes | Fri | Mike | Don | 277425852 | M | 49215.0 |
| 36 | Porsche 911 | coupe | 2021 | 185543 | yes | Mon | Sam | Cam | 452685274 | M | 209664.0 |
| 37 | Hyundai Accent | hatchback | 2015 | 13434 | yes | Thurs | Brittany | Don | 277425852 | M | 15180.0 |
| 38 | Hyundai Accent | hatchback | 2015 | 13434 | yes | Thurs | Brittany | Don | 277425852 | M | 15180.0 |
| 39 | Cadillac Escalade | sedan | 2017 | 85474 | no | Tue | Mike | Harris | 885437455 | M | 96586.0 |
| 40 | Genesis GV80 | SUV | 2020 | 78422 | yes | Mon | Sam | Rachel | 995943645 | F | 88617.0 |
| 41 | Jeep Wrangler | SUV | 2002 | 3553 | no | Sun | Brittany | Porsche | 277425858 | F | 4015.0 |
| 42 | Genesis GV80 | SUV | 2020 | 77842 | yes | Sat | Mike | Edward | 885352535 | M | 87961.0 |
| 43 | Cadillac Escalade | sedan | 2020 | 48422 | yes | Mon | Sam | Rachel | 995943645 | F | 54717.0 |
| 44 | Bentley Bentayga | SUV | 2020 | 232000 | no | Wed | Mike | Gabrielle | 885353455 | F | 262160.0 |

```python
In: def proft_margin(price, finance):
            if finance == "N":
                   if price < 10000
                         return "LOW" 
                   elif price >= 10000 and price < 25000:
                         return "MED" 
                   else:
                          return "HIGH" 
            else: 
                    if price < 7500
                         return "LOW" 
                   elif price >= 7500 and price < 20000:
                         return "MED" 
                   else:
                          return "HIGH" 
In: df["profit_margin"] = np.vectorize(profit_margin) (df["price"], df["finance"])
In: df
Out:
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

| # | car | type | year | price | finance | day | dealer | customer | social_security | sex | price_after_tax | profit_margin |
|---|-----|------|------|-------|---------|-----|--------|----------|-----------------|-----|-----------------|---------------|
| 0 | Mercedes-Benz A-Class | sedan | 2019 | 39000 | no | Sun | Mike | Stanley | 555342396 | M | 44070.0 | HIGH |
| 1 | Audi A6 | sedan | 2021 | 67800 | yes | Mon | Sam | Brittany | 887766234 | F | 76614.0 | HIGH |
| 2 | Nissan Altima | sedan | 2015 | 17500 | no | Sun | Mike | Todd | 998573477 | M | 19775.0 | MED |
| 3 | Chevrolet Equinox | SUV | 2013 | 9600 | no | Wed | Turner | Jasime | 342234563 | F | 10848.0 | LOW |
| 4 | Hyundai Accent | hatchback | 2017 | 23000 | yes | Thur | Maddy | Sam | 570566354 | M | 25990.0 | HIGH |
| 5 | Porsche Cayenne | coupe | 2021 | 82000 | yes | Fri | Mike | Morgan | 968258639 | F | 92660.0 | HIGH |
| 6 | Volkswagen Jetta | sedan | 2000 | 3500 | no | Tue | Turner | Aaron | 557275923 | M | 3955.0 | LOW |
| 7 | Audi A6 | sedan | 2020 | 78444 | no | Sat | Brittany | Shelby | 223955366 | F | 88642.0 | HIGH |
| 8 | Jeep Wrangler | SUV | 2017 | 33553 | yes | Fri | Mike | Sam | 877425852 | M | 37915.0 | HIGH |
| 9 | Volkswagen Jetta | sedan | 2012 | 9855 | no | Tue | Sam | Jessie | 885354544 | F | 11136.0 | LOW |
| 10 | Hyundai Accent | hatchback | 2014 | 17434 | no | Mon | Maddy | Taylor | 870566354 | F | 19700.0 | MED |
| 11 | Hyundai Accent | hatchback | 2011 | 7434 | no | Wed | Maddy | Monte | 870066354 | M | 8400.0 | LOW |
| 12 | Mercedes-Benz A-Class | hatchback | 2015 | 25453 | yes | Tue | Mike | Alyssa | 579521683 | F | 28762.0 | HIGH |
| 13 | Nissan Altima | sedan | 2010 | 10983 | no | Mon | Turner | Felix | 994853335 | M | 12411.0 | MED |
| 14 | Chevrolet Equinox | SUV | 2016 | 23998 | yes | Fri | Mike | Kyle | 947577792 | M | 27118.0 | HIGH |
| 15 | BMW M8 | coupe | 2021 | 158000 | yes | Wed | Maddy | Nicole | 338559922 | F | 178540.0 | HIGH |
| 16 | Toyota 4Runner | SUV | 2022 | 54000 | no | Thur | Mike | Jan | 462375343 | F | 61020.0 | HIGH |
| 17 | Audi A6 | sedan | 2015 | 58444 | yes | Sat | Brittany | Qatava | 223855366 | M | 66042.0 | HIGH |
| 18 | Jaguar XF | sedan | 2019 | 57744 | yes | Sun | Turner | Taylor | 884352886 | F | 65251.0 | HIGH |
| 19 | Volkswagen Jetta | sedan | 2004 | 2235 | no | Tue | Turner | Git | 995358322 | M | 2526.0 | LOW |
| 20 | Honda Civic | sedan | 2018 | 22333 | no | Fri | Mike | Jon | 334642443 | M | 25236.0 | MED |
| 21 | BMW M8 | coupe | 2020 | 140553 | no | Wed | Maddy | Sal | 326234886 | M | 158825.0 | HIGH |
| 22 | Ford Maverick | pickup | 2018 | 27433 | no | Mon | Sam | Murry | 588845355 | M | 30999.0 | HIGH |
| 23 | Jeep Wrangler | SUV | 2021 | 43553 | yes | Fri | Mike | Don | 277425852 | M | 49215.0 | HIGH |
| 24 | Audi A6 | sedan | 2021 | 78444 | no | Thur | Brittany | Qatava | 223855366 | M | 88642.0 | HIGH |
| 25 | Genesis GV80 | SUV | 2021 | 80444 | yes | Mon | Mike | Selena | 994447745 | F | 90902.0 | HIGH |
| 26 | Porsche Cayenne | coupe | 2015 | 52000 | no | Thur | Turner | Emily | 958258639 | F | 58760.0 | HIGH |
| 27 | Volkswagen Jetta | sedan | 2014 | 25356 | no | Wed | Sam | Pam | 995538822 | F | 28652.0 | HIGH |
| 28 | Maserati Levante | SUV | 2020 | 104325 | yes | Mon | Mike | Cam | 452685274 | M | 117887.0 | HIGH |
| 29 | Hyundai Accent | hatchback | 2017 | 17434 | no | Thurs | Maddy | Bob | 70066354 | M | 19700.0 | MED |
| 30 | Honda Civic | sedan | 2000 | 2333 | no | Sat | Brittany | Allen | 134642443 | M | 2636.0 | LOW |
| 31 | Chevrolet Camaro | coupe | 2018 | 76550 | yes | Wed | Turner | Sarah | 552422222 | F | 86501.0 | HIGH |
| 32 | Maserati Levante | SUV | 2020 | 134325 | yes | Sun | Mike | Todd | 952685274 | M | 151787.0 | HIGH |
| 33 | Mercedes-Benz A-Class | sedan | 2021 | 44032 | yes | Mon | Turner | Jon | 996435345 | M | 49756.0 | HIGH |
| 34 | Ford Maverick | pickup | 2013 | 36033 | yes | Sun | Turner | Bailey | 508845355 | F | 40717.0 | HIGH |
| 35 | Jeep Wrangler | SUV | 2021 | 43553 | yes | Fri | Mike | Don | 277425852 | M | 49215.0 | HIGH |
| 36 | Porsche 911 | coupe | 2021 | 185543 | yes | Mon | Sam | Cam | 452685274 | M | 209664.0 | HIGH |
| 37 | Hyundai Accent | hatchback | 2015 | 13434 | yes | Thurs | Brittany | Don | 277425852 | M | 15180.0 | MED |
| 38 | Hyundai Accent | hatchback | 2015 | 13434 | yes | Thurs | Brittany | Don | 277425852 | M | 15180.0 | MED |
| 39 | Cadillac Escalade | sedan | 2017 | 85474 | no | Tue | Mike | Harris | 885437455 | M | 96586.0 | HIGH |
| 40 | Genesis GV80 | SUV | 2020 | 78422 | yes | Mon | Sam | Rachel | 995943645 | F | 88617.0 | HIGH |
| 41 | Jeep Wrangler | SUV | 2002 | 3553 | no | Sun | Brittany | Porsche | 277425858 | F | 4015.0 | LOW |
| 42 | Genesis GV80 | SUV | 2020 | 77842 | yes | Sat | Mike | Edward | 885352535 | M | 87961.0 | HIGH |
| 43 | Cadillac Escalade | sedan | 2020 | 48422 | yes | Mon | Sam | Rachel | 995943645 | F | 54717.0 | HIGH |
| 44 | Bentley Bentayga | SUV | 2020 | 232000 | no | Wed | Mike | Gabrielle | 885353455 | F | 262160.0 | HIGH |

```python
In: df.describe()
Out: 
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

|       | year | price | social_security | price_after_tax |
|-------|------|-------|-----------------|-----------------|
| count | 45.000000 | 45.000000 | 4.500000e+01 | 45.000000 |
| mean | 2016.222222 | 54373.377778 | 6.358065e+08 | 61441.888889 |
| std | 5.603931 | 50910.915441 | 3.096242e+08 | 57529.393065 |
| min | 2000.000000 | 2235.000000 | 7.006635e+07 | 2526.000000 |
| 25% | 2015.000000 | 17434.000000 | 3.346424e+08 | 19700.000000 |
| 50% | 2018.000000 | 43553.000000 | 5.795217e+08 | 49215.000000 |
| 75% | 2020.000000 | 78422.000000 | 9.475778e+08 | 88617.000000 |
| max | 2022.000000 | 232000.000000 | 9.985735e+08 | 262160.000000 |

```python
In: df.describe().transpose()
Out:
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

|                 | count | mean | std | min | 25% | 50% | 75% | max |
|-----------------|-------|------|-----|-----|-----|-----|-----|-----|
| year | 45.0 | 2.016222e+03 | 5.603931e+00 | 2000.0 | 2015.0 | 2018.0 | 2020.0 | 2022.0 |
| price | 45.0 | 5.437338e+04 | 5.091092e+04 | 2235.0 | 17434.0 | 43553.0 | 78422.0 | 232000.0 |
| social_security | 45.0 | 6.358065e+08 | 3.096242e+08 | 70066354.0 | 334642443.0 | 579521683.0 | 947577792.0 | 998573477.0 |
| price_after_tax | 45.0 | 6.144189e+04 | 5.752939e+04 | 2526.0 | 19700.0 | 49215.0 | 88617.0 | 262160.0 |

```python
In:df.sort_values("price")
Out:
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

| # | car | type | year | price | finance | day | dealer | customer | social_security | sex | price_after_tax | profit_margin |
|---|-----|------|------|-------|---------|-----|--------|----------|-----------------|-----|-----------------|---------------|
| 19 | Volkswagen Jetta | sedan | 2004 | 2235 | no | Tue | Turner | Git | 995358322 | M | 2526.0 | LOW |
| 30 | Honda Civic | sedan | 2000 | 2333 | no | Sat | Brittany | Allen | 134642443 | M | 2636.0 | LOW |
| 6 | Volkswagen Jetta | sedan | 2000 | 3500 | no | Tue | Turner | Aaron | 557275923 | M | 3955.0 | LOW |
| 41 | Jeep Wrangler | SUV | 2002 | 3553 | no | Sun | Brittany | Porsche | 277425858 | F | 4015.0 | LOW |
| 11 | Hyundai Accent | hatchback | 2011 | 7434 | no | Wed | Maddy | Monte | 870066354 | M | 8400.0 | LOW |
| 3 | Chevrolet Equinox | SUV | 2013 | 9600 | no | Wed | Turner | Jasime | 342234563 | F | 10848.0 | LOW |
| 9 | Volkswagen Jetta | sedan | 2012 | 9855 | no | Tue | Sam | Jessie | 885354544 | F | 11136.0 | LOW |
| 13 | Nissan Altima | sedan | 2010 | 10983 | no | Mon | Turner | Felix | 994853335 | M | 12411.0 | MED |
| 38 | Hyundai Accent | hatchback | 2015 | 13434 | yes | Thurs | Brittany | Don | 277425852 | M | 15180.0 | MED |
| 37 | Hyundai Accent | hatchback | 2015 | 13434 | yes | Thurs | Brittany | Don | 277425852 | M | 15180.0 | MED |
| 10 | Hyundai Accent | hatchback | 2014 | 17434 | no | Mon | Maddy | Taylor | 870566354 | F | 19700.0 | MED |
| 29 | Hyundai Accent | hatchback | 2017 | 17434 | no | Thurs | Maddy | Bob | 70066354 | M | 19700.0 | MED |
| 2 | Nissan Altima | sedan | 2015 | 17500 | no | Sun | Mike | Todd | 998573477 | M | 19775.0 | MED |
| 20 | Honda Civic | sedan | 2018 | 22333 | no | Fri | Mike | Jon | 334642443 | M | 25236.0 | MED |
| 4 | Hyundai Accent | hatchback | 2017 | 23000 | yes | Thur | Maddy | Sam | 570566354 | M | 25990.0 | HIGH |
| 14 | Chevrolet Equinox | SUV | 2016 | 23998 | yes | Fri | Mike | Kyle | 947577792 | M | 27118.0 | HIGH |
| 27 | Volkswagen Jetta | sedan | 2014 | 25356 | no | Wed | Sam | Pam | 995538822 | F | 28652.0 | HIGH |
| 12 | Mercedes-Benz A-Class | hatchback | 2015 | 25453 | yes | Tue | Mike | Alyssa | 579521683 | F | 28762.0 | HIGH |
| 22 | Ford Maverick | pickup | 2018 | 27433 | no | Mon | Sam | Murry | 588845355 | M | 30999.0 | HIGH |
| 8 | Jeep Wrangler | SUV | 2017 | 33553 | yes | Fri | Mike | Sam | 877425852 | M | 37915.0 | HIGH |
| 34 | Ford Maverick | pickup | 2013 | 36033 | yes | Sun | Turner | Bailey | 508845355 | F | 40717.0 | HIGH |
| 0 | Mercedes-Benz A-Class | sedan | 2019 | 39000 | no | Sun | Mike | Stanley | 555342396 | M | 44070.0 | HIGH |
| 23 | Jeep Wrangler | SUV | 2021 | 43553 | yes | Fri | Mike | Don | 277425852 | M | 49215.0 | HIGH |
| 35 | Jeep Wrangler | SUV | 2021 | 43553 | yes | Fri | Mike | Don | 277425852 | M | 49215.0 | HIGH |
| 33 | Mercedes-Benz A-Class | sedan | 2021 | 44032 | yes | Mon | Turner | Jon | 996435345 | M | 49756.0 | HIGH |
| 43 | Cadillac Escalade | sedan | 2020 | 48422 | yes | Mon | Sam | Rachel | 995943645 | F | 54717.0 | HIGH |
| 26 | Porsche Cayenne | coupe | 2015 | 52000 | no | Thur | Turner | Emily | 958258639 | F | 58760.0 | HIGH |
| 16 | Toyota 4Runner | SUV | 2022 | 54000 | no | Thur | Mike | Jan | 462375343 | F | 61020.0 | HIGH |
| 18 | Jaguar XF | sedan | 2019 | 57744 | yes | Sun | Turner | Taylor | 884352886 | F | 65251.0 | HIGH |
| 17 | Audi A6 | sedan | 2015 | 58444 | yes | Sat | Brittany | Qatava | 223855366 | M | 66042.0 | HIGH |
| 1 | Audi A6 | sedan | 2021 | 67800 | yes | Mon | Sam | Brittany | 887766234 | F | 76614.0 | HIGH |
| 31 | Chevrolet Camaro | coupe | 2018 | 76550 | yes | Wed | Turner | Sarah | 552422222 | F | 86501.0 | HIGH |
| 42 | Genesis GV80 | SUV | 2020 | 77842 | yes | Sat | Mike | Edward | 885352535 | M | 87961.0 | HIGH |
| 40 | Genesis GV80 | SUV | 2020 | 78422 | yes | Mon | Sam | Rachel | 995943645 | F | 88617.0 | HIGH |
| 7 | Audi A6 | sedan | 2020 | 78444 | no | Sat | Brittany | Shelby | 223955366 | F | 88642.0 | HIGH |
| 24 | Audi A6 | sedan | 2021 | 78444 | no | Thur | Brittany | Qatava | 223855366 | M | 88642.0 | HIGH |
| 25 | Genesis GV80 | SUV | 2021 | 80444 | yes | Mon | Mike | Selena | 994447745 | F | 90902.0 | HIGH |
| 5 | Porsche Cayenne | coupe | 2021 | 82000 | yes | Fri | Mike | Morgan | 968258639 | F | 92660.0 | HIGH |
| 39 | Cadillac Escalade | sedan | 2017 | 85474 | no | Tue | Mike | Harris | 885437455 | M | 96586.0 | HIGH |
| 28 | Maserati Levante | SUV | 2020 | 104325 | yes | Mon | Mike | Cam | 452685274 | M | 117887.0 | HIGH |
| 32 | Maserati Levante | SUV | 2020 | 134325 | | yes | Sun | Mike | Todd | 952685274 | M | 151787.0 | HIGH |
| 21 | BMW M8 | coupe | 2020 | 140553 | no | Wed | Maddy | Sal | 326234886 | M | 158825.0 | HIGH |
| 15 | BMW M8 | coupe | 2021 | 158000 | yes | Wed | Maddy | Nicole | 338559922 | F | 178540.0 | HIGH |
| 36 | Porsche 911 | coupe | 2021 | 185543 | yes | Mon | Sam | Cam | 452685274 | M | 209664.0 | HIGH |
| 44 | Bentley Bentayga | SUV | 2020 | 232000 | no | Wed | Mike | Gabrielle | 885353455 | F | 262160.0 | HIGH |

```python
In: df.sort_values(["price", "sexr"])
Out:
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

| # | car | type | year | price | finance | day | dealer | customer | social_security | sex | price_after_tax | profit_margin |
|---|-----|------|------|-------|---------|-----|--------|----------|-----------------|-----|-----------------|---------------|
| 19 | Volkswagen Jetta | sedan | 2004 | 2235 | no | Tue | Turner | Git | 995358322 | M | 2526.0 | LOW |
| 30 | Honda Civic | sedan | 2000 | 2333 | no | Sat | Brittany | Allen | 134642443 | M | 2636.0 | LOW |
| 6 | Volkswagen Jetta | sedan | 2000 | 3500 | no | Tue | Turner | Aaron | 557275923 | M | 3955.0 | LOW |
| 41 | Jeep Wrangler | SUV | 2002 | 3553 | no | Sun | Brittany | Porsche | 277425858 | F | 4015.0 | LOW |
| 11 | Hyundai Accent | hatchback | 2011 | 7434 | no | Wed | Maddy | Monte | 870066354 | M | 8400.0 | LOW |
| 3 | Chevrolet Equinox | SUV | 2013 | 9600 | no | Wed | Turner | Jasime | 342234563 | F | 10848.0 | LOW |
| 9 | Volkswagen Jetta | sedan | 2012 | 9855 | no | Tue | Sam | Jessie | 885354544 | F | 11136.0 | LOW |
| 13 | Nissan Altima | sedan | 2010 | 10983 | no | Mon | Turner | Felix | 994853335 | M | 12411.0 | MED |
| 37 | Hyundai Accent | hatchback | 2015 | 13434 | yes | Thurs | Brittany | Don | 277425852 | M | 15180.0 | MED |
| 38 | Hyundai Accent | hatchback | 2015 | 13434 | yes | Thurs | Brittany | Don | 277425852 | M | 15180.0 | MED |
| 10 | Hyundai Accent | hatchback | 2014 | 17434 | no | Mon | Maddy | Taylor | 870566354 | F | 19700.0 | MED |
| 29 | Hyundai Accent | hatchback | 2017 | 17434 | no | Thurs | Maddy | Bob | 70066354 | M | 19700.0 | MED |
| 2 | Nissan Altima | sedan | 2015 | 17500 | no | Sun | Mike | Todd | 998573477 | M | 19775.0 | MED |
| 20 | Honda Civic | sedan | 2018 | 22333 | no | Fri | Mike | Jon | 334642443 | M | 25236.0 | MED |
| 4 | Hyundai Accent | hatchback | 2017 | 23000 | yes | Thur | Maddy | Sam | 570566354 | M | 25990.0 | HIGH |
| 14 | Chevrolet Equinox | SUV | 2016 | 23998 | yes | Fri | Mike | Kyle | 947577792 | M | 27118.0 | HIGH |
| 27 | Volkswagen Jetta | sedan | 2014 | 25356 | no | Wed | Sam | Pam | 995538822 | F | 28652.0 | HIGH |
| 12 | Mercedes-Benz A-Class | hatchback | 2015 | 25453 | yes | Tue | Mike | Alyssa | 579521683 | F | 28762.0 | HIGH |
| 22 | Ford Maverick | pickup | 2018 | 27433 | no | Mon | Sam | Murry | 588845355 | M | 30999.0 | HIGH |
| 8 | Jeep Wrangler | SUV | 2017 | 33553 | yes | Fri | Mike | Sam | 877425852 | M | 37915.0 | HIGH |
| 34 | Ford Maverick | pickup | 2013 | 36033 | yes | Sun | Turner | Bailey | 508845355 | F | 40717.0 | HIGH |
| 0 | Mercedes-Benz A-Class | sedan | 2019 | 39000 | no | Sun | Mike | Stanley | 555342396 | M | 44070.0 | HIGH |
| 23 | Jeep Wrangler | SUV | 2021 | 43553 | yes | Fri | Mike | Don | 277425852 | M | 49215.0 | HIGH |
| 35 | Jeep Wrangler | SUV | 2021 | 43553 | yes | Fri | Mike | Don | 277425852 | M | 49215.0 | HIGH |
| 33 | Mercedes-Benz A-Class | sedan | 2021 | 44032 | yes | Mon | Turner | Jon | 996435345 | M | 49756.0 | HIGH |
| 43 | Cadillac Escalade | sedan | 2020 | 48422 | yes | Mon | Sam | Rachel | 995943645 | F | 54717.0 | HIGH |
| 26 | Porsche Cayenne | coupe | 2015 | 52000 | no | Thur | Turner | Emily | 958258639 | F | 58760.0 | HIGH |
| 16 | Toyota 4Runner | SUV | 2022 | 54000 | no | Thur | Mike | Jan | 462375343 | F | 61020.0 | HIGH |
| 18 | Jaguar XF | sedan | 2019 | 57744 | yes | Sun | Turner | Taylor | 884352886 | F | 65251.0 | HIGH |
| 17 | Audi A6 | sedan | 2015 | 58444 | yes | Sat | Brittany | Qatava | 223855366 | M | 66042.0 | HIGH |
| 1 | Audi A6 | sedan | 2021 | 67800 | yes | Mon | Sam | Brittany | 887766234 | F | 76614.0 | HIGH |
| 31 | Chevrolet Camaro | coupe | 2018 | 76550 | yes | Wed | Turner | Sarah | 552422222 | F | 86501.0 | HIGH |
| 42 | Genesis GV80 | SUV | 2020 | 77842 | yes | Sat | Mike | Edward | 885352535 | M | 87961.0 | HIGH |
| 40 | Genesis GV80 | SUV | 2020 | 78422 | yes | Mon | Sam | Rachel | 995943645 | F | 88617.0 | HIGH |
| 7 | Audi A6 | sedan | 2020 | 78444 | no | Sat | Brittany | Shelby | 223955366 | F | 88642.0 | HIGH |
| 24 | Audi A6 | sedan | 2021 | 78444 | no | Thur | Brittany | Qatava | 223855366 | M | 88642.0 | HIGH |
| 25 | Genesis GV80 | SUV | 2021 | 80444 | yes | Mon | Mike | Selena | 994447745 | F | 90902.0 | HIGH |
| 5 | Porsche Cayenne | coupe | 2021 | 82000 | yes | Fri | Mike | Morgan | 968258639 | F | 92660.0 | HIGH |
| 39 | Cadillac Escalade | sedan | 2017 | 85474 | no | Tue | Mike | Harris | 885437455 | M | 96586.0 | HIGH |
| 28 | Maserati Levante | SUV | 2020 | 104325 | yes | Mon | Mike | Cam | 452685274 | M | 117887.0 | HIGH |
| 32 | Maserati Levante | SUV | 2020 | 134325 | yes | Sun | Mike | Todd | 952685274 | M | 151787.0 | HIGH |
| 21 | BMW M8 | coupe | 2020 | 140553 | no | Wed | Maddy | Sal | 326234886 | M | 158825.0 | HIGH |
| 15 | BMW M8 | coupe | 2021 | 158000 | yes | Wed | Maddy | Nicole | 338559922 | F | 178540.0 | HIGH |
| 36 | Porsche 911 | coupe | 2021 | 185543 | yes | Mon | Sam | Cam | 452685274 | M | 209664.0 | HIGH |
| 44 | Bentley Bentayga | SUV | 2020 | 232000 | no | Wed | Mike | Gabrielle | 885353455 | F | 262160.0 | HIGH |

```python
In: df["price"].max()
Out: 232000
In: df["price"].min()
Out: 2235
In: df["price"].idxmax()
Out: 44
In: df.iloc(44)
Out: 
car                Bentley Bentayga
type                            SUV
year                           2020
price                        232000
finance                          no
day                             Wed
dealer                         Mike
customer                  Gabrielle
social_security           885353455
sex                               F
price_after_tax            262160.0
profit_margin                  HIGH
Name: 44, dtype: object
In: df.iloc[df["price"].idxmax()]
Out:
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

…

```python
In: df["sex"].value_counts()
Out: 
M    26
F    19
Name: sex, dtype: int64
In: df["car"].value_counts()
Out:
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

…

```python
In: df["sex"] = df["sex"].replace(to_replace="M", value="male")
In: df
Out: 
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

…

```python
In: df["sex"] = df["sex"].replace(to_replace="F", value="female")
In:df
Out:
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

…

```python
In: df.duplicate()
Out:
0     False
1     False
2     False
3     False
4     False
5     False
6     False
7     False
8     False
9     False
10    False
11    False
12    False
13    False
14    False
15    False
16    False
17    False
18    False
19    False
20    False
21    False
22    False
23    False
24    False
25    False
26    False
27    False
28    False
29    False
30    False
31    False
32    False
33    False
34    False
35     True
36    False
37    False
38     True
39    False
40    False
41    False
42    False
43    False
44    False
dtype: bool
in: df[df.duplicated()]
Out:
```

| # | car | type | year | price | finance | day | dealer | customer | social_security | sex | price_after_tax | profit_margin |
|---|-----|------|------|-------|---------|-----|--------|----------|-----------------|-----|-----------------|---------------|
| 35 | Jeep Wrangler | SUV | 2021 | 43553 | Y | Fri | Mike | Don | 277425852 | M | 49215.0 | HIGH |
| 38 | Hyundai Accent | hatchback | 2015 | 13434 | Y | Thurs | Brittany | Don | 277425852 | M | 15180.0 | MED |

```python
In: df[df["car"] == "Jeep Wrangler"] 
Out: 
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

…

```python
In: df["car"].unique()
Out: 
array(['Stanley', 'Brittany', 'Todd', 'Jasime', 'Sam', 'Morgan', 'Aaron',
       'Shelby', 'Jessie', 'Taylor', 'Monte', 'Alyssa', 'Felix', 'Kyle',
       'Nicole', 'Jan', 'Qatava', 'Git', 'Jon', 'Sal', 'Murry', 'Don',
       'Selena', 'Emily', 'Pam', 'Cam', 'Bob', 'Allen', 'Sarah', 'Bailey',
       'Harris', 'Rachel', 'Porsche', 'Edward', 'Gabrielle'], dtype=object)
In: df["car"].nunique()
Out: 19
In: df["price"].between(10000,20000)
Out:
0     False
1     False
2      True
3     False
4     False
5     False
6     False
7     False
8     False
9     False
10     True
11    False
12    False
13     True
14    False
15    False
16    False
17    False
18    False
19    False
20    False
21    False
22    False
23    False
24    False
25    False
26    False
27    False
28    False
29     True
30    False
31    False
32    False
33    False
34    False
35    False
36    False
37     True
38     True
39    False
40    False
41    False
42    False
43    False
44    False
Name: price, dtype: bool
In: df[df["price"].between(10000,20000)]
Out:
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

| # | car | type | year | price | finance | day | dealer | customer | social_security | sex | price_after_tax | profit_margin |
|---|-----|------|------|-------|---------|-----|--------|----------|-----------------|-----|-----------------|---------------|
| 2 | Nissan Altima | sedan | 2015 | 17500 | N | Sun | Mike | Todd | 998573477 | M | 19775.0 | MED |
| 10 | Hyundai Accent | hatchback | 2014 | 17434 | N | Mon | Maddy | Taylor | 870566354 | F | 19700.0 | MED |
| 13 | Nissan Altima | sedan | 2010 | 10983 | N | Mon | Turner | Felix | 994853335 | M | 12411.0 | MED |
| 29 | Hyundai Accent | hatchback | 2017 | 17434 | N | Thurs | Maddy | Bob | 70066354 | M | 19700.0 | MED |
| 37 | Hyundai Accent | hatchback | 2015 | 13434 | Y | Thurs | Brittany | Don | 277425852 | M | 15180.0 | MED |
| 38 | Hyundai Accent | hatchback | 2015 | 13434 | Y | Thurs | Brittany | Don | 277425852 | M | 15180.0 | MED |

## Group By

```python
In: df.groupby("dealer").sum()
Out: 
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

|          | year | price | social_security | price_after_tax |
|----------|------|-------|-----------------|-----------------|
| dealer   |      |       |                 |                 |
| Brittany | 14088 | 248086 | 1638586103 | 280337.0 |
| Maddy | 12100 | 363855 | 3046060224 | 411155.0 |
| Mike | 32303 | 1099353 | 11334531066 | 1242269.0 |
| Sam | 14126 | 442831 | 5802077519 | 500399.0 |
| Turner | 18113 | 292677 | 6790036590 | 330725.0 |

```python
In: df.groupby("dealer").sum().["price"]
Out:
dealer
Brittany     248086
Maddy        363855
Mike        1099353
Sam          442831
Turner       292677
Name: price, dtype: int64
In: df.groupby("dealer").sum().index
Out:Index(['Brittany', 'Maddy', 'Mike', 'Sam', 'Turner'], dtype='object', name='dealer')
In: df.groupby("dealer").sum().columns
Out: 
Index(['year', 'price', 'social_security', 'price_after_tax'], dtype='object')
In: df.groupby("dealer").mean()
Out:
```

|          | year | price | social_security | price_after_tax |
|----------|------|-------|-----------------|-----------------|
| dealer   |      |       |                 |                 |
| Brittany | 2012.571429 | 35440.857143 | 2.340837e+08 | 40048.142857 |
| Maddy | 2016.666667 | 60642.500000 | 5.076767e+08 | 68525.833333 |
| Mike | 2018.937500 | 68709.562500 | 7.084082e+08 | 77641.812500 |
| Sam | 2018.000000 | 63261.571429 | 8.288682e+08 | 71485.571429 |
| Turner | 2012.555556 | 32519.666667 | 7.544485e+08 | 36747.222222 |

```python
In: df.groupby(["dealer", "year"]).sum()
Out: 
```

|        |      | price | social_security | price_after_tax |
|--------|------|-------|-----------------|-----------------|
| dealer | year |       |                 |                 |
| Brittany | 2000 | 2333 | 134642443 | 2636.0 |
|        | 2002 | 3553 | 277425858 | 4015.0 |
|        | 2015 | 85312 | 778707070 | 96402.0 |
|        | 2020 | 78444 | 223955366 | 88642.0 |
|        | 2021 | 78444 | 223855366 | 88642.0 |
| Maddy | 2011 | 7434 | 870066354 | 8400.0 |
|        | 2014 | 17434 | 870566354 | 19700.0 |
|        | 2017 | 40434 | 640632708 | 45690.0 |
|        | 2020 | 140553 | 326234886 | 158825.0 |
|        | 2021 | 158000 | 338559922 | 178540.0 |
| Mike | 2015 | 42953 | 1578095160 | 48537.0 |
|        | 2016 | 23998 | 947577792 | 27118.0 |
|        | 2017 | 119027 | 1762863307 | 134501.0 |
|        | 2018 | 22333 | 334642443 | 25236.0 |
|        | 2019 | 39000 | 555342396 | 44070.0 |
|        | 2020 | 548492 | 3176076538 | 619795.0 |
|        | 2021 | 249550 | 2517558088 | 281992.0 |
|        | 2022 | 54000 | 462375343 | 61020.0 |
| Sam | 2012 | 9855 | 885354544 | 11136.0 |
|        | 2014 | 25356 | 995538822 | 28652.0 |
|        | 2018 | 27433 | 588845355 | 30999.0 |
|        | 2020 | 126844 | 1991887290 | 143334.0 |
|        | 2021 | 253343 | 1340451508 | 286278.0 |
| Turner | 2000 | 3500 | 557275923 | 3955.0 |
|        | 2004 | 2235 | 995358322 | 2526.0 |
|        | 2010 | 10983 | 994853335 | 12411.0 |
|        | 2013 | 45633 | 851079918 | 51565.0 |
|        | 2015 | 52000 | 958258639 | 58760.0 |
|        | 2018 | 76550 | 552422222 | 86501.0 |
|        | 2019 | 57744 | 884352886 | 65251.0 |
|        | 2021 | 44032 | 996435345 | 49756.0 |

```python
In: df.groupby(["dealer", "year"]).sum().index
Out: 
MultiIndex([('Brittany', 2000),
            ('Brittany', 2002),
            ('Brittany', 2015),
            ('Brittany', 2020),
            ('Brittany', 2021),
            (   'Maddy', 2011),
            (   'Maddy', 2014),
            (   'Maddy', 2017),
            (   'Maddy', 2020),
            (   'Maddy', 2021),
            (    'Mike', 2015),
            (    'Mike', 2016),
            (    'Mike', 2017),
            (    'Mike', 2018),
            (    'Mike', 2019),
            (    'Mike', 2020),
            (    'Mike', 2021),
            (    'Mike', 2022),
            (     'Sam', 2012),
            (     'Sam', 2014),
            (     'Sam', 2018),
            (     'Sam', 2020),
            (     'Sam', 2021),
            (  'Turner', 2000),
            (  'Turner', 2004),
            (  'Turner', 2010),
            (  'Turner', 2013),
            (  'Turner', 2015),
            (  'Turner', 2018),
            (  'Turner', 2019),
            (  'Turner', 2021)],
           names=['dealer', 'year'])
In: df.groupby(["dealer", "year"]).sum().columns
Out: Index(['price', 'social_security', 'price_after_tax'], dtype='object')
In: dealer_year = df.groupby(["dealer", "year"]).sum()
Out:
```

|        |      | price | social_security | price_after_tax |
|--------|------|-------|-----------------|-----------------|
| dealer | year |       |                 |                 |
| Brittany | 2000 | 2333 | 134642443 | 2636.0 |
|        | 2002 | 3553 | 277425858 | 4015.0 |
|        | 2015 | 85312 | 778707070 | 96402.0 |
|        | 2020 | 78444 | 223955366 | 88642.0 |
|        | 2021 | 78444 | 223855366 | 88642.0 |
| Maddy | 2011 | 7434 | 870066354 | 8400.0 |
|        | 2014 | 17434 | 870566354 | 19700.0 |
|        | 2017 | 40434 | 640632708 | 45690.0 |
|        | 2020 | 140553 | 326234886 | 158825.0 |
|        | 2021 | 158000 | 338559922 | 178540.0 |
| Mike | 2015 | 42953 | 1578095160 | 48537.0 |
|        | 2016 | 23998 | 947577792 | 27118.0 |
|        | 2017 | 119027 | 1762863307 | 134501.0 |
|        | 2018 | 22333 | 334642443 | 25236.0 |
|        | 2019 | 39000 | 555342396 | 44070.0 |
|        | 2020 | 548492 | 3176076538 | 619795.0 |
|        | 2021 | 249550 | 2517558088 | 281992.0 |
|        | 2022 | 54000 | 462375343 | 61020.0 |
| Sam | 2012 | 9855 | 885354544 | 11136.0 |
|        | 2014 | 25356 | 995538822 | 28652.0 |
|        | 2018 | 27433 | 588845355 | 30999.0 |
|        | 2020 | 126844 | 1991887290 | 143334.0 |
|        | 2021 | 253343 | 1340451508 | 286278.0 |
| Turner | 2000 | 3500 | 557275923 | 3955.0 |
|        | 2004 | 2235 | 995358322 | 2526.0 |
|        | 2010 | 10983 | 994853335 | 12411.0 |
|        | 2013 | 45633 | 851079918 | 51565.0 |
|        | 2015 | 52000 | 958258639 | 58760.0 |
|        | 2018 | 76550 | 552422222 | 86501.0 |
|        | 2019 | 57744 | 884352886 | 65251.0 |
|        | 2021 | 44032 | 996435345 | 49756.0 |

```python
In: dealer_year.loc("Mike")
Out:
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

|      | price | social_security | price_after_tax |
|------|-------|-----------------|-----------------|
| year |       |                 |                 |
| 2015 | 42953 | 1578095160 | 48537.0 |
| 2016 | 23998 | 947577792 | 27118.0 |
| 2017 | 119027 | 1762863307 | 134501.0 |
| 2018 | 22333 | 334642443 | 25236.0 |
| 2019 | 39000 | 555342396 | 44070.0 |
| 2020 | 548492 | 3176076538 | 619795.0 |
| 2021 | 249550 | 2517558088 | 281992.0 |
| 2022 | 54000 | 462375343 | 61020.0 |

```python
In: dealer_year.loc[["Mike", "Brittany"]]
Out:
```

- https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb

|        |      | price | social_security | price_after_tax |
|--------|------|-------|-----------------|-----------------|
| dealer | year |       |                 |                 |
| Mike | 2015 | 42953 | 1578095160 | 48537.0 |
|        | 2016 | 23998 | 947577792 | 27118.0 |
|        | 2017 | 119027 | 1762863307 | 134501.0 |
|        | 2018 | 22333 | 334642443 | 25236.0 |
|        | 2019 | 39000 | 555342396 | 44070.0 |
|        | 2020 | 548492 | 3176076538 | 619795.0 |
|        | 2021 | 249550 | 2517558088 | 281992.0 |
|        | 2022 | 54000 | 462375343 | 61020.0 |
| Brittany | 2000 | 2333 | 134642443 | 2636.0 |
|        | 2002 | 3553 | 277425858 | 4015.0 |
|        | 2015 | 85312 | 778707070 | 96402.0 |
|        | 2020 | 78444 | 223955366 | 88642.0 |
|        | 2021 | 78444 | 223855366 | 88642.0 |

```python
In: dealer_year
.loc[("Mike", 2019)]
Out: 
price                  39000.0
social_security    555342396.0
price_after_tax        44070.0
Name: (Mike, 2019), dtype: float64
```
