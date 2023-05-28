# Lip_Reading_app

## End-to-End Sentence-level Lipreading
<img src="./App/animation.gif" width="338">

## Goal

The objective was to develop a robust deep learning model capable of accurately reading lips from a video, providing us with the spoken sentence by the individual.

## Data

To construct this model, I utilized videos of an individual articulating random words. Subsequently, I employed alignments to precisely annotate the spoken content, which served as training data for the model.

## Overview
___________________________________________________________________________
* I constructed a data pipeline that utilizes a data load function to retrieve videos and their respective alignments.

* Constructed the vocab to change the allignments into tokens i.e. char to num and num to char for converting the data predicted back to character.

* Additionally, I created a vocabulary to convert alignments into tokens and also tokens back to character allowing the conversion of predicted data back to sentence.

* The video data underwent a process of frame extraction, followed by conversion into numpy arrays, enabling efficient data representation. Simultaneously, the alignments associated with the videos were tokenized, preparing them for model training and analysis.

* To analyze the video frames, I employed a convolutional neural network, and further enhanced the model's training by incorporating bidirectional LSTMs within a powerful architecture.

* Then after training the model I used streamlit module of python to upload the model and videos to show the working of model on different model in real time.
___________________________________________________________________________
## Model Summary

Model: "sequential"

| Layer (type)                       |   Output Shape             | Param #  |
| :---                               |   :---                     | :---     | 
| conv3d (Conv3D)                    |   (None, 75, 46, 140, 128) | 3584     |                                                               
| activation (Activation)            |   (None, 75, 46, 140, 128) | 0        |  
| max_pooling3d (MaxPooling3D)       |   (None, 75, 23, 70, 128)  | 0        |                                                               
| conv3d_1 (Conv3D)                  |   (None, 75, 23, 70, 256)  | 884992   |  
| activation_1 (Activation)          |   (None, 75, 23, 70, 256)  | 0        |  
| max_pooling3d_1 (MaxPooling 3D)    |   (None, 75, 11, 35, 256)  | 0        |                                                               
| conv3d_2 (Conv3D)                  |   (None, 75, 11, 35, 75)   | 518475   |  
| activation_2 (Activation)          |   (None, 75, 11, 35, 75)   | 0        |  
| max_pooling3d_2 (MaxPooling 3D)    |   (None, 75, 5, 17, 75)    | 0        |                                                            
| time_distributed (TimeDistributed) |   (None, 75, 6375)         | 0        |                                                          
| bidirectional (Bidirectional)      |   (None, 75, 256)          | 6660096  |                                                             
| dropout (Dropout)                  |   (None, 75, 256)          | 0        |  
| bidirectional_1 (Bidirectional)    |   (None, 75, 256)          | 394240   |                
| dropout_1 (Dropout)                |   (None, 75, 256)          | 0        |  
| dense (Dense)                      |   (None, 75, 41)           | 10537    | 

___________________________________________________________________________
Total params: 8,471,924 | Trainable params: 8,471,924 | Non-trainable params: 0
___________________________________________________________________________

## Dependencies
* Tensorflow 2.0+
* PIP (for package installation)

## Installation

1. Clone the project:
```
$ git clone https://github.com/rrajsinghhada/Lip_Reading_app
$ cd Lip_Reading_app
```
2. Install the required dependencies by running the following command:
```
pip install requirement.txt
```
3. Run the Lip-reading_model_trainer.ipynb file
___________________________________________________________________________
1. This file contains the command to download the data required to train the model and also the pretrained model.
2. This file also contaiins the code to train the model.
___________________________________________________________________________
4. Run the following command to deploy the model as local host
```
cd App 
streamlit run streamlitapp.py
```


## Work in Progress
This is a work in progress. Errors are to be expected.
If you found some errors in terms of implementation please report them by submitting issue(s) or making PR(s). Thanks!

## License
MIT License
