### ***Project 3 Feedback***

***Nico Van de Bovenkamp***

***

**Overall**
Great work on this assignment! As I said, you are definitely on track here. You interpreted your results well, have been studying up on the material, and built a baseline model. I'm sure after more studying and the Kaggle competition, you can see how you might try out some different models and feature generation techniques. Try out all the techniques!

***Odd predictions***  
As I mentioned during our Office Hours session, I think that when you call `result.predict()` on the old result object, you are using the first model you fit. The first model you fit had a different shape with intercept at the end, while the later one you are inputing has a different order of columns. This means that your predicted values are actually going to be corresponding to the wrong coefficients! (ie. garbage in, garbage out!). Try re-fitting the model to change the predictions.

***A note on Odds Ratios***  
**I wrote this note on odds ratios to a couple other students, but here is the written feedback**
In this case, the odds ratios are calculated based on the conditional probability of P(admit=1 | prestige_1) and
P(admit=0 | prestige_1). In other words, you take good outcome, given exposed, over good outcome, given not exposed. And then you take this odds and take the ratio over bad outcome, given exposed, over bad outcome, given not exposed. Here, admission=1 is the good outcome and prestige is the thing we are testing for! If you are then given the matrix of outcomes of:  
```python
pd.crosstab(handCalc['admit'], handCalc['prestige_1.0'], rownames=['admit'])
```
#### Admission table:

| prestige_1        |  0            | 1     |
| -------------     |:-------------:| -----:|
| admit             |               |       |
| 0                 |   243         |  28   |
| 1                 |   93          |  33   |

Then the calculation is as follows:  
Odds(admitted | prestige_1) = 33/28 = 1.179  
Odds(admitted | not prestige_1) = 94/245 = 0.384      
OddsRatio = 1.179/0.384 = 3.07

Thus, the interpretation of this is that students that attended a prestige_1 school are 3 times as likely to be admitted to grad school! Note that this is _not_ a percentage, but an interpretation of relative likelihood **given** some probability, or percentage. Odds ratios are handy for some level of data exploration, and, of course, when it comes to interpreting log odds coefficients. A minor note, but instructive nonetheless. Logistic regression coefficients are not always super informative, and, for the most part, you are often much more concerned with the performance of a model!
