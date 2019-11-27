# EasyPySpin

EasyPySpin is a wrapper for FLIR Spinnaker SDK. This wrapper provides much the same way as the OpenCV VideoCapture class.


# Usage
## Live streaming
Live streaming will start when `EasyPySpin.py` is executed.
```
python3 EasyPySpin.py
```

## Use as module
`EasyPySpin.py` can be used as a module.
```python
import cv2
import EasyPySpin

cap = EasyPySpin.VideoCapture(0)

if not cap.isOpened():
    print("cap cant open\nexit")
    return -1

cap.set(cv2.CAP_PROP_EXPOSURE, 100000)
cap.set(cv2.CAP_PROP_GAIN, 10)

ret, frame = cap.read()

cv2.imwrite("frame.png", frame)
    
cv2.destroyAllWindows()
cap.release()
```
