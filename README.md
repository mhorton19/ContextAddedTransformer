# ContextAddedTransformer

In this project, I am attempting to improve the training speed of transformers by predicting the output of the self-attention operation and subtracting that from the calculated attention output before normalizing.  This is meant to address the following potential issue in transformer training:

A key and a value will be highly predictive of one another since they are projections of the same vector.  Therefore, a query should be highly predictive of the value vector of its corresponding attention output.  We can potentially magnify gradients to keys and queries by removing the predictable portion of the attention output then re-normalizing. 
