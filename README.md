# ESCOP2022-WS
Workshop on Bayesian Cognitive Modeling using brms (https://escop2022.org/escop-2022-satellite-events)

**Instructors: Julia M. Haaf & Michael D. Nunez from the [Amsterdam Mathematical Psychology Laboratory](https://www.ampl-psych.com/) at the University of Amsterdam**

### Summary

This event will introduce Bayesian analysis with a particular focus on building cognitive models. Cognitive models provide a powerful tool to disentangle different cognitive processes contributing to the same observable responses. You will learn how to fit three classes of models to your own data. In a Bayesian estimation framework, we will introduce fitting multilevel linear models to trial-level data, signal detection models to choice data, and drift-diffusion models of choice-response time data. You will use RStudio and the brms R package. We will discuss parameter estimation, choice of prior distributions, and evaluation of posterior distributions. After this workshop you will feel comfortable fitting cognitive models using RStudio and brms in your future research. We expect only a basic knowledge of statistics before this workshop. You do not need a background in R programming but some familiarity with R is helpful. If possible, the participants should bring their own laptop and install r, rstudio and brms including all packages required for brms (for installing all devices).

### Overview

- Introduction to Bayesian Statistics - Julia
- Practical mini-session using brms - Julia
- Bayesian hierarchical regression and Practical - Michael
- Intro to cognitive modeling: signal-detection (Julia)
- Intro to cognitive modeling: DDM (Michael)
- Practical either SDT (Julia) or DDM (Michael)


### Installing RStudio

https://www.rstudio.com/products/rstudio/download/#download


### Alternatives to local RStudio (slow)

There are two possibilities to use R online if you have not installed RStudio or are having trouble installing certain packages:
[Google Colab R](https://colab.to/r)
[RStudio Cloud - Requires free account creation](https://rstudio.cloud/)

### Installing brms

Try running the following 4 lines in R. Installing brms will also install Stan in the background. If you have a local RStudio, you might have either install RTools after the 3rd line or update R & RStudio to the newest version.

```R
install.packages('brms')
library(brms)
bayesian_lm = brm(zBase ~ zAge, data=epilepsy)
summary(bayesian_lm)

```

### Perceptual Decision Making (PDM) task data

```R
install.packages('curl')  #You will need to load the R package "curl" to use this cleaning code
library(curl) 

# See https://github.com/mdnunez/encodingN200 for more information about the data
pdmdat <- curl("https://tinyurl.com/dataBayesCogMod")
pdm <- read.csv(pdmdat)

head(pdm)
```


