# face_detection

import cv2

# Load the pre-trained Haar Cascade classifier for face detectio

# Load the Haar Cascade classifier for frontal face detection
face_cascade = cv2.CascadeClassifier('path/to/haarcascade_frontalface_default.xml')

# Load the image, perform face detection, and draw rectangles (as shown in the previous example)

# Load the image
image = cv2.imread('"C:\Users\nisha\Videos\face_detection_image.jpg"')

# Convert the image to grayscale for face detection
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Perform face detection
faces = face_cascade.detectMultiScale(gray, scaleFactor=1.3, minNeighbors=5, minSize=(30, 30))

# Draw rectangles around the detected faces
for (x, y, w, h) in faces:
    cv2.rectangle(image, (x, y), (x + w, y + h), (0, 255, 0), 2)

# Display the result
cv2.imshow('Face Detection', image)
cv2.waitKey(0)
cv2.destroyAllWindows()
