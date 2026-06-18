This project implements a deep learning pipeline to perform semantic segmentation of the gastrointestinal tract (stomach, small bowel, and large bowel) on abdominal CT scan images.

Source Competition: UW-Madison GI Tract Image Segmentation (Kaggle)
Here is the link to the competition: 
(https://www.kaggle.com/competitions/uw-madison-gi-tract-image-segmentation)

I have organized this project into two primary notebooks:
1. Initial orientation and getting to know the dataset: An initial deep dive into the dataset, covering data visualization, distribution analysis, and structural understanding of the scans.
2. The actual segmentation pipleline: The core implementation and pipleline, featuring a U-Net architecture.

---------------------------------------------
---------------------------------------------
---------------------------------------------
Results: (still updating)
Segmentation V_2:
Configuration: Model = U-Net (encoder= 'resnet34'), 30 epochs, loss = Diceloss, optimizer = SGD, NO image augmentation was applied

Best achieved metrics:
- Training Loss: 0.1246
- Validation Loss: 0.1718
- Validation Dice Score: 0.7731
--------------------------------------------
Segmentation V_3:
Configuration: Model = U-Net (encoder= 'resnet34'), 30 epochs, loss = dice_bce_loss, optimizer = Adam, NO image augmentation was applied

Best achieved metrics:
- Training Loss: 0.1834
- Validation Loss: 0.1641
- Validation Dice Score: 0.8068
--------------------------------------------
Segmentation V_4:
Configuration: Same as V_3, just image augmentation feature was added.
Results were almost identical to V_3

