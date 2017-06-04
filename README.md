Implemented a PID controller in C++


Video Reference:
You can see how the car performs in a simulated environment here : 

[![Alt text](https://img.youtube.com/vi/7tYUHxwhNRI/0.jpg)](https://www.youtube.com/watch?v=7tYUHxwhNRI)

# Reflection : 

In this project, I have built a PID controller and tuned the PID hyperparameters by applying the general processing flow as described in the SDCND lessons.
My implementation of the PID controller in C++ is spawned to control steer and maneuvers the vehicle around the track. The simulator provides the cross track error (CTE) and the velocity (mph) in order to compute the appropriate steering angle.

# The effect of the P, I, D component of the PID algorithm: 

I tweaked the PID coefficients via trial and error and used that to update the steering value.
While running the contoller with varying coefficients values for the P,I,D, I observed change in magnitude of oscillation, steering and cross track error. 
I observed an increase in value of P increased the magnitude of the oscillation, and setting the D coefficients too high caused sharp steering change.  
Setting the P value to 0.2 and the value for D at 3.0 gave me an expected result and found the CTE dropped down.
Then I started tweaking integral factor that counter systematic bias and setting the integral component to 0.001 helped the CTE converged down to 0.04 or -0.10.

In order to find good control gains,I will continue to work on this project and add twiddle algorithm to the controller. 

[//]: # (Image References)
[image1]: ./images/CTE-Converges-to-04.jpg
[image2]: ./images/CTE-Converges-to-0.38.jpg
[image3]: ./images/CTE-Converges-to-1.44.jpg 

## Image : CTE Converges to .04 

![alt text][image1]

## Image : CTE Converges to 0.38  

![alt text][image2]

## Image : CTE Converges to 1.44

![alt text][image3]

---
## Dependencies


* cmake >= 3.5
 * make >= 4.1
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools]((https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)
* [uWebSockets](https://github.com/uWebSockets/uWebSockets) == 0.13, but the master branch will probably work just fine.
 




 
 