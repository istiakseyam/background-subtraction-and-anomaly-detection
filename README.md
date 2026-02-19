# background-subtraction-and-anomaly-detection
**Run version 2 code to have the rules over moving objects**


Project AIM:


**How much traffic in which road?**


**Which bus is crowded?**


**Live public place crowd**


**Limitations: speed accuracy.**

Methods Used

Video Capture

The webcam is accessed using:

cv.VideoCapture(0) # in mac
capture = cv.VideoCapture(0, cv.CAP_DSHOW) # in windows

Each frame is read in a loop.

Background Subtraction (KNN)

Uses:

cv.createBackgroundSubtractorKNN()


This algorithm models the background and identifies moving objects as foreground.

Image Preprocessing

The frame is resized to 800×800 pixels.

Morphological operations are applied:

Erosion: removes small noise.

Dilation: restores object size after erosion.

Thresholding

Removes weak foreground pixels:

fgMask[np.abs(fgMask) < 250] = 0


Display

Two windows are shown:

Original video frame.

Foreground mask.

Setup
Requirements

Python 3.x

OpenCV

NumPy

Install dependencies

In PyCharm terminal or system terminal:

pip install opencv-python numpy

Run Instructions
Any IDE
Python interpreter.

Run the script.
Two windows will appear:
1. Frame: live webcam feed.
2. FG Mask: detected foreground.

Press:
q or Esc to exit.

Known Issues
Camera not opening

May show:
Unable to open


Causes:
*Camera permission not granted.
*Wrong camera index.
*Another app using the webcam.
*Mac/windows camera permission

Go to:

System Settings → Privacy & Security → Camera


Enable access for PyCharm or Python.

High CPU usage

Resizing frames to 800×800 may slow performance.

Reduce size for better speed:

frame = cv.resize(frame, (640, 480))


Foreground flickering or noise

Happens in low light or with shadows.

Can be improved by:

Adjusting kernel size.

Increasing iterations.

Using MOG2 instead of KNN.

Project is not ready yet, I will upgrade it by time.

  
