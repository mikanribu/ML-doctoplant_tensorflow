# doctoplant_tensorflow
## Discover diseases on leave photo.

Dataset from Kaggle - https://www.kaggle.com/abdallahalidev/plantvillage-dataset with:
- Data Augmentation
- Background addition
- "Others" category addition

Creation of my own CNN model composed by:

- 4 Conv2D layers with
  - Batch Normalisation
  - MaxPooling
  - ReLU activation
- 1 Flatten layer
- 2 Dense layers ReLU activation (and Dropout)
- 1 Final Dense layer with Softmax activation

> Return 39 probabilities, for each Classes we want to predict.

Training configuration:
- Use of Adam optimizer with Learning Rate of 0.0005. The choice of this learning rate have been made after multiple iteration. It allow the model to converge more quicker.
- Use of Categorical Crossentropy loss function.
- Monitor model with the Accuracy metric.

