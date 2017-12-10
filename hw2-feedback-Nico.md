### ***Project 2 Feedback***

***Nico Van de Bovenkamp***

***

**Overall:** Great job on this homework! You are clearly getting more comfortable with Pandas/Python. Also, good work looking into the interpolate function! You wrote a very clear analysis plan, and detailed a lot of information about your distributions. When we go into the next homework, if you feel you are fairly comfortable with the logistic regression that we use, then try tweaking the model a bit. We will cover more modeling soon, so you can try out some regularization, non-linear models, etc.! 


**Some Notes**

* We haven't covered the specifics quite yet, but we won't be using a linear _regression_ model in this example. We will be using a linear model, but it will be a logistic regression, which is a classification technique. Remember that a regression model _usually_ refers to a model that is learning a continuous variable (income, temperature, whatever!) whereas a classification model refers to predicting classes, like our admission (yes or no!).

**Something to think about**  
Dropping missing values can be necessary at times. In cases where you you have a lot of missing values, you might have to just drop those rows *or* ignore that feature all together (forget that column, we can't use it). However, as we proceed, you will find that data is gold to these algorithms. Very often, the more data you have, the more information you are giving to your model so it can generalize even better. To ensure we retain as much data as we can, a common practice is to fill missing values with the mean or median or mode so that you can keep those instances, without disturbing your distribution too much. As I mentioned above, great work with the interpolation function! This could be something to experiment with. You could try using this and then modeling. Then, you could try just imputing the median/mean. Maybe one will give better results than the other.

Check out these guides:
https://machinelearningmastery.com/handle-missing-data-python/
https://chrisalbon.com/python/pandas_missing_data.html
