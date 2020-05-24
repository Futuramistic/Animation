# Animation - forward and inverse kinematics 
<img src="https://github.com/Futuramistic/Animation/blob/master/GIFs/Walking.gif" align="right">

## Forward kinematics - simulate movement of a human character.
<div>
Press ‘L’ key to load a .bvh file.
In the viewport, you can rotate with left mouse,
and zoom with right mouse.
There are five display modes: joint – OpenGL matrix, joint – GLM matrix,
joint – GLM quaternion, skeleton, and mannequin. The default
mode displays joints transformed by OpenGL. 
You can also press ‘a’ or ‘A’ key to scroll to other display modes.

After a BVH file is loaded, the top left corner of the window
displays the time elapsed since the BVH file is opened, and the
frame that is currently played. 

The code uses the GLM library for vector and matrix
calculation, and the GLUT library to support OpenGL rendering
</div>
<div style="padding:20px">
 <img src="https://github.com/Futuramistic/Animation/blob/master/GIFs/jumping.gif" align="left">
</div>
The code package contains a simple BVH player and a set of .bvh motion data.

Available motion data:
<ul style="margin:20px">
 <li>T-pose</li>
 <li>Walking</li>
 <li>Jogging</li>
 <li>Side Skip</li>
 <li>Slow Trot</li>
 <li>Stomping</li>
 <li>Backwards Walking</li>
</ul>

## Inverse Kinematics - ball catching
Uncomment the following line (line #7, right below the header) in BVHPlayer.cpp: 
#define TEST_IK

This enables the program to draw a sphere at a specified target location and pose the
character's left arm to reach the target with his left hand joint.

Only uses <b>static poses</b>, i.e., only to draw the character at one
particular frame. 

We assume 3DOF (X-, Y-, Z- rotation) for shoulder joint and 1DOF for elbow
joint, i.e., 4 variables and 3 constraints. We use Jacobian Inverse method.
Use left, right, up, down arrow keys, pageUp and pageDown to move the target.

The joint constraints are <b>not</b> taken into consideration!
