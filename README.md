# Earthquake vs Blasts

This Project was inspired from the Research Paper "Seismic Signal Discrimination of Earthquakes and Quarry Blasts in North-East Italy Using
Deep Neural Networks"

## Objective

We Use deep learning Model to determine if a seismogram obtained from the feilds in time domain is caused due to a Earthquake or a Blast

## Dataset

- This Project uses 20,000 samples from the Standford Earthquake Dataset (STEAD) where 11000 belong to the Earthquake class and 9,000 belong to quarry blasts

## Feature Engineering

- We add a new coloumn which takes the fourier transform of the seismogram to convert it into frequency domain
- We then split the data into 80% train and 20% Test

## Model

![image.png](attachment:97a6da7f-2c57-4907-8cd2-463a60b56a5c.png)

## Techniques for Optimal Result

- We will use glorot normal initialization
- **Important**: When we ran the model without applying standard scaler it gave horrible result of 51%, it was just predicting every class to be earthquake class
but when we applied standard scaler we saw that a whopping improvement from 51% to 94%. We apply it to both time domain and frequency domain signals
- We use a batch size of 32
- As Suggested in the paper we will be using 4-fold cross validation, but due to lack of computation we will not retrain the whole model but use the 
one giving best validation score
