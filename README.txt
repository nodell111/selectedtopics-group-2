# selectedtopics-group-2

For assessing the deadwood (debris) detection with drone imagery, a deep learning classification model has been developed using Keras from TensorFlow. 
A CNN (Convolutional neural network) was implemented with 4 layers; 2 convolutional and 2 max-pooling ones. Accuracy parameters were calculated and 
programmed to be displayed graphically as well as the recognition results.

> For model.ipynb: 
  - This model works with tiles of 64 x 64 pixels that describe the characteristics of the groups that need to be classified. For a correct reading of
    the tiles, it is preferred that they are stored in folders named 'debris', 'forest' and 'water'.
  - path = 'data/' defines where the tiles are going to be read from (.jpeg works with this model). 
  - The parameters categories 'debris', 'forest', 'water' define the three classes the classification may belong to. All resulting tiles are split into 
    two groups 80% for training the CNN and 20% for validating the given model.
  - After all images are checked for fitting the tile size, the CNN starts taking form `early` the early stopping method from keras.callbacks. It is 
    used to prevent overfitting (as it stops when the accuracy reaches its peak and starts to decrease). Once reached the optimal form, the model is 
    applied and the metrics can be calculated.
  - From `hist` result, accuracy can be plotted and saved as desired (if we add the saving). With `confusion_matrix` and `accuracy_score` from sklearn.metrics
    confusion matrix can be created and saved as an image.
  - Additionally, an image different from the ones used to build up the tiles can be used to test the recognition model.
  - Finally, the created model is saved with .h5 extension.
> For results.ipynb
  - loadimg()and tile() functions are defined for reading the tiles (.jpeg works with this code).
  - dir_image and dir_tile set respectively the path of the image that is to be recognized and the tiles for running the model defined in model.ipynb,
    and additionally the contrast and brightness for the recognized image is redeuced on a 66% and 50% respectively. Then it is tiled in 64 x 64-pixel
    size for applying  .h5 model priorly saved.
  -The resulting image can be saved either with a null transparency layer of detection or an alpha = 0.3 as a .jpeg image in any chosen folder.

