---
layout: default
title: Visualisation and Teleop
parent: Simulation
nav_order: 1
has_toc: false
---

# 🔍 Visualisation and Teleop

* Table of contents
{:toc}

The goal of this section is to run the robot simulation using Gazebo, visualise the SMB robot in RViz, control the robot.

First of all, make sure the `smb_gazebo` has been already built successfully.

```bash
# In the host pc, build the smb_gazebo package if you haven't already
 smb_build_packages_up_to meta_smb_sim
```

## 👀 Visualisation

Run the following commands in the host pc to visualise the robot.

```bash
# In the host pc
ros2 launch smb_bringup smb_sim_exploration.launch.py
```

To run the simulation you do not need a connection to SMB.


## 🎮 Teleoperation

You can drive the robot with the keyboard. If you want to drive the robot, make sure that the terminal where you launched the simulation (i.e. where the [`teleop_twist_keyboard`](http://wiki.ros.org/teleop_twist_keyboard) node is running) is selected while pressing the keys. To use the keyboard run the following .sh file:

    ```bash
    # In the host pc
    smb_teleop_twist_keyboard
    ```

    - Use the following keys to move:

        | u | i | o |
        | j | k | l |
        | m | , | . |

    - Use the following keys to control speed:

        - `q/z`: Increase/decrease max speeds by 10%
        - `w/x`: Increase/decrease only linear speed by 10%
        - `e/c`: Increase/decrease only angular speed by 10%

    - Use any other key to stop.

    Please refer to the [package documentation](http://wiki.ros.org/teleop_twist_keyboard#Controls) for more info.

