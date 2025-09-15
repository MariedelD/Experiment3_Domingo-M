# Experiment3_Domingo-M

## I. Intended Learning Outcomes

#### 1. To identify the codes and functions incorporated in the Pandas library
#### 2. To be able to apply and use the different codes and functions in creating a Python program using a Pandas library

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
![image](https://github.com/user-attachments/assets/3d9eb492-f3bc-479b-8986-d69611cdeeb2)

---

* To display only the first five rows from the dataset stored in cars, employ **_.head() function_**.
```python
cars.head()
```

* **_.head() function_** is used to return a specified number of rows, string from the top. 

#### OUTPUT:
![image](https://github.com/user-attachments/assets/aba5bbd6-7bf7-45c1-9e0a-1c18d696eba4)

---


* To display the last five rows from the dataset stored in cars, utilize **_.tail() function_**.
```python
cars.tail()
```

* Difference from .head function, **_.tail() function_** returns a specified number of last rows.
#### OUTPUT:
![image](https://github.com/user-attachments/assets/aa4061db-0621-4600-b938-875ac138cfc2)

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
![image](https://github.com/user-attachments/assets/b5b79003-4717-42d9-b1de-9ce09e86eaaf)

---

* To determine the Row that contains the Model of Mazda RX4, utilize the **_.loc function_** .
```python
cars.loc[cars['Model'] == 'Mazda RX4']
```
* By utilizing .loc function, this will locate at all rows from the cars Dataset where the value in the 'Model' column is equal to 'Mazda RX4
#### OUTPUT:
![image](https://github.com/user-attachments/assets/cadbedb8-e573-4f33-ae70-58b1d98a2be5)

---

* To count the number of cylinders (‘cyl’) does the car model ‘Camaro Z28’ have, utilize **_.loc function_**.
```python
cars.loc[cars['Model'] == 'Camaro Z28', ['Model','cyl']]
```
* This function will select all rows from the cars dataset where the value in the 'Model' column is 'Mazda RX4' and will display only the 'Model' name and the number of cylinders ('cyl').

#### OUTPUT:
![image](https://github.com/user-attachments/assets/121c045e-89cc-49bb-b57e-e650881bb45b)

---

* To determine how many cylinders (‘cyl’) and what gear type (‘gear’) do the car models have, utilizing the following function:
```python
cars.loc[(cars['Model'] == 'Mazda RX4 Wag') |
         (cars['Model'] == 'Ford Pantera L')|
         (cars['Model'] == 'Honda Civic') ,['Model','cyl','gear']]
```
* This code locates the 'Model', 'cyl', and 'gear' columns from the cars Dataset for rows where the 'Model' is 'Mazda RX4 Wag', 'Ford Pantera L', and 'Honda Civic'

#### OUTPUT:
![image](https://github.com/user-attachments/assets/500023a4-78bd-4256-9fe8-26d8f4e8e2cb)
