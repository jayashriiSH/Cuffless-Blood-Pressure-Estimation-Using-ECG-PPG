# Cuffless-Blood-Pressure-Estimation-Using-ECG-PPG

Cuffless Blood Pressure Estimation
In this project, I tried to predict blood pressure (BP) without using a physical cuff — only using two signals from the body:

ECG (electrocardiogram) – tells us about the heart’s electrical activity

PPG (photoplethysmogram) – tracks blood flow using a light sensor
1. ECG, PPG, and BP Signals
<img width="552" height="418" alt="06826db1-aa6c-4611-811d-0a1de94d3a30" src="https://github.com/user-attachments/assets/0542bf8c-87a6-4e39-8d74-513d1becbf19" />
 This graph shows:
SBP (Systolic): Higher line (top value when heart pumps)
DBP (Diastolic): Lower line (resting value)
<img width="571" height="437" alt="625e4f23-7be5-45b2-8ed5-b6be1739ccfa" src="https://github.com/user-attachments/assets/5ed385de-009e-4ad3-b5c5-693924472cb2" />

 process :
Loaded the data
The dataset has ECG, PPG, and real blood pressure values (SBP and DBP). I used .mat or .npy files depending on the format.

Preprocessed the signals
I normalized the data (scaled it between 0 and 1), and split it into smaller time windows (so the model can learn from chunks of signals).

Extracted features
From each segment, I calculated useful values like:

Heart rate

Pulse transit time (how long the pulse takes to travel from ECG to PPG)

Peaks, intervals ect 

Trained machine learning models
I trained a few models like:

Linear Regression

<img width="1337" height="547" alt="b0585e84-2241-468e-a275-2a67c3a955de" src="https://github.com/user-attachments/assets/469f27b2-3ef5-4fba-895e-aaa72e4783f4" />

SVR (Support Vector Regression)

Random Forest Regressor
 

These models tried to learn the connection between the ECG+PPG features and actual BP values.
Evaluated the models
I checked how good the predictions were using:
MAE (Mean Absolute Error)
R² Score (how well the model fits)
Random Forest worked best in my case — it gave the lowest error and better predictions for both SBP and DBP
