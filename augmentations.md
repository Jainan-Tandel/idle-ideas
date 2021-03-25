### Augmentations

#### For producing different augmentations of the images, we manipulated the image array and/or used OpenCV functions, with preset attributes. The augmentations applied, along with the preset attributes are:

1. Horizontal shift: A random ratio is taken in the range (-r,r)
2. Vertical shift: A random ratio is taken in the range (-r,r)
3. Brightness: A random value between between 0.5 and 3 is taken, and the brightness is increased by that factor
4. Zoom: The image is zoomed by a factor of r
5. Channel-shift: The channel shift is performed by a random number between -60 and +60
6. Horizontal-flip: The image is flipped
7. Vertical-flip: The image is flipped
8. Rotation: The image is rotated by a ranodm angle between -30r and +30r degrees
9. Convolution: The image is convolved with a random 3x3 kernel
10. Blur: The image is blurred with a 5x5 kernel
11. Gaussian-Blur: The image is blurred with a 5x5 gaussian kernel with 0 standard deviation in X direction
12. Median-Blur: A median filter is applied with a kernel size of 3
13. Dialate: The image is dilated with a kernel size of 3x3, with unit values throughout
14. Erode: The image is eroded with a kernel size of 3x3, with unit values throughout
15. Morph_Grad: Gives the outline of the image, by finding difference between dilated and eroded image from above two filters
16. Clip: Clips the image array in (mean - 3.5*std, mean + 3.5*std), where mean & std are average & standard deviation of the image array
##### Note: r is a random number between 0 and 1.

#### All the user selected options from the above augmentations, are applied one after the other on the original image with a 50% chance, giving a augmented image with some random augmentations, corresponding to each image from the original dataset. The augmented images are then appended to the array of original images, increasing the difficulty of the dataset. The model is then trained on this combined dataset.
