Hey guys! Here's a guide for each experiment this week. I'll be giving some high level instructions for how to tackle each experiment, but the implementation is up to you. If you think there's a better way to achieve your experiment goals than what I've suggested, then by all means, go for it!
### Experiment 1: Use title as proxy to determine missing age values, and add title as a feature
We fill our missing ages with mean, but it might be better if we use title to guess the missing age values. Also, title might be a useful feature. Here's how I would tackle this:
* We'll mainly be dealing with the "name" column, so the first thing I'd do is isolate the title. A name might be "Mr Mitch Mathieu", so you would want to truncate it to only include the first word. Apply some operation to the "name" column to create a new column named "title", which only includes the first word in name. str.split will help you here.
* Now that you have the title, from the EDA we know that there are common titles (Mr, Ms, etc.) and some rare ones. We'd want to change all the rare titles to something like 'misc'. To do that, use pd.value_counts() to find which titles appear less than say, 10 times. This will give you a df which lists each title, and gives them a value of TRUE if rare and FALSE if not rare. Save this as rare_names or something.
* Then, apply a function to the dataset to change all the rare names to misc. Something that might work for that is `df['Title'] = df['Title'].apply(lambda x: 'misc' if rare_names.loc[x] == True else x`. Basically, this just goes through all the titles and checks if they're TRUE in the rare_names df. If they are, then the function changes that value to "misc".
* Do a groupby on titles to find the mean age for each title (including misc)
* For each missing age, fill in the mean age for the corresponding title. 
* Rerun pipeline with the new "title" feature and newly filled age values. Note CV score, submit.

### Experiment 2: Throw basic ML models against a wall, tune, see what works
* Usually something heavy like LightGBM would be our model of choice, but this is a really small dataset so we would want to try out some basic models. 
* Implement at least the following sklearn models: decision tree, support vector machine classifier (SVC), K nearest neighbors, extra trees, gaussian naive bayes. In addition, feel free to try whatever catches your fancy. Note all their CV scores. Would recommend making some function to run all the models so you don't have to run each one manually.
* Tune model hyperparameters. Focus on decision trees and SVC's first, and do the rest if you have time. Use either sklearn gridsearch or randomsearch for this. You can search for typical parameter grids online; a grid is a set of hyperparameters that the computer will try.

### Experiment 3: Implement LightGBM
* See week 2 action items, use the example for guidance. Try it first with default hyperparameters, and then DM me and I'll give you some better sets of hyperparameters to try. If you have time, also try XGBoost. It's unlikely that this experiment will boost score, but knowing how to use LightGBM is a vital skill in the future.

### Experiment 4: Implement a NN
* Neural nets tend to ensemble well with our tree based models since they tend to be super different. So try to add a NN model to our current pipeline.
* How you do this is mostly up to you. You can use Keras or PyTorch; I'm personally more familiar with torch so I might be able to help you more in that regard, but the rest of QMIND seems to love keras for some reason. Doesn't matter too much either way though since they're pretty similar for basic neural nets.
* Recommend you do a basic feed-forward neural net (can be done with "Sequential" classes in either keras or pytorch.nn). My recommendation is to first try out using one hidden layer with tanh activation and 10-20 nodes, and an output layer with sigmoid activation. Use binary cross entropy loss, and accuracy as a metric. Inputs are our current features.