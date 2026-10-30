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
- **Name:** PRIYADHARSHINI S  
- **Register Number:** 212225230218

  ### Ex. No. 01

#### 1. Read the image ('Eagle_in_Flight.jpg') using OpenCV imread() as a grayscale image.
```python

import cv2
import matplotlib.pyplot as plt
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
image = cv2.imread('photo1.jpeg') 
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()

image = cv2.imread('photo1.jpeg') 

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()

image = cv2.imread('photo1.jpeg') 

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape

rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)

plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()

image = cv2.imread('photo1.jpegg') 

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB) 

text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)

plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()

image = cv2.imread('photo1.jpeg') 
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")

image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)

plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")

image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)

plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")

image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)

plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")

image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")

image[100:400, 50:350] = [255, 0 , 255]  # Rows: 200-499, Columns: 200-499

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()

image = cv2.imread('photo1.jpeg') 
image.shape

resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)

resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape

plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()

image = cv2.imread('Qno. 1.jpg') 
image.shape

roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349

roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)

plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()

image = cv2.imread('photo1.jpeg') 

flipped_horizontally = cv2.flip(image, 1)

flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)

plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")

flipped_vertically = cv2.flip(image, 0)

flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)

plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```

## Output:

<img width="437" height="442" alt="Screenshot 2026-10-26 211557" src="https://github.com/user-attachments/assets/3ecc1e11-82ee-4f90-a7cc-ca018d4ab16e" />
<img width="410" height="382" alt="Screenshot 2026-10-26 215017" src="https://github.com/user-attachments/assets/37c08428-1413-4d9e-8a91-36b4e9b0e29c" />
<img width="383" height="391" alt="Screenshot 2026-10-26 215102" src="https://github.com/user-attachments/assets/35cd3618-1cd0-4e35-87c0-2550b7d1c0ce" />
<img width="315" height="388" alt="Screenshot 2026-10-26 215121" src="https://github.com/user-attachments/assets/9f73d3d7-37fc-4c7a-b0fa-a3320d7c1b69" />
<img width="362" height="382" alt="Screenshot 2026-10-26 215138" src="https://github.com/user-attachments/assets/ac45fba4-9ff0-4bbf-ae64-4620fc60dc79" />
<img width="376" height="397" alt="Screenshot 2026-10-26 215153" src="https://github.com/user-attachments/assets/474d48d0-8367-4d14-884b-79f886f17340" />
<img width="373" height="378" alt="Screenshot 2026-10-26 215206" src="https://github.com/user-attachments/assets/2c302530-2bec-4bbe-abca-93fe5d67ea05" />
<img width="386" height="392" alt="Screenshot 2026-10-26 215224" src="https://github.com/user-attachments/assets/d64b0858-9c09-4cce-8a7b-a8d3dbd753f9" />
<img width="377" height="387" alt="Screenshot 2026-10-26 215240" src="https://github.com/user-attachments/assets/dcd5bbd6-a205-483f-8057-fe0bef05d987" />
<img width="365" height="393" alt="Screenshot 2026-10-26 215255" src="https://github.com/user-attachments/assets/1287b3ab-cfae-4eaf-b606-21a32bf918ce" />
<img width="351" height="396" alt="Screenshot 2026-10-26 215309" src="https://github.com/user-attachments/assets/58cf8370-02aa-496b-8c27-0fd942e09b66" />
<img width="352" height="382" alt="Screenshot 2026-10-26 215324" src="https://github.com/user-attachments/assets/c34fd167-9179-4849-b2e8-a0a364e40564" />
<img width="500" height="391" alt="Screenshot 2026-10-26 215345" src="https://github.com/user-attachments/assets/344bcfb2-f541-48ce-820d-c02710ff429e" />
<img width="366" height="382" alt="Screenshot 2026-10-26 215401" src="https://github.com/user-attachments/assets/5b486e8d-8f52-4cf8-8f59-7d1ee7fb96f8" />
<img width="330" height="355" alt="Screenshot 2026-10-26 215419" src="https://github.com/user-attachments/assets/d75e957e-62ac-4df9-8d1b-5f847b9eced5" />


## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

