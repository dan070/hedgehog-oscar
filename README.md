# hedgehog-oscar
Online ML inspired by Vorpal Rabbit

Logistic regression is one of the most loved ML tools, with good reason. This project honors this invention from the 1830s(!) with a Oscar Wilde-quote.

> The world is divided into two classes, those who believe the incredible, and those who do the improbable.
>
> **Oscar Wilde**


I will also keep it simple. Do one thing good.

> A fox knows many things, but a hedgehog one important thing
>
> **Old Greek proverb**


> I never meant it very seriously. I meant it as a kind of enjoyable intellectual game, but it was taken seriously. Every classification throws light on something
>
> **Isaiah Berlin**


Anomaly detection of feature variables, drift
Simple mean variance model. If enough points and average differs too much, it’s anomaly.
Several kernels, to allow for more varied distribution.
Detect distribution.
Estimate covariance of pair variables, and test for significant change.
Make baseline when 1000 points detected and no significant changes happen. Keep it to 4 significant digits. Estimate range from initial samples.
User-set behaviour when anomaly, stop learning, send warning, carry on.

Automatic expansion of new factor variable.
If added, a new variable is created and training starts.

Detection of changed parameter values
Simple change of 10%
Tests of significance for change

Detection of changed predictions for a random selection of training examples.
Save examples and replay every 1000 obs, and compare prediction. Average pct change in prediction.

Set learning rate automatically
Set learning rate manually 
Use one or two standard rate finders


Get printout of parameters anytime
•Get prediction, even with missing data
Choose cutoff value, to go along with probability.
Allow user to get prediction from old versions as well.
Always have a median value prepared. We could also bootstrap missing values and average the resulting predictions.


Logistic regression in first version
Specify target variable, what values are considered target class.
Allow dynamic addition of features, where you set as class or numeric.
First iteration ; only numeric values. Then 1/0. Then string.
Maybe treat all nonstring as numeric and all string as classes? 
Any change or inconsistencies input data results in error.

Stop learning and estimate cutoff
Allow user to give cost of missclassified targets
Predict input data and compare to target, and build up a roc curve. From cost of missclass, choose optimal cutoff. Save cutoff continuously.
Give ROC on demand. Show confusion matrix for best cutoff.

Just stop learning (eg if feature drift)

• Rollback to previous versions
• Prediction from previous version
Version handling of models, to allow rollback
Eg when sufficiently converged. Or if drift screwed us up.
Allow saving of models with a time stamp and name/comment.
If prediction gets a version name, use that instead of current prediction.


Allow user to specify online or batch 
Use data as microbatch and online, what works best
Being able to store training data and replay it both for training and for prediction.
Allow user to set n=1 to n=quite high, for online or batch learning.


Prediction must be lightning fast.
Lookup of parameter.
Adding up parameter.
Using missing value parameter.
Unlogit and apply cut off.

Should try it in R first.
Go is fast but I need to verify behaviour.
How do I unit test the stuff?
We are talking Webb rest api. Or other?


https://www.internalpointers.com/post/cost-function-logistic-regression

https://arxiv.org/pdf/1704.04289.pdf

https://ml-cheatsheet.readthedocs.io/en/latest/gradient_descent.html

http://doingbayesiandataanalysis.blogspot.com/2014/08/how-to-use-mcmc-posterior-as-prior-for.html?m=1

https://link.medium.com/ZXR9Gd0JlX

https://github.com/jasoncapehart/go-sgd/blob/master/sgd.go
