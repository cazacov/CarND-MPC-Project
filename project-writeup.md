# Model Predictive Control (MPC)

## Model

This projects presents a car with simplified Kinematic model that ignores tire forces, gravity and mass.

![X](img/xt.png)
![Y](img/yt.png)
![P](img/psi.png)
![V](img/a.png)

Model state is tracked in a vector with the following variables:

- x - X position in car's coordinate 
- y - Y position 
- psi - Yaw angle in radians
- v - Velocity in meters per second

To capture how errors are changing over time the state vector includes also
- cte - Cross track error  
- epsi - Orientation error 

The goal is to calculate desired 
- delta - Steering wheel angle
- acc - Acceleration from throttle and break pedals
 

## Timestep

## Preprocessing

## Handling latency