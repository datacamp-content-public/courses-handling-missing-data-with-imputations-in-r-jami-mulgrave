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
