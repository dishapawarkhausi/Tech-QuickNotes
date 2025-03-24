# Object Detection in Images Using OpenCV

OpenCV provides powerful tools for object detection using pre-trained models like Haar cascades, deep learning models (YOLO, SSD, Faster R-CNN), and contour detection.

---

## 1. Install OpenCV
Ensure you have OpenCV installed:
```bash
pip install opencv-python opencv-python-headless
```

---

## 2. Load and Display an Image
```python
import cv2

# Load the image
image = cv2.imread('image.jpg')

# Display the image
cv2.imshow('Image', image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

## 3. Object Detection Using Haar Cascades

Haar cascades are pre-trained XML classifiers for face, eyes, etc.

### **Download Haar Cascades**
```python
# Load pre-trained Haar cascade for face detection
face_cascade = cv2.CascadeClassifier(cv2.data.haarcascades + 'haarcascade_frontalface_default.xml')
```

### **Apply Detection**
```python
# Convert image to grayscale
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Detect faces
faces = face_cascade.detectMultiScale(gray, scaleFactor=1.1, minNeighbors=5, minSize=(30, 30))

# Draw rectangles around detected faces
for (x, y, w, h) in faces:
    cv2.rectangle(image, (x, y), (x + w, y + h), (0, 255, 0), 2)

cv2.imshow('Detected Faces', image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

## 4. Object Detection Using Contours

Contours help detect objects based on edges.

```python
# Convert image to grayscale and apply threshold
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
_, thresh = cv2.threshold(gray, 150, 255, cv2.THRESH_BINARY)

# Find contours
contours, _ = cv2.findContours(thresh, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)

# Draw contours on the image
cv2.drawContours(image, contours, -1, (0, 255, 0), 2)

cv2.imshow('Contours', image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

## 5. Object Detection Using YOLO (Deep Learning)

### **Download YOLO Weights and Config**
Download the pre-trained YOLO model files (`yolov3.weights`, `yolov3.cfg`, `coco.names`).

### **Load YOLO Model in OpenCV**
```python
net = cv2.dnn.readNet('yolov3.weights', 'yolov3.cfg')
layer_names = net.getLayerNames()
output_layers = [layer_names[i - 1] for i in net.getUnconnectedOutLayers()]
```

### **Perform Detection**
```python
# Convert image to blob and perform forward pass
blob = cv2.dnn.blobFromImage(image, scalefactor=1/255.0, size=(416, 416), swapRB=True, crop=False)
net.setInput(blob)
detections = net.forward(output_layers)

# Process detections
for detection in detections:
    for obj in detection:
        scores = obj[5:]
        class_id = int(scores.argmax())
        confidence = scores[class_id]

        if confidence > 0.5:
            center_x, center_y, width, height = (obj[:4] * image.shape[1]).astype("int")
            x, y = int(center_x - width / 2), int(center_y - height / 2)
            cv2.rectangle(image, (x, y), (x + width, y + height), (0, 255, 0), 2)

cv2.imshow('YOLO Detection', image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

## **Conclusion**

- **Haar cascades** are fast but work best for faces and predefined objects.
- **Contours** detect objects based on shapes and edges.
- **YOLO** is a deep learning model that provides high accuracy for object detection.

For real-time detection, use OpenCV with a webcam! 🚀
