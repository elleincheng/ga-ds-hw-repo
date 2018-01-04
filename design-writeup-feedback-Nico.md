### ***Design Write-up Feedback***

***Nico Van de Bovenkamp***

***

Awesome work! This is a great start to your project, and you have outlined an effective path to build your model!

***Dealing with missing values***  
There are a lot of missing or un-reported values in this dataset. You will have to choose which features you will/can use as a function of how much data you actually have. One thing to consider, as we showed in the second homework, is how you will deal with those instances of missing values. Will you drop them, impute mean/mode, will you use another more engineered technique? My advise is to start simple and build the best model you can with dropped values, and move on form there to test for improvement.

***Plotting distributions***  
Numbers and summary statistics are important, but plotting really helps you understand what your data looks like. There are tons of ways you can plot your data to help you understand it's shape, what transforms you might want to use, and what variables look interesting! As I mentioned on slack, with many binary/boolean variables, you would just be graphing proportions or counts of each indicator. You can also do hue'ed counts. In other words, you could do "means of control counts" by "age" or something of this sort. Let me know if you have any further questions!

***Scope of your data***  
Scope is definitely a significant problem in this context. There are tons unknown cases, and it ensures that your model will be slightly limited. However, this does not mean your model is meaningless. It may not be totally representative, but it will give you some insight as long as you are interpreting those results within the bounds of limited data.
