Model Code
------------
Please see model file:  https://github.com/peeyushsinghal/EVA/blob/main/S7-Assignment/model.py

Torch Summary
-------------
       Layer (type)               Output Shape         Param #
            Conv2d-1           [-1, 32, 32, 32]             896
              ReLU-2           [-1, 32, 32, 32]               0
       BatchNorm2d-3           [-1, 32, 32, 32]              64
           Dropout-4           [-1, 32, 32, 32]               0
            Conv2d-5           [-1, 32, 32, 32]           9,248
              ReLU-6           [-1, 32, 32, 32]               0
       BatchNorm2d-7           [-1, 32, 32, 32]              64
           Dropout-8           [-1, 32, 32, 32]               0
            Conv2d-9           [-1, 32, 32, 32]           9,248
             ReLU-10           [-1, 32, 32, 32]               0
      BatchNorm2d-11           [-1, 32, 32, 32]              64
          Dropout-12           [-1, 32, 32, 32]               0
           Conv2d-13           [-1, 32, 16, 16]           9,248
             ReLU-14           [-1, 32, 16, 16]               0
      BatchNorm2d-15           [-1, 32, 16, 16]              64
          Dropout-16           [-1, 32, 16, 16]               0
           Conv2d-17           [-1, 32, 16, 16]             320
           Conv2d-18           [-1, 32, 16, 16]           1,056
             ReLU-19           [-1, 32, 16, 16]               0
      BatchNorm2d-20           [-1, 32, 16, 16]              64
          Dropout-21           [-1, 32, 16, 16]               0
           Conv2d-22           [-1, 32, 16, 16]           9,248
             ReLU-23           [-1, 32, 16, 16]               0
      BatchNorm2d-24           [-1, 32, 16, 16]              64
          Dropout-25           [-1, 32, 16, 16]               0
           Conv2d-26             [-1, 32, 8, 8]           9,248
             ReLU-27             [-1, 32, 8, 8]               0
      BatchNorm2d-28             [-1, 32, 8, 8]              64
          Dropout-29             [-1, 32, 8, 8]               0
           Conv2d-30             [-1, 32, 6, 6]           9,248
             ReLU-31             [-1, 32, 6, 6]               0
      BatchNorm2d-32             [-1, 32, 6, 6]              64
          Dropout-33             [-1, 32, 6, 6]               0
           Conv2d-34             [-1, 32, 6, 6]           9,248
             ReLU-35             [-1, 32, 6, 6]               0
      BatchNorm2d-36             [-1, 32, 6, 6]              64
          Dropout-37             [-1, 32, 6, 6]               0
           Conv2d-38             [-1, 32, 3, 3]           9,248
             ReLU-39             [-1, 32, 3, 3]               0
      BatchNorm2d-40             [-1, 32, 3, 3]              64
          Dropout-41             [-1, 32, 3, 3]               0
           Conv2d-42             [-1, 32, 3, 3]           9,248
             ReLU-43             [-1, 32, 3, 3]               0
      BatchNorm2d-44             [-1, 32, 3, 3]              64
          Dropout-45             [-1, 32, 3, 3]               0
           Conv2d-46             [-1, 32, 3, 3]             320
           Conv2d-47             [-1, 10, 3, 3]             330
        AvgPool2d-48             [-1, 10, 1, 1]               0

Total params: 86,858
Trainable params: 86,858
Non-trainable params: 0


Input size (MB): 0.01
Forward/backward pass size (MB): 3.97
Params size (MB): 0.33
Estimated Total Size (MB): 4.31


Albumentation Transformations
-----------------------------
    train_transforms = A.Compose([
        A.HorizontalFlip(p=0.2),
        A.ShiftScaleRotate(shift_limit=0.1, scale_limit=0.1, rotate_limit=10, p=0.2),
        A.CoarseDropout(
            max_holes=1, max_height=16, max_width=16, min_holes=1, min_height=16, min_width=16, fill_value=tuple((x * 255.0 for x in mean)), p=0.2,
        ),
        A.ToGray(p=0.15),
        A.Normalize(mean=mean, std=std_dev, always_apply=True),
        ToTensorV2(),
    ])

    test_transforms = A.Compose([
        A.Normalize(mean=mean, std=std_dev, always_apply=True),
        ToTensorV2(),
    ])


Training Log
-------------
