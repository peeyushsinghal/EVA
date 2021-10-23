Purpose
-------
The purpose is the classify MNIST dataset accurately using Deep Neural network
- 99.4% (this must be consistently shown in your last few epochs, and not a one-time achievement)
- In less than or equal to 15 Epochs
- In less than 10000 Parameters (additional points for doing this in less than 8000 pts)

Structured progress must be shown in all attempts and all attempts must include target, results, and analysis with links

Experiment 1
-------------

**Objective / Target**

  - Initial Setup and Model
  - Getting the model correct
  - Very basic model
  
**Results**

  - Parameters: 6,379,786
  - Best Train Accuracy: 99.92 %
  - Best Test Accuracy: 99.21 %

**Analysis**

  - Large but working model
  - Overfitting (train - test accuracy) > 0
  
**Next Steps**

- Reduce Number of Params
- Remove overfitting

Experiment 2
-------------

**Objective / Target**

  - Reduce params (number of channels are reduced, use of GAP)
  - Reduce Overfitting (used dropout, and BN)
  
**Results**

  - Parameters: 4,038
  - Best Train Accuracy: 97.84 %
  - Best Test Accuracy: 98.46 %

**Analysis**

  - Small Model, but not hitting the accuracy mark
  - Overfitting (train - test accuracy) < 0 is largely containted, model underfits
  
**Next Steps**

- Look to increase accuracy by increasing number of params

Experiment 3
-------------

**Objective / Target**

  - increase accuracy by increasing number of params
  
**Results**

  - Parameters: 9,790
  - Best Train Accuracy: 98.87 %
  - Best Test Accuracy: 99.00 %

**Analysis**

  - Not hitting the accuracy mark
  - Overfitting (train - test accuracy) < 0 is largely containted, model underfits
  - Number of params < 10K
  
**Next Steps**

- Look to increase accuracy

Experiment 4
-------------

**Objective / Target**

  - increase accuracy by increasing number of params by using other tricks...
  - include augmentation
  - step learning rate

**Results**

  - Parameters: 9,590
  - Best Train Accuracy: 98.72%
  - Best Test Accuracy: 99.29%

**Analysis**

  - Not hitting the accuracy mark
  - Overfitting (train - test accuracy) < 0 is largely containted, model underfits
  - Number of params < 10K
  
**Next Steps**

- Look to increase accuracy
