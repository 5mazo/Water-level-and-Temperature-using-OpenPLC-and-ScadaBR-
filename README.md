PLC Control Systems Project
Overview
This project implements two industrial control systems using OpenPLC platform:

Temperature Control System - Controls a heater based on temperature feedback
Liquid Level Control System - Manages fill and drain valves with level monitoring and alarms

🎯 Project Objectives
Task 1: Temperature Control

Implement PLC logic for temperature control using heater and temperature sensor
Linear temperature increase at 0.5°C/second when heater is ON
Linear temperature decrease at 0.25°C/second when heater is OFF
Temperature range: 0°C to 100°C

Task 2: Liquid Level Control

Implement PLC logic for liquid level control with proportional valves
Fill valve (0-10V) increases level proportionally
Drain valve (0-10V) decreases level proportionally
Level range: 0% to 100%
High level alarm (>80%) and low level alarm (<20%)
Specific rate calculations based on valve positions

🛠 Technology Stack

PLC Programming: OpenPLC Editor
PLC Runtime: OpenPLC Runtime
HMI/SCADA: ScadaBR
Programming Language: Ladder Logic / Structured Text (specify which you used)
Platform: Cross-platform (Windows/Linux/macOS)

📋 System Requirements
Software Requirements

OpenPLC Editor (latest version)
OpenPLC Runtime
ScadaBR
Java Runtime Environment (for ScadaBR)
Web browser (for ScadaBR interface)

Hardware Requirements (Minimum)

2GB RAM
1GB free disk space
Network connection for communication between components

🚀 Installation Guide
Step 1: Install OpenPLC Editor

Download OpenPLC Editor from official website
Install following platform-specific instructions
Launch OpenPLC Editor

Step 2: Install OpenPLC Runtime

Download OpenPLC Runtime for your platform
Install and configure the runtime
Start the runtime service
Access web interface at http://localhost:8080

Step 3: Install ScadaBR

Download ScadaBR from official repository
Extract and install Java-based application
Configure database connection
Start ScadaBR service
Access web interface at http://localhost:8080/ScadaBR

🎥 Demo Video
Watch the complete project demonstration on YouTube:
PLC Control Systems - Temperature & Level Control Demo
The video shows both systems in operation with real-time HMI interaction.
🔧 Configuration Setup
OpenPLC Runtime Configuration

Open OpenPLC Runtime web interface
Navigate to "Programs" section
Upload your .st program files
Configure I/O mapping:

Temperature sensor input
Heater output
Fill valve analog input
Drain valve analog input
Level sensor input
Alarm outputs



ScadaBR Configuration

Create new data source for Modbus TCP
Configure connection to OpenPLC Runtime (typically localhost:502)
Add data points for:

Temperature value
Heater status
Level percentage
Fill valve position
Drain valve position
High/Low level alarms


Design HMI screens with appropriate controls and displays

Communication Setup

OpenPLC Runtime acts as Modbus TCP server
ScadaBR connects as Modbus TCP client
Default Modbus port: 502
Ensure firewall allows communication

🎮 How to Use
Running the Temperature Control System

Load temperature control program in OpenPLC Runtime
Start the PLC program
Open ScadaBR temperature control screen
Monitor temperature readings
Control heater ON/OFF status
Observe temperature changes (0.5°C/s increase, 0.25°C/s decrease)

Running the Liquid Level Control System

Load level control program in OpenPLC Runtime
Start the PLC program
Open ScadaBR level control screen
Adjust fill valve position (0-10V / 0-100%)
Adjust drain valve position (0-10V / 0-100%)
Monitor level changes and alarm states
Test specific scenarios:

Fill 100% / Drain 0% → +10%/s
Fill 0% / Drain 100% → -10%/s
Fill 50% / Drain 50% → No change
Fill 25% / Drain 50% → -2.5%/s
Fill 50% / Drain 25% → +2.5%/s



📊 System Specifications
Temperature Control Parameters

Heating Rate: 0.5°C per second
Cooling Rate: 0.25°C per second
Temperature Range: 0°C to 100°C
Control Method: ON/OFF control

Level Control Parameters

Fill Rate: 10%/second at 100% valve opening
Drain Rate: 10%/second at 100% valve opening
Level Range: 0% to 100%
High Alarm: >80%
Low Alarm: <20%
Control Method: Proportional control

🔍 Troubleshooting
Common Issues
OpenPLC Runtime not starting

Check if port 8080 is available
Verify OpenPLC installation
Check system logs for error messages

ScadaBR connection issues

Verify Modbus TCP settings
Check firewall settings
Ensure OpenPLC Runtime is running
Verify IP addresses and ports

HMI not updating

Check data source configuration
Verify point mappings
Refresh ScadaBR data source
Check PLC program execution

Simulation not working correctly

Verify timer configurations in PLC code
Check variable scaling
Validate logic implementation

🤝 Contributing

Fork the repository
Create feature branch (git checkout -b feature/improvement)
Commit changes (git commit -am 'Add new feature')
Push to branch (git push origin feature/improvement)
Create Pull Request

📝 License
This project is licensed under the MIT License - see the LICENSE file for details.
👥 Authors

Your Name - Initial work - YourGitHub

🙏 Acknowledgments

OpenPLC Project team for the excellent open-source platform
ScadaBR community for the HMI/SCADA solution
Industrial automation community for inspiration and best practices

📞 Support
For support and questions:

Create an issue in this repository
Check OpenPLC documentation: https://www.openplcproject.com/
ScadaBR documentation and forums

🔗 Useful Links

OpenPLC Official Website
OpenPLC Documentation
ScadaBR Project
IEC 61131-3 Standards


Note: This project is for educational purposes and demonstrates basic PLC programming concepts. For production use, additional safety measures and error handling should be implemented.
