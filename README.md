
# 🚍 Real-Time Cloud-Based Bus Monitoring System

A scalable and intelligent system for real-time monitoring of city and intercity buses using cloud services and Python. This project demonstrates the power of cloud computing in enhancing the efficiency, transparency, and manageability of public transportation systems.

## 📌 Overview

In today's data-driven world, smart transportation systems are essential for improving urban mobility. This project presents a **cloud-based bus tracking system** that enables real-time supervision of public transport buses. It collects and transmits critical data—such as bus locations, passenger counts, driver information, and technical status—to a centralized control center via the internet.

The system leverages **Infrastructure as a Service (IaaS)**, using virtual machines and cloud databases to deliver scalable and secure performance. Though originally intended to interface with embedded systems and mobile applications, this implementation uses Python-based simulators for demonstration.

## 🔧 Key Components

### 🖥️ Server (Core Backend)
- **File:** `server.py`  
- **Responsibilities:**  
  - Manages communication with buses and users via socket programming  
  - Stores data in both local and cloud databases (SQLite + MongoDB)  
  - Interfaces with cloud object storage (Arvan Cloud) for media storage  
  - Exposes APIs for modular and extensible integration

### 🚌 Bus Client (Publisher)
- **File:** `busClient.py`  
- **Simulation of an embedded client system** installed in buses  
- **Data sent periodically:**  
  - GPS coordinates  
  - Passenger count  
  - Driver’s name and image  
  - Timestamp of transmission  

### 📱 User Client (Subscriber)
- **File:** `appClient.py`  
- **Simulation of a mobile app** for passengers or managers  
- **Receives real-time updates** from the server for informed travel decisions  
- Designed for future integration with Android/iOS platforms

## 🧱 System Architecture

     [BusClient]       [BusClient]        ...
         |                  |        
         |  Socket Comm.    |
         v                  v
     +------------------------------+
     |           Server             |
     |  - Data Processing           |
     |  - API Management            |
     |  - Local + Cloud DBs         |
     |  - File Upload to Arvan      |
     +------------------------------+
         |                  |
         |  Real-time Data  |
         v                  v
    [UserClient]      [Control Center / Dashboard]

## ☁️ Cloud Stack

| Service           | Technology           |
|------------------|----------------------|
| Cloud Provider    | Ferdowsi Cloud (VM)  |
| Object Storage    | Arvan Cloud          |
| Local DB          | SQLite               |
| Cloud DB          | MongoDB              |
| Architecture Type | IaaS (VM-based)      |

## ⚙️ Tech Stack

- **Language:** Python  
- **Communication:** TCP Sockets  
- **Databases:** SQLite (local), MongoDB (cloud)  
- **Storage:** Arvan Object Storage  
- **Deployment:** Ferdowsi Cloud Virtual Machine  
- **API Integration:** Modular interface for future expansion

## 🚧 Future Development

To elevate the functionality and real-world applicability of the system, the following enhancements are proposed:

- ✅ Native Android/iOS mobile applications  
- ✅ Integration with live GPS modules and onboard sensors  
- ✅ Real-time driver behavior analysis and performance scoring  
- ✅ Admin dashboard with route visualization and analytics  
- ✅ Role-based access control (admin/driver/passenger)

## 📁 Project Directory Structure

    ├── server.py          # Main backend server
    ├── busClient.py       # Simulated publisher (bus)
    ├── appClient.py       # Simulated subscriber (user)
    ├── /database/         # SQLite/MongoDB setup (if applicable)
    ├── /storage/          # Cloud file upload utilities
    └── README.md          # Project documentation

## 📖 How to Run (Simulated Mode)

1. **Start the server:**
   python server.py

2. **Run the bus client (in a separate terminal):**
   python busClient.py

3. **Run the user client (in a separate terminal):**
   python appClient.py

Make sure the server is running before launching clients.

## 📜 License

Distributed under the MIT License. See `LICENSE` for more information.


