# doctoplant_tensorflow
## Discover diseases on leave photo.

Computer Vision Project - Image classification.

Creation of CNN model composed by:
- 3 Conv2D layers with
  - Batch Normalisation
  - MaxPooling
  - ReLU activation
- 1 GlobalAveragePooling layer
- 2 Dense layers ReLU activation (and Dropout)
- 1 Final Dense layer with Softmax activation (38 classes - output shape)

Test set > Scrapping from Google image (different from actual Dataset distribution).

### Iteration 1
Dataset from Kaggle - https://www.kaggle.com/vipoooool/new-plant-diseases-dataset:
- Dataset balanced
- Leave on an uniform background

Code > 01-cnn_tensorflow_doctoplant_dataset1.ipynb


### Iteration 2 / 2-bis
Dataset from Kaggle - https://www.kaggle.com/abdallahalidev/plantvillage-dataset:
- Dataset unbalanced
- Leave - image segmented

Adding on top:
- Data Augmentation
- Background addition:
  - **Fix** for iteration 2
  - **Random** for iteration 2-bis
- "Others" category addition
- Update final layer - 39 classes

Code:
> 02-cnn_tensorflow_doctoplant_data_augmented_fix_bckgrnd.ipynb
> 02bis-cnn_tensorflow_doctoplant_random_bckg.ipynb


### Iteration 3
Dataset (same as Iteration 2) from Kaggle - https://www.kaggle.com/abdallahalidev/plantvillage-dataset:
- Dataset unbalanced
- Leave - image segmented

Adding on top:
- Data Augmentation
- Background addition:
  - **Fix** for iteration 2
  - **Random** for iteration 2-bis
- "Others" category addition
- Update Final Dense layer - multi-output
- Custom Loss function

New CNN model:
- 3 Conv2D layers with
  - Batch Normalisation
  - MaxPooling
  - ReLU activation
- 1 GlobalAveragePooling layer
- 2 Dense layers ReLU activation (and Dropout)
- 1 Dense layer with Softmax activation - plant_classification (38 classes)
- 1 Dense layer with Sigmoid activation - object_proba (1 neuron)
- Concatenation > plant_classification + object_proba

Code > 03-cnn_tensorflow_doctoplant_sigmoid.ipynb

**Training configuration**:
- Use of Adam optimizer.
- L2 regularization to avoid overfitting.
- Use of Categorical Crossentropy loss function (for iteration 1&2).
- Monitor model with the Accuracy metric.

