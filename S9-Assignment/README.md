Objective
-----------

Write a custom ResNet architecture for CIFAR10 that has the following architecture:

PrepLayer - 
    Conv 3x3 s1, p1) >> BN >> RELU [64k]
  
Layer1 -


    X = Conv 3x3 (s1, p1) >> MaxPool2D >> BN >> RELU [128k]
    R1 = ResBlock( (Conv-BN-ReLU-Conv-BN-ReLU))(X) [128k] 
    Add(X, R1)
  
Layer 2 -


    Conv 3x3 [256k]
    MaxPooling2D
    BN
    ReLU
  
Layer 3 -
    X = Conv 3x3 (s1, p1) >> MaxPool2D >> BN >> RELU [512k]
    R2 = ResBlock( (Conv-BN-ReLU-Conv-BN-ReLU))(X) [512k]
    Add(X, R2)
  
MaxPooling with Kernel Size 4

FC Layer 

SoftMax

Uses One Cycle Policy such that:

    Total Epochs = 24
    Max at Epoch = 5
    LRMIN = FIND
    LRMAX = FIND
NO Annihilation

Uses this transform -
  RandomCrop 32, 32 (after padding of 4) >> FlipLR >> Followed by CutOut(8, 8)

Batch size = 512

Target Accuracy: 90% 


Train and Validation(Test) Statistics
------------------------------------
![image](https://user-images.githubusercontent.com/10797988/143888529-a344ca80-8743-47e4-9500-c23c88372ee2.png)
![image](https://user-images.githubusercontent.com/10797988/143888601-f9656bc7-d9ce-4931-9d1c-82230d36b8d0.png)


Misclassified Images by Network
-------------------------------
![image](https://user-images.githubusercontent.com/10797988/143888661-03a7ba33-6f0c-45f5-bf61-66a5db4f1236.png)


GradCAM output of the misclassified images
------------------------------------------
![image](https://user-images.githubusercontent.com/10797988/143888702-51064e75-88b5-4d6b-a49d-266f19154543.png)

![image](https://user-images.githubusercontent.com/10797988/143888731-c7915c7e-2fe8-4b2a-933a-270f2d00ed20.png)


Training log
-------------
EPOCH: 1
Loss=1.4322515726089478 Batch_id=97 Accuracy=35.47: 100%|██████████| 98/98 [01:43<00:00,  1.06s/it]
Test set: Average loss: 0.0001, Accuracy: 4883/10000 (48.83%)

EPOCH: 2
Loss=1.2158520221710205 Batch_id=97 Accuracy=53.52: 100%|██████████| 98/98 [01:43<00:00,  1.06s/it]
Test set: Average loss: 0.0001, Accuracy: 6006/10000 (60.06%)

EPOCH: 3
Loss=0.9168333411216736 Batch_id=97 Accuracy=61.27: 100%|██████████| 98/98 [01:43<00:00,  1.06s/it]
Test set: Average loss: 0.0001, Accuracy: 6085/10000 (60.85%)

EPOCH: 4
Loss=0.9032187461853027 Batch_id=97 Accuracy=66.27: 100%|██████████| 98/98 [01:44<00:00,  1.06s/it]
Test set: Average loss: 0.0001, Accuracy: 6903/10000 (69.03%)

EPOCH: 5
Loss=0.7975691556930542 Batch_id=97 Accuracy=70.09: 100%|██████████| 98/98 [01:44<00:00,  1.06s/it]
Test set: Average loss: 0.0001, Accuracy: 7074/10000 (70.74%)

EPOCH: 6
Loss=0.7810900807380676 Batch_id=97 Accuracy=72.93: 100%|██████████| 98/98 [01:43<00:00,  1.06s/it]
Test set: Average loss: 0.0001, Accuracy: 7691/10000 (76.91%)

EPOCH: 7
Loss=0.7243731617927551 Batch_id=97 Accuracy=76.08: 100%|██████████| 98/98 [01:44<00:00,  1.06s/it]
Test set: Average loss: 0.0001, Accuracy: 7763/10000 (77.63%)

EPOCH: 8
Loss=0.5636580586433411 Batch_id=97 Accuracy=77.76: 100%|██████████| 98/98 [01:43<00:00,  1.06s/it]
Test set: Average loss: 0.0001, Accuracy: 7937/10000 (79.37%)

EPOCH: 9
Loss=0.563583493232727 Batch_id=97 Accuracy=79.18: 100%|██████████| 98/98 [01:43<00:00,  1.06s/it]
Test set: Average loss: 0.0001, Accuracy: 8072/10000 (80.72%)

EPOCH: 10
Loss=0.5036690831184387 Batch_id=97 Accuracy=80.69: 100%|██████████| 98/98 [01:44<00:00,  1.07s/it]
Test set: Average loss: 0.0001, Accuracy: 8164/10000 (81.64%)

EPOCH: 11
Loss=0.5903857350349426 Batch_id=97 Accuracy=81.91: 100%|██████████| 98/98 [01:44<00:00,  1.06s/it]
Test set: Average loss: 0.0001, Accuracy: 8048/10000 (80.48%)

EPOCH: 12
Loss=0.49352991580963135 Batch_id=97 Accuracy=83.19: 100%|██████████| 98/98 [01:43<00:00,  1.06s/it]
Test set: Average loss: 0.0000, Accuracy: 8241/10000 (82.41%)

EPOCH: 13
Loss=0.5216323733329773 Batch_id=97 Accuracy=83.81: 100%|██████████| 98/98 [01:43<00:00,  1.06s/it]
Test set: Average loss: 0.0000, Accuracy: 8497/10000 (84.97%)

EPOCH: 14
Loss=0.46687230467796326 Batch_id=97 Accuracy=84.75: 100%|██████████| 98/98 [01:44<00:00,  1.06s/it]
Test set: Average loss: 0.0000, Accuracy: 8473/10000 (84.73%)

EPOCH: 15
Loss=0.4551044702529907 Batch_id=97 Accuracy=85.97: 100%|██████████| 98/98 [01:44<00:00,  1.07s/it]
Test set: Average loss: 0.0000, Accuracy: 8555/10000 (85.55%)

EPOCH: 16
Loss=0.3722503185272217 Batch_id=97 Accuracy=86.51: 100%|██████████| 98/98 [01:43<00:00,  1.06s/it]
Test set: Average loss: 0.0000, Accuracy: 8556/10000 (85.56%)

EPOCH: 17
Loss=0.2952621877193451 Batch_id=97 Accuracy=87.19: 100%|██████████| 98/98 [01:43<00:00,  1.06s/it]
Test set: Average loss: 0.0000, Accuracy: 8595/10000 (85.95%)

EPOCH: 18
Loss=0.44956573843955994 Batch_id=97 Accuracy=87.92: 100%|██████████| 98/98 [01:43<00:00,  1.06s/it]
Test set: Average loss: 0.0000, Accuracy: 8702/10000 (87.02%)

EPOCH: 19
Loss=0.3167794644832611 Batch_id=97 Accuracy=88.77: 100%|██████████| 98/98 [01:44<00:00,  1.07s/it]
Test set: Average loss: 0.0000, Accuracy: 8736/10000 (87.36%)

EPOCH: 20
Loss=0.34926944971084595 Batch_id=97 Accuracy=89.27: 100%|██████████| 98/98 [01:44<00:00,  1.06s/it]
Test set: Average loss: 0.0000, Accuracy: 8774/10000 (87.74%)

EPOCH: 21
Loss=0.21581025421619415 Batch_id=97 Accuracy=89.67: 100%|██████████| 98/98 [01:44<00:00,  1.06s/it]
Test set: Average loss: 0.0000, Accuracy: 8768/10000 (87.68%)

EPOCH: 22
Loss=0.2535221576690674 Batch_id=97 Accuracy=90.52: 100%|██████████| 98/98 [01:43<00:00,  1.06s/it]
Test set: Average loss: 0.0000, Accuracy: 8817/10000 (88.17%)

EPOCH: 23
Loss=0.2825440764427185 Batch_id=97 Accuracy=90.61: 100%|██████████| 98/98 [01:43<00:00,  1.06s/it]
Test set: Average loss: 0.0000, Accuracy: 8814/10000 (88.14%)

EPOCH: 24
Loss=0.24924243986606598 Batch_id=97 Accuracy=90.74: 100%|██████████| 98/98 [01:44<00:00,  1.07s/it]
Test set: Average loss: 0.0000, Accuracy: 8807/10000 (88.07%)
