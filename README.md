# Experiment 3: Phyton Data Analysis (PANDAS)
### Submitted by: Mariedel Domingo

## I. Introduction

### Intended Learning Outcomes

- In this experiment, the intended learning outcome is to utilize and apply the built in fucntion incorporated Pandas Library in different sample problem.

## II. Instructions

### PROBLEM 1

> [!IMPORTANT]
> Save your file as Surname_Pandas-P1.py
> 
#### $\color{Apricot}{Using\ knowledge\ obtained\ from\ the\ experiment\ and\ demonstrations\ :}$ 

#### a. Load the corresponding .csv file into a data frama named cars using pandas.
* The following .csv file can be downloaded [here](http://bit.ly/Cars_file)
  > NOTE: 
  >   Ensure that the following file is saved in the same directory as your Jupyter notebook so that the notebook can locate it.
#### b. Display the first five and last five rows of the resulting cars.

### PROBLEM 2

> [!IMPORTANT]
> Save your file as Surname_Pandas-P2.py
> 
#### $\color{Apricot}{Using\ the\ dataframe\ cars\ in\ problem\ 1\ ,\ extract\ the\ following\ information\ using\ subsetting\ ,\ slicing\ ,\ and\ indexing\ operations. }$  
#### a. Display the first five rows with odd-numbered columns (columns 1, 3, 5, 7...) of cars.
#### b. Display the row that contains the ‘Model’ of ‘Mazda RX4’.
#### c. How many cylinders (‘cyl’) does the car model ‘Camaro Z28’ have?
#### d. Determine how many cylinders (‘cyl’) and what gear type (‘gear’) do the car models ‘Mazda RX4 Wag’, ‘Ford Pantera L’ and ‘Honda Civic’ have.

## III. Solutions

### Problem 1: 

* Using this **_import convention_** allows access to the Pandas library, which will be utilized throughout the entire program.
```python
import pandas as pd
```

* After accessing the Pandas Library, **_save the .csv file_** in the same directory as your Jupyter notebook to ensure that the notebook can locate it.
```python
cars = pd.read_csv('cars.csv')
cars
```
* By using the **_pd.read_csv() function_**, the file will be located and its dataset stored in the variable cars.
#### OUTPUT:

---

* To display only the first five rows from the dataset stored in cars, employ **_.head() function_**.
```python
cars.head()
```

* **_.head() function_** is used to return a specified number of rows, string from the top. 

#### OUTPUT:


---


* To display the last five rows from the dataset stored in cars, utilize **_.tail() function_**.
```python
cars.tail()
```

* Difference from .head function, **_.tail() function_** returns a specified number of last rows.
#### OUTPUT:


### Problem 2:

* Utilize slicing to display the first five odd-numbered columns of cars by specifying column indices for slicing. Slicing helps identify these columns, and the default syntax for slicing is as follows:
```python
cars.loc[0:4,::2]
```
* Wherein:
```python
cars.loc[range of index,iteration]
```

#### OUTPUT:


---

* To determine the Row that contains the Model of Mazda RX4, utilize the **_.loc function_** .
```python
cars.loc[cars['Model'] == 'Mazda RX4']
```
* By utilizing .loc function, this will locate at all rows from the cars Dataset where the value in the 'Model' column is equal to 'Mazda RX4
#### OUTPUT:


---

* To count the number of cylinders (‘cyl’) does the car model ‘Camaro Z28’ have, utilize **_.loc function_**.
```python
cars.loc[cars['Model'] == 'Camaro Z28', ['Model','cyl']]
```
* This function will select all rows from the cars dataset where the value in the 'Model' column is 'Mazda RX4' and will display only the 'Model' name and the number of cylinders ('cyl').

#### OUTPUT:


---

* To determine how many cylinders (‘cyl’) and what gear type (‘gear’) do the car models have, utilizing the following function:
```python
cars.loc[(cars['Model'] == 'Mazda RX4 Wag') |
         (cars['Model'] == 'Ford Pantera L')|
         (cars['Model'] == 'Honda Civic') ,['Model','cyl','gear']]
```
* This code locates the 'Model', 'cyl', and 'gear' columns from the cars Dataset for rows where the 'Model' is 'Mazda RX4 Wag', 'Ford Pantera L', and 'Honda Civic'

#### OUTPUT:

