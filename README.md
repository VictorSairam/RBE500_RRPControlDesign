# Final Course Project on Joint Space PID Control of an RRP Robot Manipulator in ROS

Course Project for RBE500 - Foundations of Robotics (Fall 2021)

Master of Science in Robotics Engineering at [Worcester Polytechnic Institute](https://www.wpi.edu/)

**Group Members: -**
- [Sairam Venkataramani](https://github.com/VictorSairam)
- [Ravi Teja Alapari]

## Project Description

### Dependencies

- ROS Distro : [Noetic v1.15.13](http://wiki.ros.org/noetic)
- OS : [Ubuntu 20.04 LTS](https://releases.ubuntu.com/20.04/)

- Install the ROS dependencies using the following command:

    ```
    sudo apt-get install ros-noetic-ros-control ros-noetic-ros-controllers ros-noetic-gazebo-ros-pkgs ros-noetic-gazebo-ros-control
    ```

- To run this project, you need to clone the following additional repository in the `/src` of your ROS workspace

    [rrp_robot](https://github.com/ranebhushan/rrp_robot.git)

    ```
    git clone https://github.com/ranebhushan/rrp_robot.git
    ```

### Usage Guidelines

- To run this project, you will need to clone this repository in the `/src` of your ROS workspace 
    ```
    git clone https://github.com/ranebhushan/PID_Control_RRP.git
    ```

- Build your ROS workspace using either `catkin_make` or `catkin build` (depending on how your workspace was created)

- Open your ROS workspace in terminal and run the following command:
    ```
    source devel/setup.bash
    ``` 

- Launch the RRP robot manipulator in Gazebo Simulation Environment using by the following command:
    ```
    roslaunch rrp_gazebo gazebo.launch
    ```

- After the robot is successfully spawned in Gazebo, open a new terminal and launch the effort controller node and the joint state publisher by using the following command:
    ```
    roslaunch rrp_control rrp_effort_control.launch
    ```

- Begin the robot motion to target positions using the following command:
    ```
    roslaunch rbe500_project rrp.launch
    ```

- Meanwhile, open a new terminal to visualize current position, velocity and forces/torques of each robot joint as follows:

    ```
    rostopic echo /rrp/joint_states
    ```