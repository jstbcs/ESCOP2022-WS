# ESCOP2022-WS
Workshop on Bayesian Cognitive Modeling using brms

**Instructors: Julia M. Haaf & Michael D. Nunez from the [Amsterdam Mathematical Psychology Laboratory](https://www.ampl-psych.com/) at the University of Amsterdam**

### Overview

- Intro to Bayes - Julia (20min)
- Practical usign brms but non-hierarchical - Julia (see Bayes stats course) (10min)
- Bayesian hierarchical regression (20min) and Practical (25min) - Michael (total: 45min)
- Intro to cognitive modeling: signal-detection (Julia) (15min)
- Intro to cognitive modeling: DDM (Michael) (15min)
- Practical either SDT (Julia) or DDM (Michael) (15min) - blog posts

### Perceptual Decision Making (PDM) task data

```R
install.packages('curl')  #You will need to load the R package "curl" to use this cleaning code
library(curl) 


# See https://github.com/mdnunez/encodingN200 for more information about the data
filename <- curl("https://raw.githubusercontent.com/mdnunez/encodingN200/master/Data/N200_rt_window_150_275.csv")
pdm <- read.csv(filename)
colnames(pdm) <- c('N200_latencies', 'N200_amplitudes', 'RT', 'accuracy', 'condition', 'EEG_session', 'experiment', 'session', 'subject')
pdm <- pdm[pdm$experiment == 1, ]  # Take on the data from the first experiment
pdm$N200_latencies <- pdm$N200_latencies/1000  # Convert from milliseconds to seconds
pdm$RT <- pdm$RT/1000 # Convert from milliseconds to seconds

ntrial <- dim(pdm)[1]
nsub <- length(unique(pdm$subject))

head(pdm)
```


