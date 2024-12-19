[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/UDdkOEMs)


# AAR Crack detection with CNN and ViT

This project focuses on detecting cracks caused by alkali-aggregate reaction (AAR), which are subtle and challenging to identify. While CNNs are effective for crack detection, their performance declines with microscale cracks, and AAR detection remains under-explored. Building on prior work with limited models like Inception V3, this study explores the performance of pre-trained CNNs in binary classification of AAR cracks.


## Authors

- Nathan Kabas Kuroiwa 
- Amélie Menoud
- Lisa Van de Panne


## Code organization

The project is divided into different notebooks. 

- "Step_0_Data Augmentation.ipynb": In this notebook we have the data augmentation test we performed before choosing the one for our final model. 

- "Step_1_Model_archi.ipynb": This is the notebook in which we did the search for the best model architecture, by comparating the losses, AUC's and F1-score. 

- "Step_2_Pretraining_and_training.ipynb": Here, we are experimenting with a pretrained or non pretrained Googlenet model, which was the model with the best performance from step 1. 


- "Step_3_Hyperparameters_tuning_1.ipynb" and "Step_3_Hyperparameters_tuning_2.ipynb": These files contains our trials with different learning rates and decreasing learning rate strategy. We used these strategy: constant LR, cosine LR schedulers and  ReduceLROnPlateau, which reduces the LR when a metric has stopped improving. 

- "Step_4_Results.ipynb": The results of our best model with the best hyperparameters and data augmentation from the last files. A visualization of our results are shown with ROC curves, use of the gradient method and a visualization of the results per walls. Also the final results of accuracies, F1-scores and losses are provided.

- "Vit Transformer.ipynb": This final notebook contains the attempt of ViT transformers, with the use of vit-tiny and vit-b-16 and their results. 



## Usage: 

We used googlecolab for the project, and all the codes work with a path to a google drive that contains the data (the link to this drive is provided only to the IMOS lab). 

To make the code work, the path to the data at the beginning of each notebook should be changed. Also, the data needs to be prepared: Manually put the clean and cracked images in folders called "Clean" and "Cracked" for each split, so that the dataloader can work. Then, when training the code, the saving path should also be changed. And lastly, the path to load the models should be changed as well. 

The weights for the final model are provided in the github as the file 'GoogLeNet_trial_1_best.pth', and can be used in the "Step_4_Results.ipynb" to reproduce our final results.

## About the txt files:

- Three txt files containing the details of our final predictions are provided (training_set.txt, validation_set.txt, test_set.txt).

- requirements.txt: file containing all external libraries used.

