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
