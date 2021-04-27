Required alterations:

    To allow joystick_control.launch to work properly    

    Following changes needs to be updated to:
    moveitjoy_module.py 

    Path:
    /opt/ros/noetic/lib/python3/dist-packages/moveit_ros_visualization/moveitjoy_module.py

    (changes can be found by CTRL+F: "Jan Edit")

        Line 516:
            # for name in planning_groups.keys():       # Original
            for name in list(planning_groups.keys()):   ¤ Jan Edit

        Line 523:
            # self.planning_groups_keys = planning_groups.keys()       # Original #we'd like to store the 'order'
            self.planning_groups_keys = list(planning_groups.keys())   # Jan Edit

        Line 770
            # if self.counter % 10:                             # Jan Edit (comment out)
        #     self.update_start_state_pub.publish(Empty())

    MoveIt RVIZ:
        To allow joystick_control 
        Planning Group: End Effector
