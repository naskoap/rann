# Team RANN – Tool Comparison: Hyperopt vs Optuna

### Team Members:
- Nasko Apostolov
- Audrey Bertin
- Nelson Evbarunegbe
- Raymond Li

### Project Overview:

Hyperopt and Optuna are two Python-based tools designed to help with the step of __hyperparameter optimization__ in a machine learning pipeline. Both have UI features that allow users to compare the performance of different parameter combinations, and both integrate with standard Python ML libraries, including `scikit-learn` and `Tensorflow`.

Official resources for Hyperopt and Optuna are provided below:

#### Hyperopt:

- GitHub Repository: https://github.com/hyperopt/hyperopt

- Documentation: http://hyperopt.github.io/hyperopt/

#### Optuna:

- GitHub Repository: https://github.com/optuna/optuna

- Website (includes documentation and tutorials): https://optuna.org


In this project, we compare the two tools to one another AND to how many people might complete the hyperparameterparameter optimization without a tool (grid search).

There are three different parts to this comparison:
1. A code review of the official repositories
2. A UI review where we look at the UI features available in both tools
3. An experiment where we run a full machine learning pipeline using each of our tools--Grid Search, Hyperopt, and Optuna--to compare algorithm speed and performance (in terms of improving model scores). For each tool, we test it on two separate datasets, one for classification and one for regression.


### Repository Structure

#### Data Folder

The `/data` folder contains the data used in the experiment. There is one dataset for classification, under the `/classification` subfolder, and one dataset for regression under the `/regression` subfolder. 

Both datasets come from Kaggle, at the following links:

Classification -- predicting whether a patient will be readmitted to the hospital based on data from their last hospital visit:
https://www.kaggle.com/code/iabhishekofficial/prediction-on-hospital-readmission

Regression -- predicting CO2 emissions from vehicles based on features of the car (engine size, fuel type, etc.):
https://www.kaggle.com/datasets/debajyotipodder/co2-emission-by-vehicles

In each subfolder, there is a raw version of the data as directly downloaded from Kaggle, as well as a cleaned version, which has been reformatted and simplified into a format that can be processed by a random forest model. There is also a Jupyter notebook that includes all of the code used to convert the data from the original format to the cleaned format.

#### Experiment Folder

In the `/experiment` folder, we store all of the code used to run the machine learning pipelines for each of the experimental conditions: Grid Search, Hyperopt, and Optuna.

#### Report folder

In the `/report` subfolder we store all of the files used to generate the midpoint report and final report, including the files used to write the documents, any images that are embedded, and PDF outputs.


### Project Google Folder 

In addition to this repository, we also have a project Google Folder which stores additional items. 

This folder contains slides shared at midpoint and final presentations, as well as any other media such as recordings.

https://drive.google.com/drive/folders/1knJQ2KCqIkrWExxXIYlPUy4Rd-sNyZU0?usp=share_link



