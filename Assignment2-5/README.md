Pytorch Assignment
--------------
The aim to create a neural network that take 2 inputs:
  1. an image from the MNIST dataset (say 5), and
  2. a random number between 0 and 9, (say 7)
  
and gives two outputs:
  1. the "number" that was represented by the MNIST image (predict 5), and
  2. the "sum" of this number with the random number and the input image to the network (predict 5 + 7 = 12)
 
 Data Strategy
 _________________
 Extended datasets.MNIST class and modified __getitem__() in the child such that 
 - a random integer between 0 and 9 is added 
 - it provides not only the label of the image, but also sum of the label and the random integer

Further dataloaders - train and test loader were created

Network
_________________
The network takes in two inputs
1. Image : This is passed through CNN (conv1->conv2->maxpool) twice, to understand a representation / embedding, which is then flattened
2. Random Number : The random number is converted into one hot encoding 

the image representation and random number (one hot encoding) is concatenated

The network then have two heads of fully connected layers, have similar forward (FC1->FC2->OUT), with only the out layer having different out features viz 10 and 19. 




