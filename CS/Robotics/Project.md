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