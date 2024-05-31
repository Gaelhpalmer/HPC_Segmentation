# Project information
<p>This is a toy project aimed at getting some familiarity working with image segmentation tasks. I have selected a dataset containing MRIs of the hippocampus obtained from the <a href="http://medicaldecathlon.com/">Medical Segmentation Decathelon</a>. 

The dataset contains 349 3D volumes (263 Training  & 131 Testing) obtained from a Mono-modal MRI. These 3D volumes are stored in .nii formatted files.

### Actions to be taken

The goal is to first select a single sagital slice to work with based on the labels and images in the dataset. Then, data cleaning will be done ro remove any images which have mismatched labels. A subset of training data (60 images) will be reserved for model evaluation.

Next, a CNN pipeline will be constructed using ResNET-50 architecture. The CNN will be trained on the the sagital slices and labels identified in the exploratory analysis. Hyperparameter tuning and optimizer selection will be done using multi-fold cross-validation. 

Once sufficient cross-val scores are obtained, the model will be evaluated using the test images as well as the reserved training data. The reserved training data will be used to calculate Dice correspondance scores between the CNN's segmentation performance and the training masks.