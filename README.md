# :bank:Customer retention risk modeling in Banking Industry - Deep Learning  
The project focuses on developing a churn model using a **Feedforward Neural Network (FFNN)** to predict customer turnover in a banking context. Dataset incorporates customer details such as credit score, gender, and banking activity. By optimizing the network architecture through **grid search** and evaluating with **cross-validation**, the model achieves improved prediction accuracy. The prroject aims to offer a practical application in enhancing **marketing efforts** and reducing **turnover-related losses**.  
## Dataset 
Before starting to train a model, make sure to download the dataset from [kaggle/churn-modelling](https://www.kaggle.com/datasets/shubh0799/churn-modelling "悬停显示")  
A simple analysis of the data through histograms gives us the distribution of some of churned customers and active members.  
<img src="/pic/fig2Histogram.png" width = "500" height = "500" alt="histogram" />

## Methodology
* *Pre-processing*  
Remove Nan values, normalize data into uniform range, eliminate non-essential variables
* *Train FFNN model*  
The network comprises a sequential model with layers arranged linearly, including an input layer matched to the dataset's features, a dense hidden layer with **ReLU activation** for non-linearity, a dropout layer for regularization, and batch normalization for input standardization, culminating in an output layer utilizing a **sigmoid function** for binary classification. The model's configuration for training employs **RMSprop optimizer** and **binary cross-entropy loss**, achieving an 85.8% accuracy on validation, with performance evaluation on test data via the predict function.  
* *Tuning*  
This process involved adjusting the number of **layers** and **neurons**, introducing a configuration of decreasing neuron counts across four added hidden layers to refine model accuracy. Additionally, **batch size** and **optimizers** (adam and rmsprop) were evaluated for their impact on performance. Post-tuning, the model's accuracy improved to 86.13%, indicating the effectiveness of the selected hyperparameters in optimizing the network for better classification results.  

## Evaluation - Cross validation and Accuracy  
<div>

|   | Accuracy | Precision | recall   | F1-score |
| ---------- | -----------| -----------| -----------| -----------|
| Original model  | 0.83   | 0.86 | 0.96 | 0.92 |
| Tunned model   | 0.86   | 0.88 | 0.97 | 0.92 |

</div>

## Result  
These pictures indicate that the accuracy of the model has improved to some extent after tunning. However, there is no significant change in the recall and f1-score data, which indicates that there is still some room for improvement in the model.  
<img src="/pic/fig11ConfusionMatixO.JPG" width = "250" height = "250" alt="cmo" />
<img src="/pic/fig12ConfusionMatixT.JPG" width = "250" height = "250" alt="cmt" />

## Application  
The model is primarily applied in the **banking sector**, focusing on customer churn prediction. By accurately identifying customers likely to leave, banks can develop targeted intervention strategies to improve retention. This model aids in understanding customer behavior patterns, enabling personalized customer engagement and optimizing marketing efforts to reduce churn. Its implementation can significantly enhance customer satisfaction and loyalty, leading to improved business outcomes.
