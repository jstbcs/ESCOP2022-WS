# ESCOP2022-WS
Workshop on Bayesian Cognitive Modeling using brms

**Instructors: Julia M. Haaf & Michael D. Nunez from the [Amsterdam Mathematical Psychology Laboratory](https://www.ampl-psych.com/) at the University of Amsterdam**

### Overview

- Intro to Bayes - Julia (20min)
- Introduction to the Perceptual Decision Making data - Michael (5min)
- Practical usign brms but non-hierarchical - Julia (see Bayes stats course) (10min)
- Bayesian hierarchical regression (20min) and Practical (20min) - Michael (total: 40min)
- Intro to cognitive modeling: signal-detection (Julia) (15min)
- Intro to cognitive modeling: DDM (Michael) (15min)
- Practical either SDT (Julia) or DDM (Michael) (15min) - blog posts

### Perceptual Decision Making (PDM) task data

```R
install.packages('curl')  #You will need to load the R package "curl" to use this cleaning code
library(curl) 

# See https://github.com/mdnunez/encodingN200 for more information about the data
pdmdat <- curl("https://tinyurl.com/dataBayesCogMod")
pdm <- read.csv(pdmdat)

head(pdm)
```


