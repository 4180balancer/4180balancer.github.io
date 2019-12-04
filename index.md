# Welcome to the 4180Balancer Project!
`Created by John Lee, Nyle Malik, and Austin Lowe`

Below is a description of a balancing robot designed for ECE 4180 at Georgia Tech.

## Project Idea

<p align="center">
  <img width="460" height="300" src=""><br/>
  <b>Image of Bot</b>
</p>

The general idea of this project was to design a mobile robot with a tall base that adjusts its wheel speeds to stay upright. With major changes in parts used, complexity of design, and how the motors are driven, it was inspired by Mark William's [Success with a Balancing Robot using a Raspberry Pi](http://ozzmaker.com/success-with-a-balancing-robot-using-a-raspberry-pi/). Our design incorporated learnings and parts from previous labs within 4180 itself, such as the use of a dual H bridge motor driver, IMU, and a Raspberry Pi, as well as new concepts developed in Mark William's project, including work with a PID controller and encoders. The combination of these efforts led to what we call the **4180Balancer**.

<p align="center">
  <img width="460" height="300" src=""><br/>
  <b>Video Demo</b>
</p>

## Instructions & Hardware Setup

Prior knowledge of the following concepts were used:
- Controls
- C++
- Raspberry Pi<br/><br/>

1. To begin, acquire the following components and materials:
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
- Wires<br/>

2. Assemble the base whether by 3D printing or building one. Our base was two 8in x 3in x 1/2in parts connected by four 4in rods.

3. [Setup the Rasberry Pi is set up](https://projects.raspberrypi.org/en/projects/raspberry-pi-setting-up/6).

4. Once the Pi is set up, copy our code in the section below onto it using Filezilla or another similar process. 

5. With the Pi fully loaded, place components on the base starting with assembling the Motors, Mounting Hubs and Wheels, which go underneath the base, connecting the IMU, H Bridge and Pi to the breadboard, which will go on the top platform, and putting the Pi on the lower platform.<br/>
<p align="center">
  <img width="460" height="300" src=""><br/>
  <i>Under the Bottom Platform</i>
</p>
<p align="center">
  <img width="460" height="300" src=""><br/>
  <i>On top of the Bottom Platform</i>
</p>
<p align="center">
  <img width="460" height="300" src=""><br/>
  <i>On top of the Top Platform</i>
</p>

6. Connect power to the Pi with the cord that comes with it and power to the breadboard with the 9V power cord, stepped down to 6V using resistors and a [voltage divider](https://learn.sparkfun.com/tutorials/voltage-dividers/all).

7. Once all of the components are in place, launch the Pi, navigate to the folder where your code is stored and run it using the following commands, where XXX should be the XXX values.<br/>
`make`
`./final XXX`

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
