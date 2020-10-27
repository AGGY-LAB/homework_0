---
title: "Gun murder rate"
author: "Agnes Munee"
date: "10/26/2020"
output: github_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

## Introduction

This is a report on the 2010 US murder rates obtained from FBI reports.The original data was obtained from [this wikipedia page] <https://en.wikipedia.org/wiki/Murder_in_the_United_States_by_state>

We are going to use the following library 


```{r loading-libs,message=FALSE}
library(tidyverse)
```
and load the data we already wrangled
```{r}
load("rda/murders.rda")
```

## Murder rate by state

We note the large state to state variability by generating a barplot showing the murder rate by state:

```{r murder-rate-by-state,echo=FALSE}
murders %>% mutate(abb = reorder(abb, rate)) %>%
  ggplot(aes(abb, rate)) +
  geom_bar(width = 0.5, stat = "identity", color = "black") +
  coord_flip()
```


