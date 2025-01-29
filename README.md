# Automatic-Parking-Simulator
Matlab

The full description of the project is presented in the document "Automatic Parking"

The environmental model is a map of the environment. This map includes available and occupied parking spaces, road markings, and obstacles such as pedestrians or other vehicles. Such a map is usually built using Simultaneous Localization and Mapping (SLAM) by integrating
observations from lidar sensors and the camera. In this scenario, the map is already provided. The map used is composed of three layers of occupancy grids:
	Stationary obstacles: This layer contains stationary obstacles such as walls, barriers, and parking limits.
	Road markings: This layer contains information about road markings, including road markings for parking spaces.
	Parked cars: This layer contains information about parking spaces that are already occupied.

![Image](https://github.com/user-attachments/assets/cc88a5af-dee2-4c05-a5dd-bf4d7cdf36ff)

The table specifies the start and end positions of the segment, as well as the properties of the segment, such as the speed limit.

![Image](https://github.com/user-attachments/assets/186a7c3b-4ccf-40aa-8b78-d5ecb06bd580)

Planning is a hierarchical process, each successive layer being
responsible for a more precise task. The behavior layer is at the top of this stack. Block Behavior Planner
triggers a sequence of navigation tasks based on the global route plan, providing an intermediate objective and configuration for the Motion Planning and Trajectory Generation blocks. Each path segment is navigated using these steps:
  •	Motion planning: Plan a feasible path through the environment map using the optimal Fast Random Tree Exploration (RRT*) algorithm (pathPlannerRRT).
  
  •	Trajectory Generation: Smooth the reference path by matching splines, to it using the Path Smoother Spline block. It then converts the smoothed path to a trajectory by generating a velocity profile using the Velocity Profiler block.
  
  •	Vehicle control: HelperPathAnalyzer provides the signal reference for the Vehicle Controller subsystem that controls the direction and speed of the vehicle.
  
  •	Goal check: whether the vehicle has reached the final position.

![Image](https://github.com/user-attachments/assets/abc1ba61-3e1a-4861-8a29-ff036315c671)

#Functionality

The way the vehicle follows the reference path to a specific empty parking space in order to park.

![Image](https://github.com/user-attachments/assets/5da530f1-c35d-44ba-9a27-ca9adebcad96)

The estimated time until the vehicle reaches its destination is approximately 40 seconds.

![Image](https://github.com/user-attachments/assets/a1bca004-3f6d-4b10-a38d-4216d25483fc)

The automated parking lots bring numerous benefits, including increased efficiency, time and space savings, reduced traffic and emissions, thus facilitating a more sustainable approach to urban mobility. However, their implementation requires adequate infrastructure and significant investments in technology.







