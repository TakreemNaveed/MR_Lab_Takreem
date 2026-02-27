# Week 1 Lab: Linux Onboarding and ROS 2 Setup

## Brief Description
[cite_start]This lab focused on the foundational setup required for ROS 2 development[cite: 7]. [cite_start]The primary objectives were to create a working ROS 2 development workspace, build a Python-based ROS 2 package named `my_first_pkg`, and successfully execute a basic node using the terminal[cite: 7, 8, 9]. [cite_start]This also involved learning essential Linux terminal navigation and understanding how the build system manages packages[cite: 73, 148].

## Commands Used
Here are the primary commands utilized during this lab session:
* [cite_start]`mkdir -p ~/ros2_ws_takreem/src`: Created the workspace and source directories[cite: 150]
* [cite_start]`sudo apt install python3-colcon-common-extensions`: Installed the necessary colcon build tools[cite: 250].
* [cite_start]`colcon build`: Compiled the workspace[cite: 152].
* [cite_start]`source install/setup.bash`: Sourced the workspace so ROS 2 could locate the new packages[cite: 154].
* [cite_start]`ros2 pkg create --build-type ament_python my_first_pkg`: Created the new Python package[cite: 169].
* [cite_start]`ros2 pkg list | grep my_first_pkg`: Verified the package was recognized by the system[cite: 175].
* [cite_start]`ros2 run my_first_pkg simple_node`: Executed the python node[cite: 234].

## Problems Faced and Solutions
1. [cite_start]**Command Not Found Error:** Initially, running `colcon build` resulted in a "command not found" error[cite: 247]. [cite_start]I solved this by using the package manager to install the missing tool with `sudo apt install python3-colcon-common-extensions`[cite: 250].
2. [cite_start]**Unrecognized Package:** After creating `my_first_pkg`, running the `grep` command returned a blank line, meaning ROS 2 couldn't find it[cite: 251]. [cite_start]I fixed this by ensuring I ran `colcon build` from the root workspace directory (`ros2_ws_takreem`) and, most importantly, running `source install/setup.bash` afterward in the current terminal[cite: 260, 261, 262].
3. **License Warning:** During the build process, I received a `UserWarning` stating that a license was set in `package.xml` but no `LICENSE` file was created. I realized this is a non-critical warning and does not prevent the package from building or running successfully.

## Reflection
This first lab provided a hands-on introduction to the structural requirements of ROS 2. Navigating the Linux terminal initially required some adjustment, but understanding the flow of creating a package, building it, and then sourcing the environment clarified how ROS 2 manages dependencies. The most crucial takeaway was the importance of the `source install/setup.bash` command; without it, the terminal remains completely blind to any newly written code. Grasping the distinction between a workspace (the overarching folder) and a package (the specific code module) makes the distributed architecture of ROS 2 much easier to visualize. Overall, resolving the minor build and pathing errors was highly educational for understanding the system's strict structural rules.
