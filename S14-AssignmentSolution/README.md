DETR
-------
DETR (https://arxiv.org/abs/2005.12872) is a object detection model based on trnasformers, it still uses backbone as CNN though. It provides good results viz a viz the rest of the object detection models like fast RCNN family and Single Shot Dection, Yolo

Encoder-decoder architecture
----------------------------
Encoder-Decoder architecture contains two blocks - Encoder with the aim of encoding the information or provide representation, and Decoder with aims to use representation and other conditioned information to perform a task

Bipartite loss
--------------
Bipartitie loss is a loss associated with matching of two list which have equal number of elements, the aim to to minimize overall loss - which happens when the elements of two lists are matched correctly.
In case of DETR, each element contains class information label and bounding box. the loss is at the lowest when the predicted class and bounding box matches with ground truth. This allevates the need of non-max supression kind algorithms


Object queries
---------------
These are conditional information sent to the decoder, which helps decoder attend to elements of encoder vector to perform the tasks better.


Results ( model on dataset)
-------------------------
![image](https://user-images.githubusercontent.com/10797988/150816809-dba05bcc-6d4b-4a34-99ea-f61070376bf3.png)
![image](https://user-images.githubusercontent.com/10797988/150816829-679dd185-1971-4d21-893d-f2676efd13dc.png)

