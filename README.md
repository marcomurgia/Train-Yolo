# Train-Yolo

The following guides were used to train Yolo and detect custom objects:
1) https://pysource.com/2020/04/02/train-yolo-to-detect-a-custom-object-online-with-free-gpu/
2) https://github.com/AlexeyAB/darknet#how-to-train-to-detect-your-custom-objects

The first explains how to train Yolo and detect a single object, using the free GPU, available online, of google colab.
Google colab is a free service where you can run python scripts and use machine learning libraries taking advantage of their powerful hardware. It’s for free with the only disadvantage the you can use it for 12 hours in a row, after that you’ll be disconnected and your files will be deleted. 

The second explains how to train Yolo and detect your personalized objects. 
So to train the algorithm with a data set of multiple objects, using google colab, the python file Train_YoloV3.ipynb was copied and renamed to Train_YoloV3_mo.ipynb. This new file has been modified taking into account the guide of the second link.

The steps to follow to train YOLO and detect custom objects are as follows:

1) Go on google drive and log in. If you’ don’t have an account, create one and log in.
2) Create a new folder called “yolov3”.
3) Then upload the "images.zip" and "train.txt" files.
4) Go on google colab: https://colab.research.google.com/notebooks/intro.ipynb#recent=true and log in with the same account you used to log in on google drive.
5) Upload this file “Train_YoloV3_mo.ipynb”
6) Then we need to enable the GPU. So click on “Edit”, then "Notebook settings" and we select “GPU” and click save.
7) Now we’re ready to connect Colab with our drive. Run the cell where it’s written "# Check if NVIDIA GPU is enabled", then run the cell “from google.colab import drive” and then click on the link that appears.
8) This links is to grant access to your google drive. Once you enter it asks you to allow the Google drive file Stream. Click on “Allow”. And then copy the code that appears.
9) Paste the code on the notebook and press “Enter”.
10) Now you can start the training by clicking on “Runtime”, then “Run all”.

Usually are sufficient 2000 iterations for each class(object), but not less than number of training images and not less than 6000 iterations in total. When you see that average loss 0.xxxxxx avg no longer decreases at many iterations then you should stop training. The final avgerage loss can be from 0.05 (for a small model and easy dataset) to 3.0 (for a big model and a difficult dataset).

If your work is blocked on google colab and your files are deleted, it means that we have exceeded 12 hours. So let's go to File -> Open notebook -> upload and insert the Train_YoloV3_12h.ipynb file.\
Then we repeat steps 6, 7, 8, 9 and 10.

It may happen that google colab tells you that you cannot use the GPU because you have exceeded the limit, in this case we log out and come back after a some hours.

After training the algorithm, we can test it on our webcam.
To test Yolo we download the yolov3_training_last.weights file from the yolov3 directory of our account drive. We copy this file into the object_detection directory. We open the object_detection directory and launch the following line of code from the command line:
```
./object_detection --config=yolov3_training.cfg --model=yolov3_training_last.weights --classes=classes_13_obj.txt --width=416 --height=416 --scale=0.0392 --rgb
```
For more information on object_detection visit this site:
https://docs.opencv.org/master/da/d9d/tutorial_dnn_yolo.html

# Train-Yolo
