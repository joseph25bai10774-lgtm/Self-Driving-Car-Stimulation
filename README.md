# Self-Driving-Car-Stimulation
A simple Prolog-based project that simulates a self-driving car using rule-based decision making for traffic lights, obstacles, and speed control.


HUMAN LIKE SELF DRIVING CAR AL (PROLOG)
    A smart self driving simulation built in Prolog that mimics human-like reasoning, decision-making, and learning behavior.
## Overview
   This repository contains a logic-based simulation environment for autonomous vehicles (AVs) built entirely in Prolog.
   
   
   ## Key Features
* **Rule-Based Decision Making:** Encodes real-world traffic laws and safety constraints into a logical expert system.
* **Symbolic Environmental Processing:** Represents the road, intersections, and hazards as discrete facts for the AI to process.
* **Deterministic Hazard Avoidance:** Uses logical deductions to guarantee safe braking and maneuvering when obstacles are detected.
* **State-Space Pathfinding:** Leverages Prolog's native backtracking to calculate optimal routes through a simulated grid or road network.

## How It Works
The environment is defined by a set of dynamic facts, while the car's behavior is governed by Prolog rules. The core engine continuously queries the best `action/1` based on the current state of the road. 

**Example Logic:**
```prolog
% The car must stop if the light is red and the intersection is near.
action(stop) :- 
    sensor(traffic_light, red), 
    distance(intersection, D), D < 10.

% The car may proceed if the path is clear.
action(drive_forward) :- 
    sensor(path_ahead, clear), 
    sensor(traffic_light, green).
