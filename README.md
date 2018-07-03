# Medical Diagnosis from X-ray Imaging
Deep learning project for Pulmonary pathologies classification and localization from X-ray imaging using Pytorch.
Dataset used: NIH Chest X-ray

**Classification**
The main dataset used for the project implementation is the NIH Chest X-ray Dataset of 14 Common Thorax Diseases from National Institutes of Health - Clinical Center. 
The dataset contains 112120 frontal-view X-ray images of 30,805 unique patients with text-mined fourteen disease image labels (where each image can have multiple labels).
A network surgery was performed on pre-trained models, specifically on DenseNet121, leaving out the fully-connected and the final classification layers,  inserting a transition and prediction layer at the end. Fine tuning over existing weights on the DenseNet121 architecture was performed. We used Binary Cross Entropy Loss (BCEL) for individual probability prediction. 
Area Under the ROC Curve (AUROC/AUC) was used as our main metric.


**Detection**
For the detection task we used 985 pathology samples in a total of 880 different X-rays. Each sample was labeled with its corresponding bounding box information.
For our detection approach we developed experiments with the YOLO(You Only Look Once) architecture.
To adapt the YOLO architecture for our X-ray dataset and additional linear layer with reshaping was added as a final layer for prediction. This final layer is our prediction tensor and was shaped as 7x7x18 when experimenting with a 2 bounding boxes approach.
 

