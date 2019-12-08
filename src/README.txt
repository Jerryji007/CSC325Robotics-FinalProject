CSC325 Final Project "Coffee" delivering to Nick

We use gmapping and amcl to map out the Steinmetz hallway and 
picked 3 three locations (nick, matt, resource) 
and wrote a script for the turtlebot to navigate automatically to 
the destination after placing the turtlebot in the hallway and give it an 2D position.

Here are the procedures on how to test and use our project:
1. Configure the machine with ros indigo installed with the turtlebot-01. 
   (The iMAC in the corner of the crochet has already been configured to the turtlebot-01.)

2. Bring the turtlebot to any desired starting point on the Steinmetz hallway.

3. Turn on the base and the computer. 
   (Shut down entirely and restart if the following steps doesn’t work.)

4. SSH to the turtlebot-01 from the configured machine and on the turltebot terminal run: 
	$ roslaunch turtlebot_bringup minimal.launch

5. In a new turtlebot terminal, type:
	$ export TURTLEBOT_MAP_FILE=~/Desktop/steinmetz_hall.yaml
	$ roslaunch turtlebot_navigation amcl_demo.launch

6. On a new terminal from the configured machine, type:
	$ roslaunch turtlebot_rviz_launchers view_navigation.launch --screen

7. Then do a 2D-pose estimation on the rviz interface

8. Start a new turtlebot terminal and type:
	$ rosrun deliver destination.py <destination>
	Currently, only “nick”, “matt” and “resource” would work.

9. Run and the turtlebot would go to the desired location.
	If there are severe offset during the path like Wifi connection, 
	people moving the turtlebot, please go back to step 7. 
	If not working please go back to step 3.
