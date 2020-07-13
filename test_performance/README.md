# Test Performance

To test the performance of the trained algorithm, the object_detection.cpp file was copied and renamed to object_detection_test.cpp, then it was modified in order to detect the execution time of each frame. In addition, an arithmetic mean of the frames detected during a test has also been added.

This test can be done with various optimization options. The levels that can be chosen are: -O0, -O1, -O2, -O3 and -Os.\
To choose the level, simply enter the Makefile and modify the "OPTIMIZATION = -O0" line.

After choosing the code optimization level, you can start the test. The steps to be executed from are as follows:
1. Run the "make" command from the terminal.
2. Copy the object_detection_test file to the object_detection folder.
3. Run this command from the terminal:
```
./object_detection_test --config=yolov3_training.cfg --model=yolov3_training_last.weights --classes=classes_87_obj.txt --width=416 --height=416 --scale=0.0392 --rgb
```
