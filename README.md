# HyperParamTuning

# Purpose
​
The purpose of this notebook is to compare the RMSE score from two different hyperparameter tuning methods; RandomizedSearchCV and BayesSearchCV.<br>
The Summary section shows a summary of the results.<br>
​
 * BayesSearchCV is an intelligent hyperparameter tuning search that can identify regions of a search space that will return hyperparameters that produce better scores.
 * RandomizedSearchCV is a non-intelligent (it does not learn from prior hyperparams tested) hyperparameter tuning search that tries random hyperparameters based on the distributions given.
 
In the Summary section the following observations were noted:
 * RandomizedSearchCV is faster in all cases due to parallel computing.  BayesSearchCV is mostly sequential processing due to the nature of the algorithmn.
 * RandomizedSearchCV performs poorly with lower iterations whereas BaysSearchCV performs much better.
 * RandomizedSearchCV after a certain number of iterations does not seem to produce much imporvements whereas BayesSearchCV improves greatly which makes sense given its nature of optimizations.
 * After a given threashold (50 iterstions), RandomizedSearchCV produced the better scores up until 200 iterations where BayesSearchCV produced better scores (not by much, however). 
​
Surprisingly, RandomizedSearchCV performed rather well for being an non-intelligent search method.  In most cases RandomizedSearchCV produced the best scores while taking less time to execute its task.<br>
There is a balance with hyperparameter tuning that requires the user to consider their cost budget when it comes to time and computing resources.<br>
Based off the results form this experiment, RandomizedSearchCV produces satisfactory while producing those results with quicker execution time.<br>
​
Some notes:  The seed was changed for each change in the number of iterations.  There was a situation where RandomizedSearchCV was producing the best score regardless of the iteration number and this was due to chance that the best hyperparameters were randomly selected early in the iterations.  A better test would remove the seed/random_state to inject pure randomness and test each iteration level several times to create a distribution of scores for each iteration level.  However, that would be rather resource intensive.  Also, this test did not set out to conduct extensive feature engineering or feature selection.  It is quite possible that impacted the results.  However, both RandomizedSearchCV and BayesSearchCV scores were generally in the same ballpark.
