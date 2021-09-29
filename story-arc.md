## Welcome (1 lecture)
Shoebill

## Intro to Data (2 lectures)
- Data is diverse (images, text, sound, matrices)
- Data Frame as a data structure to facilitate analysis
- Go through examples of tidy and not tidy dataframes
- Define variables (columns) and units of obs (rows)
- Taxonomy of Data as way to think about variables

## R (1 lecture)
- On board:
    - functions
    - arguments
    - saving objects
    - the pipe
    - loading a package

## Reproducibility (1 lecture)
- Rogoff and Reinhardt
- How Rmds work

## Describing Data

## Numerical Data (1 lecture)
- [average man video]
- description involves information loss
- histograms
- verbal descriptions with histograms: skew, modality, center, spread.
- constructing statistics as ways to put a number to each of those words.

## Categorical Data (2 lecture)
- counts, proportions of one variable
- counts, proportions of 2 variables
- barplots: stacked, dodged, standardized
---
- What's the denominator?
- Simpson's Paradox

## Grammar of graphics (2 lectures)

implementation detail
- Use wbstats and WBI r packages to recreate hans roslings graphic


## Study Design (3 lectures)
- Sampling
- principles of experimental design
    Use: random assignment, control, and replicates
- stratification and blocking

### Exp Design lecture
- Decide on two groups to "interview" in class: paired and not
- Set up cups on tables at front to demonstrate their setups
- Ask the same set of questions to each group (something like):
    - Did 
    Use: random assignment, control, and replicates
    
---
Transitioning to this doc being just "lessons learned"

## Probability
- Ditch the "table method" for showing the arithmetic behind the summation notation. Just expand out the sum so that you can show the contribution from each element.
- With conditional prob, students need to work through one more example in lecture.

# Dplyr
- lay the ground work earlier. in general, from easiest to hardest
    - select
    - arrange
    - mutate
    - filter and logicals
    - summarize
    - group_by x summarize
- strip all na's out of data sets so that you don't need to discuss drop_na vs na.rm vs na.omit vs is.na().
- explicitly teach why we use the pipe as we move from R as a calculator to R as a language for data pipelines.
