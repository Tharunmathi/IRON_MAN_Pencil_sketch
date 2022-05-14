# IRON_MAN_Pencil_sketch
It is a small and simple example of pencil_sketch in open cv library.just give the path of the image in the program and run the program that's if , the image is converted to pencil sketch in just one click  install opencv2 by running the following command in the terminal  pip install opencv-python  then give the path of the image and run the program..




import cv2
img = cv2.imread("C:\\Users\\THARUN\\OneDrive\\Pictures\\Downloads\\IRON_MAN.jpg")
gray_image = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
inverted_image =255- gray_image
blurred = cv2.GaussianBlur(inverted_image,(21,21),5)
inverted_blured = 255-blurred
pencil_sketch = cv2.divide(gray_image,inverted_blured,scale=256.0)

cv2.imshow("original Image",img)
cv2.imshow("pencil sketch",pencil_sketch)
cv2.waitKey(0)
