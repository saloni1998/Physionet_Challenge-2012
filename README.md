# Physionet_Challenge-2012-
<b> About the Dataset </b><br>
The data used for the challenge consist of records from 12,000 ICU stays. Out of this ,4000 samples were used as training data. Up to 42 variables were recorded at least once during the first 48 hours after admission to the ICU. Some of the features are Cholestrol,RespRate,Bilirubin,Albumin etc. Highest score achieved on this dataset is shown at this link. https://physionet.org/challenge/2012/top-scores.shtml. 

<b> Data Preprocessing </b><br>
 Not all 42 variables were used in training. Features were removed having high correlation between them. They are :<br>
 1. ALT and AST <br>
 2. NIMAP and NIDiasAMP <br>
 3. NISysABP and NIMAP <br>
 4. SysABP and DiasABP <br>
 5. Lactate and ICUType <br>
 6. HCO3 and PaCO2 <br>
 
 MechVent was also dropped because its value is same throughout the dataset.<br>
 
 <b>As the data is skewed, I used a small portion of the majority class from the data such that both the classes have equal distribution for training. Later prediction was made on the data not included to check the performance of the model</b>
 
<b>Scoring</b><br>
The goal is to predict in-hospital mortality.It is a binary classification.<br>

Scoring for the same is given here https://physionet.org/challenge/2012/ as :<br>

Se = TP / (TP + FN)	[the fraction of in-hospital deaths that are predicted]<br>
+P = TP / (TP + FP)	[the fraction of correct predictions of in-hospital deaths]<br>
<b>Score1 = min(Se,+P)	</b>[the minimum of Sensitivity and positive predictivity]<br>

Highest score achieved is 0.5353.

<b> Results </b><br>

<b> 1. Random Forest Classifier </b><br>

Simply applying the random forest gave a score of <b>0.7213</b> and an accuracy of around 0.703 % <br>

<b> 2. Neural Network </b><br>
The model architecture is based on the concept of stacking of layers taken from VGG16 model. The score achieved is <b>0.751</b> and acuracy obtained is 0.757 on the validation data. The data not taken into training which has samples of survivor (majority class) only gave an accuracy of around <b>70%</b> with this model.


