# Record-Image-Acquisition-using-Web-Camera
# Experiment 02 – Webcam Image Capture and Video Processing Using OpenCV

## AIM

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Capture and save a frame as a JPG image.
2. Display the live webcam video.
3. Display the video by resizing the frame.
4. Rotate and display the video.

## SOFTWARE REQUIRED

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (`cv2`)
- Matplotlib
- IPython

## ALGORITHM

**Step 1:** Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

**Step 2:** Capture frames continuously from the webcam.

**Step 3:** Save a captured frame as a JPG image using `cv2.imwrite()`.

**Step 4:** Display the live video stream using Matplotlib and `clear_output()`.

**Step 5:** Resize the captured frames using `cv2.resize()` and display the resized video.

**Step 6:** Rotate the video frames by 90° clockwise using `cv2.rotate()` and display the rotated video.

---

## PROGRAM

### i) Capture an image and save it as a JPG file

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

ret, frame = cap.read()

if ret:
    cv2.imwrite(
        r"C:\Users\acer\Pictures\Camera Roll\WIN_20260723_19_14_37_Pro.jpg",
        frame
    )

cap.release()

captured_image = cv2.imread(
    r"C:\Users\acer\Pictures\Camera Roll\WIN_20260723_19_14_37_Pro.jpg"
)

plt.imshow(captured_image[:, :, ::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```

### ii) Display the video

```python
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
```

### iii) Display the video by resizing the window

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    resized_frame = cv2.resize(frame, (100, 150))

    frame_rgb = cv2.cvtColor(
        resized_frame, cv2.COLOR_BGR2RGB
    )

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()

    time.sleep(0.05)

cap.release()
```

### iv) Rotate and display the video

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    rotated_frame = cv2.rotate(
        frame, cv2.ROTATE_90_CLOCKWISE
    )

    frame_rgb = cv2.cvtColor(
        rotated_frame, cv2.COLOR_BGR2RGB
    )

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()

    time.sleep(0.05)

cap.release()
```

---

## OUTPUT

### i) Write the frame as a JPG image

The captured webcam frame is successfully saved as `WIN_20260723_19_14_37_Pro.jpg`.

<img width="598" height="467" alt="image" src="https://github.com/user-attachments/assets/44f8f535-7455-4a95-83c1-10b854ec0021" />


### ii) Display the video

The live webcam video is displayed successfully.

<img width="555" height="430" alt="image" src="https://github.com/user-attachments/assets/728aae2d-68eb-4026-a461-8948fbe9e61c" />


### iii) Display the video by resizing the window

The webcam video is displayed after resizing the frame.

<img width="412" height="442" alt="image" src="https://github.com/user-attachments/assets/f8cd2276-a0e0-4543-8797-028a52e42bdc" />


### iv) Rotate and display the video

The webcam video is successfully rotated by 90° clockwise and displayed.

<img width="322" height="438" alt="image" src="https://github.com/user-attachments/assets/735cdd79-7092-4e4e-a22a-60449e5ed38e" />


---

## RESULT

Thus, an image was successfully captured from the webcam and saved as a JPG file. Various video processing operations, including displaying, resizing, and rotating the live webcam video, were successfully performed using Python and OpenCV.
