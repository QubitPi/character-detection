* [Basic - Does not save video output, but image output is saved](./basic.py)
  - `python basic.py -v in.MP4 -o out.avi` ([OpenCV for video containers supports only the **avi** extension](https://stackoverflow.com/a/48484222/14312712) and size of Writer have to matched with the frame size of video)
  - `python basic.py -i image.png -o out.png`
  - https://data-flair.training/blogs/python-project-real-time-human-detection-counting/
  - [Histograms of Oriented Gradients for Human Detection](./Histogram%20of%20Oriented%20Gradient%20Descriptor.pdf)
  - [HOG wikipedia](https://en.wikipedia.org/wiki/Histogram_of_oriented_gradients)
  - Detects "multiple persons" in each frame. In order to track the "right" person, a simple technique would be to pick
    up the nearest person in the next frame due to how a person moves.
  - **_This is essentially an object detection not people/character detection. So we might not use this script_**

Then [next](https://medium.com/@madhawavidanapathirana/https-medium-com-madhawavidanapathirana-real-time-human-detection-in-computer-vision-part-1-2acb851f4e55):

Early approaches for Human Detection
------------------------------------

### Haar Cascades for Human Detection

Haar feature based approach for object detection is proposed by Paul Viola and Michael Jones in their paper
[Rapid Object Detection using a Boosted Cascade of Simple Features](./Rapid%20Object%20Detection%20using%20a%20Boosted%20Cascade%20of%20Simple%20Features.pdf) published in 2001. This 
approach is widely used for Face Detection.

**OpenCV** includes inbuilt functionality to provide Haar cascade based object detection. Pre-trained models provided by OpenCV for "**Full Body Detection**", "**Upper Body Detection**" and "**Lower Body Detection**" are available
[here](https://github.com/opencv/opencv/tree/master/data/haarcascades).

Modern approaches for Human Detection
-------------------------------------

### Human Detection using Tensorflow Object Detection API

#### Setting up a Basic Human Detector

1. Make sure **Open CV** 3.0 (or above) and **Tensorflow** 2.0 (or above) are installed. It is recommended to use the
   Tensorflow GPU version when Nvidia GPU is available
2. Download
   [faster_rcnn_inception_v2_coco.tar.gz](http://download.tensorflow.org/models/object_detection/faster_rcnn_inception_v2_coco_2018_01_28.tar.gz)
   from Tensorflow Detection Model Zoo. Extract the downloaded file. If remote download is not available, here is the
   [local alternative](./faster_rcnn_inception_v2_coco_2018_01_28.tar.gz) that has been downloaded from there. Place
   the extracted directory at "tensorflow_basic_human_detector.py/.."
3. Run `python3 tensorflow_basic_human_detector.py` and observe the output on screen. (Press 'Q' to exit). May adjust
   the threshold parameter to improve the results.
   - Video being analyzed should be placed in the same directory
   - Analysis result will be written to "out.avi" in the same directory
   