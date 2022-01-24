Vision Transfomer
=================
Dataset = https://www.kaggle.com/c/dogs-vs-cats-redux-kernels-edition/data

How it works
-------------
ViT breaks an input image of 16×16 to a  sequence of patches, just like a series of word embeddings generated by an NLP Transformers. Each patch gets flattened into a single vector in a series of interconnected channels of all pixels in a patch, then projects it to desired input dimension. Because transformers operate in self-attention mode, and they do not necessarily depend on the structure of the input elements, which in turns helps the architecture to learn and relate sparsely-distributed information more efficiently. In Vit, the relationship between the patches in an image is not known and thus allows it to learn more relevant features from the training data and encode in positional embedding in ViT. 

Training Logs
-------------
100%
313/313 [03:36<00:00, 1.82it/s]
Epoch : 1 - loss : 0.6969 - acc: 0.5048 - val_loss : 0.6916 - val_acc: 0.5423

100%
313/313 [03:19<00:00, 1.82it/s]
Epoch : 2 - loss : 0.6923 - acc: 0.5189 - val_loss : 0.6878 - val_acc: 0.5459

100%
313/313 [03:16<00:00, 1.86it/s]
Epoch : 3 - loss : 0.6862 - acc: 0.5486 - val_loss : 0.6779 - val_acc: 0.5718

100%
313/313 [03:18<00:00, 1.80it/s]
Epoch : 4 - loss : 0.6726 - acc: 0.5807 - val_loss : 0.6676 - val_acc: 0.5941

100%
313/313 [03:17<00:00, 1.84it/s]
Epoch : 5 - loss : 0.6634 - acc: 0.5918 - val_loss : 0.6670 - val_acc: 0.5874

Test_Output
-----------
![image](https://user-images.githubusercontent.com/10797988/148806746-2117f3af-887d-47c6-8b8f-f6737d2531b4.png)