MNIST Classification with use of Normalization Layers
-----------------------------------------------------
* In order to classify MNIST digits, 3 Normalization techniques are used - Batch Normalization, Layer Normalization and Group Normalization.
* Batch normalization is further used with L1 regularizaion (lambda = 0.001) 
* Test/validation loss and accuracy is understood for all 3 normalization techniques
* 10 Misclassified images are understood and presented, for each normalization technique

Implementation details - Batch Normalization (BN), Layer Normalization (LN) and Group Normalization (GN)
-------------------
* Previous assignment code was taken as base
* The Neural Network Module was changed to take in a parameter in constructor to understand BN, LN, GN
* Based on the param, the corresponding layers were used.
* BN : It is done using the channel as the attribute, futher L1 regularlization was added only for BN (lambda = 0.001)
* LN : It is done using the channel and dimensions of image
* GN : It is done using number of groups and channel as the attribute

Observations
-------------
* The accuracy figures are below than before.

Validation / Test accuracy and loss
--------------------------------------
![image](https://user-images.githubusercontent.com/10797988/140800230-8847ad5c-3e33-4acc-9c31-adb640ccb24b.png)


Misclassification of Images
--------------------------------------
![image](https://user-images.githubusercontent.com/10797988/140800330-1467ec70-30e7-410b-96de-ab08a02052d8.png)
