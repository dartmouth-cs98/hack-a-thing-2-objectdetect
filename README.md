# hack-a-thing-2-Object Detection

## Jerry Wang & Timothy Qiu

### CS98 19F



#### Short Description

Object detection has really evolved in the past few years and has become an essential part of our everyday lives. From the first spark of autonomous vehicles to now all different kinds of eyewear and wearables, object detection has really penetrated all aspects of our surroundings. The origins of object detection came from extremely complex deep learning models that trained on thousands of images, and took days of time. However, since this technique is so mature now, we can reap the benefits of the past research quite easily by using very well documented packages such as the object-detection module in Tensorflow and the pre-trained ssd_mobilenet model.

​	In our program we try to tie object detection with human computer interaction. Instead of using the model to detect objects in high resolution images, which they are built for, we try to see its capabilities to recognize more obscure drawings by humans. Human drawn doodles are quite different from actual photos because they do not give the model contextual knowledge via the background and surroundings. In order to make the program work as smoothly as possible, we picked from a few drawing APIs and a few recognition models and settled on Turtle and ssd-mobilenet since it yielded the best performance.

​	In order to test the program, users simply open the `detect.ipynb` file in Jupyter Notebook and select the Run All Cells option. It will prompt you to draw a doodle via a separate screen. In this module, you can draw via dragging the left button on the mouse and finish by right clicking. The right click will automatically signal to save the image and perform object detection on it. The results will be directly printed on the Jupyter Notebook interface. To combat the problem of sometimes having low-res identification labels, we also print out in text the exact item the object-detection model detected.


#### Work Allocation

Jerry:

* Testing and implementing drawing APIs
* Formatting and modulating code
* Testing and optimization

Timothy:

* Testing different models in the Tensorflow Object Detection API
* Explored different Python drawing packages
* Readme



#### What We Learned

Human-Computer Interaction ws something we have always been interested in. In this project we have designed a system that allow the user to draw their imaginations on a drawing board provided by the program. We did this by exploring different packages such as Turtle, Pygame, Pyglet and PyCairo and found that Turtle is the one that fits our purpose the best. It is really easy to use and powerful. It is capable of detecting mouse-click events and can capture the current canvas and save it as an eps file, which we can turn into a jpg file using the PIL package that we have newly discovered. The Turtle package lays the ground work for HCI object detection, and after this project, we no longer need to draw on a paper and take a picture to let the computer know what we have in mind.  

A big part of the project was devoted to how we can actually make the computer capable of detecting objects within a jpg file. We explored an online open source package called Tensorflow Object Detection API, which has a built-in framework for object detection using Python. We have tried different models, such as ssd\_mobilenet\_v1\_coco, ssd\_resnet\_v1\_fpn, ssd\_pnasnet, faster\_rcnn\_inception\_resnet, faster\_rcnn\_nas, and it turns out that the ssd\_mobilenet\_v1\_coco has the best performance when invoked on human doodle drawing. The package is capable of detecting 100 different objects, ranging from person to animals to different concrete objects. This is a very important package to learn as it is a crucial step in the process of Human-Computer Interaction, and this is something we are very likely to use in our final project. 

#### What didn't work

* The Tensorflow Object Detection API is having a hard time recognizing human doodle. Sometimes even though the drawing is obvious to a human, the computer fails to classify it. Also, the model seems to lean towards the category 'person' as it often gives the highest affinity score to the 'person' class even though the picture has no human in it. In some sense this is inevitable because we are asking the computer to classify a human doodle drawing which lacks contextual and spatial information. We have tested the model against real and colored images and the performance was satisfactory, but on black-and-white doodles, even when we chose the best performance model, it still needs improvement. 

* The Turtle package only supports single-stroke drawing. Thus it is not possible to create a very complex image to feed into the object detection API. For the purpose of this project, this functionality is exactly what we want. However, for future projects/work, we may want to explore and use more complex drawing libraries of Python that supports multi-stroke drawing. 

* The Turtle package has a little bug when the user finishes drawing on a Mac system. The drawing board will freeze and the canvas will remain on the screen even after the program has already terminated the drawing window. It would not stop the program from executing later lines but it is troublesome to manually quit the drawing window everytime we finish drawing. 

























