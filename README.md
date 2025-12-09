# Insider Threat Detection

This project explores various machine-learning based anomaly detection approaches to detect potential insider threats representing different scenario. 
We explored using the Isolation Forest, LSTM Autoencoder, LOF, and GMM models. This readme will talk about the required steps needed for running the python notebooks. 

## Step 1. Downloading Necessary Files In The Dataset

The Dataset is the CERT Insider Threat Dataset from Carnegie Melon Univerisity. The reference link is here: 
https://kilthub.cmu.edu/articles/dataset/Insider_Threat_Test_Dataset/12841247

This dataset has many versions, but we are using the latest version 6.2, On this webpage, download `answers.tar.bz2` and extract the tar file.
In this tar file, many files will be shown. The main ones to look at are:
- `insiders.csv`: giving a list of all the insider threats.
- `scenarios.txt`: This file lists out 5 unique scenarios for insider threats to occur. For the purposes of the project, we worked on scenario 3 and scenario 4.
- Any of the `r6.2-_.csv` files: This lists all the activity logs that connected with the insider threat. There are 5 of these files, with each file representing one user for one of the five scanarios.

Additionally, this dataset can be found in Kaggle, which is where the individual activity log files come from:
https://www.kaggle.com/datasets/mrajaxnp/cert-insider-threat-detection-research/data

A challenge with downloading the dataset directly from the CMU website is that it is 100 GB in size consisting of many files. Main reason is the `http.csv` file, but that is not used in this project.
So, the recommendation is to download the specific activity log files in the dataset from Kaggle that would be used. In our project those included:
1. `file.csv`
2. `logon.csv`
3. `device.csv`
4. `email.csv`
5. `decoys.csv`

## Step 2. Creating the File Path

The Python notebooks are designed in a way to run on Google Colab. Hence why these lines of code exist in the beginning every notebook. This is for mounting with Google Drive:
```
from google.colab import drive
drive.mount('/content/drive')
```

In Google Drive, create a folder called `235kaggle`. The file path should then be `content/drive/MyDrive/235kaggle`

This folder will be where all of the activity logs will be stored for the model notebooks to access.

## Step 3. Running the Notebooks

After creating the `235kaggle` folder with the necessary activity log csv files, we can export these four python notebooks into Google Colab and run each cell. 
The recommendation is to use a TPU to speed the running process.
