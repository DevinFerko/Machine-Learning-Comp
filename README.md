# Machine-Learning-Comp

## Built Using :
<div>
  <img src="https://github.com/devicons/devicon/blob/master/icons/python/python-original.svg" title="Python" alt="Python" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/pandas/pandas-original.svg" title="pandas" alt="pandas" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/numpy/numpy-original.svg" title="numpy" alt="numpy" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/tensorflow/tensorflow-original.svg" title="tf" alt="tf" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/jupyter/jupyter-original.svg" title="jupyter" alt="jupyter" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/git/git-original.svg" title="Git" alt="Git" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/github/github-original.svg" title="Github" alt="Github" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/vscode/vscode-original.svg" title="vscode" alt="vscode" width="40" height="40"/>&nbsp;
</div>

This repository contains comparisons between out-of-the-box machine learning algorithms. We will be using the following datasets for this project:

- MNIST: a dataset of handwritten digits
- Wine Quality: a dataset comparing the qualities of several wines
- Housing prices: a dataset with a list of housing features and their respective prices 

## MNIST Dataset

This was the first dataset I applied the models to. This dataset contains a series of handwritten digits with labels identifying each. After training the models and tracking their accuracy scores I found that the SVC (support vector classifier) model performed most accurately of all the models. This would make sense as SVC is a classifier-type model typically used for classification in supervised machine-learning scenarios. 

### Accuracy of Models against the MNIST Datasets

![Models' accuracy on test data (MNIST)](https://github.com/DevinFerko/Machine-Learning-Comp/blob/544e22323bf07ac1dd260ac6916fcf923bd7aac1/MNIST_Dataset/Accuracy%20of%20models.png)

## Wine Quality Dataset

This Dataset contained a series of red and white wines and was found on Kaggle. It is important to note that this dataset is not very balanced as it contains far more high-quality wines than low. I believe this dataset gives us a good example of when machine learning may not be the best solution when used for comparisons. This is evident with a high-scoring 'Dummy Classifier'.

In the future, I would like to re-visit this dataset maybe with a feature selection angle in mind. I would also like to note that at the time of writing, I am also working on debugging my Neural Network model to improve the very low score I am receiving.

![Models' accuracy on test data (MNIST)](https://github.com/DevinFerko/Machine-Learning-Comp/blob/5e140b8103a3c108078620438f5820522c4366fb/Wine_Quality_Dataset/accuracy-normalized.png)

Update: I used the same dataset to train a Neural Network separately (wine_NN.ipynb). This time I chose to perform more feature selection work by eliminating unimportant features. This resulted in much higher accuracy results seen below.

![MAE Neural Network (MNIST)](https://github.com/DevinFerko/Machine-Learning-Comp/blob/1c0372e171beedd69518188678fe686fcce38e44/Wine_Quality_Dataset/MAE%20for%20Neural%20Network%20Model.png)
![Neural Network Accuracy (MNIST)](https://github.com/DevinFerko/Machine-Learning-Comp/blob/1c0372e171beedd69518188678fe686fcce38e44/Wine_Quality_Dataset/Neural%20Network%20Model%20Accuracy.png)

## Housing Prices Dataset

This dataset contains a series of houses with additional information such as Lot Area, Pool Area, Sale Condition, etc..... The training information comes with price values while the test data contains no pricing information. This project was part of a Kaggle competition to predict an accurate sale price for each test house ID. 

![Housing Pricing Accuracy Chart](https://github.com/DevinFerko/Machine-Learning-Comp/blob/7bc02183624ec51d08b9d8041f97cc57085f1f36/Housing_Dataset/Accuracy%20of%20models.png)

# Models I used for this project

My goal with this project was to compare several machine learning models by testing them against different datasets. Below are brief descriptions of the models I used

## Linear Models

### Linear Regression

Linear regression is a machine learning model that simply put uses independent variables to plot a line of best fit within the data. This can be used to predict outcome values of dependent variables. This simple yet powerful machine learning model is used for predictive analysis problems. 

This model will use the values between X and Y to plot a line of best fit on a graph. Using this plot, we can then use the value of X we have to try and make a prediction for the value of Y we want. 

### Logistic Regression

Logistic Regression uses the relationship between two data factors to create a ratio that can be used to make predictions. Outcomes in logistic regression must be a categorical or discrete value, however, meaning that values received can be either yes or no, true or false, 0 or 1, etc.

A good example of logistic regression is whether or not a baseball pitcher will throw a strike, if the probability that the pitcher will throw a strike is 0.75 then the probability that the pitcher won’t throw a strike is 1 - 0.75 = 0.25. 

In the MNIST dataset, this type of model was used to predict the probability that the image matched a numerical digit. For example, if an image of a handwritten one scored 0.95 for 1, 0.56 for 2, and 0.23 for 3, the model will pick that the image is that of a handwritten one. 

### RidgeClassifier & RidgeClassifierCV

The RidgeClassifier machine learning algorithm is a linear classification algorithm used to classify data into two or more ‘classes’ based on the data’s features. This classifier aims to minimize the sum of squared errors between the actual and predicted values. The algorithm also comes with a penalty component that prevents the model from overfitting the data.

RidgeClassifierCV works in the same way but with built-in cross-validation. Cross-validation separates the data into two groups, one group which trains the machine learning model and another smaller group which validates the model.

### SGD Classifier

SGD Classifier (Stochastic Gradient Descent Classifier) is a linear classifier with gradient descent training. It uses a stochastic gradient descent algorithm to enhance the coefficients of the linear regression equation. This updates the model’s parameters after each ‘step’, based on the gradient of the loss function.

### Support Vector Classifier – SVC

SVC is a machine learning supervised algorithm used primarily for classification tasks. This algorithm works by plotting the data points to a high-dimensional space and then finding a plane to divide the data into two classes. It is essential to note that this model performed very highly in both the Wine Quality and MNIST datasets.

## Naïve Bayes Models

### BernoulliNB 

Bernoulli Naïve Bayes is an algorithm that is part of the Naïve Bayes family. This model accepts only binary values and then fits these values based on the Bernoulli Distribution. The BernoulliNB model therefore excels at handling Boolean or binary problems/attributes, with other Naïve Bayes models better suited for other data types.

### GaussianNB

Gaussian Naïve Bayes, another algorithm that is part of the Naïve Bayes family, assumes that the numerical attributes of a dataset are distributed normally. If you were to plot a Gaussian Naïve Bayes function you would be left with a unique ‘bell-shaped’ curve where the highest value for Y would in theory land at the centre X value. 

It is worth noting that with the MNIST dataset, this algorithm received the lowest accuracy score. This is because Gaussian Naïve Bayes assumes the data’s features to be continuous which the MNIST dataset by nature is not. For future projects, I would opt to use the Multinomial Naïve Bayes model for this type of data as it assumes the features are discrete instead.

## Neighbors

### K-Nearest Neighbors

KNeighborsClassifier is a machine learning algorithm that uses data ‘neighbours’ to classify data points. Essentially this model plots our data unto an X/Y grid, once plotted the algorithm creates points and calculates the distance towards the next nearest datapoint. The original point will then be moved to better suit the distance between points, this process continues until all the created points are centralized in a data grouping (Neighborhood). These groups or clusters can then be used to classify data by calculating which data grouping it is closest to. 

It is important to note that the user will need to select the n_neighbors value when running this algorithm, otherwise, the algorithm defaults to 5 ‘neighbour’ points.

## Tree-Based Models

### Decision Tree

Decision Tree models are supervised learning algorithms used for classification and regression. They work in a hierarchical nature. Visually they can be viewed as a ‘tree-type’ structure with a root node that branches off into internal and leaf nodes. 

A good example would be a model that classifies whether an animal is a cat or a dog. The training set should include features like whiskers (yes/no), barks (yes/no), paw size, etc. The algorithm would then fit a model that splits at each feature until ending on a leaf that would identify whether the animal is a cat or dog. You can then use this model to classify an animal based on the features that this animal has. 

It is important to note that this model is not ideal for very large datasets, or datasets that contain a lot of ‘noise’. Data ‘noise’ is essentially an error that occurs during the data collection stage.

### Random Forest

The Random Forest algorithm builds upon the decision tree model, and as such is commonly used for classification and regression problems as well. Essentially this model will build multiple decision trees based on several different samples, when the user inputs their dataset the model will select either the majority vote for classification results or the average case for regression results.

This model improved upon the decision tree model when it came to the MNIST dataset. Scoring a 94.8% accuracy versus the 79.5% accuracy achieved by the decision tree model.

### Gradient Boosting & XGBoost 

Gradient Boosting trees use a series of weak-performing decision trees to continually improve a model. Essentially an initial model is made, predictions are made using the whole dataset, an error is calculated using the predictions and actual values, a weight or penalty is then assigned to these incorrect predictions, and another model is then created that attempts to fix the errors of the last model. This process continues until the user is presented with a final model created by weighting the mean of all the models. 

XGBoost is essentially a gradient-boosting tree that uses advanced regularization. Regularization is a term that refers to various techniques used to calibrate machine learning models, these techniques attempt to adjust the loss function to prevent over or under-fitting. 

## Multi-layer Perceptron

### MLP Classifier

The Multi-layer Perceptron (MLP) Classifier is a model that uses a Neural Network to perform classification tasks. This model is made up of firstly the input layer, which accepts the user’s input, one or multiple hidden layers, which perform the computational work on the dataset, and finally, the output layer, which makes a prediction or decision about the outcome.

This type of model is mostly used for supervised learning problems, as the model trains on a dataset containing input and output data.
