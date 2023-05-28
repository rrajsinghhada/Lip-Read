# Lip_Reading_app

## LipNet: End-to-End Sentence-level Lipreading
<img src="./App/animation.gif" width="338">

## Goal

The objective was to develop a robust deep learning model capable of accurately reading lips from a video, providing us with the spoken sentence by the individual.

## Data

To construct this model, I utilized videos of an individual articulating random words. Subsequently, I employed alignments to precisely annotate the spoken content, which served as training data for the model.


## Model Summary

Model: "sequential"

___________________________________________________________________________
 Layer (type)                          Output Shape              Param # 
===========================================================================
 conv3d (Conv3D)                       (None, 75, 46, 140, 128)  3584      
                                                                 
 activation (Activation)               (None, 75, 46, 140, 128)  0         
                                                                 
 max_pooling3d (MaxPooling3D)           (None, 75, 23, 70, 128)  0                                                       
                                                                 
 conv3d_1 (Conv3D)                     (None, 75, 23, 70, 256)   884992    
                                                                 
 activation_1 (Activation)             (None, 75, 23, 70, 256)   0         
                                                                 
 max_pooling3d_1 (MaxPooling 3D)        (None, 75, 11, 35, 256)  0                                                                      
                                                                 
 conv3d_2 (Conv3D)                     (None, 75, 11, 35, 75)    518475    
                                                                 
 activation_2 (Activation)             (None, 75, 11, 35, 75)    0         
                                                                 
 max_pooling3d_2 (MaxPooling 3D)        (None, 75, 5, 17, 75)    0                                                                   
                                                                 
 time_distributed (TimeDistributed)     (None, 75, 6375)         0                                                                 
                                                                 
 bidirectional (Bidirectional)          (None, 75, 256)          6660096                                                              
                                                                 
 dropout (Dropout)                     (None, 75, 256)           0         
                                                                 
 bidirectional_1 (Bidirectional)        (None, 75, 256)          394240    
                                                                                              
 dropout_1 (Dropout)                   (None, 75, 256)           0         
                                                                 
 dense (Dense)                         (None, 75, 41)            10537     
                                                                 
===========================================================================
Total params: 8,471,924
Trainable params: 8,471,924
Non-trainable params: 0
___________________________________________________________________________


## Dependencies
* Tensorflow 2.0+
* PIP (for package installation)


## Work in Progress
This is a work in progress. Errors are to be expected.
If you found some errors in terms of implementation please report them by submitting issue(s) or making PR(s). Thanks!

## License
MIT License
