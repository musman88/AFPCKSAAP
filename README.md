# AFP-CKSAAP
AFP-CKSAAP: Prediction of Antifreeze Proteins Using Composition of k-Spaced Amino Acid Pairs with Deep Neural Network

# Requirements
- Python >= 3.5.4
- Tensorflow = 1.13.1
- Keras = 2.2.4

# Description
The deep learning model is implemented using Python on Keras (Tensorflow). The necessary files to run the model have been uploaded. 
For verification purposes, a trained model has been uploaded with necessary data files. For self implementation, the model file has also been uploaded and the procedure of extracting features is described below.

# Dataset
The dataset is obtained from Kandaswamy et. al containing 481 antifreeze proteins and 9493 non-antifreeze proteins.
A sample fasta file for both AFP and non-AFP is uploaded in the folder "Sample_Dataset_Fas.fas" in fasta format.

# Features
The features from the dataset are extracted using CKSAAP encoding technique. 
# Composition of k-Spaced Amino Acid Pairs (CKSAAP)
This scheme reflects the amino acid pair information in small and large range with in the peptides depending upon the value of k(gap).

The encoding scheme was utilized from iFeature web server which can be downloaded from 
(https://github.com/Superzchen/iFeature)

# Feature Extraction
The CKSAAP feature descriptors can be extracted using the command 

**path/iFeature-master>python iFeature.py --file xyz/test-protein.txt --type CKSAAP --out xyz/test-protein-features.txt**

The CKSAAP feature encoding calculates the frequency of amino acid pairs separated by any k residues. The default value of k is 5. To change the the value of k open "CKSAAP.py" and replace gap="5" in line no 20 to any other integer > 0. A file named "placeholder.txt" has been uploaded with the aforementioned modification in line 20 of "CKSAAP.py".  The features used in this paper were extracted by selecting the value of k=8.

A sample feature file has been uploaded named "Sample_Features.csv"

# Validation
Download the followning files:
- CKSAAP_AFP_Pred.py
- models.py
- utilis.py
- data.h5
- my_model.h5
