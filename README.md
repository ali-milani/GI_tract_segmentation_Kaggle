This project implements a deep learning pipeline to perform semantic segmentation of the gastrointestinal tract (stomach, small bowel, and large bowel) on abdominal CT scan images.

Source Competition: UW-Madison GI Tract Image Segmentation (Kaggle)
Here is the link to the competition: 
(https://www.kaggle.com/competitions/uw-madison-gi-tract-image-segmentation)

I have organized this project into two primary notebooks:
1. Initial orientation and getting to know the dataset: An initial deep dive into the dataset, covering data visualization, distribution analysis, and structural understanding of the scans.
2. The actual segmentation pipleline: The core implementation and pipleline, featuring a U-Net architecture.

---------------------------------------------
Results (still updating):
---------------------------------------------
Segmentation V_2:
Configuration: Model = U-Net (encoder= 'resnet34'), 30 epochs, loss = Diceloss, optimizer = SGD, NO image augmentation was applied

Best achieved metrics:
- Training Loss: 0.1246
- Validation Loss: 0.1718
- Validation Dice coefficient: 0.7731
--------------------------------------------
Segmentation V_3:
Configuration: Model = U-Net (encoder= 'resnet34'), 30 epochs, loss = dice_bce_loss, optimizer = Adam, NO image augmentation was applied

Best achieved metrics:
- Training Loss: 0.1834
- Validation Loss: 0.1641
- Validation Dice coefficient: 0.8068
--------------------------------------------
Segmentation V_4:
Configuration: Same as V_3, just image augmentation feature was added. The results were almost identical to the V_3

--------------------------------------------
Segmentation V_5:
Configuration: Model = U-Net (encoder= 'timm-efficientnet-b4'), 30 epochs, loss = dice_bce_loss, optimizer = Adam, NO image augmentation was applied

Best achieved metrics:
- Training Loss: 0.1239
- Validation Loss: 0.1483
- Validation Dice coefficient: 0.8234
---------------------------------------------
Segmentation V_6:
Configuration: identical to V_5 but image augmentation was added
- Training Loss: 0.1516
- Validation Loss: 0.1352
- Validation Dice coefficient: 0.8288
- ---------------------------------------------
Segmentation V_7:
Configuration: identical to V_6 but a new approch applied:
The authors of top solutions in Kaggle competition page for this project have recommended adding a classifier model to the very begining of the pipeline.
Based on these recommendations I added a classifier unit to the begining of the pipelie and got a significant improvement in the results. However, there are few things notable: 
The augementation startegy that I have applied thus far is a weak one. Also, the number of epochs that I run the segmentation loop is fairly low (n=30). i have also trained the classifier only for (n=8) epochs.
I think, these factors are required to be addressed before we can harvest the full impact of the classifier unit.
BY THE WAY, my new results:
- Training Loss: 0.1399
- Validation Loss: 0.5385
- Validation Dice coefficient: 0.8344
