Hey guys! Here's what I need you all to do this week. Since the project isn't parallizable yet, you'll all be doing the same tasks, so try not to collaborate with others while doing these tasks. Learning via google, stackexchange, and package documentation is a vital part of winning kaggle. 

**1. Run the pipeline and make your first submission.**  
Observe your local validation score, and the actual test set score from kaggle. Our team only gets 5 submissions per day so please don't spam submission files. However, it's important nonetheless to actually do it at least once. Note the validation accuracy, write it down somewhere.

**2. I'll need you all to do the following cleaning tasks to both the training and test sets:**
* Embarked has 2 missing values. Fill them with "S", since "S" is the most common.

**3. I'll need you all to do the following feature engineering tasks for both train and test sets:**
* Engineer a new feature column called "age_binned". In this feature, bin the age feature into 5 buckets: age <= 16, 16 < age <= 32, 32 < age <= 48, 48 < age <= 65, 64 < age. 
* Make a new feature called "family_size, which is the sum of sibsp+parch
* Make a new feature called "is_alone", which is 1 if sibsp+parch=0, and 0 otherwise. 
* Use the **sklearn** label encoder on embarked column to change the values from letters to numbers ("S"->0, "C"->1, "Q"->2,as an example mapping). Use this mapping to overwrite the current "embarked column".
* Drop all the columns except for Survived, pclass, sex, age_binned, fam_size, is_alone, embarked. Use these all as features, except Survived which is the target.
* One-hot encode both datasets for all variables except for fam_size.

**4. I'll need you to do the following modelling tasks:**
* Use our new features, rerun the pipeline, note the new val score.
* Upgrade our classifier to a random forest classifier, using the example as a guide. Note the new val score. Submit again and see where we end up on the leaderboard.  
**Optional task if you have time left:**
* Upgrade our classifier to a LightGBM classifier. This is going to be the most time-consuming part of the project; however, it's important since LightGBM is now by far the most common, so it pays to understand how to use it so that you can read other people's implementations. Keep in mind for lightGBM that you have to declare categoricals explicitly, and need to feed it label-encoded rather than one-hot encoded data. Use this example [here](https://github.com/Microsoft/LightGBM/blob/master/examples/python-guide/simple_example.py) to start, but make sure you change the objective, and metric to something suitable for classification. Also, add a list of column indices of categorical variables in the params list (e.g. categorical_variable=[0,1,2]).
