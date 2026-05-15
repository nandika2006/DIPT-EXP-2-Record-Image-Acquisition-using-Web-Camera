### EX. NO:02
## IMAGE ACQUISITION USING WEB CAMERA

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  


## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## ⚙️ Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

## 💻 Program

### Developed By:
**Name:** NANDIKA S 
### Register No: 21222230175
    import cv2
    import matplotlib.pyplot as plt
    from IPython.display import clear_output
    import time
    cap = cv2.VideoCapture(0)
    ret, frame = cap.read()
    if ret:
        cv2.imwrite("captured_frame.jpg", frame)
    cap.release()
    captured_image = cv2.imread('captured_frame.jpg')
    plt.imshow(captured_image[:,:,::-1])
    plt.title('Captured Frame')
    plt.axis('off')
    plt.show()
    cap = cv2.VideoCapture(0)
    
    for i in range(50):
        ret, frame = cap.read()
        if not ret:
            break
        frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
        clear_output(wait=True)
        plt.imshow(frame_rgb)
        plt.axis('off')
        plt.show()
        time.sleep(0.05)
    cap.release()
    cap = cv2.VideoCapture(0)
    
    for i in range(50):
        ret, frame = cap.read()
        if not ret:
            break
        resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
        frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
        clear_output(wait=True)
        plt.imshow(frame_rgb)
        plt.axis('off')
        plt.show()
        time.sleep(0.05)
    cap.release()
    
    cap = cv2.VideoCapture(0)
    
    for i in range(50):
        ret, frame = cap.read()
        if not ret:
            break
        rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
        frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
        clear_output(wait=True)
        plt.imshow(frame_rgb)
        plt.axis('off')
        plt.show()
        time.sleep(0.05)
    cap.release()

## Output

1. CAPTURED FRAME
<img width="661" height="368" alt="image" src="https://github.com/user-attachments/assets/da99ac62-4cc0-4bcb-a60e-76c818272a43" />

2. DISPLAYING THE VIDEO
<img width="669" height="370" alt="image" src="https://github.com/user-attachments/assets/0a1db2c1-9c71-4752-8577-ded913a51fc0" />

3. DISPLAYING THE VIDEO BY RESIZING THE WINDOW
<img width="329" height="496" alt="image" src="https://github.com/user-attachments/assets/0b4576d4-6310-467a-9dbf-553f2c4bb4a6" />

4. ROTATE AND DISPLAY THE VIDEO
<img width="276" height="496" alt="image" src="https://github.com/user-attachments/assets/ce19593b-9f9f-441c-892d-9365b52bdb5e" />

## Result
Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
