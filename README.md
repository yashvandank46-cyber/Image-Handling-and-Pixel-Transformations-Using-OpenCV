# Experiment 1: Image Handling and Pixel Transformations Using OpenCV

## Name: YASHVANDAN K
## Register Number: 212225100060


---

## AIM

To perform image handling and pixel transformations using Python and OpenCV, including reading and displaying images, drawing shapes, adding text, color space conversion, pixel manipulation, image resizing, cropping, flipping, and saving the modified image.

## SOFTWARE REQUIRED

- Python
- OpenCV
- Matplotlib
- Jupyter Notebook
- Anaconda (optional)

## INSTALLATION

Install the required libraries using the following command:

```bash
pip install opencv-contrib-python-headless matplotlib
```

## ALGORITHM

### Step 1: Read and Display an Image

1. Import OpenCV and Matplotlib libraries.
2. Read an image from the local directory using `cv2.imread()`.
3. Convert the image from BGR to RGB.
4. Display the original image using Matplotlib.

### Step 2: Draw Shapes and Add Text

1. Draw a line from the top-left to the bottom-right of the image.
2. Draw a circle at the center of the image.
3. Draw a rectangle around the image.
4. Add the text "OpenCV Drawing" at the top-left corner.

### Step 3: Color Space Conversion

1. Convert the RGB image to HSV and display it.
2. Convert the RGB image to grayscale and display it.
3. Convert the RGB image to YCrCb and display it.
4. Convert the HSV image back to RGB and display it.

### Step 4: Pixel Manipulation

1. Access and print the pixel value at coordinates `(100, 100)`.
2. Change the pixel at coordinates `(200, 200)` to white.
3. Modify a 300 × 300 region of the image to white.
4. Display the modified image.

### Step 5: Image Resizing

1. Read the original image.
2. Resize the image to half its original width and height.
3. Display the resized image.

### Step 6: Image Cropping

1. Read the original image.
2. Extract a 300 × 300 region of interest starting at `(50, 50)`.
3. Display the cropped image.

### Step 7: Image Flipping

1. Flip the original image horizontally.
2. Flip the original image vertically.
3. Display both flipped images.

### Step 8: Save the Final Modified Image

1. Save the modified image in the local directory using `cv2.imwrite()`.
2. Verify that the image has been saved successfully.

---

## PROGRAM

```
import cv2
import matplotlib.pyplot as plt
img = cv2.imread('1.jpg', cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()

import cv2
import matplotlib.pyplot as plt

# Read the image
img = cv2.imread('1.jpg')

# Convert BGR to RGB
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Display image shape
print(img_rgb.shape)

# Draw a red line on the image
line_img = cv2.line(img_rgb.copy(), (0, 0), (500, 600), (255, 0, 0), 2)

# Display the image
plt.imshow(line_img)
plt.title("Image with Line")
plt.axis('off')
plt.show()

import cv2
import matplotlib.pyplot as plt

# Read the uploaded image
img = cv2.imread('1.jpg')

# Convert BGR to RGB
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Get image dimensions
print(img_rgb.shape)

# Draw a red circle around the face
circle_img = cv2.circle(img_rgb.copy(), (260, 250), 120, (255, 0, 0), 5)

# Display the image
plt.imshow(circle_img)
plt.title("Image with Circle")
plt.axis('off')
plt.show()

import cv2
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('1.jpg')

# Convert BGR to RGB
img_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Get image dimensions
height, width = img_rgb.shape[:2]

# Draw a slightly adjusted blue rectangle
rectangle_img = cv2.rectangle(img_rgb.copy(),(20, 10),(width - 10, height - 10),(0, 0, 255),6)

# Display the image
plt.imshow(rectangle_img)
plt.title("Image with Rectangle")
plt.axis('off')
plt.show()

import cv2
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('1.jpg')

# Convert BGR to RGB
img_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Add text to the image
text_img = cv2.putText(
    img_rgb.copy(),
    "OpenCV Drawing",
    (10, 30),
    cv2.FONT_HERSHEY_SIMPLEX,
    1,
    (255, 255, 255),
    2
)

# Display the image
plt.imshow(text_img)
plt.title("Image with Text")
plt.axis('off')
plt.show() 

image = cv2.imread('1.jpg') 
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

import cv2
import matplotlib.pyplot as plt

# Load the original image
image = cv2.imread('1.jpg')

# Add a 300x300 white block
image[100:400, 100:400] = [255, 255, 255]

# Convert BGR to RGB
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Display the image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()

import cv2
import matplotlib.pyplot as plt

image = cv2.imread('1.jpg')

print("Original Image Shape:", image.shape)

resized_image = cv2.resize(image, (260, 320))

resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)

print("Resized Image Shape:", resized_image_rgb.shape)

plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()

image = cv2.imread('1.jpg') 
image.shape
roi = image[50:350, 50:350]  
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()

image = cv2.imread('1.jpg')
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


## OUTPUT
<img width="420" height="515" alt="Screenshot 2026-10-29 095643" src="https://github.com/user-attachments/assets/06450074-cdf2-4498-bd1e-c1922533676f" />
<img width="426" height="521" alt="Screenshot 2026-10-29 095651" src="https://github.com/user-attachments/assets/d6e98de5-2248-4cbd-9431-f594724d19bd" />
<img width="382" height="500" alt="Screenshot 2026-10-29 095700" src="https://github.com/user-attachments/assets/e440a11e-75e1-41b9-8a0e-855a327b5456" />
<img width="388" height="512" alt="Screenshot 2026-10-29 095711" src="https://github.com/user-attachments/assets/8daf9638-25e1-4a42-b343-2fcc04594151" />
<img width="377" height="515" alt="Screenshot 2026-10-29 095722" src="https://github.com/user-attachments/assets/517e835e-5cc5-45f1-b4d4-5ce3d74faf78" />
<img width="375" height="500" alt="Screenshot 2026-10-29 095733" src="https://github.com/user-attachments/assets/6500bebd-214e-4c3f-8840-f7ce9e714679" />
<img width="397" height="507" alt="Screenshot 2026-10-29 095741" src="https://github.com/user-attachments/assets/0856c055-c1f4-4b4a-b761-3e8e82a8f711" />
<img width="337" height="491" alt="Screenshot 2026-10-29 095751" src="https://github.com/user-attachments/assets/aa6ea370-3278-407e-9bfa-318f9e5f8ae4" />
<img width="382" height="492" alt="Screenshot 2026-10-29 095759" src="https://github.com/user-attachments/assets/7b15cd6f-2997-40af-8d4b-754bfa8342d8" />
<img width="402" height="496" alt="Screenshot 2026-10-29 095809" src="https://github.com/user-attachments/assets/16fc8cfb-a7b5-40d9-81cf-60408c8c7316" />
<img width="387" height="506" alt="Screenshot 2026-10-29 095818" src="https://github.com/user-attachments/assets/37ff5bff-b87d-4e7a-a23d-593ac8b1853a" />
<img width="440" height="546" alt="Screenshot 2026-10-29 095828" src="https://github.com/user-attachments/assets/af904ea0-e59b-47bd-bd50-badf48c2f521" />
<img width="518" height="527" alt="Screenshot 2026-10-29 095836" src="https://github.com/user-attachments/assets/f91e110e-b0d0-4d80-803e-16783add8677" />
<img width="445" height="502" alt="Screenshot 2026-10-29 095843" src="https://github.com/user-attachments/assets/240dae55-6c48-481e-ad20-7d7baae42e28" />
<img width="392" height="503" alt="Screenshot 2026-10-29 095850" src="https://github.com/user-attachments/assets/0ac80bc5-9071-4074-8e3f-d4bd2995cceb" />



## RESULT

Thus, image handling and pixel transformations were performed using Python, OpenCV, and Matplotlib. The experiment demonstrated image reading, shape drawing, text insertion, color space conversion, pixel manipulation, image resizing, cropping, flipping, and saving.

---
