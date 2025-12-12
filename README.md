# Robotics Project 2025 – Warehouse Automation (OAMK)

This project is a full warehouse automation system using GoPiGo robot cars, UR robot arms, 
and a drone system. It includes cloud integration, WebSocket communication, path navigation, 
and multi-robot coordination.

## 📚 Technologies Used
- **Python 3.7+** (Robot control & automation)
- **Raspberry Pi** (Embedded systems)
- **WebSockets** (Real-time communication)
- **Flask** (Camera streaming server)
- **EasyGoPiGo3 Library** (Direct hardware control)
- **Line Following & Distance Sensors** (Autonomous navigation)
- **QR Code Scanning** (Product identification)
- **Node.js Backend** (Cloud server)
- **React Frontend** (Dashboard UI)
- **Multi-robot Coordination** (Autonomous warehouse system)

---

## 📦 Project Repositories (University GitHub Organization)

| # | Subsystem | Repo |
|---|-----------|------|
| 1 | **GoPiGo Cars Control – My Main Contribution** | [🔗 link](https://github.com/Robotics-project-2025-DIN23SP/go-pi-go-cars-control) |
| 2 | UR Robot Arm (Main) | [🔗 link](https://github.com/Robotics-project-2025-DIN23SP/ur-robot-arm) |
| 3 | UR Robot Arm 2 | [🔗 link](https://github.com/Robotics-project-2025-DIN23SP/2-ur-robot-arm-2) |
| 4 | Drone System | [🔗 link](https://github.com/Robotics-project-2025-DIN23SP/DroneSystem) |
| 5 | Robotics Backend | [🔗 link](https://github.com/Robotics-project-2025-DIN23SP/robotics-backend) |
| 6 | Robotics Frontend | [🔗 link](https://github.com/Robotics-project-2025-DIN23SP/robotics-frontend) |
| 7 | Integration Weekly Tests | [🔗 link](https://github.com/Robotics-project-2025-DIN23SP/IntegrationWeeklyTest) |

---

## 🤖 My Role & Contributions

### Primary Focus: GoPiGo Robot Car Development

I led the development of **two autonomous GoPiGo robots** that work together in the warehouse automation system:

#### **🚗 GoPiGo 1 - Delivery Robot**
- **WebSocket Integration**: Implemented real-time communication with cloud server (`ws://192.168.1.120:8765`)
- **Modular Architecture**: Designed phase-based navigation system (move_to_station → deliver_product → return_to_start)
- **Checkpoint Navigation**: Developed line-following algorithm with precise checkpoint detection (0→3→5→6)
- **Servo Control**: Integrated servo motor for automated product pickup and delivery
- **Hardware Abstraction**: Created `GopiGoBase` class for reusable robot initialization

#### **🚗 GoPiGo 2 - Circuit Patrol Robot**
- **Autonomous Operation**: Developed independent circuit monitoring system
- **Obstacle Detection**: Implemented distance sensor logic (25cm stop threshold, 30cm resume)
- **Continuous Line Following**: Created 5-sensor array line follower with checkpoint counting
- **Safety Features**: Added real-time distance monitoring to prevent collisions

#### **📹 Camera System**
- **Dual-Mode Streaming**: Built Flask HTTP server (port 5001) + WebSocket video streaming
- **Real-time Video**: Achieved 640x480 @ 30fps with Base64 encoding for WebSocket transmission
- **Automatic Reconnection**: Implemented robust connection handling for network stability

### Technical Achievements

✅ **Direct Hardware Control**: Transitioned from RPyC remote control to direct `easygopigo3` library usage  
✅ **Modular Design**: Created reusable base classes and separate navigation modules for maintainability  
✅ **Documentation**: Wrote comprehensive SETUP.md, README.md, and ARCHITECTURE.md for each robot  
✅ **Testing Utilities**: Developed diagnostic tools (`distance_sensor_test.py`, servo tests, line sensor calibration)  
✅ **Network Integration**: Configured multi-device system (3 Raspberry Pis, WebSocket server, camera streaming)  
✅ **Collision Avoidance**: Implemented distance-based obstacle detection throughout entire circuit patrol  
✅ **Error Handling**: Added robust error handling and automatic reconnection for WebSocket connections  

### Code Highlights

**Repository Structure:**
```
go-pi-go-cars-control/
├── GoPiGo_1_Pi_Direct/     # Delivery robot (WebSocket controlled)
├── GoPiGo_2_Pi_Direct/     # Circuit patrol (autonomous)
├── Camera_Modules/         # Video streaming system
└── Sensor_Tests/           # Hardware diagnostics
```

**Key Files I Developed:**
- `gopigo_websocket_client.py` - Main WebSocket controller with event routing
- `follow_circuit.py` - Autonomous circuit patrol with obstacle detection
- `camera_stream_server.py` - Flask + WebSocket video streaming
- `gopigo_base.py` - Hardware abstraction layer
- Multiple SETUP.md and README.md documentation files

---

## 🛠️ Development Process

### Collaboration & Integration
- Worked closely with UR Robot Arm and Drone teams for system integration
- Participated in weekly integration testing sessions
- Coordinated robot handoffs and timing with other subsystems
- Contributed to sprint planning and retrospectives

### Problem-Solving Examples
1. **Port Conflict Resolution**: Changed camera server from port 5000 → 5001 to avoid conflicts
2. **Hardware Initialization**: Solved multiple hardware initialization conflicts by implementing object sharing
3. **Checkpoint Detection**: Fixed missed checkpoint issues with edge detection algorithms
4. **Distance Sensor Optimization**: Reduced lag by optimizing sensor reading frequency (every 3 rounds)

---

## 📊 Project Statistics

- **Lines of Code**: 2000+ Python code across robot modules
- **Documentation**: 1500+ lines of comprehensive setup guides
- **Hardware**: 3 Raspberry Pis, 2 GoPiGo robots, 1 Camera module
- **Sensors**: Line follower (5-sensor array), Distance sensor (AD1 port), Servo motor
- **Network Devices**: 5 networked devices with real-time communication

---

## 🎯 Skills Demonstrated

**Embedded Systems**
- Raspberry Pi configuration and deployment
- GPIO control via pigpio daemon
- Hardware driver integration (easygopigo3)

**Robotics**
- Line following algorithms
- Checkpoint-based navigation
- Obstacle detection and avoidance
- Servo motor control

**Networking**
- WebSocket client/server communication
- Multi-device network configuration
- Real-time video streaming (Flask + WebSocket)
- Base64 encoding for binary data transmission

**Software Engineering**
- Modular architecture design
- Object-oriented programming (inheritance, base classes)
- Error handling and recovery
- Comprehensive documentation
- Version control (Git/GitHub)

**Testing & Debugging**
- Created diagnostic tools for hardware testing
- System integration testing
- Network troubleshooting
- Performance optimization

---

## 🎓 Learning Outcomes

This project provided hands-on experience with:
- Multi-robot coordination in industrial automation
- Real-time communication protocols (WebSockets)
- Embedded Linux systems (Raspberry Pi OS)
- Sensor integration and calibration
- Modular software design for robotics
- Technical documentation and knowledge transfer
- Team collaboration in complex systems

---

## 🎯 Summary

This project demonstrates **full end-to-end warehouse automation** using multiple robots. My primary contribution was developing and integrating two autonomous GoPiGo robots with distinct roles: one for product delivery (WebSocket-controlled) and one for circuit patrol (autonomous with obstacle detection). The system includes sophisticated navigation, cloud interaction, sensor-driven workflows, camera streaming, and seamless integration with drone and UR robot arm subsystems.

The complete codebase showcases professional-level robotics development with emphasis on modularity, documentation, and real-world deployment considerations.

---

**Team**: OAMK Robotics - Year 3, Semester 2 (November 2025)  
**Contributors**: Ryan ([@ryandilthusha](https://github.com/ryandilthusha)), Mahboba ([@MahbobaAkter](https://github.com/MahbobaAkter)), Connor ([@HaCuong04](https://github.com/HaCuong04))
