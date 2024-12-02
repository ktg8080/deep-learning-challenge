# deep-learning-challenge

# Neural Network Model Analysis

## Overview

The goal of this project was to build and evaluate a deep learning model to predict whether applicants would successfully receive funding from Alphabet Soup. Using a neural network, the data was preprocessed, the model was trained and optimized, and its performance was evaluated.

## Results

### Data Preprocessing

	•	Target Variable: IS_SUCCESSFUL (1 = funding successful, 0 = funding unsuccessful).
	•	Features: Includes numerical data like STATUS and log-transformed ASK_AMT, as well as categorical variables (APPLICATION_TYPE, CLASSIFICATION).
	•	Removed Data: EIN and NAME were excluded as they were identifiers with no predictive value.

### Model Design

	•	Neurons and Layers:
	•	80 neurons in the first layer, 50 in the second, 20 in the third.
	•	ReLU activation for hidden layers and sigmoid for the output layer.
	•	Regularization:
	•	Dropout layers were added to reduce overfitting, and early stopping was used to halt training when validation loss stopped improving.

### Performance

	•	Accuracy: The model achieved ~73%, just below the target range of 75-80%.
	•	Improvements:
	•	Addressed class imbalance using SMOTE to oversample the minority class.
	•	Simplified categorical data by grouping low-frequency categories into “Other.”
	•	Tuned learning rates and added dropout to enhance training stability.

## Visualizations

	1.	Training Accuracy and Loss:
		• Accuracy steadily improved during training (~73%), while loss decreased.

  		![Training Accuracy](https://github.com/ktg8080/deep-learning-challenge/blob/main/Images/training_accuracy.png?raw=true)
    
	2.	Training Loss:
		• The training loss steadily decreased over time, indicating that the model was learning effectively. However, there were 		diminishing improvements after approximately 60 epochs, which suggests that the model had converged.

    
 ## Recommendation

Although the neural network performed reasonably well, a tree-based model such as XGBoost or Random Forest could be more effective for this type of structured, tabular data. These models are better at handling class imbalance and may improve metrics like precision and recall for the minority class (IS_SUCCESSFUL = 1).
