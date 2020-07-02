# Train Yolo 87 objects 

In order to obtain a more complete detection of  Italian Traffic Signs, it was decided to expand the dataset to 87 road signs.\
To train the algorithm of such a large datset you need a very large number of iterations, so a faster algorithm has been sought. The fastest to train that has been found is the yolov4-tiny.cfg.

The steps to train this algorithm are very similar to those already seen in the main README. The differences are as follows:

In step 2 the "yolov4" folder should be created instead of the "yolov3" folder.\
In step 3 the "obj.names" file must be added to the newly created folder, in addition to the "images.zip" and "train.txt" files.\
In step 5 the file "Train_YoloV4_tiny.ipynb" should be loaded instead of "Train_YoloV3_mo.ipynb".

The remaining steps are the same.

If you exceed 12 hours of work on google colab go to File -> Open notebook -> upload and insert the file Train_YoloV3_12h.ipynb.
Then we repeat steps 6, 7, 8, 9 and 10.

After training the algorithm, we can test it on our webcam.
To test Yolo we download the yolov4_training_last.weights file from the yolov4 directory of our account drive. We copy this file into the object_detection directory. We open the object_detection directory and launch the following line of code from the command line:
```
./object_detection --config=yolov4_training.cfg --model=yolov4_training_last.weights --classes=classes_87_obj.txt --width=416 --height=416 --scale=0.0392 --rgb
```
