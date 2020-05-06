### Number-Plate-Detection

Method
1. Detect License Plate

2. Perform segmentation of characters

3. Train a DL model to predict characters

4. Prediction of characters in License Plate

The approach used to segment the images is Connected Component Analysis. Connected regions wil imply that all the connected pixels belong to the same object. A pixel is said to be connected to another if they both have the same value and are adjacent to each other.

Car Image -> Grayscale Image -> Binary Image -> Applying CCA to get connected regions -> Detect license plate out of all connected regions (Assumptions made : width of the license plate region to the full image ranges between 15% and 40% and height of the license plate region to the full image is between 8% & 20%)

Output of first step is a license plate image detected in a car image. This is provided as input to step2 and CCA is applied on this image to bound the characters in plate.Each character identified is appended into a list.

Model is trained using SVC (4 cross fold validation) with dataset present in directory train20X20. The model is saved as finalized_model.sav which is then loaded to predict each character.

Once the characters of plate is obtained and model is trained, the model is loaded in order to predict each character.

FLASK Based API Coming Soon...

![Step 1](https://user-images.githubusercontent.com/42993095/79063111-4a928180-7cbd-11ea-8002-4e381760e976.png)
A Grayscale image is produced of the given file.

![Step 2](https://user-images.githubusercontent.com/42993095/79063128-5d0cbb00-7cbd-11ea-8467-76cb71dde10a.png)
The license plate is detected from the input image.
![Step 3](https://user-images.githubusercontent.com/42993095/79063149-701f8b00-7cbd-11ea-804a-6206109b53ba.png)
Characters segmentation is applied to recognize distinct characters.

The output of the detected characters is displayed in the code output.


