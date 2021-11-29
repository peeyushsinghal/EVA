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
Loss=1.3305370807647705 Batch_id=97 Accuracy=37.58: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0001, Accuracy: 5299/10000 (52.99%)

EPOCH: 2
Loss=1.2330145835876465 Batch_id=97 Accuracy=55.47: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0001, Accuracy: 6184/10000 (61.84%)

EPOCH: 3
Loss=0.981168270111084 Batch_id=97 Accuracy=62.97: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0001, Accuracy: 6997/10000 (69.97%)

EPOCH: 4
Loss=0.8501313328742981 Batch_id=97 Accuracy=68.68: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0001, Accuracy: 6860/10000 (68.60%)

EPOCH: 5
Loss=0.8192320466041565 Batch_id=97 Accuracy=72.66: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0001, Accuracy: 7704/10000 (77.04%)

EPOCH: 6
Loss=0.6596350073814392 Batch_id=97 Accuracy=75.80: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0001, Accuracy: 7907/10000 (79.07%)

EPOCH: 7
Loss=0.4861445128917694 Batch_id=97 Accuracy=77.86: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0001, Accuracy: 8073/10000 (80.73%)

EPOCH: 8
Loss=0.6025633811950684 Batch_id=97 Accuracy=79.65: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0001, Accuracy: 8104/10000 (81.04%)

EPOCH: 9
Loss=0.5482447147369385 Batch_id=97 Accuracy=81.25: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0001, Accuracy: 8299/10000 (82.99%)

EPOCH: 10
Loss=0.5739644765853882 Batch_id=97 Accuracy=82.60: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0001, Accuracy: 8301/10000 (83.01%)

EPOCH: 11
Loss=0.5005548596382141 Batch_id=97 Accuracy=83.60: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0000, Accuracy: 8357/10000 (83.57%)

EPOCH: 12
Loss=0.3860888183116913 Batch_id=97 Accuracy=84.73: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0000, Accuracy: 8515/10000 (85.15%)

EPOCH: 13
Loss=0.3348631262779236 Batch_id=97 Accuracy=85.85: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0000, Accuracy: 8501/10000 (85.01%)

EPOCH: 14
Loss=0.38578006625175476 Batch_id=97 Accuracy=86.99: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0000, Accuracy: 8592/10000 (85.92%)

EPOCH: 15
Loss=0.3191969394683838 Batch_id=97 Accuracy=87.58: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0000, Accuracy: 8610/10000 (86.10%)

EPOCH: 16
Loss=0.41100677847862244 Batch_id=97 Accuracy=88.46: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0000, Accuracy: 8713/10000 (87.13%)

EPOCH: 17
Loss=0.35348325967788696 Batch_id=97 Accuracy=89.14: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0000, Accuracy: 8703/10000 (87.03%)

EPOCH: 18
Loss=0.3318176567554474 Batch_id=97 Accuracy=90.00: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0000, Accuracy: 8823/10000 (88.23%)

EPOCH: 19
Loss=0.3275820314884186 Batch_id=97 Accuracy=90.67: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0000, Accuracy: 8886/10000 (88.86%)

EPOCH: 20
Loss=0.24565726518630981 Batch_id=97 Accuracy=91.52: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0000, Accuracy: 8892/10000 (88.92%)

EPOCH: 21
Loss=0.2497399002313614 Batch_id=97 Accuracy=92.06: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0000, Accuracy: 8918/10000 (89.18%)

EPOCH: 22
Loss=0.1872614622116089 Batch_id=97 Accuracy=92.58: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0000, Accuracy: 8968/10000 (89.68%)

EPOCH: 23
Loss=0.20135940611362457 Batch_id=97 Accuracy=92.88: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0000, Accuracy: 8965/10000 (89.65%)

EPOCH: 24
Loss=0.16695024073123932 Batch_id=97 Accuracy=92.98: 100%|██████████| 98/98 [01:42<00:00,  1.05s/it]

Test set: Average loss: 0.0000, Accuracy: 8960/10000 (89.60%)
