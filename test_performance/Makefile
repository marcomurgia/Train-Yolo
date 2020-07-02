CC=g++

OC4CFLAGS = `pkg-config --cflags opencv4`
OC4LIBS = `pkg-config --libs opencv4`  

CFLAGS = $(OC4CFLAGS) -I. -fPIC -frtti -pthread 
LIBS = $(OC4LIBS) -pthread

OBJS := object_detection_test.o
EXECUTABLE = object_detection_test
OPTIMIZATION = -O0

all: $(OBJS)
	$(CC) $(OBJS) -o $(EXECUTABLE) $(LIBS)

object_detection_test.o: object_detection_test.cpp
	$(CC) -c $(OPTIMIZATION) object_detection_test.cpp -o $(OBJS) $(CFLAGS)

clean:
	rm -f *.o
	rm -f $(EXECUTABLE)

