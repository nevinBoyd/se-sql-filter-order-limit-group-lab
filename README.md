# Lab: Filtering, Ordering, Limiting, and Grouping Data with SQL

## Introduction

In this lab assessment you will explore writing more advanced SQL queries aimed at analyzing data on a more granular level. You will be working with 3 different databases throughout the assessment.
- planets.db: Contains data pertaining to planets in our solar system
- dogs.db: Contains data pertaining to famous fictional dog characters
- babe_ruth.db: Contains data pertaining to Babe Ruth's baseball career statistics

SQL (Structured Query Language) provides powerful tools for manipulating and analyzing data in relational databases. Four key operations for working with data are filtering, ordering, limiting, and grouping. These operations can be combined in a single query to perform complex data analysis and extraction tasks, allowing for powerful and flexible data manipulation.

## Learning Objectives

* Retrieve a subset of records from a table using a `WHERE` clause
* Filter results using conditional operators
* Apply an aggregate function to the result of a query
* Order the results of your queries by using `ORDER BY` (`ASC` & `DESC`)
* Limit the number of records returned by a query using `LIMIT`
* Use `GROUP BY` statements in SQL to apply aggregate functions

## Set Up

* Fork and Clone the GitHub Repo
* Install dependencies and enter the virtual environment:
    * `pipenv install`
    * `pipenv shell`

All your code will be in `main.py`. You can add any print statements needed to check your code and run the file with `python3 main.py`. The lab will be graded using the test suite, which you can also use to check your work by running `pytest` or `pytest -x`.

## Part I: Basic Filtering

You will begin by looking at the planets data to perform some basic filtering queries.

Table Name: planets

```python
# STEP 0

import pandas as pd
import sqlite3

# Create the connection
# Note the connect is 'conn1' since there will be multiple .db used
conn1 = sqlite3.connect('planets.db')

# Select all
pd.read_sql("""SELECT * FROM planets; """, conn1)
```

### Step 1

Return all the columns for planets that have 0 moons.

```python
# STEP 1
# Replace None with your code
df_no_moons = None
```

### Step 2

Return the name and mass of each planet that has a name with exactly 7 letters. Avoid hard coding this filter subset as much as possible.

```python
# STEP 2
# Replace None with your code
df_name_seven = None
```

## Part 2: Advanced Filtering

### Step 3

Return the name and mass for each planet that has a mass that is less than or equal to 1.00.

```python
# STEP 3
# Replace None with your code
df_mass = None
```

### Step 4

Return all the columns for planets that have at least one moon and a mass less than 1.00.

```python
# STEP 4
# Replace None with your code
df_mass_moon = None
```

### Step 5

Return the name and color of planets that have a color containing the string "blue".

```python
# STEP 5
# Replace None with your code
df_blue = None
```

## Part 3: Ordering and Limiting

This database has some fictional, yet generally famous, dogs.

Table Name: dogs

```python
# STEP 0

# Create a connection
# Note the connect is 'conn2' since they will be multiple .db used
conn2 = sqlite3.connect('dogs.db')

# Select all
pd.read_sql("SELECT * FROM dogs;", conn2)
```

### Step 6

Return the name, age, and breed of all dogs that are hungry (binary flag of 1) and sort them from youngest to oldest.

```python
# STEP 6
# Replace None with your code
df_hungry = None
```

### Step 7

Return the name, age, and hungry columns for hungry dogs between the ages of two and seven. This query should also sort these dogs in alphabetical order.

```python
# STEP 7
# Replace None with your code
df_hungry_ages = None
```

### Step 8

Return the name, age, and breed for the 4 oldest dogs. Sort the result alphabetically based on the breed.

```python
# STEP 8
# Replace None with your code
df_4_oldest = None
```

## Part 4: Aggregation

In the next few parts, you'll query data from a table populated with Babe Ruth's career hitting statistics. You'll use aggregate functions to pull interesting information from the table that basic queries cannot track.

Table Name: babe_ruth_stats

```python
# STEP 0

# Create a connection
# Note the connect is 'conn3' since they will be multiple .db used
conn3 = sqlite3.connect('babe_ruth.db')

# Select all
pd.read_sql("""
SELECT * FROM babe_ruth_stats; """, conn3)
```

### Step 9

Return the total number of years that Babe Ruth played professional baseball

```python
# STEP 9
# Replace None with your code
df_ruth_years = None
```

### Step 10

Return the total number of homeruns hit by Babe Ruth during his career.

```python
# STEP 10
# Replace None with your code
df_hr_total = None
```

## Part 5: Grouping and Aggregation

### Step 11

For each team that Babe Ruth has played on, return the team name and the number of years he played on that team, aliased as 'number_years'.

```python
# STEP 11
# Replace None with your code
df_teams_years = None
```

### Step 12

For each team that Babe Ruth played on and averged over 200 at bats with, return the team name and average number of at bats, aliased as 'average_at_bats'.

```python
# STEP 12
# Replace None with your code
df_at_bats = None
```

#### Close the connections
```python
# This code is already at the bottom of the file
conn1.close()
conn2.close()
conn3.close()
```
---

## Developer Notes

Used Pandas + SQLite to write filtering, ordering, limiting, grouping, and aggregation queries.

Used Python REPL to confirm real column names in all 3 databases:
- planets: num_of_moons
- dogs: hungry, age, breed
- babe_ruth: HR

