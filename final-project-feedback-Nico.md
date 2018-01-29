### ***Final Project Feedback***

***Nico Van de Bovenkamp***

***

**Overall**  
Awesome, awesome job on this assignment! You put in a ton of work into this project, and burned through lots of data, and lots of code. Seeing as you are interested in continuing this work past class, I am sure you found this very insightful and helpful.

There is only a little bit of work left to be done, and then it's model building time! I have laid out some recommendations below:

**Recommendations**  

***For Loops and Simplifying code***  
Lots of code could be simplified a bit. I recall you saying you were doing a lot of work in Excel and then recoding it in python, which can lead to some lengthy code. While it takes a bit of practice and time to test yourself, and see other people's code, thinking through things the pythonic way can save some time. For example, when you see patterns of a recurring task, maybe take a step back and see what you could simplify. For example, in all of the replacement code for -99, you could have done something like this:

```python
laborTypeColumns =  [col for col in GD_data.columns if "typeOfLabour" in col]
for type in laborTypeColumns:
    GD_data[type].replace(-99,0,inplace=True)
```

That's a good bit less code, with the same result! Though list comprehensions of this sort are a bit more advanced, they make a good bit of sense! Additionally, you could wrap that in a function and input a string you want it to contain, and/or a value you want to fill it with instead of 0, and you could have a function that would work on all of these columns with even less code to replicate! (Just like you did with your apply functions).

***Filling in missing values***  
As we discussed previously, be careful when you are imputing missing values (-99) into your dataset. When you are taking the value that is missing, -99, and replacing it with 0, you are hardcoding some level of biased information into your model. Now, you are specifically encoding into your model that each one of these individuals did NOT experience this type of labor, means of control, etc. when in fact, we simply don't know! This can be a concerning if you are imputing untruthful information. Our goal is to build a model that describes the universe of whatever domain we are working in. In this case, then, you are forcing your model to believe a world in which each person, described with the data you do have, is also described by the data you are putting in (those 0s that indicate each person did NOT experience [blank]).

***One Hot Encoding***  
Though it's not a problem for all models, watch out for multi-colinearity encoded in your data! When you are making dummy variables you not only want to encode them, but we "One Hot" them such that we drop one. All the same information is in there (if male = 1, then we know that implicitly male = 0 means female). If you don't drop one, then you will alter your coefficients learned because there is now a direct relationship between your variables (when male is 1, female is certainly 0).

***Plots***  
You're definitely right! You want to plot out some of these variables. Digging through those groupbys, counts, and odds ratios is very, very helpful, but sometimes you get dramatically more insight just by seeing your data! Pick some of the most interesting, or key findings, and then make some plots of those.


***Modeling***  
Now that you have a feature set, and you have manipulated all of your data, it's time to model! Take all that encoded data and start building some models. As we discussed that one office hours long ago, take some basic models and start iterating based on some set validation metric (percision, recall, roc_auc, f1 score, etc.)

***And don't forget that train/test split, cross-validation, and grid-search!***
