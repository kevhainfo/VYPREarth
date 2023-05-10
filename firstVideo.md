plz add important stuff not mentioned

GENERAL STEPS
1. Data is prepared by cropping images into manageable sizes
2. Convert Hex color code to RGB to one hot encoding
3. Generate predicted segmented images
4. Do smooth blending

Note: in this example, the images are being trained on the masks

IMPORTS
1. numpy
2. matplotlib
3. patchify
4. segmentation_models
5. MeanIoU from keras.models


PREPARING DATA {


GETTING IMAGES
1. for every path, subdirectories, files in root directory
  2. print every file
  3. If the directory name indicates the file an images
      process it:
      4. How to process it: 
      cv2.imread(...) to read image
      convert image to cropped image
      make numpy array of image
      use patchify to put small images into big image //edit
      scale each patch and add it to the image dataset
      
GETTING MASKS
1. Do the same thing as images, convert BGR to RGB


Now: Convert image and mask datasets to numpy arrays, if they are not aligned model may not converge

CONVERT FROM RGB TO HEXADECIMAL
1. Hexadecimal is hexadecimal

Take RGB
R/16 = quotient*a number + remainder
Quotient and remainder are written as first two digits of hexadecimal

G/16= quotient2* anumber + remainder
Quotient and reaminder are written as 3rd and fourth digits of hexadecimal

B/16= you get it, they're the last two digits of hex code

}


LABEL MASKS(training data)
{
1. we know certain colors correspond to certain types of land cover for each pixel
2. we label the masks using this information
}

ONE-HOT ENCODING{
1. right now we have integer values for each pixel as labels
2. change it to categorical label

Ex: let's say a pixel has label 5, we convert it into a table that looks like this:
1 : no
2 : no
3 : no
4 : no
5 : yes

}


TESTING AND TRAINING
{
1. train test split
2. define weights, loss function(toy with these)
3. import unet model, compile and run it
    4. model= get model(), model.compile(optimizer, loss, metrics), model.fit(X_train, y_train)
5. predict it on images
6. visualize a couple 

}








   

