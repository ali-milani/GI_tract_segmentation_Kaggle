
<img width="783" height="402" alt="1780849967403" src="https://github.com/user-attachments/assets/6fd4238b-7287-4631-ab09-42451ca1f6d9" />


<br><br>
# UW-Madison GI Tract Image Segmentation

This project presents a deep learning-based approach for semantic segmentation of gastrointestinal tract structures, specifically the stomach, small bowel, and large bowel, from abdominal CT scan images.

It is based on the [UW-Madison GI Tract Image Segmentation](https://www.kaggle.com/competitions/uw-madison-gi-tract-image-segmentation) competition hosted on Kaggle, which focuses on the automated delineation of healthy organs in medical scans to support more accurate radiotherapy planning and cancer treatment.

The work has been organized into two primary notebooks:

- **Orientation (EDA) notebook**: In this notebook I have tried to get to know the dataset and familiarize my self with the images and masks
- **Segmentation notebook(s)**: These are the notebooks that contain the segmentation pipeline. I have included multiple versions of the work in a chronological order, as I was gradually improving the pipleline, to document its development over time.
  

---------------------------------------------
⏳ **Results (still updating):**
---------------------------------------------

🛑 Segmentation V_2:  
🚧 Model = U-Net (encoder= 'resnet34'), 30 epochs, loss = Diceloss, optimizer = SGD, NO image augmentation was applied  
🧪 Best achieved metrics:
- Training Loss: 0.1246
- Validation Loss: 0.1718
- Validation Dice coefficient: 0.7731

🛑 Segmentation V_3:  
🚧 Model = U-Net (encoder= 'resnet34'), 30 epochs, loss = dice_bce_loss, optimizer = Adam, NO image augmentation was applied
🧪 Best achieved metrics:
- Training Loss: 0.1834
- Validation Loss: 0.1641
- Validation Dice coefficient: 0.8068

🛑 Segmentation V_4:  
🚧 Same as V_3, just image augmentation feature was added.   
🧪 Best achieved metrics:
The results were almost identical to the V_3

🛑 Segmentation V_5:  
🚧 Model = U-Net (encoder= 'timm-efficientnet-b4'), 30 epochs, loss = dice_bce_loss, optimizer = Adam, NO image augmentation was applied  
🧪 Best achieved metrics:
- Training Loss: 0.1239
- Validation Loss: 0.1483
- Validation Dice coefficient: 0.8234

🛑 Segmentation V_6:  
🚧 identical to V_5 but image augmentation was added  
🧪 Best achieved metrics:
- Training Loss: 0.1516
- Validation Loss: 0.1352
- Validation Dice coefficient: 0.8288

🛑 Segmentation V_7:  
🚧 identical to V_6 but a method refered to as 2.5D approach was used. This is basically 2D approach but since data from three slices are simultaneously given to the model, people call it 2.5D. This method was recommended by best solutions authors on Kaggle competition website.  
🧪 Best achieved metrics:
- Training Loss: 0.1641
- Validation Loss: 0.1130
- Validation Dice coefficient: 0.8522
