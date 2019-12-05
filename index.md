# Welcome to the 4180Balancer Project!
`Created by John Lee, Nyle Malik, and Austin Lowe`

Below is a description of a balancing robot designed for ECE 4180 at Georgia Tech.

## Project Idea

The general idea of this project was to design a mobile robot with a tall base that adjusts its wheel speeds to stay upright. With major changes in parts used, complexity of design, and how the motors are driven, it was inspired by Mark William's [Success with a Balancing Robot using a Raspberry Pi](http://ozzmaker.com/success-with-a-balancing-robot-using-a-raspberry-pi/). Our design incorporated learnings and parts from previous labs within 4180 itself, such as the use of a dual H bridge motor driver, IMU, and a Raspberry Pi, as well as new concepts developed in Mark William's project, including work with a PID controller and encoders. The combination of these efforts led to what we call the **4180Balancer**.<br/><br/>

<p align="center">
  <img width="300" height="300" src="https://raw.githubusercontent.com/4180balancer/4180balancer.github.io/master/all.jpg"><br/>
</p>

### PID Explained

One of the main difficults of this project was dealing with PID, Proportional Integral Derivative. PID is a control algorithm that keeps the robot stable and balanced by ensuring that the center of gravity is always inline, above the wheels. The main features in our PID are acceleration and gyro, measured by the IMU as it moves around.<br/><br/>

First, the gyro should determine the speed of rotation in degrees per second. This number will be found by multiplying by a constant value depending on the sensitivity of a particular gyro by the raw data from the x-axis. Once this speed of rotation is found, multiply it by the time it takes to complete one cycle of the main loop, and save this number as gyroXangle, the current X angle determined by the gyro.<br/><br/>

Next, we can compute the accelerometer angle by taking the raw accelerometer Y and Z values and using *Atan2* to determine the X angle. This number should be added to pi and then converted from radians to degrees. As a result, save this value as the AccXangle, the acceleration of the X angle.<br/><br/>

Finally, we need to add our filter. Two main ones you could use are the Kalman Filter or the Complementary Filter, but we went with the Complementary Filter because it is simpler to understand and less harsh on your CPU. With our resulting degrees from the previous part, run the following equation to get a final angle that will be used to balance the 4180Balancer.<br/><br/>

```markdown
CFangleX = 0.98*(CFangleX + gyroXangle) + 0.02 * AccXangle
```

### Demo of 4180Balancer
<p align="center">
  <img width="300" height="300" src=""><br/>
</p>

## Instructions

Prior knowledge of the following concepts were used:
- Controls
- C++
- Raspberry Pi<br/><br/>

1. To begin, acquire the following components and materials:<br/><br/>
- [9DoF IMU](https://www.sparkfun.com/products/13944)
- [Raspberry Pi 4](https://www.raspberrypi.org/products/raspberry-pi-4-model-b/)
- [Dual H Bridge](https://www.sparkfun.com/products/14450)
- [2 Motors with Encoders](https://www.pololu.com/product/4822)
- [2 Wheels](https://www.pololu.com/product/1435)
- [Mounting Hubs for the Wheels](https://www.pololu.com/product/1081)
- 9V Power Cord
- Small breadboard
- A 3D-printed base (could be substituted with any other materials, including wood, metal, etc.)
- Super glue
- Zip ties
- Wires<br/><br/>

2. Assemble the base whether by 3D printing or building one. Our base was two 8in x 3in x 1/2in parts connected by four 4in rods.

3. [Setup the Rasberry Pi.](https://projects.raspberrypi.org/en/projects/raspberry-pi-setting-up/6)

4. Once the Pi is set up, copy our code in the section below onto it using Filezilla or another similar process. 

5. With the Pi fully loaded, place components on the base starting with assembling the Motors, Mounting Hubs and Wheels, which go underneath the base, connecting the IMU, H Bridge and Pi to the breadboard, which will go on the top platform, and putting the Pi on the lower platform.<br/>
<p align="center">
  <img width="300" height="300" src="https://raw.githubusercontent.com/4180balancer/4180balancer.github.io/master/bottom.jpg"><br/>
  <i>Under the Bottom Platform</i>
</p>
<p align="center">
  <img width="300" height="300" src="https://raw.githubusercontent.com/4180balancer/4180balancer.github.io/master/lower.jpg"><br/>
  <i>On top of the Bottom Platform</i>
</p>
<p align="center">
  <img width="300" height="300" src="https://raw.githubusercontent.com/4180balancer/4180balancer.github.io/master/top.jpg"><br/>
  <i>On top of the Top Platform</i>
</p>

6. Connect power to the Pi with the cord that comes with it and power to the breadboard with the 9V power cord, stepped down to 6V using resistors and a [voltage divider](https://learn.sparkfun.com/tutorials/voltage-dividers/all).

7. Once all of the components are in place, launch the Pi, navigate to the folder where your code is stored and run it using the following commands, where XXX should be the XXX values.<br/>
```markdown
make
./final XXX
```

8. Watch the **4180Balancer** do its job!

## Code

Makefile
```markdown
xxx
```

main.cpp
```markdown
xxx
```

encoders.h
```markdown
xxx
```

GPIOpinsMotorConstroller.h
```markdown
xxx
```

pins.h
```markdown
xxx
```

## Hardware Setups

XXX Table for the pin outs
