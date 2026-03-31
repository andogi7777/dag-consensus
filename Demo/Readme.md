CDML Drone Swarm Simulation

This project is a drone swarm simulation that faithfully implements the CDML specification.

Files
cdml_drone_swarm_sim.html
- Main simulation interface
cdml_drone_swarm_stage1.html
- Metrics and analytics dashboard

Button Scenarios
Add Intruder
Adds a Tier 0 drone with TLC = 0
When Mission Assignment is triggered:
- hasDB = false
- TX rejection logs can be observed

Cut GCS
Simulates GCS going offline
The drone with the highest TLC is automatically elected as the [C] coordinator
Coordinator is highlighted with an orange dashed ring

Assign Mission
Missions are distributed to Tier 2+ drones
Verifies k-of-n witness quorum signatures
Coordinated drones are highlighted with a green dashed ring

Metrics Panels
Intrusion Drone Blocking Rate
- Real-time tracking of intrusion attempts vs. rejections
msgs/TX
- Maintained between 15–19, independent of swarm size
GCS Recovery Time
- Time (in seconds) from GCS failure to coordinator election
Cross-network Mesh Density
- Number of active network edges

Parameters
Adjust system behavior using sliders:
- Half-life
- Swarm size
- Cross-link interval
- Quorum (k/n)
All values update dynamically in real time

Charts
TLC Distribution Time Series
- Tracks average TLC trends across tiers over time
msgs/TX by Swarm Size
- Bar chart comparing message overhead across different swarm sizes

Scenarios
Network Split
- Simulates a network partition
- Automatically reconnects after 6 seconds
- Logs cross-link recovery events

DDoS Witness Scenario
- Forces 3 nodes offline
- Triggers EmergencyReplace
- System recovers within 2.5 seconds

Export
Download all metrics as CSV: cdml_swarm_metrics.csv

Overview
This simulation demonstrates:
- Distributed drone coordination
- Consensus-based mission assignment
- Fault tolerance and recovery
- Adaptive network topology
