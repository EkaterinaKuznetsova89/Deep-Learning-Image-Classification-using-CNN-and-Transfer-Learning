# Deep-Learning-Image-Classification-using-CNN-and-Transfer-Learning

Loading and visualizing data:
•	The data was divided into 5 training batches, each with 1k images. The data was balanced
•	Number sample per class was even 

Data preprocessing:
•	Reshaping wasn’t necessary. It was already in correct shape
•	Normalizing pixel values to the [0, 1] range to speed up training.
•	Encode the labels using one-hot encoding for categorical classification

Building CNN model
•	There were not major changes in CNN. I changed the input shape - input size: 32x32 pixels, added density by 128 neurons and dropout 50%. So it could help with prevention for overfitting
#32-64-128 (doubling)
#32-64-64 (stabilizing)
#64-64-128-256(increasing)
•	The model is 72% accurate.
•	 Precision and recall are balanced, which is good.
•	 The F1-score being close to accuracy confirms your model is consistent.
•	airplane, automobile, ship are performing well.
•	cat and bird are underperforming — these are often visually similar and hard for the model to distinguish.
The model doesn’t predict animals that well.
Improving the model
•	CNN with more layers reached about 76.7–77.2% accuracy on the test set
•	Adding more layers helped the model
Hyper tuning and early stopping
•	The model reached about 74.7% test accuracy.
•	Slightly lower than your previous model with more Conv layers (~77%)
Data augmentation
•	The best performance so far, showing that data augmentation helped your model generalize better.
Inception V3
1. Data Augmentation helped generalization
•	Jumped to ~92.14% test accuracy — solid result on CIFAR-10.
•	Helped prevent overfitting early.
2. Fine-Tuning improved test accuracy slightly
•	Train accuracy went way up to 99.82%, which shows the model really fit the training data.
•	Test accuracy improved from 92.14% -> 92.78%, which is good but small, suggesting that:
o	Most learning came from the pre-trained layers.
o	Fine-tuning the top layers gave gain
3. Drop-out regularized the model slightly
•	Dropout reduced overfitting slightly — but test accuracy remains high.
•	The higher loss (0.5327) despite good accuracy 92.61%  - model is making mostly correct predictions, but it’s not very confident in those predictions..
