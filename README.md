# CIFAR10
The CIFAR10 dataset is a popular dataset containing coulured images of 10 different objects in different states and their labels 
Solving the CIFAR10 dataset using a shallow CNN ans Resnet and trying out different architectures.
This project involves an analysis of acuuracy and loss over epochs based on controlled variations in the learning rates. 

Frameworks used: PyTorch, NumPy, Pandas, Matplotlib, Torchvision.

Preprocessing:
![image](https://user-images.githubusercontent.com/74304695/183104278-152d4e30-26a0-4417-b450-62a5090e22b7.png)

![image](https://user-images.githubusercontent.com/74304695/183114191-2a41ad9f-8ff4-478d-a6d9-fa438e148700.png)


The data preprocessing done via Torchvision transforms involves normalizing the images, followed by randomly cropping, flipping and reflecting the images in order to include variaton in the dataset and prevent overfitting into the training data  

![image](https://user-images.githubusercontent.com/74304695/183101235-8d2ddaba-af29-45d5-a176-666217876576.png)

Based on a preliminary CNN architecture, we get an accuracy of roughly 65-67% which can be improved upon by 

![image](https://user-images.githubusercontent.com/74304695/183103380-6b6d1005-6e96-4a90-88a2-ee262953f429.png)

Simply Switching to a resnet architecture elevates the the training accuracy to 86% and the validation accuracy to 84%, getting closer to the end goal of 90%

![image](https://user-images.githubusercontent.com/74304695/183109461-3b72c087-f8eb-4f91-af02-8292207e29e9.png)

Using a triangular cyclic learing rate with a decrement factor 0.5 increases the accuracy to 91%, however it is observed that the the period of incerasing learning rate results in a periodically increasing loss and decreasing accuracy. 

![image](https://user-images.githubusercontent.com/74304695/183109872-18edf6dd-0b54-4675-8997-bdc2dc644b4c.png)

the same learning rate with a decrement factor of 0.25 results in a mrginally better accuracy, but is able to smoothen out the loss curve to a decent extent and lower fluctuations in the accuracy. 

![image](https://user-images.githubusercontent.com/74304695/183105500-d4f6f3ac-49bd-4eaf-8225-e058a79891a6.png) 

Using a cyclic learning rate with a decrement factor of 0.5, with a triangular shape where the the learnig rate is increased immediately rateher than gradually gives results similar to the case with a gradual increase, however causes a sharp increase in the loss rather than a gradual one, this is able to cut don on the epochs where the loss increases.

![image](https://user-images.githubusercontent.com/74304695/183106929-107b011e-9a89-4d96-a84b-527ace06b8e6.png)

The same triangular learning rate with a sharp increase and decrement factor of 0.25 results in a similar result, with marginally lower accuracies. The loss and accuracies give smoother curves in this case. 




IMPROVEMENTS: 
1. Trying out decrement factors other than 0.5 and 0.25.
2. Using another type of learning rate variation. 
