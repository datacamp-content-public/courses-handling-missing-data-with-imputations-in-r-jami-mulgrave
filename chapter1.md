---
title: 'Hot-deck Imputation'
description: 'Learner will be able to impute values based on how similar those values are to other values using R. '
free_preview: true
---

## Impute by Matching

```yaml
type: VideoExercise
key: a297bfdc4c
xp: 50
```

`@projector_key`
8a75340ffe779b8d3cfdd8597519ffe0

---

## Using HotDeck in R

```yaml
type: NormalExercise
key: a52f360854
xp: 100
```

Here is a quick exercise to learn how to use the hotdeck procedure in R.  We will use the mammal sleep data that is pre-loaded in the VIM package.  A data frame with 62 observations on the following 10 variables:
- BodyWgt a numeric vector
- BrainWgt a numeric vector
- NonD a numeric vector
- Dream a numeric vector
- Sleep a numeric vector
- Span a numeric vector
- Gest a numeric vector
- Pred a numeric vector
- Exp a numeric vector
- Danger a numeric vector

`@instructions`
1. Install the VIM package. 
2. Load the sleep data.
3. Choose the 'BrainWgt' variable to sort the data before imputation.
4. Impute the missing variables using hotdeck.

`@hint`
Use the "ord_var" to choose the "BrainWgt" variable.

`@pre_exercise_code`
```{r}
install.packages('VIM')
library('VIM')
data(sleep)
```

`@sample_code`
```{r}
install.packages('VIM')
library('VIM')
data(sleep)
sleepI2 <- hotdeck(...)
```

`@solution`
```{r}
install.packages('VIM')
library('VIM')
data(sleep)
sleepI2 <- hotdeck(sleep,ord_var="BodyWgt")
```

`@sct`
```{r}
success_msg('Good job on completing the exercise!', praise = FALSE)
```

---

## Simple Imputation Approaches in R

```yaml
type: NormalExercise
key: fd410340f7
xp: 100
```

Now we will practice the simple imputation techniques that we have learned in R.  We will try a few of these techniques out on a dataset about class grades. For this data, the recorded values are the average of sub-components: e.g the Tutorial variable is the average of all tutorials, the Final exam variable is the average of all questions in the final, written exam.  

`@instructions`
First let's visualize the missing variables.  Create an aggregation plot using VIM.  Does there appear to be a lot of missing values or a little?

Next, let's try mean imputation for the missing values.  Try using mean imputation with the HMSIC package for the two variables that have missing data.

`@hint`


`@pre_exercise_code`
```{r}
library(VIM)
library(Hmisc)

data <- read.csv(file = "class-grades.csv", header = TRUE) #load the data


```

`@sample_code`
```{r}
agg_data <- (, numbers = TRUE, prop = c(TRUE, FALSE))

data$ImputedFinal <- (, )

data$ImputedTakeHome <- (, )

```

`@solution`
```{r}
#aggregation plots
agg_data <- aggr(data, numbers = TRUE, prop = c(TRUE, FALSE))

#mean imputation
data$ImputedFinal <- impute(data$Final, mean)

data$ImputedTakeHome <- impute(data$TakeHome, mean)

```

`@sct`
```{r}
#User should use impute()

#User should use agg()

print('Great job getting the exercise done!')
```
