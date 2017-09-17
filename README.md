# jackal-move
Moving jackal to a location while avoiding an obstacle.
***************
To run it:
roslaunch jackal_gazebo jackal_world.launch config:=front_laser
roslaunch jackal_navigation amcl_demo.launch map_file:=/home/hassan/jackal-move/mazemap.yaml 
roslaunch jackal_viz view_robot.launch config:=localization
rosrun movejak movetoloc.py 
****************
Initially I thought of using movet package since my expeirnce with motion planning was avec this package and that was my main issue. I had my first plan to launch the jackal in a world in gazebo and then map it using gmapping, save the map and use it for motion planning. However, I spent a lot of time trying to figure out how to do it and I did create a configuration package for jackal based on its urdf file, yet it didn't work. 
Eventually I could reach to the correct source of information to use move_base when it's a mobile robot. So, I procedded as follows:
First, familiarized myself with jackal through the already existing packages for navigation and simulation.
Second, I used the launch files and gazebo and mapping to create a map and saved it. (mazemap.yaml)
Third, I used rviz to pick a coordinate for a point to set as a goal
Finally, I used the code on learnrobotics to plan for a path to the desired goal 
