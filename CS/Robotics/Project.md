Project goal 
==
Build a physical remote controller (not a phone app) that can manually control a robot with an arm while showing a live camera feed on a small screen.

What makes your group different  
Other groups will build a software only controller (app).  
Your group will build a hardware remote with:

- joysticks and buttons for control
    
- a screen to view the robot camera live
    

System architecture  
You will have two Raspberry Pis:

Remote Raspberry Pi

- reads joystick and button inputs
    
- displays the live camera feed on the screen
    
- sends control commands to the robot
    

Robot Raspberry Pi

- receives commands and controls motors and arm
    
- streams camera feed back to the remote
    
- will later run autonomous mode logic
    

Communication is two way:

- Remote → Robot: control commands
    
- Robot → Remote: camera stream
    

Network model discussed:

- Robot is the server
    
- Remote is the client
    

Manual mode requirements  
In manual mode, the human controls everything by watching the screen and using the remote.

Minimum controls:

- 2 joysticks
    
    - Joystick 1: robot movement (forward, backward, turning, skid turns)
        
    - Joystick 2: arm movement (mapped to smooth arm behavior)
        
- Gripper control
    
    - Gripper Open button
        
    - Gripper Close button
        
- Emergency stop button (recommended)
    

Key technical challenge:

- Mapping joystick motion to smooth arm behavior
    
    - not just moving one joint at a time
        
    - joystick should trigger coordinated motor motions (behavior based movement)
        

Automatic mode requirements  
Final competition is autonomous, no human driving.

Your remote must support switching into autonomous mode:

- Mode selector:
    
    - Manual: joysticks control live
        
    - Auto: remote sends START AUTO once, then mainly shows camera feed
        

Best option:

- Manual/Auto toggle switch
    

Backup:

- Two buttons (Manual button and Auto button)
    

Important design idea:

- Build movement functions like move forward, turn, pick up, etc as reusable functions.
    
    - Manual mode calls them because human commands them.
        
    - Auto mode calls the same functions, but robot decides based on camera processing.
        

Deliverables (current phase)

- The physical remote controller
    
- Robot manual control integration  
    No separate PC display app required (PC is only used for coding).
    

Tentative remote hardware list you mentioned

- SD card reader
    
- SD card
    
- 7 inch display
    
- Breadboard
    
- Power bank (must support 5 V 5 A) we have 2 available
    

Next action items

- Keep remote smaller and simpler (screen size, fewer controls if possible)
    
- Finalize the full shopping list (including joysticks, buttons, switch, wiring, power)
    
- Start reading and implementing the protocol for:
    
    - sending joystick commands
        
    - streaming camera feed back


Understanding Projects
==

**Title:**  
**==1. Getting Ready==**

**Subsections:**  
**1.1** Introduction to MasterPi -> 

- 1.1.1 Product Introduction
	- Master Pi Robot has a mecanum chasis, meaning it has omnidrectional wheels that are essential for 360 (Degree) movements, it uses the OpenCV library in python to perform various image processing tasks.
- 1.1.2 Usage Precautions
- 1.1.3 Copyright Notice
- 1.1.4 Disclaimer

**1.2** Packing List

**1.3** Introduction to Raspberry Pi 5

- 1.3.1 Brief Introduction of Raspberry Pi 5
- 1.3.2 Hardware Structure and Feature
- 1.3.3 Dimension Diagram
- 1.3.4 The Use of Raspberry Pi

**1.4** Burn Raspberry Pi Image

- 1.4.1 Preparation
- 1.4.2 Format SD Card
- 1.4.3 Burn Image

**1.5** Robot Assembly

**1.6** Charging and Power-On Status Description

- 1.6.1 Lithium Battery Charging and Installation
- 1.6.2 Check Camera Connection
- 1.6.3 Startup Instruction
- 1.6.4 Activate Self-check Program
- 1.6.5 Check Battery Level

**1.7** Remote Desktop Installation and Connection

- 1.7.1 Preparation
- 1.7.2 Connect to Robot
- 1.7.3 Introduction to Desktop

**1.8** Adjust Pan-Tilt

- 1.8.1 Whether the deviation needs to be adjusted
- 1.8.2 The Causes of Deviation
- 1.8.3 The Standard of Deviation Adjustment
- 1.8.4 Adjustment Method