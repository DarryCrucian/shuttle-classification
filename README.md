## Overview

This repository contains Python code for performing classification on the Shuttle dataset using three different classifiers: Linear Discriminant Analysis (LDA), Quadratic Discriminant Analysis (QDA), and Bayesian Decision Rule (BDR). Each classifier is implemented with the necessary preprocessing steps and hyperparameter tuning where applicable.

## Dataset

The code is designed to work with the Shuttle dataset, which is assumed to be available as two CSV files: `train_shuttle.csv` for training data and `test_shuttle.csv` for testing data. The dataset should have the following structure:

- Each row represents a data point.
- The last column contains the class labels (1 for the positive class, and other integers for different classes).

You should replace the file paths with the actual paths to your dataset files.

## Dependencies

Make sure you have the following Python libraries installed:

- pandas
- numpy
- scikit-learn (for train-test splitting, feature scaling, and model evaluation)
- scipy (for Kernel Density Estimation in BDR)

You can install these dependencies using pip:

```
pip install pandas numpy scikit-learn scipy
```

## Code Structure

The code is divided into three main sections, one for each classifier: LDA, QDA, and BDR.

### LDA Training and Accuracy

The LDA classifier is trained using the training data, and its accuracy is calculated on the test data. The majority class (class 1) is undersampled to handle class imbalance.

### QDA Training and Accuracy

The QDA classifier is trained using the training data, and hyperparameter tuning is performed using GridSearchCV to find the best regularization parameter (`reg_param`). The accuracy of the tuned QDA model is calculated on the test data.

### BDR Training and Accuracy

The BDR classifier is implemented as follows:

1. The training data is loaded and standardized.
2. A grid size for the feature space is defined.
3. KDE models are trained for each class using the training data.
4. For each test sample, the grid element it belongs to is calculated.
5. The class with the highest posterior probability within the grid element is assigned as the predicted class.

The accuracy of the BDR classifier is calculated on the test data.

## Usage

1. Ensure you have the necessary dataset files (`train_shuttle.csv` and `test_shuttle.csv`) in the same directory as the code or specify the correct file paths in the code.

2. Run each section of the code (LDA, QDA, BDR) separately in a Python environment. You can use Jupyter Notebook or a code editor of your choice.

3. The code will print the accuracy of each classifier on the test data.

4. Experiment with different hyperparameters, grid sizes, or bandwidth values as needed for your specific classification task.

## License

This code is provided under the MIT License. You are free to use and modify it as needed for your projects.

## Acknowledgments

This code was created for educational and demonstration purposes. If you find it useful, please consider giving credit by referencing this GitHub repository.

---
