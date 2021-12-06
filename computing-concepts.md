# First Course

## basic functionality
- R as a calculator
- Functions
- Arguments
- Printing output vs variable assignment
- Constructing vectors of various types
- Querying type with class
- Constructing a dataframe with tibble (to show classes)
- Loading packages
- Loading data
- Getting help (?, online documentation, posting on Ed)

- mean
- sum
- sqrt
- abs
- nrow
- log
- exponents

## rmarkdown
- Difference between console and Rmd environments
- YAML options
    - title
    - author
    - output: pdf
- "Run all chunks above" button

## ggplot2
- ggplot
- geom_
    - histogram
    - boxplot
    - bar
    - point
    - density
    - dotplot
- facet_wrap
- labs
- lims
- theme

## dplyr
- select
- count
- filter
    - logical operators
- arrange
- mutate
- summarize
- group_by + summarize

## stat20data
- get_first

## infer
- specify
- hypothesize
- generate
- calculate
- visualize
- shade_p_value
- get_p_value
- get_ci

## linear models
- lm

* * *

# Computing concepts left to second course
- drop_na    # dealing with missing data
- case_when  # recoding variables
- pivot_     # reshaping dataframes

* * *

# To-do list to clean-up and improve computing

1. Be sure all data sets load in the same manner (all in packages, as tibbles, documented, loaded without data()).
2. Add header to all pdf docs that has course no. and semester/year in a manner that can be automatically updated.
3. Consider adding very basic lab Rmd template to stat20data package.
4. Curate learnr tutorials:
    1. Basic R
    2. ggplot2
    3. dplyr
    4. infer

* * *

# Random computing resources
- tidy data tutor: https://tidydatatutor.com/
- fix leaky pipes in R: https://www.rostrum.blog/2019/04/07/fix-leaky-pipes/