Pytorch Assignment
--------------
The aim to create a neural network that take 2 inputs:
  1. an image from the MNIST dataset (say 5), and
  2. a random number between 0 and 9, (say 7)
  
and gives two outputs:
  1. the "number" that was represented by the MNIST image (predict 5), and
  2. the "sum" of this number with the random number and the input image to the network (predict 5 + 7 = 12)
 
 Data Strategy
----------------
 Extended datasets.MNIST class and modified __getitem__() in the child such that 
 - a random integer between 0 and 9 is added 
 - it provides not only the label of the image, but also sum of the label and the random integer

Further dataloaders - train and test loader were created

Network
------------
The network takes in two inputs
1. Image : This is passed through CNN (conv1->conv2->maxpool) twice, to understand a representation / embedding, which is then flattened
2. Random Number : The random number is converted into one hot encoding 

the image representation and random number (one hot encoding) is concatenated

The network then have two heads of fully connected layers, have similar forward (FC1->FC2->OUT), with only the out layer having different out features viz 10 and 19. 

Loss Function
----------
Tested with many loss functions - used F.nll_loss, as it provided reducing loss
The loss function was applied to individual losses - label loss and sum loss
Then the loss was averaged and back propogated

Training and Test Function
-------------------------
 Train function takes in model, train_loader (data), optimizer and epoch and then trains the model
 It is a single epoch train function, it is expected that it would be inside a loop
    - model - network
    - device - GPU or CPU
    - train_loader - custom train loader
    - optimizer - optimizer object
    - epoch - epoch number, in a loop typically executed
    
  Test function takes in model, test_loader (data), and evaluates the model
    - model - network
    - device - GPU or CPU
    - test_loader - custom test data loader
    
  Sample Test
  -----------
  some samples were tested after training
  
  Training and Test logs
  ----------------------
  Inside Training epoch - 1, processing step 1 , Training loss: -0.109375
Inside Training epoch - 1, processing step 101 , Training loss: -0.125
Inside Training epoch - 1, processing step 201 , Training loss: -0.0625
Inside Training epoch - 1, processing step 301 , Training loss: -0.015625
Inside Training epoch - 1, processing step 401 , Training loss: -0.125
Inside Training epoch - 1, processing step 501 , Training loss: -0.109375
Inside Training epoch - 1, processing step 601 , Training loss: -0.109375
Inside Training epoch - 1, processing step 701 , Training loss: -0.125
Inside Training epoch - 1, processing step 801 , Training loss: -0.078125
Inside Training epoch - 1, processing step 901 , Training loss: -0.140625
Inside Training epoch - 1, processing step 1001 , Training loss: -0.140625
Inside Training epoch - 1, processing step 1101 , Training loss: -0.15625
Inside Training epoch - 1, processing step 1201 , Training loss: -0.0625
Inside Training epoch - 1, processing step 1301 , Training loss: -0.125
Inside Training epoch - 1, processing step 1401 , Training loss: -0.125
Inside Training epoch - 1, processing step 1501 , Training loss: -0.0625
Inside Training epoch - 1, processing step 1601 , Training loss: -0.125
Inside Training epoch - 1, processing step 1701 , Training loss: -0.046875
Inside Training epoch - 1, processing step 1801 , Training loss: -0.09375
After completion of epoch 1   Training loss: -0.09375
Testing...
Test loss: -5.917500011622906 total_correct_label: 5918 accuracy_labels: 9.863 %  total_correct_sum: 5917 accuracy_correct_sum: 9.862 % 
Inside Training epoch - 2, processing step 1 , Training loss: -0.1875
Inside Training epoch - 2, processing step 101 , Training loss: -0.109375
Inside Training epoch - 2, processing step 201 , Training loss: -0.15625
Inside Training epoch - 2, processing step 301 , Training loss: -0.109375
Inside Training epoch - 2, processing step 401 , Training loss: -0.140625
Inside Training epoch - 2, processing step 501 , Training loss: -0.140625
Inside Training epoch - 2, processing step 601 , Training loss: -0.09375
Inside Training epoch - 2, processing step 701 , Training loss: -0.140625
Inside Training epoch - 2, processing step 801 , Training loss: -0.109375
Inside Training epoch - 2, processing step 901 , Training loss: -0.046875
Inside Training epoch - 2, processing step 1001 , Training loss: -0.0625
Inside Training epoch - 2, processing step 1101 , Training loss: -0.046875
Inside Training epoch - 2, processing step 1201 , Training loss: -0.09375
Inside Training epoch - 2, processing step 1301 , Training loss: -0.078125
Inside Training epoch - 2, processing step 1401 , Training loss: -0.046875
Inside Training epoch - 2, processing step 1501 , Training loss: -0.140625
Inside Training epoch - 2, processing step 1601 , Training loss: -0.09375
Inside Training epoch - 2, processing step 1701 , Training loss: -0.21875
Inside Training epoch - 2, processing step 1801 , Training loss: -0.15625
After completion of epoch 2   Training loss: -0.109375
Testing...
Test loss: -5.905499994754791 total_correct_label: 5918 accuracy_labels: 9.863 %  total_correct_sum: 5893 accuracy_correct_sum: 9.822 % 
Inside Training epoch - 3, processing step 1 , Training loss: -0.125
Inside Training epoch - 3, processing step 101 , Training loss: -0.078125
Inside Training epoch - 3, processing step 201 , Training loss: -0.109375
Inside Training epoch - 3, processing step 301 , Training loss: -0.25
Inside Training epoch - 3, processing step 401 , Training loss: -0.078125
Inside Training epoch - 3, processing step 501 , Training loss: -0.0625
Inside Training epoch - 3, processing step 601 , Training loss: -0.078125
Inside Training epoch - 3, processing step 701 , Training loss: -0.09375
Inside Training epoch - 3, processing step 801 , Training loss: -0.125
Inside Training epoch - 3, processing step 901 , Training loss: -0.09375
Inside Training epoch - 3, processing step 1001 , Training loss: -0.0625
Inside Training epoch - 3, processing step 1101 , Training loss: -0.078125
Inside Training epoch - 3, processing step 1201 , Training loss: -0.109375
Inside Training epoch - 3, processing step 1301 , Training loss: -0.125
Inside Training epoch - 3, processing step 1401 , Training loss: -0.0625
Inside Training epoch - 3, processing step 1501 , Training loss: -0.140625
Inside Training epoch - 3, processing step 1601 , Training loss: -0.15625
Inside Training epoch - 3, processing step 1701 , Training loss: -0.078125
Inside Training epoch - 3, processing step 1801 , Training loss: -0.09375
After completion of epoch 3   Training loss: -0.09375
Testing...
Test loss: -5.936000011861324 total_correct_label: 5918 accuracy_labels: 9.863 %  total_correct_sum: 5954 accuracy_correct_sum: 9.923 % 
Inside Training epoch - 4, processing step 1 , Training loss: -0.09375
Inside Training epoch - 4, processing step 101 , Training loss: -0.109375
Inside Training epoch - 4, processing step 201 , Training loss: -0.140625
Inside Training epoch - 4, processing step 301 , Training loss: -0.03125
Inside Training epoch - 4, processing step 401 , Training loss: -0.09375
Inside Training epoch - 4, processing step 501 , Training loss: -0.125
Inside Training epoch - 4, processing step 601 , Training loss: -0.109375
Inside Training epoch - 4, processing step 701 , Training loss: -0.15625
Inside Training epoch - 4, processing step 801 , Training loss: -0.125
Inside Training epoch - 4, processing step 901 , Training loss: -0.140625
Inside Training epoch - 4, processing step 1001 , Training loss: -0.0625
Inside Training epoch - 4, processing step 1101 , Training loss: -0.0625
Inside Training epoch - 4, processing step 1201 , Training loss: -0.078125
Inside Training epoch - 4, processing step 1301 , Training loss: -0.078125
Inside Training epoch - 4, processing step 1401 , Training loss: -0.109375
Inside Training epoch - 4, processing step 1501 , Training loss: -0.0625
Inside Training epoch - 4, processing step 1601 , Training loss: -0.046875
Inside Training epoch - 4, processing step 1701 , Training loss: -0.09375
Inside Training epoch - 4, processing step 1801 , Training loss: -0.125
After completion of epoch 4   Training loss: -0.140625
Testing...
Test loss: -5.998000018298626 total_correct_label: 5918 accuracy_labels: 9.863 %  total_correct_sum: 6078 accuracy_correct_sum: 10.13 % 
Inside Training epoch - 5, processing step 1 , Training loss: -0.1875
Inside Training epoch - 5, processing step 101 , Training loss: -0.109375
Inside Training epoch - 5, processing step 201 , Training loss: -0.0625
Inside Training epoch - 5, processing step 301 , Training loss: -0.109375
Inside Training epoch - 5, processing step 401 , Training loss: -0.109375
Inside Training epoch - 5, processing step 501 , Training loss: -0.0625
Inside Training epoch - 5, processing step 601 , Training loss: -0.078125
Inside Training epoch - 5, processing step 701 , Training loss: -0.1875
Inside Training epoch - 5, processing step 801 , Training loss: -0.15625
Inside Training epoch - 5, processing step 901 , Training loss: -0.109375
Inside Training epoch - 5, processing step 1001 , Training loss: -0.125
Inside Training epoch - 5, processing step 1101 , Training loss: -0.125
Inside Training epoch - 5, processing step 1201 , Training loss: -0.0625
Inside Training epoch - 5, processing step 1301 , Training loss: -0.0625
Inside Training epoch - 5, processing step 1401 , Training loss: -0.1875
Inside Training epoch - 5, processing step 1501 , Training loss: -0.09375
Inside Training epoch - 5, processing step 1601 , Training loss: -0.109375
Inside Training epoch - 5, processing step 1701 , Training loss: -0.0625
Inside Training epoch - 5, processing step 1801 , Training loss: -0.09375
After completion of epoch 5   Training loss: -0.0625
Testing...
Test loss: -5.9285000041127205 total_correct_label: 5918 accuracy_labels: 9.863 %  total_correct_sum: 5939 accuracy_correct_sum: 9.898 % 





