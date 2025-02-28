# dsa-queue-simulator
Traffic Light Simulation using SDL3

**Overview**

This project is a Traffic Light Simulation built with C and SDL3, designed to simulate the movement of vehicles based on traffic light changes and predefined road rules.

**Key Features**

Traffic Light System: Lights switch at regular intervals to control vehicle movement.

Vehicle Queue Management: Vehicles are randomly generated and dequeued when the light turns green.

Intersection Handling: The simulation includes roads with three lanes per direction.

Basic Rendering: Roads and pedestrian crossings are visually represented.

Here is the traffic simulation GIF:

![Final Traffic GIF](gif/final%20traffic.gif)

**Current Progress**

✅ Vehicle Generator: Generates vehicles with unique attributes and writes data to files.

✅ Data Parsing in Simulator: Successfully processes vehicle data.

🚧 Simulation Execution: Works up to lane switching; dequeue implementation and light transitions are in progress.

**System Components**

**1. Vehicle Generator**

The generator continuously creates vehicles and assigns them:

Unique ID

Entry and exit lanes

Direction (North, East, South, or West)

Movement state:

0: Queued (waiting at red light)

1: Moving (on green light)

2: Passed (successfully crossed the intersection)

The generated data is stored in text files (e.g., AL2.txt).

**2. Traffic Simulator**

The simulator reads vehicle data from the generator's output and simulates their movement based on predefined traffic rules. It processes vehicles from the queue and updates their state as they transition through lanes.

**3. Lane Movement Rules**

L3 lanes always turn left:

AL1 → BL3

BL3 → CL1

CL1 → DL3

DL3 → AL1

L2 lanes can go straight or turn right:

AL2 → CL1 or DL1

BL2 → AL1 or DL1

CL2 → AL2 or BL1

Vehicles follow these rules as they move through the simulation.

**4. Data Exchange Between Components**

The generator writes vehicle data to files that are continuously updated.

The simulator reads these files and processes vehicle movement based on traffic rules.

The vehicle data format includes details like ID, lane position, direction, and state.
