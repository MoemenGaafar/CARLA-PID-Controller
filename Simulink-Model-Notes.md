In the attached simulink file are two block diagrams of our closed loop system: 

In the first diagram:
- We connected the plant, the controller, a step input, and a few scopes or "To Workspace" dataset blocks. 
- The aim of this diagram was to design each iteration of the controller and then analyze the system's step
response and deduce the controller's specifications. 

In the second diagram: 
- We connected the plant, the controller, an input dataset named "DesiredYaw", and a scope that plots the plant's
output, the "DesiredYaw" dataset, and a third "ActualYaw" dataset.
- Before explained what these datasets hold, we note that due to the interpolation of waypoints performed by 
the Carla python client we used, the set of desired yaws our car aims to reach in each run are dependent on the 
controller orchestrating its motion. Hence to compare the response of the Carla car and the simulink model to 
any particular controller, we had to simulate our car's motion on the given racetrack and collect the set of 
desired yaws it followed then give those as reference to the simulink model.
- Thus, "DesiredYaw" is a "From Workspace" dataset of the desired yaws produced by the Carla Simulator each
timestep, and "ActualYaw" is a "From Workspace" dataset of the car's yaw each timestep.
- Finally, this block diagram aimed to test and plot for each designed controller the response of both
the simulink plant and the Carla vehicle to the same set of desired yaws. 