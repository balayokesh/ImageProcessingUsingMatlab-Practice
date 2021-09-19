<h1 align='center'>ImageProcessingUsing-Matlab-Practice</h1>

**Reference:** Image processing onramp course by Mathworks

## Workflow:
import -> preprocess -> segment -> post process -> classify

## functions used for Image processing in matlab:
**Normal read and write operations**
1. `imread(<img_name>);` - used to read an image and store it in a variable
2. `imshow(<img_name>)` - Prints the image
3. `imshowpair(<img1>, <img2>, "montage")` - prints pair of images in same line with specified theme/mode 
4. `imwrite(<image_processed>, <image_name_with_format>)` - writes or creates a new/processed image
5. `size(<img>)` - returns image size  
  
**Images involving RGB are stored in 3d arrays**
1. variable = img(:, :, <1-3>)  
  ```
  1 - represents R array values  
  2 - represents G array values  
  3 - represents B array values
  ```
2. `max(<img>, [], "all")` - returns max color value in max an image
3. `min(<img>, [], "all")` - returns min color value in max an image
4. `[R, G, B] = imsplit(<img>)` - splites the 3d array (RGB array) of that image and stores it in R, G, B variables
5. `montage ({<R-img>, <G-img>, <B-img>})` - prints montage of all the three images

**Grayscale and color images**
1. `A = im2gray(<img>);` - converts image to grayscale so that text can be more easily readable in black and white theme.

**Using histogram to check contrast**
1. `imhist(<img>)` - shows histogram of contrast/intensity rate in an image
2. `imadjust(<img>)` - used to increase contrast of greyscale image
3. `imlocalbrighten(<img>)` - used to icnrease contrast of coloured image

**Open matlab tool**
1. `imtool` - opens matlab interactive GUI tool

## Image segmenting
Definition: Segmenting various objects in an image by edge detection, texture, specific shapes and sizes and color


**Adjusting image threshold example:**  
**Step 1:**   
Convert to grayscale  
**Step 2:**   
Increase contrast `imgAdj = imgadjust(<img>)`    
**Step3:**  
1. `BW = imgAdj > 255/2`  
2. `BW = imgAdj > 200`  
(or)  
use `imbinarize(<img>);`  
**Eg:** `imbinarize(gsAdj, "adaptive", "ForegroundPolarity", "dark");`

### Finding whether a image is a receipt or not
Receipt contains more 0 values in its grayscale row.  
**To calculate row sum**  
`rsum = sum(<img>, 2)`  
**To plot the image row addition values**  
`plot(rsum)`

## Post processing:
**Filtering noise**  
`H = fspecial("average", n)` - creates n by n averaging filter with name H
