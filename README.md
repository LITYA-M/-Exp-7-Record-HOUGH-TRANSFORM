# Exp-7-Record-HOUGH-TRANSFORM
# Aim:
To detect straight lines in an image using the Hough Transform technique.

# Software Required:
 .Anaconda – Python 3.7
 .Jupyter Notebook / VS Code
 .OpenCV (cv2)
 .NumPy
 .Matplotlib

# Algorithm:

Step1:
Import all the necessary modules for the program.

Step2:
Load a image using imread() from cv2 module.

Step3:
Convert the image to grayscale.

Step4:
Using Canny operator from cv2, detect the edges of the image.

Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images. Using For loop, draw the lines on the found co-ordinates. Display the image.

# Program

Developed By

Name: Litya M

Register No: 212225230152

Input image 

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('butterfly.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
```

Grayscale image

```
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```

Canny Edge detector 

```
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
(np.float64(-0.5), np.float64(1759.5), np.float64(1173.5), np.float64(-0.5))

```

Hough transform

```
lines = cv2.HoughLinesP(
    edges,
    1,
    np.pi / 180,
    100,
    minLineLength=50,
    maxLineGap=10
)
if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line
        cv2.line(image, (x1, y1), (x2, y2), (0, 0, 0), 2)
# Display the result of Hough Transform

plt.figure(figsize=(10, 6))
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Result of Hough Transform")
plt.axis("off")
plt.show()
```

Result of Hough Transform

```
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
(np.float64(-0.5), np.float64(1759.5), np.float64(1173.5), np.float64(-0.5))
```

# output
<img width="628" height="443" alt="image" src="https://github.com/user-attachments/assets/7524b971-39f7-47c8-93d7-1b520f75893c" />

<img width="627" height="437" alt="image" src="https://github.com/user-attachments/assets/fbac2884-8eda-46cf-a642-8f27bbdb5f13" />

<img width="623" height="440" alt="image" src="https://github.com/user-attachments/assets/295ab964-9351-4124-81c4-16c0a9df4999" />

<img width="876" height="620" alt="image" src="https://github.com/user-attachments/assets/29be7bce-17c3-41c0-bf38-8d014dfd2c34" />

<img width="622" height="445" alt="image" src="https://github.com/user-attachments/assets/65f1f920-90d9-4bcf-9182-699bac155224" />


# Result:
Thus, the straight lines present in the given image were successfully detected using the Hough Transform.
