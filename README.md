# Movie poster classification

## Validation data

Split the code into 60/20/20 train/validation/testing data. In the trainig loop, test the model on each epoch on the validation data, including the per-epoch average loss.

## Model improvement

Make incremental alterations to the model until you see the model converge faster to a lower loss. You can look at other people's online solutions, but you can't directly copy them -- the point is to experiment repeatedly with variations on the model in the notebook until you find a change that starts to improve the model and causes convergence earlier than the model in the original notebook.

Using only the training and validation data for the model improvement.

## Evaluation objective

Manually implement the Jaccard index. Print the Jaccard index along with the binary cross-entropy loss in both the validation part of the training loop as well as the testing procedure. Evaluate any interesting variants of your models on the testing data as a final step.

## Report

The report is written in the Jupyter notebook.
