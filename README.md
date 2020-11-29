# Breast Cancer Predictor Using Clinical and Anthropometric Data.

This is the repo for the group project for DSCI 522 (group 16)

- Author: DSCI 522 GROUP 16
- Contributors: Aditya, Ifeanyi Anene, Rahul Kuriyedath, Saule Atymtayeva

A data analysis project for DSCI 522; a course in the Master of Data Science program at the University of British Columbia.

# About 
At the current stage of this project, we are trying to answer the predictive question: given clinical and anthropometric data and parameters available, predict if a patient has breast cancer or not? Answering this question is important because breast cancer is the most common malignancy amongst women worldwide (Crisóstomo et al., 2016) and developing a prediction model that can act as a biomarker for breast cancer will help mitigate the mortality rate of patients.


The dataset used in this project consists of anthropometric data and parameters gathered in a standard blood analysis. This dataset was created by Miguel Patrício, José Pereira, Joana Crisóstomo, Paulo Matafome, Raquel Seiça, Francisco Caramelo, all from the Faculty of Medicine of the University of Coimbra and also Manuel Gomes from the University Hospital Centre of Coimbra (Patrício et al., 2018). The dataset was sourced from the UCI Machine Learning Repository (Dua and Graff 2017) and it can be found [here](https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Coimbra), particularly [this file](https://archive.ics.uci.edu/ml/machine-learning-databases/00451/dataR2.csv). Each row in this dataset represents a set of observations of individual patients and each column represents a variable. In this dataset, there are 116 observations and 9 features which are all numerical. There are zero observations with missing values for each class in the dataset. The target column is a binary dependent variable, which indicates the presence (Classification = 2) or absence (Classification = 1) of breast cancer.


To avoid breaking the golden rule, we separated the data set into a train and test set (splitting on 80:20) and then an exploratory data analysis was undertaken to assess the features that might be important for prediction. Furthermore, given that there are only numerical features in this dataset, the features were scaled using the standard scaler function during data preprocessing. Subsequently, multiple machine learning classifiers were explored based on multiple classification evaluation metrics such as recall, f1, precision and accuracy scores. The baseline model was created using sklearn's DummyClassifier. This classifier was included as a sanity check to use in comparison with the other, more complicated classifiers.  Furthermore, these more complicated classifiers were explored, and then a classifier was chosen based on the important classification metrics indicated in the analysis and conclusion section (an example being: because we are interested in identifying patients with breast cancer, therefore that would be our "positive" class, which will make the recall metric vital in selecting a model).
  

A literate code document of the current analysis undertaken can be found [here](src/EDA.ipynb).


# Usage
To replicate the analysis, clone this GitHub repository, install the [dependencies](#dependencies) listed below, and run the following commands at the command line/terminal from the root directory of this project:

1. Create a conda envrioment using the `group16.yml`

```bash
conda env create -f group16.yml
conda activate group16
```

2. Download breast cancer coimbra dataset in the data directory

```Python download_data.py --url='https://archive.ics.uci.edu/ml/machine-learning-databases/00451/dataR2.csv' --out_file='C:/data/raw/data.csv'```

3. Split the data into training and test splits.

This script takes in the raw data and splits it into train and test data using 80/20 split.

 ```Python split_train_test.py --in_train_file='C:/dataR2.csv' --train_out='C:/data/raw/train.csv' --test_out='C:/data/raw/test.csv'```



4. A script that creates exploratory data visualizations. 




5. A script that performs machine learning analysis and summarizes the results as a table.




# Dependencies

To run this project, please install the required dependencies [here](https://github.com/UBC-MDS/dsci522-group16/blob/main/group16.yml)



# License 

The Breast Cancer Predictor Using Anthropometric data materials are licensed under the Creative Commons Attribution 2.5 Canada License (CC BY 2.5 CA). If re-using/re-mixing please provide attribution and link to this webpage.



# References 

Patrício, M., Pereira, J., Crisóstomo, J., Matafome, P., Gomes, M., Seiça, R. and Caramelo, F., 2018. Using Resistin, glucose, age and BMI to predict the presence of breast cancer. BMC Cancer, 18(1). https://doi.org/10.1186/s12885-017-3877-1

Dua, Dheeru, and Casey Graff. 2017. “UCI Machine Learning Repository.” University of California, Irvine, School of Information; Computer Sciences. http://archive.ics.uci.edu/ml.

Crisóstomo, J., Matafome, P., Santos-Silva, D., Gomes, A., Gomes, M., Patrício, M., Letra, L., Sarmento-Ribeiro, A., Santos, L. and Seiça, R., 2016. Hyperresistinemia and metabolic dysregulation: a risky crosstalk in obese breast cancer. Endocrine, 53(2), pp.433-442.

