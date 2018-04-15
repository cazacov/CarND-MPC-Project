# Model Predictive Control (MPC)

## Model

This projects replaces real car with a simplified Kinematic model that ignores tire forces, gravity and mass and predicts next state based only on trigonometric considerations. 

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
- a - Acceleration from throttle and break pedals
 
The model has also hyperparameter Lt equal to distance between car's center of gravity and forward wheels in meters.   

## Timestep

First I set the prediction horizon to 1 second and split it into 20 steps.

![T=1, N=20 dt=0.05](img/T1.jpg)

The car was little bit unstable because it could not predict road turns in advance, so I decieded to increase the prediction horizon to 2.4 seconds. That matches good with the waypoints provided by the simulator.

![T=2, N=24 dt=0.1](img/T24.jpg)

Finally I reduced the number of steps to 12 to reduce the calculation effort.

![T=2, N=24 dt=0.1](img/N12.jpg)

- T = 2.4 seconds
- N = 12 steps
- dt = 0.2 seconds


## Preprocessing

## Handling latency