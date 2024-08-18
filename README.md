# ros2-turtlesim-turtlebot-integration-project# Turtlesim and TurtleBot ROS2 Project

Welcome to the Turtlesim and TurtleBot integration ROS2 Project! This project is all about understanding how to manage a robot’s lifecycle, handle actions, and control a robot in simulation using ROS2. I started with something simple like Turtlesim and then adapted the code to work with TurtleBot in Gazebo.

## Project Overview

This project walks you through several key steps:
1. **Start with Turtlesim**: We’ll begin by setting up the Turtlesim, a basic 2D simulator, and spawning or removing turtles from the environment.
2. **Action Server (MoveTurtle)**: You’ll create an action server to move the turtle. The action server will also include goal validation and a policy for accepting or rejecting goals.
3. **Lifecycle Management**: The action server will be enhanced by turning it into a lifecycle node, allowing you to activate or deactivate it as needed.
4. **Component Architecture**: The lifecycle node will then be turned into a component that can be dynamically loaded into a component container.
5. **XML Launch File**: We’ll create an XML launch file to bring everything together, making it easy to start up the system.
6. **Adaptation for TurtleBot**: Finally, we’ll adapt the code to work with a TurtleBot in the Gazebo simulation environment.

## Features

- **Turtlesim Integration**: Learn how to manage turtles in a simulated 2D world.
- **Action Server**: Create a server that controls turtle movements with validation checks.
- **Lifecycle Node**: Manage the action server’s state to ensure it only runs when needed.
- **Component-based Design**: Convert the lifecycle node into a reusable component.
- **Gazebo Simulation**: Adapt your code for a 3D TurtleBot simulation in Gazebo.

## What's Inside

Here's a breakdown of what you'll find in this project:

- **launch/**: Contains the launch files that start the simulation, component_containter_mt and the lifecycle nodes.
- **src/**: Holds the main source code for the TurtleBot and Turtlesim controllers.
- **include/**: Contains the header files for the project.
- **CMakeLists.txt**: The CMake build script for compiling the project.
- **package.xml**: The package manifest file with dependencies and metadata.

## Getting Started

### Prerequisites

Before you begin, make sure you have:

- **ROS2 Humble** installed.
- **Gazebo** installed.
- **Turtlesim** and **Turtlebot3** installed.

### How to Run the Project

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/Realone16/ros2-turtlesim-turtlebot-integration-project.git
    cd ros2-turtlesim-turtlebot-integration-project
    ```

2. **Source Your ROS2 Workspace**:
    ```bash
    source /opt/ros/humble/setup.bash
    ```

3. **Build the Packages in Your Workspace**:
    ```bash
    colcon build --packages-select final_project my_robot_bringup
    ```
    
4. **Launch the XML Launch File**:
    ```bash
    ros2 launch my_robot_bringup turtle_controller.launch.xml
    ```

5. **Send the goal to the action server**:
    ```bash
    ros2 action send_goal /move_turtle_abc my_robot_interfaces/action/MoveTurtle "{linear_vel_x: 1.5, angular_vel_z: 0.7, duration_sec: 5.0}"
    ```

6. **Adapt the codes so as to control TurtleBot**:
    When you're ready, switch over to the turtlebot_controller.cpp code and the launch file turtle_controller.launch.xml in final_project and           my_robot_bringup packages respectively for simulation in Gazebo.


7. **Launch the XML Launch File**:
    ```bash
    ros2 launch my_robot_bringup turtlebot_controller.launch.xml
    ```

8. **Send the goal to the action server**:
    ```bash
    ros2 action send_goal /move_turtle my_robot_interfaces/action/MoveTurtle "{linear_vel_x: 1.5, angular_vel_z: 0.7, duration_sec: 5.0}"
    ```

