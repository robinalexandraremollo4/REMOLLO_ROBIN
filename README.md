# ECE-2112-PA-3

**Made by: Robin Alexandra B. Remollo | 2ECE-D**

This content of this repository contains the Programming Assignment 3 for our course "Advanced Computer Programming and Algorithms" this S.Y. 2026-2027. This project covers three Python problems pertaining to Experiment 3: Python Data Analysis (Pandas)

## I. OBJECTIVES OF THE EXPERIMENT

The objectives of the experiment are the following:

- Load a CSV dataset into a Pandas `DataFrame`;
- select rows and columns using positional and label-based indexing;
- filter records using conditions on a DataFrame column; and
- extract a well-defined subset of data without changing the source data.

## II. PROGRAMMING PROBLEMS

## A. Positional and Label-Based Slicing

Instructions:

1. Display the shape and complete list of column names of `cars`.
2. Using positional slicing, create `cars_6_to_10` containing rows 6 through 10 of the dataset, where the first data row is row 1.
3. From cars_6_to_10, display only the columns `Model`, `mpg`, `cyl`, `hp`, and `gear`, in that order.

**Requirement**: The row selection in part (b) must use iloc; the column selection in part (c) must
use column labels.

The following methods were used in this problem:

- `cars.loc[:,['Model']]` = This selects the Model column using label-based indexing
- ` cars.iloc[6:11]` = This selects rows using positional indexing by starting at position 6 and stops before position 11.
- `.loc[:,['Model', 'mpg', 'cyl', 'hp', 'gear']]` = This selects all rows and only the specified columns using column labels.

``` python

import pandas as pd

cars = pd.read_csv('cars.csv')
cars

cars.loc[:,['Model']]

cars_6_to_10 = cars.iloc[6:11]
cars_6_to_10

cars_6_to_10.loc[:,['Model', 'mpg', 'cyl', 'hp', 'gear']]


```

## B. Model Lookup

Instructions:
1. Use Boolean indexing on the `Model` column to answer both requests.
2. Display the complete row for `Toyota Corolla`.
3. For Pontiac Firebird, display only `Model`, `mpg`, `hp`, and `wt`.
4. Store the two results in `toyota` and `pontiac`, respectively. Do not use a hard-coded row number to locate either model.

The following methods were used in this problem:

- `cars.loc[cars['Model'] == 'Toyota Corolla']` = This uses Boolean indexing to find the row where the `Model` column matches `Toyota Corolla`. The complete row is displayed since no specific columns are provided.
- `cars.loc[cars['Model'] == 'Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt']]` = This uses Boolean indexing to find the row where the `Model` is `Pontiac Firebird`, then selects only the specified columns: `Model`, `mpg`, `hp`, and `wt`.

``` python

toyota = cars.loc[cars['Model'] == 'Toyota Corolla']
toyota

pontiac = cars.loc[cars['Model'] == 'Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt']]
pontiac

```

## C. Multi-Model Subsetting

Instructions:
1. Create a DataFrame named `selected_cars` containing only the records for three models: `Datsun 710`, `Lotus Europa`, and `Ferrari Dino`.
2. For these records, retain only `Model`, `mpg`, `cyl`, `hp`, and `gear`. Select the rows by their model values rather than by row numbers. Display `selected_cars` and its shape.
3. **Required check**: The final DataFrame must contain exactly three rows and five columns.

The following methods were used in this problem:

- `cars.loc[(cars['Model'] == 'Datsun 710')` 
- `(cars['Model'] == 'Lotus Europa')`
- `(cars['Model'] == 'Ferrari Dino')`

Uses `.loc` to select specific rows and columns from the DataFrame. The row selection is based on conditions in the `Model` column.

- `['Model', 'mpg', 'cyl', 'hp', 'gear']]` = This specifies which columns to keep among the displayed
- `|` = This represents the OR in Boolean indexing for Pandas. It allows multiple conditions to be combined.
- `selected_cars.shape` = Displays the row and column dimensions of the subset. This DataFrame contains exactly 3 rows and 5 columns `(3, 5)`.

``` python

models = ['Datsun 710', 'Lotus Europa', 'Ferrari Dino']

selected_cars = cars.loc[(cars['Model'] == 'Datsun 710') | (cars['Model'] == 'Lotus Europa') | (cars['Model'] == 'Ferrari Dino'), ['Model', 'mpg', 'cyl', 'hp', 'gear']]
selected_cars

selected_cars.shape

```
Thank you for reading!

To see the main python program for Programming Assignment 2, click this link [https://github.com/robinalexandraremollo4/REMOLLO_ALEX].

READ ME FILE VERSION HISTORY

August 26, 2026 - Coding on Google Colab, finished A. Reproducible Normalization Problem.

September 1, 2026 - Finishing of B. Cubes Divisible by 4 Problem and C. Above-Mean Squares Problem.

September 2, 2026 - Finalization of code structures and flow of README file. Creation of a cohesive Github repository for all requirements.


















