# ⚙️ PLC Control Systems Project

This project implements two industrial control systems using the **OpenPLC** platform:

- **Temperature Control System** – Controls a heater based on temperature feedback  
- **Liquid Level Control System** – Manages fill and drain valves with level monitoring and alarms  

---

## 🎯 Project Objectives

### Task 1: Temperature Control
- Implement PLC logic for temperature control using heater and temperature sensor  
- Linear temperature increase: **0.5°C/second** when heater is ON  
- Linear temperature decrease: **0.25°C/second** when heater is OFF  
- Temperature range: **0°C → 100°C**  

### Task 2: Liquid Level Control
- Implement PLC logic for liquid level control with proportional valves  
- Fill valve (0–10V) → increases level proportionally  
- Drain valve (0–10V) → decreases level proportionally  
- Level range: **0% → 100%**  
- High-level alarm: **> 80%**  
- Low-level alarm: **< 20%**  
- Specific rate calculations based on valve positions  

---

## 🛠 Technology Stack
- **PLC Programming:** OpenPLC Editor  
- **PLC Runtime:** OpenPLC Runtime  
- **HMI/SCADA:** [ScadaBR](http://www.scadabr.org.br/)  
- **Programming Language:** Ladder Logic / Structured Text *(specify which was used)*  
- **Platform:** Cross-platform (Windows/Linux/macOS)  

---

## 📋 System Requirements

### Software
- [OpenPLC Editor](https://www.openplcproject.com/) (latest version)  
- [OpenPLC Runtime](https://www.openplcproject.com/runtime/)  
- [ScadaBR](http://www.scadabr.org.br/)  
- [Java Runtime Environment](https://www.java.com/en/download/) *(for ScadaBR)*  
- Web browser *(for ScadaBR interface)*  

### Hardware
- Minimum **2GB RAM**  
- Minimum **1GB free disk space**  
- Network connection for communication between components  

---

## 🚀 Installation Guide

### Step 1: Install OpenPLC Editor
1. [Download OpenPLC Editor](https://www.openplcproject.com/editor/)  
2. Install following platform-specific instructions  
3. Launch OpenPLC Editor  

### Step 2: Install OpenPLC Runtime
1. [Download OpenPLC Runtime](https://www.openplcproject.com/runtime/)  
2. Install and configure the runtime  
3. Start the runtime service  
4. Access web interface: [http://localhost:8080](http://localhost:8080)  

### Step 3: Install ScadaBR
1. [Download ScadaBR](http://www.scadabr.org.br/)  
2. Extract and install Java-based application  
3. Configure database connection  
4. Start ScadaBR service  
5. Access web interface: [http://localhost:8080/ScadaBR](http://localhost:8080/ScadaBR)  

---

## 🎥 Demo Video
📺 [Watch the complete project demonstration on YouTube](https://youtu.be/YPctxyFbLac)  

---

## 🔧 Configuration Setup

### OpenPLC Runtime
- Open [OpenPLC Runtime web interface](http://localhost:8080)  
- Upload `.st` program files  
- Configure I/O mapping:
  - Temperature sensor input  
  - Heater output  
  - Fill valve analog input  
  - Drain valve analog input  
  - Level sensor input  
  - Alarm outputs  

### ScadaBR
- Create new data source for **Modbus TCP**  
- Configure connection to OpenPLC Runtime (default: `localhost:502`)  
- Add data points for:  
  - Temperature value  
  - Heater status  
  - Level percentage  
  - Fill/Drain valve positions  
  - High/Low level alarms  
- Design HMI screens with appropriate controls and displays  

### Communication Setup
- OpenPLC Runtime → acts as **Modbus TCP server**  
- ScadaBR → connects as **Modbus TCP client**  
- Default Modbus port: `502`  
- Ensure firewall allows communication  

---

## 🎮 How to Use

### Temperature Control System
1. Load temperature control program in OpenPLC Runtime  
2. Start PLC program  
3. Open ScadaBR temperature control screen  
4. Monitor readings + toggle heater ON/OFF  
5. Observe temperature changes:  
   - Increase: **+0.5°C/s**  
   - Decrease: **-0.25°C/s**  

### Liquid Level Control System
1. Load level control program in OpenPLC Runtime  
2. Start PLC program  
3. Open ScadaBR level control screen  
4. Adjust valve positions (0–10V / 0–100%)  
5. Monitor level + alarms  
6. Test scenarios:  

| Fill (%) | Drain (%) | Result |
|----------|-----------|--------|
| 100      | 0         | +10%/s |
| 0        | 100       | -10%/s |
| 50       | 50        | 0      |
| 25       | 50        | -2.5%/s |
| 50       | 25        | +2.5%/s |

---

## 📊 System Specifications

### Temperature Control
- Heating Rate: **+0.5°C/s**  
- Cooling Rate: **-0.25°C/s**  
- Range: **0°C → 100°C**  
- Control: **ON/OFF**  

### Level Control
- Fill Rate: **10%/s at 100% valve opening**  
- Drain Rate: **10%/s at 100% valve opening**  
- Range: **0% → 100%**  
- High Alarm: **>80%**  
- Low Alarm: **<20%**  
- Control: **Proportional**  

---

## 🔍 Troubleshooting

- **OpenPLC Runtime not starting**
  - Check port `8080` availability  
  - Verify installation  
  - Check system logs  

- **ScadaBR connection issues**
  - Verify Modbus TCP settings  
  - Check firewall + runtime status  

- **HMI not updating**
  - Check data source configuration  
  - Refresh data source  
  - Verify PLC program execution  

- **Simulation not working**
  - Check timer configurations  
  - Verify variable scaling  
  - Validate logic  

---

## 🤝 Contributing
1. Fork the repo  
2. Create feature branch → `git checkout -b feature/improvement`  
3. Commit → `git commit -am 'Add new feature'`  
4. Push → `git push origin feature/improvement`  
5. Create Pull Request  

---

## 📝 License
This project is licensed under the [MIT License](LICENSE).  

---

## 👥 Authors
- **Mazen Mahrous** – Initial work – [GitHub Profile](https://github.com/5mazo)  

---

## 🙏 Acknowledgments
- [OpenPLC Project](https://www.openplcproject.com/) team  
- [ScadaBR community](http://www.scadabr.org.br/)  
- Industrial automation community for inspiration  

---

## 📞 Support
- Create an issue in this repository  
- 📘 [OpenPLC Documentation](https://www.openplcproject.com/documentation/)  
- 📘 [ScadaBR Documentation](http://www.scadabr.org.br/)  

---

## 🔗 Useful Links
- 🌐 [OpenPLC Official Website](https://www.openplcproject.com/)  
- 📖 [IEC 61131-3 Standards](https://en.wikipedia.org/wiki/IEC_61131-3)  
