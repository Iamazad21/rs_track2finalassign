## Assignment of the Research Track 2 course 
 mohammad azad hussain (matricola 4916211)

# About the assignment
This action branch defines the controlling the robot in GAZEBO simulation with the ros. Including the action server in the given package nodes .ROS Actions have a client-to-server communication relationship with a specified protocol. The actions use ROS topics to send goal messages from a client to the server. You can cancel goals using the action client. ... This function enables you to return the result message, final state of the goal and status of the server.
The robot starts from the origin with out any orientation or velocity. When the user is requestes the gotopoint requests the (x,y,theta)  to position server and position server returns the values. Action server is used to pause the simullation.

# ACTION SERVER 
The ActionClient and ActionServer communicate via a "ROS Action Protocol", which is built on top of ROS messages. The client and server then provide a simple API for users to request goals (on the client side) or to execute goals (on the server side) via function calls and callbacks

action
ROS Actions have a client-to-server communication relationship with a specified protocol. The actions use ROS topics to send goal messages from a client to the server. You can cancel goals using the action client. ... This function enables you to return the result message, final state of the goal and status of the server.

CMakelist.txt
CMakeLists. txt file contains a set of directives and instructions describing the project's source files and targets (executable, library, or both). When you create a new project, CLion generates CMakeLists. ... txt files to describe the build, contents, and target rules for a subdirectory of the assignment.

package.xml
The package manifest is an XML file called package. xml that must be included with any catkin-compliant package's root folder. This file defines properties about the package such as the package name, version numbers, authors, maintainers, and dependencies on other catkin packages.

# Topics list

- cmdvel                  
- odom                  
- tf                    
- clock                    

# nodes list

- gotopoint                  
- Position server                  
- UserInterface       
- statemachine
- Gazebo

go_to_point:
go_to_point node will implements a service to start or stop the robot towards a point in the environment.And the service implemented in this node would be able to drive the robot towards a certain position in space of (x,y) and with a certain angle (theta) and the action server is included.

user_interface:
User interface node is to control the robot with the attributes start and stop and calls the service implemented in the state_machine node.

position_service:
The node PositionServer, which implements a random Position Server.And the service implemented in this node will gives the random values for x,y and theta in which the the values of x and y should be limited between min and max value.




# Executing the package(individual)

create a workspace in root repositories

```
cd
```

```
mkdir "name of the workspace"
```

```
cd "name of the package"
```

```
mkdir src
```

Build the package

```
catkin_make
```

clone the repository 

```
git clone -b action https://github.com/vikasreddy636/rt2_assignment1.git
```

Refresh the workspace using

```
rospack profile
```

To launch the node
````
roslaunch rt2_assignment1 sim.launch
````

in other terminal, open coppeliasim
````
./coppeliaSim
````
