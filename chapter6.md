  ---
  title       : Experiments 6: Common Issues in Experiments
  description : These videos and exercises will discuss common issues in carrying out experiments
  attachments :
  video_link :


--- type:VideoExercise lang:r aspect_ratio:62.5 xp:50 skills:1 key:ef7f2e2846
## Important Issues in Experiment Design These Modules Ignore
*** =video_link
//player.vimeo.com/video/198212060


--- type:VideoExercise lang:r aspect_ratio:62.5 xp:50 skills:1 key:5f5a6d0023
## Common Issues in Experiments
*** =video_link
//player.vimeo.com/video/199856354


--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:e302f4bddd
## Multiple Choice: Drawing conclusions from experiments
The transportation network company, Unter Technologies, is interested in increasing their revenue. They hypothesize that they would generate substantially greater profits if they lowered their costs and profit margins per each ride. 

Unter conducts an experiment on how its sales are sensitive to price reductions by offering a 25% discount for all of its services for one day. To their pleasant surprise, Unter sees a huge spike in sales and profits during the promotional day. 

Seeing the results of his experiment, Unter's CEO decides that Unter should lower its prices permanently. Why might this conclusion be a bit hasty?

*** =instructions
- Unter did not survey its customers to determine if they were enticed by Unter's lower prices.
- Unter does not have enough data to test the statistical significance of its findings.
- The treatment in Unter's experiment might not have the same effect as the treatment in their policy proposal.
- Unter's experiment didn't address the strategic responses of its competitors.
*** =sct
```{r}
msg1 = "Doing additional research to learn The Why behind a behavioral change can be helpful, but there's an experiment design issue to address first. Try again"
msg2 = "This question doesn't say how much data Unter used, but there's another experiment design issue to consider, so try again"
msg3 = "Correct! Unter's experiment specifically tests the effect on profits of a temporary price reduction in its services, rather than the effect of a permanent price reduction. Profits increased during the promotional period, but there is no evidence that profits would remain higher over a longer period of time."
msg4 = "While Unter's profits are a function of its competitors' behavior, there is another experiment design issue that is more appropriate. Try again"
test_mc(correct = 3, feedback_msgs = c(msg1,msg2,msg3,msg4))
```

--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:fa050e19b1
## Multiple Choice: Generalizing experimental results
Unter's CEO is still convinced that lowering the prices of their services might increase the company's profits. He is hesitant to lower Unter's prices for a longer period, since the company would risk losing a great deal of income if the price-drop did not substantially increase revenue. 

Therefore, to understand how a long-term price drop would affect Unter's profits, the CEO of Unter decides to drop the prices of their services in one city. Over the course of a year, Unter's profits in that city rose substantially. Unter's CEO is now convinced that he should drop Unter's prices nation-wide. Why might this conclusion still be too hasty?

*** =instructions
- Unter's experiment did not pay attention to how its changes affected its competitors.
- The context in Unter's experiment might not generalize to other contexts affected by Unter's policy proposal.
- Unter's experiment did not specify why people might be enticed by lower prices.
- Unter's experiment did not control for noncompliance.
*** =sct
```{r}
msg1 = "The company probably does exist in a complex market, but there's something else to worry about without that consideration. Try again"
msg2 = "Correct! Unter's experimental results may have been specific to the city that Unter conducted the experiment in. People from other cities may not be as sensitive to price-reductions as the city in Unter's experiment."
msg3 = "Doing some qualitative research to learn The Why behind a behavior change can be helpful, but there's an experiment design issue to address first. Try again"
msg4 = "The question assumes the CEO can successfully set prices in his own company, so if that's true, what other answer might still be a design issue we need to worry about?"
test_mc(correct = 2, feedback_msgs = c(msg1,msg2,msg3,msg4))
```

--- type:VideoExercise lang:r aspect_ratio:62.5 xp:50 skills:1 key:0f5e7a1e15
## Difficulties in Performing Randomized Experiments
*** =video_link
//player.vimeo.com/video/200052274


--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:7c1f83a32b
## Multiple Choice: Ethics in experiments
Which of the following causal questions is possible to answer with a randomized experiment (without major ethical concerns)?

*** =instructions
- The effect of losing one's job on mental health.
- The effect of religion on financial well-being.
- The effect of social isolation on academic performance.
- The effect of financial incentives on athletic performance.
*** =sct
```{r}
msg1 = "This would definitely cause major ethical concerns because randomly assigning people to lose their job is not allowed.Try again"
msg2 = "This is a very personal topic to many people, and likely to involve big ethical concerns, so try again"
msg3 = "Randomly assigning people to social isolation is incredibly unethical, so look for a better answer!"
msg4 = "Correct! Each of the other experiments is not only difficult to create, but could cause substantial harm to an experiment's participants."
test_mc(correct = 4, feedback_msgs = c(msg1,msg2,msg3,msg4))
```