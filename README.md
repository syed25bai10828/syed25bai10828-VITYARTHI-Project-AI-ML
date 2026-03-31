# syed25bai10828-VITYARTHI-Project-AI-ML
Industrial Protocol Logic Firewall (IPLF)
Deterministic Cybersecurity for Industrial Control Systems
This project implements a Rule-Based  AI Detector designed to protect industrial machinery (like valves, motors, or turbines) from malicious command injections and automated bot attacks. Instead of guessing with probability, it uses a Finite State Machine (FSM) to ensure every command is physically and logically valid.
________________________________________
Overview
In industrial environments, safety is paramount. A standard firewall might allow a command because the "password" is correct, but it won't know that opening a valve while the system is OFF could cause a physical explosion.
This Protocol Logic Firewall fills that gap by maintaining "State Awareness." It tracks the current status of the machine and blocks any command that violates the predefined industrial workflow.

How It Works
The core of the system is a State Transition Map. The firewall only permits a command if it is a valid "next step" from the current machine state.
Current State	Allowed Next Commands
OFF	STARTING
STARTING	RUNNING, OFF
RUNNING	OPEN_VALVE, STOPPING, OFF
OPEN_VALVE	CLOSE_VALVE, EMERGENCY_STOP
________________________________________
Installation & Usage
Prerequisites
•	Python 3.x installed.
Running the Detector
1.	Clone this repository or copy the code to a file named firewall.py.
2.	Run the simulation using:
Bash
CODE FILE.PY
Example Output
Plaintext
--- Starting Normal Operations ---
[NETWORK] Incoming Command: STARTING
[SAFE] Transition: OFF -> STARTING

--- Starting Malicious/AI Injection Test ---
[NETWORK] Incoming Command: OPEN_VALVE
[!!! ALARM !!!] Logic Violation Detected!
Reason: Cannot execute 'OPEN_VALVE' while system is in 'OFF' state.
[FIREWALL] Packet Dropped. System Integrity Maintained.
Industrial Application
•	Cybersecurity: Prevents "Stuxnet-style" attacks where malicious code tries to force hardware into dangerous states.
•	Safety Engineering: Acts as a digital "Dead-Man's Switch" to ensure operators follow correct procedures.
•	IoT Integrity: Filters out noisy or corrupted sensor data that could lead to machine failure.
________________________________________
