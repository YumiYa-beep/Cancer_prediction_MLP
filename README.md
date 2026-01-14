# Cancer_prediction_MLP
M2 AIDA project of Group 8. 

We constructed a MLP, with and without autoencoder, to predict presence of hepatocellular carcinoma (liver cancer) based on transcriptomic data and achieved good accuracy. Additionally, we tried to predict survival based on transcriptomic data, age, sex, cancer stage and cancer grade.

## Complete pipeline : 
### Creation of the gene expression matrix (samples x genes+metadata)
- matrice_creation.ipynb creates the gene expression matrix from TCGA files → expression.matrix.csv (the input dataset is included in the repo)

### Prediction of cancer (0 = normal, 1 = cancer)
- data_preprocessing_cancer.ipynb takes the expression matrix, does QC, preprocessing and aggregation of genes to pathways
- deep_learning_cancer.ipynb takes the preprocessed pathways matrix and implements deep learning for cancer prediction
- *(deep_learning_cancer_allpathways.ipynb implements deep learning on pathways not filtered by cancer-related keywords)*
- learning_SHAP_cancer.ipynb runs the same deep learning and creates figures based on SHAP values of the MLP

### Prediction of survival (0 = <2 years, 1 = >2 years)
Prediction of survival was attempted, with moderately good accuracies.
- data_preprocessing_survival.ipynb takes the expression matrix, does QC, preprocessing and aggregation of genes to pathways
- deep_learning_survival.ipynb takes the preprocessed pathways matrix and implements deep learning for survival prediction
- *(deep_learning_surv_allpathways.ipynb implements deep learning on pathways not filtered by cancer-related keywords)*
- learning_SHAP_survival.ipynb runs the same deep learning and creates figures based on SHAP values of the MLP

