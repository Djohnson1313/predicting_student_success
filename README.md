![grad pic](https://github.com/user-attachments/assets/0db9bf96-236b-4e58-af9d-6d95ce468881)

# Predicting Student Success

- Darryn Johnson
- Instructor : Mark Barbour
- Date : 10/30/2024
- Blog :
- Link to repository :[predicting_student_success](https://github.com/Djohnson1313/predicting_student_success)
- Link to notebook :[predicting_student_success_notebook](https://github.com/Djohnson1313/predicting_student_success/blob/main/predicting_student_success_notebook.ipynb)
- Link to Presentation :[predicting_student_success.pdf](https://github.com/Djohnson1313/predicting_student_success/blob/main/prediciting_student_success_presentation.pdf)
- Link to original dataset : [predict student dropout and academic success](https://www.kaggle.com/datasets/syedfaizanalii/predict-students-dropout-and-academic-success)
- Link to header image : [File:IB Graduation Ceremony at LIS.jpg](https://commons.wikimedia.org/wiki/File:IB_Graduation_Ceremony_at_LIS.jpg)

## Business Understanding 

In this repository, we look into a dataframe containing 4,424 entries with 37 columns. Each row represents an individual, with each corresponding column containing the socio-economic, demographic and academic factors for each person. The targets in this data are `graduate`, `dropout` and `enrolled`. For the purpose of this project, enrolled will not be used in the modeling process, as it does not assist with the problem we are aiming to solve. The problem we are aiming to solve is loan companies loaning money to students who are unlikely to return the loan, due to not graduating. The model created in this notebook has a 91% precision score, which is good since we want to have a low false positive rate.

## Data Distribution 

![Screenshot 2024-10-30 170054](https://github.com/user-attachments/assets/ea76ff87-f5d2-45f0-ac3b-430f7773c32e)

Here we see that a majority of the individuals have graduated, with droupout trailing close behined. As mentioned above, `enrolled` does not pertain to the problem at hand.

## Modeling 

There are a few pre-modeling steps that had to be done, prior to the data being ran through a model. A very important step for this specifc dataset was decoding the data. The data was coded using numbers to represent what the value is. This would cause the model not to pick up on what we actully want it to, outputing meaningless data. Some other model preparation included label encoding (turning the target into binary values), one-hot encoding (allowing the model to see each metric as a binary value), and oversampling/undersampling if needed. For the actual modeling process, `RandomForestClassifier` was chosen to be the main contender. The reasoning behind this is because it is easy to use and understand, requires not much pre-processng, and worked well for the problemm at hand.

## Evaluation

To evaluate this model, we will primarily be using the metric `precision`. `Precision` is the measurement of `false positives`. This is an imporntant metric to watch as false positives are when the model says a student will graduate, when in reality they are more likely to dropout. This is an issue for loan offices becuase this creates a situation where a loan is given to a student that may not be able to pay it off, due to not getting the job they wanted. This results in not getting the loan returned. To validate the model we will be using `train_test_split` to create train data and test data. 

# Conclusion 

The chosen model performed well, with a precision score of 91%. While the neural network this model was put up against did perform well, it was beaten out by about 4%. Just because an individual is marked as potentially `dropout`, does not men the end of their potential to be a customer of ours. A good way to capitalize on an individual marked as so, is to partner with a tutoring company that we can recommend  them to. This allows them to make some adjustments they need to succed, and potentially still get a loan with us.

## Reproducibility
In this quick section, we will be going over how to reproduce the same results shown in this notebook. A few key elements needed to run locally on your system are as follows:

- download python off of [Python.org](https://www.python.org/downloads/)
- ensure you have the respective packages also downloaded as noted in imports. These downloads/instructions can be found by searching the name online.
- the data downloaded either from the links in the `Sources and Links` section in the notebook or using google colab.
If you are running google colab, you have no additional tasks to complete other than potentially having to rename the data to match what is in the project. If so, follow the instructions in the notebook.

## Repository Structure
```
├── .gitignore
├── Predict Student Dropout and Academic Success.csv
├── README.md
├── dataset_metadata.ipynb
├── predicting_student_success_presentation.pdf
└── predicting_student_success_notebook.ipynb
```
