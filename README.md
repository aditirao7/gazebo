# Gazebo Simulation
  Gazebo simulation of a bot equipped with GPS navigation using navigation stack.
  
## TF Tree
   ![alt text](https://github.com/aditirao7/nav_stack/blob/master/graphs/tf_tree.jpg)
   
## RQT Graph
   ![alt text](https://github.com/aditirao7/nav_stack/blob/master/graphs/rqt_graph.jpg)
  
## How to Run
   1. Install:
      ```bash
         sudo apt-get install ros-melodic-navigation && sudo apt-get install ros-melodic-robot-localization
      ```
   2. Clone repo **inside workspace src**.
      ```bash
         git clone https://github.com/aditirao7/gazebo.git
      ```
   3. On 4 separate terminals, run:
      ```bash
         catkin_make && source devel/setup.bash
      ```
   4. Then run:
      ```bash
         roslaunch mybot_gazebo mybot_world.launch
         
         roslaunch mybot_navigation localization.launch
         
         roslaunch mybot_description navigation_rviz.launch
         
         cd src/gazebo/mybot_navigation
         chmod +x goal.py
         rosrun mybot_navigation goal.py 49.9000357573 8.8999449505
      ```
   5. Give the GPS location for goal.py accordingly.
   
## Issues
   - Goal that is too far will give warning: "goal is off the global costmap" in the localization terminal.
   - GPS goal orientation is 1.0 because move_base requires goal orientation 

