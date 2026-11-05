# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
- **Name:** KANAGAVEL R 
- **Register Number:** 212223040085

  ### Ex. No. 01

```
import cv2
import matplotlib.pyplot as plt
# Read the image using OpenCV
img = cv2.imread('me.jpg', cv2.IMREAD_COLOR)
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```

<img width="395" height="500" alt="Screenshot 2026-11-05 095550" src="https://github.com/user-attachments/assets/2e276c59-0a4b-4242-b788-16906f900efc" />

```
# Load the image
image = cv2.imread('me.jpg')
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (0, 255, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
```

<img width="392" height="512" alt="Screenshot 2026-11-05 095823" src="https://github.com/user-attachments/assets/995a473c-78ca-4ebf-96fa-aa03c404e3d0" />

```
# Load the image
image = cv2.imread('me.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
circle_img = cv2.circle(img_rgb,(400,300),150,(0,255,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```

<img width="393" height="511" alt="Screenshot 2026-11-05 095924" src="https://github.com/user-attachments/assets/cf303604-8f4f-4af0-b147-73c48842ac46" />

```
# Load the image
image = cv2.imread('me.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```

<img width="385" height="506" alt="Screenshot 2026-11-05 100045" src="https://github.com/user-attachments/assets/ea40f7e9-4c55-4923-82bc-02014fba01db" />

```
# Load the image
image = cv2.imread('me.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Add text to the image
text_img = cv2.putText(img_rgb, "KANAGAVEL R", (30, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (0, 0, 255), 800)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```

<img width="395" height="507" alt="Screenshot 2026-11-05 100144" src="https://github.com/user-attachments/assets/5634164c-8096-48dc-8b67-5d279db9c7da" />

```
# Load the image
image = cv2.imread('me.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
```

<img width="687" height="542" alt="Screenshot 2026-11-05 100240" src="https://github.com/user-attachments/assets/a113ed54-e351-4e70-aa30-4008395a90cb" />

```
# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
```

<img width="682" height="552" alt="Screenshot 2026-11-05 100323" src="https://github.com/user-attachments/assets/690138c9-d3c7-4316-8755-ddc01afbfa21" />

```
# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```

<img width="682" height="537" alt="Screenshot 2026-11-05 100407" src="https://github.com/user-attachments/assets/3f8f9e38-10aa-4342-8fcc-bdc02cd02954" />

```
# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
```

<img width="681" height="541" alt="Screenshot 2026-11-05 100451" src="https://github.com/user-attachments/assets/b2a04781-bf6e-4169-954f-665bbe74f4e3" />

```
# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```

<img width="678" height="546" alt="Screenshot 2026-11-05 100545" src="https://github.com/user-attachments/assets/01d98fba-c515-43f4-b671-7fc8ce83c314" />

```
# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```

<img width="385" height="502" alt="Screenshot 2026-11-05 100634" src="https://github.com/user-attachments/assets/c743372f-18a2-4cc5-b04d-066baa4f1737" />

```
# Load the image
image = cv2.imread('me.jpg')
image.shape
# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```

<img width="625" height="502" alt="Screenshot 2026-11-05 100749" src="https://github.com/user-attachments/assets/6d60665e-ff5c-42d9-86bd-3c264662617f" />

```
# Load the image
image = cv2.imread('me.jpg')
image.shape
# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```

<img width="462" height="380" alt="Screenshot 2026-11-05 100851" src="https://github.com/user-attachments/assets/e52b37b3-a3a5-4a94-bd98-a080a4e70fbc" />

```
# Load the image
image = cv2.imread('me.jpg') 
# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)
# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
```

<img width="692" height="546" alt="Screenshot 2026-11-05 100955" src="https://github.com/user-attachments/assets/705011ea-24c7-40e6-9c5a-dbadc877cc82" />

```
# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)
# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```

<img width="690" height="503" alt="Screenshot 2026-11-05 101043" src="https://github.com/user-attachments/assets/f59729e3-4a44-4bab-b7ba-ccf8d9dad5ec" />


## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
