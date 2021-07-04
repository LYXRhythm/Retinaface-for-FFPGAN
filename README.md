## Retinaface：This is the face detection model for the FFPGAN.
---
## Environment
pytorch==1.2.0
## Catalogue
1. [Performance](#Performance)
2. [Attention](#Attention)
3. [How-to-predict](#How-to-predict)
4. [How-to-train](#How-to-train)
5. [Evaluate](#Evaluate)

## Performance
| Model | Train Dataset | Test Dataset | Easy | Medium | Hard |
| :-----: | :-----: | :------: | :------: | :------: | :-----: |
| RetinaFace(resnet50) | Widerface-Train | Widerface-Val | 94.48% | 93.04% | 84.43% |
| RetinaFace(FFPGAN)-Ours | Widerface-Train | Widerface-Val | 90.07% | 87.16% | 75.82% |

## Attention
In the model_data folder, our model Retinaface_mobilenet_FFPGAN.pth is there, which could be used for prediction directly.

## How-to-predict
1. Run predict.py, and input  
```python
img/timg.jpg
```  
2. In the file predict.py, fps and video test can be set.  

## How-to-train
1. We used widerface dataset for training, and if you want to retrain, download the widerface and put it in the data folder.  
2. Modify the parameters and run the train.py.
3. We could get the model in the logs.  

## Evaluate  
1. In retinaface.py, you should set the right parameters.  
```python
 = {
    "model_path"        : 'model_data/Retinaface_mobilenet0.25.pth',
    "backbone"          : 'mobilenet',
    "confidence"        : 0.5,
    "nms_iou"           : 0.45,
    "cuda"              : True,
    "input_shape"       : [1280, 1280, 3],
    "letterbox_image"   : True
}
```
2. Download the widerface dataset, which inclued the val dataset and decompression it in the root.
3. Run evaluation.py.


