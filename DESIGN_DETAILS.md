# Project Design Details

## 1. Start Turtlesim, Spawn/Kill Turtles, and Create the Code Base

We begin with Turtlesim, a simple 2D simulator. The main tasks here are:

- **Start Turtlesim**: Launch Turtlesim using ROS2.
- **Spawn/Kill Turtles**: Add or remove turtles in the Turtlesim environment through service calls.
- **Create the Code Base**: Establish the basic structure of the project, including service clients for spawning and killing turtles.

## 2. Action Server (MoveTurtle)

The core of our project is the **MoveTurtle** action server. This server will:

- **Accept Goals**: Take in a goal position for the turtle.
- **Validate Goals**: Check whether the goal is achievable (e.g., within the screen boundaries).
- **Goal Policy**: Implement a policy to reject goals that are not feasible.

The server will handle the entire process of moving the turtle to the desired position.

## 3. Transform into a Lifecycle Node

To add more control over the **MoveTurtle** action server, we’ll convert it into a lifecycle node. This means:

- **Activate/Deactivate**: The server can be turned on or off, depending on the system’s needs.
- **Lifecycle Management**: We’ll manage the server’s state transitions (e.g., from inactive to active).

## 4. Transform into a Component

Next, we’ll take the lifecycle node and make it a component. This allows the node to be loaded into a component container dynamically. The steps include:

- **Create a Component**: Turn the lifecycle node into a component.
- **Load into a Container**: Use a component container to run the component.

## 5. XML Launch File

We’ll create an XML-based launch file that simplifies starting the entire system. This file will:

- **Launch Components**: Automatically bring up the necessary nodes and components.
- **Manage Parameters**: Allow for easy configuration of the system’s parameters.

## 6. Adapt the Code for TurtleBot in Gazebo

Finally, we’ll take everything we’ve built and adapt it for use with TurtleBot in a 3D Gazebo environment. This includes:

- **Code Adaptation**: Modify the code to work with TurtleBot’s movement and sensors.
- **Gazebo Integration**: Ensure the TurtleBot operates correctly in the Gazebo simulation.
