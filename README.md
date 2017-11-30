# PID Control Project 
By Pablo Sauras Perez

## Submission code location
The submited code can be found in the **src** directory. In particular, the following files have been modified:
- main.cpp
- PID.cpp

## Important Depencencies
As stated in the project description, these are the important dependencies.
- cmake >= 3.5
- make >= 4.1 (Linux, Mac), 3.81 (Windows)
- gcc/g++ >= 5.4

## Basic Build Instructions
As stated in th project description, from the project top directory:
- ```mkdir build && cd build```
- ```cmake .. && make```
-   ```./pid```

## Results
As it can be seen in the [results video](https://github.com/pablosaurasperez/CarND-PID-Control-Project/blob/master/PID_result.mov), there are some parts where the CTE increases and oscillates. However, the vehicle is within the road limits for the whole lap (the driver may be a little bit dizzy after the ride...).

### Parameter effect
The parameters affect in this way to the controller:
- **P:** The steering angle changes proportionally to the CTE. Thus, if the CTE is big, there will be large steering angle corrections. Ig I set this parameter really big, this may cause unestability because the car would steer all of a sudden.
- **I:** This parameter tries to correct potential bias in the system. As stated in the lesson, if the steering hasn't been ajusted properly, there would be some bias. In this project I assume that the steering has been perfectly calibrated. This, I don't touch this parameter.
- **D:** This parameter tries to avoid the overshooting. In this way, steering oscillations can be reduced.

### Parameter tunning
I have manually tunned the PID parameters:
- **P:** I studied this parameter first, mantaining the other two 0. I tunned it in such a way that the oscillations where "minimized".
- **I:** I am assuming that there is no bias in the steering angle. So I keep this parameter 0.
- **D:** Only with the P parameter, the vehicle overshoots. Thus, I tune this parameter to try to "minimize" the overshooting.

The final value of my parameters are: 

**- P = 0.1 
- I = 0.0
- D = 3.0**

The results could have been improved by implementing Parameter Optimization algorithms such a Twiddle.
