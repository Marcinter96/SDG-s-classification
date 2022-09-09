# AFD: Codes to analyse the involvements of french written projects into the SDG


## Abstract:

The goal of the following project is to analyse documents implications and their mentions for each of the sustainable development goals. To do so we first need to clean the documents we want to analyse and conserve only the sentences into a csv file. With then use our pre-trained model to predict the SDG mention for each project and export the result for every sentences as well as a png barplot wich shows the results. 


## Codes:
We present a small explanation for each code and how to use them:

### TextExtractor:
This code takes as input the path and file name for the given PDF or Word document we want to analyse and extract the wanted sentences and saved them into a csv file. 

For use Run all cells and input first file path then file name when asked by the system.

### ScanExtractor:
This code takes as input the path and file name for the a given scanned document we want to analyse and extract the wanted sentences and saved them into a csv file. There is some big losses of text as it is hardly possible to get all text from picture files but for the purpose of this exercise results are still satisfying.

For use Run all cells and input first file path then file name when asked by the system.


### Training_Model:
This code takes as input our cleaned trainset and create the model features using a TF-IDF approach. We then run our XGBoost defined algorithm with the created features to get the fit that will be used for the predictions. The fit are saved as joblib model in order to be used for the predictions. 

If Value Error: appears when doing predictions with XGB_Classifier_French, re-run this code to get compatible joblib fit for our model. This can happen when packages are updated.

### XGB_Classifier_French:

This code uses as entry a csv file containing text and predict for each entries if belongs to zero, one or more SDG's. The code used the previously defined model fits as well as the chosen tresholds to decide wheter a sentences belongs to an SDG. 

For use Run all cells and input first file path then file name and column name of the text we want to predict from when asked by the system.





## Notes
The `requirements.txt` file should list all Python libraries that your notebooks
depend on, and they will be installed using:

```
pip install -r requirements.txt
```
Warning: - For the use of Tika package to extract text from PDF and Word documents, need to install Java 8 on the path.
         - If requirements fails to download, need to install packages manually to resolve dependencies issues.
         


         
