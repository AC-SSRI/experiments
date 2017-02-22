  ---
  title       : Experiments 4: Statistical Inference in Experiments
  description : These videos and exercises will help you understand why we need statistical inference in experiments
  attachments :
  video_link :


--- type:VideoExercise lang:r aspect_ratio:62.5 xp:50 skills:1 key:42e831dde4
## What is the Point of Statistical Inference?
*** =video_link
//player.vimeo.com/video/198212067

--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:6ae426b824
## Multiple Choice: Statistical inference
Under which scenario might an experimenter *not* need to use statistical inference to justify his causal claims?

*** =instructions
- When his causal claim is logically sound.
- When his sample is large.
- When his experiment is well-designed.
- When he can have his entire population of interest participate in the experiment.
*** =sct
```{r}
msg1 = "Even if it makes sense, an argument without data isn't science, so it's not enough to avoid using statistical inference. Try again"
msg2 = "Even with a large sample, you still need to use statistical measures to verify the experiment's validity, so try again"
msg3 = "Even with a well-designed experiment, you still will have just a sample of the possible data to look at, so that's not quite right. Try again"
msg4 = "Correct! The purpose of statistical inference in randomized experiments is to help researchers make valid propositions about a population given a sample. This is unnecessary if the entire population of interest participates in the experiment."
test_mc(correct = 4, feedback_msgs = c(msg1,msg2,msg3,msg4))
```
--- type:VideoExercise lang:r aspect_ratio:62.5 xp:50 skills:1 key:76542ba835
## p values, Confidence Intervals, and Hypothesis Tests
*** =video_link
//player.vimeo.com/video/205124286

--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:d2fc3d44de
## Multiple Choice: Sample size
A professor was interested in whether myopia in children could be caused by environmental factors. He found a completely random sample of 10 children, and had 5 of them sleep with nightlights and 5 of them sleep without nightlights for the first 10 years of their lives. 

All of the children who had slept with nightlights developed myopia, whereas only 2 of the children who did not sleep with nightlights developed myopia. From this study, the professor determined that the average treatment effect of using a nightlight on myopia was 5/5 - 2/5 = 3/5, or 60%. Why might the professor want to get a larger sample before publishing these results?

*** =instructions
- To please his reviewers.
- To control for non-compliance.
- To make sure that the observed average treatment effect did not occur by chance.
- To control for confounding variables.

*** =sct
```{r}
msg1 = "While this might feel like the most immediate reason, what other reason do you think his reviewers mentioned? Try again"
msg2 = "Noncompliance isn't mentioned as an issue in this case, so it's not the key issue we're looking for. Try again"
msg3 = "Correct! Even when we draw from a completely random sample, there is always the chance that our sample is not representative of the whole population. The larger the sample size that we draw from, the less likely that our findings were to have occurred by chance."
msg4 = "Confounders are always an issue, particularly when looking at real world data, but that's not quite the best reason to get a larger sample in this case. Try again"
test_mc(correct = 3, feedback_msgs = c(msg1,msg2,msg3,msg4))
```
--- type:VideoExercise lang:r aspect_ratio:62.5 xp:50 skills:1 key:7b5a9a2cb6
## Randomized Controlled Trials
*** =video_link
//player.vimeo.com/video/198212064

--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:7eab53249a
## Multiple Choice: Experiments vs. RCTs
How are the results from randomized control trials interpreted differently than randomized experiments?

*** =instructions
- They are not interpreted differently from randomized experiments.
- They have real-world implications.
- They do not need to be tested for statistical significance.
- They should be estimated with conditional average treatment effects.

*** =sct
```{r}
msg1 = "Correct! A randomized control trial is a type of randomized experiment."
msg2 = "RCTs are not the only things with real-world implications, so try again"
msg3 = "RCTs must be analyzed using statistical methods as much as any experiment, so try again"
msg4 = "You can use all kinds of tools with RCTs, not just CATEs, so look again for a better answer"
test_mc(correct = 1, feedback_msgs = c(msg1,msg2,msg3,msg4))
```