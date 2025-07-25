# Introduction to R

## Fundamentals

'#' - comment

3 + 4 - simple code

An **addition** - 5 + 5

A **subtraction** - 5 - 5

A **multiplication** - 3 * 5

A **division -** (5 + 5) / 2

**Exponentiation** - 2^5

**Modulo** - 28 %% 6

*Assign the value* 42 to x - x <- 42

Check class of my_logical - class(my_logical)

*Creating vectors - c()*

roulette_vector <- c(-24, -50, 100, -350, 10)

*Index starts with 1*

*Define a new variable based on a selection*

poker_midweek <- poker_vector[c(2, 3, 4)]

Pwede rin gumamit nito [2:4]

Average - mean()

### How to make a matrix:

matrix(1:9, byrow = TRUE, nrow = 4)

Sum Matrix - rowSums() & colSums (

#### Example

Calculate worldwide box office figures

worldwide_vector <- rowSums(star_wars_matrix)

Bind Matrix - cbind() & rbind()

#### Example

Define vectors

vec1 <- c(1, 2, 3)
vec2 <- c(4, 5, 6)

cbind()

vec1 vec2
[1,]    1    4
[2,]    2    5
[3,]    3    6

rbind()

    [,1] [,2] [,3]
vec1    1    2    3
vec2    4    5    6

### How to look for rows & columns

Rows - [1, ]

Columns - [, 2]

### Factor

factor() - store categorical values

summary()

levels()

ordered = TRUE/FALSE

### Data Frames

str() - get rapid overview of the data

head() - the front

tail()

data.frame()

subset() - shortcut to select a subset

order(a) - make things in order

a[order(a)] - reshuffle order

#### Example:

Select first 5 values of diameter column

planets_df[1:5, "diameter"]

Shortcut - planets_df$rings

note: see the "$"" symbol

#### Example:

Adapt the code to select all columns for planets with rings

planets_df[rings_vector, ]

#### Example:

Select planets with diameter < 1

subset(planets_df, subset = diameter < 1)

#### Example:

Use order() to create positions

positions <-  order(planets_df$diameter)

Use positions to sort planets_df

<<<<<<< HEAD
planets_df[positions, ]

### List

list() - components can be matrices, vectors, other lists

#### Example

Name the lists

my_list <- list(vec = my_vector, mat = my_matrix, df = my_df)

planets_df[positions, ]

rownames - use to name rows

#### Sample Problem

Return a table with **nine** rows and **five** columns.

* The five columns should be aliased as: `stay`, `count_int`, `average_phq`, `average_scs`, and `average_as`,  **in that order** .
* The average columns should contain the average of the `todep` (PHQ-9 test), `tosc` (SCS test), and `toas` (ASISS test) columns for each length of stay,  **rounded to two decimal places** .
* The `count_int` column should be the number of international students for each length of stay.
* Sort the results by the length of stay in  **descending order** .

SELECT
    stay,
    COUNT(inter_dom) AS count_int,
    ROUND(AVG(todep), 2) AS average_phq,
    ROUND(AVG(tosc), 2) AS average_scs,
    ROUND(AVG(toas), 2) AS average_as
FROM
    students
WHERE
	inter_dom = 'Inter'
GROUP BY
    stay
ORDER BY
    stay DESC
LIMIT 9;

# Intermediate R

## Relational Operators

### **Equality ==**

|  TRUE == TRUE<br />Output: TRUE  | "hello" == "goodbye"<br />Output: FALSE |
| :-------------------------------: | :-------------------------------------: |
| TRUE == FALSE<br />Output: FALSE |        3 == 2<br />Output: FALSE        |

### **Inequality ==**

| TRUE != TRUE<br />Output: FALSE | "hello" != "goodbye"<br />Output: TRUE |
| :------------------------------: | :-------------------------------------: |
| TRUE != FALSE<br />Output: TRUE |        3 != 2<br />Output: TRUE        |

### <= and >=

| 5 >= 3<br />Output: TRUE |
| ------------------------ |
| 3  >= 3                 |
| Output: TRUE             |

### Relational Operators & Vectors

linkedin <- c(16, 9, 13, 5, 2, 17, 14)

linkedin

Output: 16 9 13 5 2 17 14

linkedin > 10

TRUE FALSE TRUE FALSE FALSE TRUE TRUE

Note: Can also compare vectors n vectors

## Logical Operators


AND operator &

|  TRUE & TRUE<br />Output: TRUE  | TRUE & FALSE<br />Output: FALSE |
| :-----------------------------: | :------------------------------: |
| FALSE & TRUE<br />Output: FALSE | FALSE & FALSE<br />Output: FALSE |

OR operator "|"

| TRUE & TRUE<br />Output: TRUE | TRUE & FALSE<br />Output: TRUE |
| :----------------------------: | :------------------------------: |
| FALSE & TRUE<br />Output: TRUE | FALSE & FALSE<br />Output: FALSE |

The double ampersand and or only return the first comparison
