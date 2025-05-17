# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
## Program:

## Name:Harshini Y
## reg no:212223240050
```
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```
```
image = cv2.imread('chess.png')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```
```
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Input Image")
plt.axis('off')
plt.show()
```

### Input image and grayscale image


![image](https://github.com/user-attachments/assets/b49e7888-205f-4e5c-9068-36cea528be32)
```
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
plt.show()
```

![image](https://github.com/user-attachments/assets/abd6ed51-c4ae-4dfe-af50-d8efac707e01)
```
edges = cv2.Canny(gray_image, 50, 150)
```
```
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
plt.show()
```

![image](https://github.com/user-attachments/assets/762b84bc-c433-4dd1-ad28-01738d87af77)
```
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
```
```
for line in lines:
    x1, y1, x2, y2 = line[0] 
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
```
```
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Result of Hough Transform")
plt.axis('off')
plt.show()
```

![image](https://github.com/user-attachments/assets/277dfd49-03f8-4690-8317-3dcbacdbea8b)

## Result:
Thus the python program toto detect the lines using Hough Transform is done successfully
