## Prediction Accuracy
- Typically measured by calcualting a *prediction error*. In regression for example we measure the prediction error my taking the mean over the squared errors of prediction (actual output variable - predicted output).
- residual mean square $:= \frac{1}{\#data}\sum_{data}(\text{real output} -\text{predicted output})^2$
- Because thie measure is taken over the whole dataset, including the data the model war trained on, it will unterestimate the error we would observe on new data.

## Generalization error
- To measure a models ability to react to new data we need an estimate to see how well it predicts the outcome of data that is independent from the training set we use to fit the model. 
- If the model's generalization error is low on new data the model is able to generalize the input whereas if the model has a high generalization error it fits the triaining data too much and is unable to generalise the features.
- Here splitting the data comes into play: we use one subset $\mathcal{L}$ to train the data and one subset $\mathcal{V}$ to validatet the model. Sometimes there is also a third subset $\mathcal{T}$ to test the data.
- The mean squared sum of the errors is called *regression learning error* if we aggregate over  $\mathcal{L}$ and it is called *regression test error* if we aggregate it over $\mathcal{T}$. (Analog for calssification we average over correctely and incorrectly classified outputs.)
- There are other techniques 
    - **V-fold corss-validation:** Randomly divide the data into $V$ subsets and then fit the model using $V-1$ of the subsets while using the one left subset to calculate the error. Repeat this $V$ times and choosing each time a different subset for validation. Now the test error is given by avaraging the $V$ test erros.
    - **bootstraping**: sample from the dataset with replacement with the same size as the original data set to get arbitrarly many samples. After fitting one model on each bootstrap sample the GE (why use the prediction error?)
- We call the expected prediction error over an an independent test set the generalization error. Usually the goal is to reduce this error.


## Overfitting
- In case the model learned prediction too close to the training data, while the learning error will be really small the test error will increase.
- Usually overfittet model include too many parameters and are too complicated  relative to the size of the learnign set.
