# Picture Calculator

## Description
This program calculates a handwritten expression. 
Decide name of the image in the code.
Options will be added later.


## Dependencies
- matplot
- matplotlib.pyplot
- sklearn.model_selection
- sklearn.svm
- sklearn
- sklearn.externals
- sklearn.metrics
- random§
- skimage.feature
- imutils
- cv2
- os
- PIL

## Functions Created

### `train()` to create a training data for the recognition
- load the image, pre-process it, and store it in the data list
- extract the class label from the image path and update the labels list
- Scale the raw pixel intensities to the range [0,1]
- Partition the data into training and testing splits using 75% of the data for training and the remaining 25% for testing
- convert the labels from integers to vectors
- trainY = to_categorical(trainY, num_classes=14)
- testY = to_categorical(testY, num_classes=14)
- trainX = trainX.reshape(trainX.shape[0], img_rows, img_cols, 1)
- testX = testX.reshape(testX.shape[0], img_rows, img_cols, 1)

### `chk_dig(n)` checks for digit

### `math_part(l)` 

### `sort_contours(cnts, method="left-to-right")` sorting of the data
- handle if we need to sort in reverse
- handle if we are sorting against the y-coordinate rather than the x-coordinate of the bounding box
- construct the list of bounding boxes and sort them from top to bottom
- return the list of sorted contours and bounding boxes

### `draw_contour(image, c , i)`
- compute the center of the contour area and draw a circle representing the center
- draw the countour number on the image
- return the image with the contour number drawn on it

### `test()`
- Threshold the image
- show the original, unsorted contour image
- sort the contours according to the provided method
- Get rectangles contains each contour
- For each rectangular region, calculate HOG features and predict
- the digit using Linear SVM
- print(predictions)

## Run Instructions
- Install all the dependencies on your machine
- Run training.py

## Workflow
1. Machine gets trained using the dataset provided
2. It forms a test.pkl file
3. Then it taks image as input
4. determines the characters in the equation
5. calculates and gives the answer

## Version
0.1