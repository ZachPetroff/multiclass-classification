# multiclass-classification
Multi-class classification using Sklearn and Pytorch

# Data Preprocessing

	Thankfully, there was not much data preprocessing required. There were no missing values, thus data imputation/deletion was not required. Moreover, the continuous values seemed to already be normalized between 0 and 1. The only data preprocessing that was required was one-hot encoding the color and type columns. I did this by using the pandas get_dummies method.

# Model Building and Fine-Tuning

	I tried many different model’s for this task: SVC, Nearest Neighbors, Random Forest, and a basic feed forward neural network. Initially, I used sklearn to implement SVC, Nearest Neighbors, and Random Forest, using cross-validation to evaluate each model. I found that Random Forest outperformed SVC and Nearest Neighbors by a large margin (about a 35% accuracy difference. Thus, I attempted to fine tune the Random Forest algorithm by itself. I tried to find the optimal values for the number of estimators (50, 100, 250, 500), maximum depths (1, 2, 3), and the cutoff criteria (gini or entropy). After doing this, I realized both of the two highest scores had a max depth of 3, so I increased the search range for max depth. I found the best pairing of parameters was a max depth of 4, 50 estimators, paired with the ‘gini’ criterion. I then tried to build a neural network using Pytorch. I ended up creating two neural networks with similar accuracies to the Random Forest algorithm, in an attempt to build a voting classifier. However, when I saved the file, the model accuracies were very different from what I found while training the model. For some reason, the training of the neural network was very unreliable and the performance varied dramatically. Thus, I ended up only using a Random Forest Classifier, with a validation accuracy of around 71%.
