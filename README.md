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
<img width="661" height="486" alt="image" src="https://github.com/user-attachments/assets/08f781d6-41c0-4ce8-b82d-1250aaa0a2ea" />


2. DISPLAYING THE VIDEO
<img width="663" height="489" alt="image" src="https://github.com/user-attachments/assets/d87bca61-0770-4474-887f-56e855f5be43" />


3. DISPLAYING THE VIDEO BY RESIZING THE WINDOW
<img width="325" height="484" alt="image" src="https://github.com/user-attachments/assets/09330035-dfb7-4ecf-b7bb-31b2b51ae9b9" />

4. ROTATE AND DISPLAY THE VIDEO
<img width="382" height="492" alt="image" src="https://github.com/user-attachments/assets/410959a9-8ced-4307-9b93-e883e1c9a027" />


## Result
Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
