# ESCOP2022-WS
Workshop on Bayesian Cognitive Modeling using brms

##DATA

library(curl) ##You will need to load the R package "curl" to use this cleaning code

###Stroop Data (Data Set 1)
filename <- curl("https://raw.githubusercontent.com/PerceptionCognitionLab/data0/master/contexteffects/FlankerStroopSimon/LEF_stroop.csv")
stroop <- read.csv2(filename, header=TRUE, dec=".")

stroop$cond <- as.numeric(stroop$congruency)  #congruent -> 1, incongruent -> 2, neutral -> 3
ntrial <- length(stroop[stroop$ID == stroop$ID[1], 1])
nsub <- length(unique(stroop$ID))
stroop$trial <- rep(1:ntrial, nsub)
stroop$rt <- stroop$RT/1000 #rt data in seconds

stroop <- stroop[stroop$rt > .2 & stroop$rt < 2, ]
stroop <- subset(stroop, accuracy == 1 & cond != 3)

##PLAN

- Intro to Bayes - Julia (15-20min)
- Practical usign brms but non-hierarchical - Julia (see Bayes stats course) (10min)
- Bayesian (multilevel) regression - Michael (20min)
- Practical (see Bayes stats course) - Michael (25min)
- Intro cognitive modeling signal-detection (Julia) & DDM (Michael) (30mins)
- Practical either SDT (Julia) or DDM (Michael) (15min) - blog posts
