# Bank-Loan
A bank is trying to get more people to apply for personal loans. Using the dataset provided by them, which is based of the previous year when they were offering loans packages, they want me to check which of their current and future customers would be interested in acquiring a personal loan and how to make this option attractive and available to them.

More people applying for personal loans will aenable them to generate more revenue in the form of interest and loan fees. They'll also be able to attract new customers and strengthen relationship with exisitng customers and increase their loyalty.

The data provided by them contains information about the previous customers who have applied for personal loans based on the previous campaign they ran versus those who didn't apply. I'll use this information to find a link and create a pipeline to determine the type of customers they should promote thier services to them and how to make taking the loan attractive to them.

The source for the dataset is linked below: https://www.kaggle.com/datasets/krantiswalke/bank-personal-loan-modelling

Modelling 

After importing the necessary libraries and the Sequential model. I imported the layers Dense, Flatten and Dropout and the activaton functions LeakyReLU and PReLU.

I chose to only run four models and compare them.

Created an early_stopping variable and set it to monitor val_loss and gave it a patience of 20. This is so that if the val_loss remains the same during the training then after 20 seconds, it should automatically stop running.

When training the models, the batch size is set to 30 and no of epochs 500.

For the first model: the metrics was initiall set to accuracy, but when it started running the accuracy started with 60% and gradually went down to 20. val_accuracy was also low. So I switched it to binary_accuracy and it worked in reverse, starting with 80% and steadly going higher. These were the values after trianing :

loss: 0.0221
binary_accuracy: 0.9944
val_loss: 0.0587
val_binary_accuracy: 0.980
Module 2: Kept it same but increased the number of unit in the dense layer, and introduced another dense layer and set activation to keras.layers.LeakyReLU(alpha=0.03). These were the values after trianing :

loss: 0.0018
binary_accuracy: 0.9997
val_loss: 0.0470
val_binary_accuracy: 0.9909
Module 3: this was left the same as module 3 but I introduced a dropout layer and set it to 0.25% and changed the optimizer from adam to rmsprop. These were the values after trianing :

loss: 0.0122
binary_accuracy: 0.9965
val_loss: 0.0543
val_binary_accuracy: 0.9920
Module 4: For this I introduced another layer dense layer with activation keras.layers.LeakyReLU(alpha=0.02). These were the values after trianing :

loss: 0.0177
binary_accuracy: 0.9970
val_loss: 0.0481
val_binary_accuracy: 0.9898
I'll be plotting the loss, val_loss, val_binary_accuracy and binary_accuracy od module two since it has the lowest loss. Their Binary accuracy are all in 99 but that of module2 is much higher, almost reach a 100 if rounded up.

Model Evaluation

Evaluatig module 2 with the test dataset to check performance. We can see the model performed very well and gave an accuracy of 99.6% and a loss of 1.98 %.

Conclusion

The model learned well on the training and performed very well on the test dataset.

Recommendation

Can offer the interest payment to start 2 years after receiving the loan
Personalise Loan offers
Improve loan application process by making the wait period for result shorter
Run targetted ads to attract new customers
