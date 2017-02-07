  ---
  title       : Average Treatment Effects
  description : This exercise helps you get to know the basics of statistical inference
  attachments :
  video_link :


--- type:VideoExercise lang:r aspect_ratio:62.5 xp:50 skills:1
## What is the Point of Statistical Inference?
*** =video_link
//player.vimeo.com/video/198212067

--- type:MultipleChoiceExercise lang:r xp:50 skills:1
## MC 1
Under which scenario might an experimenter not need to use statistical inference to justify his causal claims?

*** =instructions
- When his causal claim seems intuitive.
- When his sample is large.
- When his experiment is well-designed.
- When he can have his entire population of interest participate in the experiment.
*** =sct
```{r}
msg1 = "Try again!"
msg2 = "Try again"
msg3 = "Try again"
msg4 = "Correct! The purpose of statistical inference in randomized experiments is to help researchers make valid propositions about a population given a sample. This is unnecessary if the entire population of interest participates in the experiment."
test_mc(correct = 4, feedback_msgs = c(msg1,msg2,msg3,msg4))
```

--- type:MultipleChoiceExercise lang:r xp:50 skills:1
## MC 2
A professor was interested in whether myopia in children could be caused by environmental factors. He found a completely random sample of 10 children, and had 5 of them sleep with nightlights and 5 of them sleep without nightlights for the first 10 years of their lives. All of the children who had slept with nightlights developed myopia, whereas only 2 of the children who did not sleep with nightlights developed myopia. From this study, the professor determined that the average treatment effect of using a nightlight on myopia was (100% - 40% =) 60%. Why might the professor want to get a larger sample before publishing these results?

*** =instructions
- To please his reviewers.
- To control for non-compliance.
- To make sure that the observed average treatment effect did not occur by chance.
- To control for confounding variables.

*** =sct
```{r}
msg1 = "Try again"
msg2 = "Try again"
msg3 = "Correct! Even when we draw from a completely random sample, there is always the chance that our sample is not representative of the whole population. The larger the sample size that we draw from, the less likely that our findings were to have occurred by chance."
msg4 = "Try again"
test_mc(correct = 3, feedback_msgs = c(msg1,msg2,msg3,msg4))
```

## Randomized Controlled Trial
*** =video_link
//player.vimeo.com/video/198212064

--- type:MultipleChoiceExercise lang:r xp:50 skills:1
## MC 3
How are the results from randomized control trials interpreted differently than randomized experiments?

*** =instructions
- They are not interpreted differently from randomized experiments.
- They have real-world implications.
- They do not need to be tested for statistical significance.
- They should be estimated with conditional average treatment effects.

*** =sct
```{r}
msg1 = "Correct! A randomized control trial is a type of randomized experiment."
msg2 = "Try again"
msg3 = "Try again"
msg4 = "Try again"
test_mc(correct = 3, feedback_msgs = c(msg1,msg2,msg3,msg4))
```

## The Design of the Oregon Health Experiment.
*** =video_link
//player.vimeo.com/video/198212064

--- type:NormalExercise lang:r aspect_ratio:62.5 xp:50 skills:1
## Practice Reading Tables
Let's practice reading tables from the Oregon Health Experiment. The dataframe "OregonHealthDepressionResults" indicates results from the Oregon Health Experiment (in percentages) pertaining to depression. With this dataframe, answer the following questions:

*** =instructions
- What is the mean value of positive screening in the control group?
- What is the average treatment effect of medicaid coverage on diagnosis after lottery? 
- Which average treatment effect of medicaid coverage on depression was not statistically significant? 

*** =pre_exercise_code
```{r}
OregonHealth<-data.frame(c("Blood pressure - Systolic (mm Hg)","Blood pressure - Diastolic (mm Hg)","Blood pressure - Elevated (%)","Hypertension - Diagnosis after lottery (%)","Hypertension - Current use of medication for hypertension (%)","Cholesterol - Total level (mg/dl)","Cholesterol - High total level (%)","Cholesterol - HDL level (mg/dl)","Cholesterol - Low HDL level (%)","Hypercholesterolemia - Diagnosis after lottery (%)","Hypercholesterolemia - Current use of medication for high cholesterol level (%)","Glycated hemoglobin - Level (%)","Glycated hemoglobin - Level ???6.5% (%)","Diabetes - Diagnosis after lottery (%)","Diabetes - Current use of medication for diabetes (%)","Depression - Positive screening result (%)","Depression - Diagnosis after lottery (%)","Depression - Current use of medication for depression (%)","Framingham risk score - Overall","Framingham risk score - High-risk diagnosis","Framingham risk score - Age 50-65 yr"),
              c(119.3,76,16.3,5.6,13.9,204.1,14.1,47.6,28,6.1,8.5,5.3,5.1,1.1,6.4,30,4.8,16.8,8.2,11.6,13.9),
              c(-0.52,-0.81,-1.33,1.76,0.66,2.2,-2.43,0.83,-2.82,2.39,3.8,0.01,-0.93,3.83,5.43,-9.15,3.81,5.49,-0.21,1.63,-0.37),
              c(-2.97,-2.65,-7.16,-1.89,-4.48,-3.44,-7.75,-1.31,-10.28,-1.52,-0.75,-0.09,-4.44,1.93,1.39,-16.7,0.15,-0.46,-1.56,-1.11,-2.64),
              c(1.93,1.04,4.49,5.4,5.8,7.84,2.89,2.98,4.64,6.29,8.35,0.11,2.59,5.73,9.48,-1.6,7.46,11.45,1.15,4.37,1.9),
              c(0.68,0.39,0.65,0.34,0.8,0.45,0.37,0.45,0.46,0.23,0.1,0.82,0.61,0.001,0.008,0.02,0.04,0.07,0.76,0.24,0.75))
names(OregonHealth)<-c("Variable","Mean Value in Control Group","Change with Medicaid Coverage","95% Confidence Interval (lower bound)","95% Confidence Interval (Upper Bound)","P Value")
OregonHealthResults<-OregonHealth[16:18,]
OregonHealthResults$Variable<-c("Positive_Screening","Diagnosis_After_Lottery","Current_Use_Of_Medication")
rm(OregonHealth)
```
*** =sample_code
```{r}
str(OregonHealthResults) # Dataframe

print(Solution1<- ) # Write mean value of positive screening in the control group

print(Solution2<- ) # Write average treatment effect of medicaid coverage on diagnosis after lottery

print(Solution3<-"") # Write name of variable whose average treatment effect was not statistically significant

```

*** =solution
```{r}
print(Solution1<-OregonHealthResults[OregonHealthResults$Variable=="Positive_Screening",]$`Mean Value in Control Group`)
print(Solution2<-OregonHealthResults[OregonHealthResults$Variable=="Diagnosis_After_Lottery",]$`Change with Medicaid Coverage`)
print(Solution3<-OregonHealthResults[OregonHealthResults$`P Value`>.05,]$Variable)

```

*** =sct
```{r}
ex() %>% check_output("30.*",
missing_msg = "Solution1 is incorrect. Make sure to print the answer")
ex() %>% check_output("3.81.*",
missing_msg = "Solution2 is incorrect. Make sure to print the answer")
ex() %>% check_output('"[C|c]urrent.*"',
missing_msg = "Solution3 is incorrect. Please write out your answer. Make sure it is in string format and printed in the console") 
success_msg("Good work!")
```

## The Design of the Oregon Health Experiment.
*** =video_link
//player.vimeo.com/video/198212064


--- type:NormalExercise lang:r aspect_ratio:62.5 xp:50 skills:1
## Practice working with the Oregon Health Experiment
A simulated version of the Oregon Health Insurance Experiment data, `OHIE`, is available in the workspace. This has been divided into two separate dataframes: `treatmentgroup` and `controlgroup` denoting the treatment and control groups, respectively. With this dataframe, determine the following:

*** =instructions
- Create a new data frame called `TreatmentGroup` that contains only treated individuals, and a new data frame called `ControlGroup` that contains only control individuals 
- Test if there is a statistically significant difference in gender between the treament and control groups (i.e. whether gender is balanced between the treatment and control group). 
- Determine if the treatment and control groups have significantly different average values for the following health outcomes: systolic blood pressure (variable `bp_sar_inp`), and diastolic blood pressure (variable `bp_dar_inp`).

*** =hint
- For the first question, you will need to `subset` the `OHIE` data frame by treatment. 
- For each of the following questions, use the `t.test` function where (mu=0) to statistically test whether the treatment and control group are different from each other.


*** =pre_exercise_code
```{r}
set.seed(1)
load(url('http://s3.amazonaws.com/assets.datacamp.com/production/course_1566/datasets/OHIEexperimental.Rda'))
OHIE <- OHIE[!is.na(OHIE$treatment),c("id","treatment","gender_inp","bp_sar_inp","bp_dar_inp")]

```

*** =sample_code
```{r}
str(OHIE) #Dataframe

TreatmentGroup<- # Create a new data frame called `TreatmentGroup` that contains only treated individuals 

ControlGroup<- # Create a new data frame called `ControlGroup` that contains only control individuals 

print(Solution1a<- ) # Test if gender is balanced between the treatment and control groups 

print(Solution1b<-"" ) # Is gender balanced? Answer with "Yes" or "No" 

print(Solution2a<- ) # Test if the treatment had a statistically significant effect on systolic blood pressure 

print(Solution2b<-"" ) # Does the treatment have a statistically significant effect on systolic blood pressure? Answer with "Yes" or "No" 

print(Solution3a<- ) # Test if the treatment had a statistically significant effect on diastolic blood pressure 

print(Solution3b<-"" ) # Does the treatment have a statistically significant effect on diastolic blood pressure? Answer with "Yes" or "No" 

```

*** =solution
```{r}
TreatmentGroup <- OHIE[OHIE$treatment==1, ]
ControlGroup <- OHIE[OHIE$treatment==0, ]
print(Solution1a<- t.test(TreatmentGroup$gender_inp,ControlGroup$gender_inp,mu=0))
print(Solution1b<-"Yes")
print(Solution2a<- t.test(TreatmentGroup$bp_sar_inp,ControlGroup$bp_sar_inp,mu=0))
print(Solution2b<-"No")
print(Solution3a<- t.test(TreatmentGroup$bp_dar_inp,ControlGroup$bp_dar_inp,mu=0))
print(Solution3b<-"Yes")

```


*** =sct
```{r}
test_object("TreatmentGroup")
test_object("ControlGroup")
test_object("Solution1a")
test_object("Solution1b")
test_object("Solution2a")
test_object("Solution2b")
test_object("Solution3a")
test_object("Solution3b")

success_msg("Good work!")
```

--- type:VideoExercise lang:r aspect_ratio:62.5 xp:50 skills:1
## Important Issues in Experiment Design These Modules Ignore
*** =video_link
//player.vimeo.com/video/198212060


--- type:VideoExercise lang:r aspect_ratio:62.5 xp:50 skills:1
## Common Issues in Experiments
*** =video_link
//player.vimeo.com/video/199856354


--- type:MultipleChoiceExercise lang:r xp:50 skills:1
## MC 4
The transportation network company, Unter Technologies, is interested in increasing their revenue. They hypothesize that they would generate substantially greater profits if they lowered their costs and profit margins per each ride. Unter conducts an experiment on how its sales are sensitive to price reductions by offering a 25% off promotion for all of its services for one day. To their pleasant surprise, Unter sees a huge spike in sales and net profit during the promotional day. Seeing the results of his experiment, Unter's CEO decides that Unter should lower its prices permanently. Why might this conclusion be a bit hasty?

*** =instructions
- Unter did not survey its consumers to determine if people were enticed by Unter's lower prices.
- Unter does not have enough data to test the statistical significance of its findings.
- The treatment in Unter's experiment might not have the same effect as the treatment in their policy proposal.
- Unter cars are not very fast.
*** =sct
```{r}
msg1 = "Try again"
msg2 = "Try again"
msg3 = "Correct! Unter's experiment specifically tests the effect of a temporary price reduction in its services, rather than the effect of a permanent price reduction. Sales may have increased during the promotional period, but sales might not have increased quite as much during a longer period of time."
msg4 = "Try again"
test_mc(correct = 3, feedback_msgs = c(msg1,msg2,msg3,msg4))
```

--- type:MultipleChoiceExercise lang:r xp:50 skills:1
## MC 5
Unter's CEO is still convinced that lowering the prices of their services might increase the company's net profits. He is hesitant to lower Unter's prices for a longer period, since the company would risk losing a great deal of income if the price-drop did not substantially increase revenue. Therefore, to experiment how a long-term price drop would effect Unter's profits, the CEO of Unter decides to drop the prices of their services in one city. Over the course of a year, Unter's profits in that city rose substantially. Unter's CEO is now convinced that he should drop Unter's prices nation-wide. Why might this conclusion still be too hasty?

*** =instructions
- Unter's experiment did not pay attention to how its changes affected its competitors.
- The context in Unter's experiment might not generalize to other contexts effected by Unter's policy proposal.
- Unter's experiment did not specify why people might be enticed by lower prices.
- Unter's experiment did not control for noncompliance.
*** =sct
```{r}
msg1 = "Try again"
msg2 = "Correct! Unter's experimental results may have been specific to the city that Unter conducted the experiment in. People from other cities may not be as sensitive to price-reductions as the city in Unter's experiment."
msg3 = "Try again"
msg4 = "Try again"
test_mc(correct = 2, feedback_msgs = c(msg1,msg2,msg3,msg4))
```


--- type:VideoExercise lang:r aspect_ratio:62.5 xp:50 skills:1
## Difficulties in Performing Randomized Experiments
*** =video_link
//player.vimeo.com/video/200052274


--- type:MultipleChoiceExercise lang:r xp:50 skills:1
## MC 6
Which of the following causal questions is possible to answer with a randomized experiment (without major ethical concerns)?

*** =instructions
- The effect of losing one's job on mental health.
- The effect of religion on financial well-being.
- The effect of social isolation on academic performance.
- The effect of economic incentives on athletic performance.
*** =sct
```{r}
msg1 = "Try again"
msg2 = "Try again"
msg3 = "Try again"
msg4 = "Correct! Each other experiment is not only difficult to create, but could cause substantial harm to an experiment's participants."
test_mc(correct = 4, feedback_msgs = c(msg1,msg2,msg3,msg4))
```

--- type:VideoExercise lang:r aspect_ratio:62.5 xp:50 skills:1
## Noncompliance in Experiments
*** =video_link
//player.vimeo.com/video/198212091

--- type:MultipleChoiceExercise lang:r xp:50 skills:1
## MC 7
Which one of the following approaches is *not* an appropriate way to deal with treatment noncompliance?

*** =instructions
- Bounds Analysis
- Instrumental Variables
- Randomized Control Trial
- Intention to Treat Analysis
- Assume Random Compliance
*** =sct
```{r}
msg1 = "Try again"
msg2 = "Try again"
msg3 = "Correct! Randomized Control Trials are not a valid way to correct for noncompliance, because they themselves are suscpetible to treatment noncompliance."
msg4 = "Try again"
msg5 = "Try again"
test_mc(correct = 3, feedback_msgs = c(msg1,msg2,msg3,msg4,msg5))
```

--- type:VideoExercise lang:r aspect_ratio:62.5 xp:50 skills:1
## Survey Noncompliance
*** =video_link
//player.vimeo.com/video/198212102


--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:1557ba9536
## MC 8
CreditCo, a large credit card company, decides to run an experiment. It sends an offer in the mail to a random 50% group of its customers: those in the treatment group are invited to navigate to a webpage to opt in for a 10% higher credit limit. CreditCo wants to see how credit balances and late payments are impacted six months later as a result of the experiment. Suppose that, of the group that received the mail offer, 40% of people opted in. Do you think that noncompliance will be a problem for CreditCo's analysis? Why or why not?

*** =instructions
- No, because people in the treatment group likely decided to opt in based on a coin flip
- Yes, because the opt-in rate is low
- No, because an opt-in rate of 40% is actually quite high
- Yes, because the set of people opting in are probably people with worse spending habits.
*** =sct
```{r}
msg1 = "This is partially correct. A low compliance rate is one symptom of a noncompliance problem."
msg2 = "While this is a possibility, it is unlikely to actually be the case."
msg3 = "While high compliance rates indicate a lower noncompliance problem, the rate of 40% in this situation is likely to be problematic."
msg4 = "Correct! In this situation, researchers at CreditCo should be worried about the spending habits of those who opted in to the offer."
test_mc(correct = 4, feedback_msgs = c(msg1,msg2,msg3,msg4))
```



--- type:NormalExercise lang:r xp:100 skills:1
## Working with non-compliance
Let's continue with the CreditCo dataset described in the previous exercise.

A simulated version of this dataset, `CreditCo`, is available in the workspace.

In this exercise, you will compute the average treatment effect of taking a credit line increase offer on late payments (default).

*** =instructions
- See if treatment and control groups are of equal size
- Compute the fraction of people who opted in to the credit offer
- Compute a naive average treatment effect
- The treatment variable is a column in `CreditCo` called `offered`
- The opt-in variable is a column called `opt_in` 
- The late-payment variable is called `default_post`

*** =hint
- Remember to select the appropriate sample when computing the opt-in rate of the credit offer.


*** =pre_exercise_code
```{r}
  set.seed(1)
  n             <- 9e5
  frac_treated  <- .5
  frac_female   <- .5656
  frac_white    <- .688

# Initialize dataframe
  CreditCo <- as.data.frame(matrix(0, ncol=11,nrow=n))
  colnames(CreditCo) <- c("id","offered","opt_in","FICO","age","female","race_white","default_pre","default_post","balance_pre","balance_post")

# Simulate baseline data
  CreditCo$id         <- seq(1,n,1)
  CreditCo$offered    <- as.integer(runif(n)<frac_treated)
  CreditCo$opt_in     <- rep.int(0,n)
  CreditCo$FICO       <- rnorm(n, mean=736, sd=300)
  CreditCo$age        <- sample(18:55, n, replace=T)
  CreditCo$female     <- as.integer(runif(n)<frac_female)
  CreditCo$race_white <- as.integer(runif(n)<frac_white)

# make FICO score intelligible
  CreditCo$FICO[CreditCo$FICO>850] <- 850
  CreditCo$FICO[CreditCo$FICO<300] <- 300
  CreditCo$FICO                    <- round(CreditCo$FICO)

# simulate pre-experiment default rate
  draw <- runif(n)
  xb   <- -1.82-0.2*CreditCo$FICO/100+.046*(CreditCo$FICO^2)/10000-5.1*CreditCo$female-7*CreditCo$race_white
  p    <- exp(xb)/(1+exp(xb))
  CreditCo$default_pre <- as.integer(draw<p)

# simulate pre-experiment balance level
  draw <- rnorm(n, mean=0, sd=0.5)
  CreditCo$balance_pre <- 8.5-0.2*CreditCo$FICO/100+.046*(CreditCo$FICO^2)/10000-0.15*CreditCo$female-0.85*CreditCo$race_white + draw
  CreditCo$balance_pre <- exp(CreditCo$balance_pre)

# Simulate noncompliance and opt-in behavior
  draw <- runif(sum(CreditCo$offered))
  xb   <- 6.75-1.2*CreditCo$FICO/100+.07*(CreditCo$FICO^2)/10000-2.1*CreditCo$female-2*CreditCo$race_white
  p    <- exp(xb)/(1+exp(xb))
  CreditCo$opt_in[CreditCo$offered==1] <- as.integer(draw<p[CreditCo$offered==1])

# Simulate post outcomes
  draw <- runif(n)
  xb   <- -1.82-0.2*CreditCo$FICO/100+.046*(CreditCo$FICO^2)/10000-5.1*CreditCo$female-7*CreditCo$race_white+4*CreditCo$offered*CreditCo$opt_in
  p    <- exp(xb)/(1+exp(xb))
  CreditCo$default_post <- as.integer(draw<p)

# balance
  draw <- rnorm(n, mean=0, sd=0.5)
  CreditCo$balance_post <- 8.5-0.2*CreditCo$FICO/100+.046*(CreditCo$FICO^2)/10000-0.15*CreditCo$female-0.85*CreditCo$race_white + 1*CreditCo$offered*CreditCo$opt_in + draw
  CreditCo$balance_post <- exp(CreditCo$balance_post)

# Remove elements and variables from environment
  rm(draw,frac_female,frac_treated,frac_white,n,p,xb)
  CreditCo <- CreditCo[,c("id","offered","opt_in","FICO","female","race_white","default_pre","default_post","balance_pre","balance_post")]
```

*** =sample_code
```{r}
# The dataset `CreditCo` is available in your workspace

print(Solution1<- )# Compute the fraction of people who were offered a higher credit limit

print(Solution2<- )# Of the people who were offered, what fraction opted in?

print(Solution3<- )# Compute a naive average treatment effect of late payment (variable `default_post`), where treatment state is defined by having been offered and opted in to the program

```

*** =solution
```{r}
Solution1<-mean(CreditCo$offered)
Solution2<-mean(CreditCo$opt_in[CreditCo$offered==1])
Solution3<-mean(CreditCo$default_post[CreditCo$opt_in==1])-mean(CreditCo$default_post[CreditCo$offered==0])
```

*** =sct
```{r}
test_object("Solution1")
test_object("Solution2")
test_object("Solution3")
```

--- type:VideoExercise lang:r aspect_ratio:62.5 xp:50 skills:1
## Bounds Analysis for Missing Data
*** =video_link
//player.vimeo.com/video/199858153


--- type:NormalExercise lang:r xp:100 skills:1 key:a42175703d
## Computing bounds under non-compliance
Continuing with the dataset from the previous exercise, you will now compute the bounds of average treatment effect of opting into a credit line increase offer.

*** =instructions
- Compute bounds on the average treatment effect under non-compliant behavior, and compare with other methods of correcting for non-compliance.

*** =hint
- Remember to be aware of selecting the correct subsample

*** =pre_exercise_code
```{r}
  set.seed(1)
  n             <- 9e5
  frac_treated  <- .5
  frac_female   <- .5656
  frac_white    <- .688

# Initialize dataframe
  CreditCo <- as.data.frame(matrix(0, ncol=11,nrow=n))
  colnames(CreditCo) <- c("id","offered","opt_in","FICO","age","female","race_white","default_pre","default_post","balance_pre","balance_post")

# Simulate baseline data
  CreditCo$id         <- seq(1,n,1)
  CreditCo$offered    <- as.integer(runif(n)<frac_treated)
  CreditCo$opt_in     <- rep.int(0,n)
  CreditCo$FICO       <- rnorm(n, mean=736, sd=300)
  CreditCo$age        <- sample(18:55, n, replace=T)
  CreditCo$female     <- as.integer(runif(n)<frac_female)
  CreditCo$race_white <- as.integer(runif(n)<frac_white)

# make FICO score intelligible
  CreditCo$FICO[CreditCo$FICO>850] <- 850
  CreditCo$FICO[CreditCo$FICO<300] <- 300
  CreditCo$FICO                    <- round(CreditCo$FICO)

# simulate pre-experiment default rate
  draw <- runif(n)
  xb   <- -1.82-0.2*CreditCo$FICO/100+.046*(CreditCo$FICO^2)/10000-5.1*CreditCo$female-7*CreditCo$race_white
  p    <- exp(xb)/(1+exp(xb))
  CreditCo$default_pre <- as.integer(draw<p)

# simulate pre-experiment balance level
  draw <- rnorm(n, mean=0, sd=0.5)
  CreditCo$balance_pre <- 8.5-0.2*CreditCo$FICO/100+.046*(CreditCo$FICO^2)/10000-0.15*CreditCo$female-0.85*CreditCo$race_white + draw
  CreditCo$balance_pre <- exp(CreditCo$balance_pre)

# Simulate noncompliance and opt-in behavior
  draw <- runif(sum(CreditCo$offered))
  xb   <- 6.75-1.2*CreditCo$FICO/100+.07*(CreditCo$FICO^2)/10000-2.1*CreditCo$female-2*CreditCo$race_white
  p    <- exp(xb)/(1+exp(xb))
  CreditCo$opt_in[CreditCo$offered==1] <- as.integer(draw<p[CreditCo$offered==1])

# Simulate post outcomes
  draw <- runif(n)
  xb   <- -1.82-0.2*CreditCo$FICO/100+.046*(CreditCo$FICO^2)/10000-5.1*CreditCo$female-7*CreditCo$race_white+4*CreditCo$offered*CreditCo$opt_in
  p    <- exp(xb)/(1+exp(xb))
  CreditCo$default_post <- as.integer(draw<p)

# balance
  draw <- rnorm(n, mean=0, sd=0.5)
  CreditCo$balance_post <- 8.5-0.2*CreditCo$FICO/100+.046*(CreditCo$FICO^2)/10000-0.15*CreditCo$female-0.85*CreditCo$race_white + 1*CreditCo$offered*CreditCo$opt_in + draw
  CreditCo$balance_post <- exp(CreditCo$balance_post)

# Remove elements and variables from environment
  rm(draw,frac_female,frac_treated,frac_white,n,p,xb)
  CreditCo <- CreditCo[,c("id","offered","opt_in","FICO","female","race_white","default_pre","default_post","balance_pre","balance_post")]
```

*** =sample_code
```{r}
# The dataset `CreditCo` is available in your workspace

print(Solution1<- )# Determine the fraction of opt-in among those offered the increase

print(Solution2<- )# Calculate the upper bound of the ATE by assuming that all non-opt-in customers have a late payment, and subtract the non-offered average from this value

print(Solution3<- )# Calculate the lower bound of the ATE by assuming that all non-opt-in customers don't have a late payment, and subtract the non-offered average from this value

```

*** =solution
```{r}
Solution1 <- mean(CreditCo$opt_in[CreditCo$offered==1])
Solution2 <- Solution1*mean(CreditCo$default_post[CreditCo$opt_in==1]) + (1-Solution1)*1 - mean(CreditCo$default_post[CreditCo$offered==0])
Solution3 <- Solution1*mean(CreditCo$default_post[CreditCo$opt_in==1]) + (1-Solution1)*0 - mean(CreditCo$default_post[CreditCo$offered==0])

```

*** =sct
```{r}
test_object("Solution1")
test_object("Solution2")
test_object("Solution3")
```


















