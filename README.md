# CS4222PA3-ShootingApp
A CS4222 project
 
Sun Siyue A0101491U
Guo Xiang A0112659A
Ji Yahui A0101973J

1. We add a new variable "private Sensor orientationSensor" to hold the newly added "Rotation Vector Sensor";

2. We put the "orientationSensor" to "initSensors" function to initilize it to TYPE_ROTATION_VECTOR;

3. We added the "orientationSensor" to "StartSensing" function to add it to the listener.

4. In "onSensorChanged" function, we added a else if condition where the sensor type is "TYPE_ROTATION_VECTOR";

5. We implemented a new function called "processOrientation", which would be called when we find the sensor has "TYPE_ROTATION_VECTOR";

6. In the "processOrientation" function, we first pass in the event argument, then we use the function "getRotationMatrixFromVector" to convert the values to a rotation matrix, next we use the function "getOrientation" to extract the current 3D orientation from the rotation matrix to an array of floats, convert them to degrees, 
then we get the first value of the array and it is the orientation we were looking for.

7. The range of the degree was from -180 to 180, so we increase it by 180 and divide by 45 to get the region number and assign it to display.

8. We tried to smoothen the orientation value with a mean filter, but it seemed that there was not difference, probably because being a virtual sensor, the rotation vector sensor had already been smoothened before outputing data.
