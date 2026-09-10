# ECE-2112-PA-3
**Made by: Jomari Josh V. Barrientos | 2ECE-C**

The content of this repository contains the Programming Assignment 3 for the course ECE2112 or Advanced Computer Programming and Algorithms, this 1st semester of the A.Y. 2026 - 2027. This covers the 3 coding problems under Module 3 - Pandas

The following objectives of this assignment are to:

1. load a CSV dataset into a Pandas DataFrame;
2. select rows and columns using positional and label-based indexing;
3. filter records using conditions on a DataFrame column; and
4. extract a well-defined subset of data without changing the source data.

Note: the data for the problems on this assignment are based on the given file `cars.asd`. Furthermore, Pandas was imported using the function:
```python 
import pandas as pd
```

# A. Positional and Label-based Slicing
In this problem, there are three operations needed to do:

  1. Display the shape and complete list of column names of cars.
  
  The function to get the shape and list of column names for the dataframe `cars`.
      
```python
      cars.shape
      cars.columns
```

  2. Create `cars_6to_10` where it displays the rows 6 to 10 of the dataset.
  
``` python
      cars_6_to_10 = cars.iloc[5:10]      
```
      
  Wherein using `iloc` with the range here creates a new dataset by slicing from the first boundary `5` and the non-inclusive upper boundary `10`, creating a new set that targets the rows 6 to 10 of the original dataset. 

  3. From the created `cars_6_to_10`, display only the columns `Model`, `mpg`, `cyl`, `hp`, and `gear`, in that order.

``` python
    print(cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']])
```

For this step of the problem, we get the previously created variable `cars_6-to_10` and add conditions to display only these columns in this particular order.

# B. Model Lookup
  In this part, the task is to use Boolean indexing on the Model column in order to satisfy the given conditions.

```python
  toyota = cars.loc[cars['Model'] =='Toyota Corolla']

  pontiac = cars.loc[(cars['Model'] == 'Pontiac Firebird'), ['Model', 'mpg', 'hp', 'wt']]
```
  Both steps of the problem utilize the function `cars.loc` but the difference is that for `toyota`, it displays the whole columns since there are no restrictions. As for `pontiac`, the only required columns to be displayed are `Model`, `mpg`, `hp`, and `wt` in that particular order, hence the addition of this bracket `['Model', 'mpg', 'hp', 'wt']` after the Boolean statement in order to satisfy the requirement.

# C. Multi-model Subsetting
  The requirements for this problem are to create a dataset named `selected_cars` that records only the models of: `Datsun 710`, `Lotus Europa`, and `Ferrari Dino`. It must also have the columns `Model`, `mpg`, `cyl`, `hp`, and `gear`.

  ```python
      selected_cars = cars.loc[(cars['Model'] == 'Datsun 710') |
                (cars['Model'] == 'Lotus Europa') |
                 (cars['Model'] == 'Ferrari Dino'), ['Model', 'mpg', 'cyl', 'hp', 'gear']]
```
In order to satisfy the given conditions, the bitwise operator `|` OR is utilized so that it would return true and it would be included in `selected_cars`. After that is the conditions of which columns will appear and in what order they should be.

Then next is to display `selected_cars` and its shape.
```python
    print(selected_cars)
    print('Shape:', selected_cars.shape)
```

# Version History
September 10 - README.md file was created

September 11 - README.md file was edited
