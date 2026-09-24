# 🛡️ PyShield PUDLP

## USB Data Leak Protection (PUDLP)

**PyShield PUDLP** is an open-source USB Data Loss Prevention (DLP) solution designed to help protect systems from unauthorized USB-based data access and potential data leakage.

The system monitors USB devices connected to a computer, identifies device activity, applies security policies, records USB-related events, and helps prevent unauthorized data transfer through removable storage devices.

---

## 📌 Project Overview

USB devices such as pen drives, external hard disks, and other removable storage devices are commonly used for transferring data.

However, unauthorized USB devices can create security risks such as:

- Unauthorized data copying
- Sensitive information leakage
- Malware introduction
- Accidental data transfer
- Insider data theft
- Unauthorized removable storage access

**PyShield PUDLP** aims to provide a software-based approach for monitoring and controlling USB device access.

The system can detect USB devices, monitor their activity, apply predefined security policies, and maintain security logs for auditing.

---

## 🎯 Objectives

The main objectives of PyShield PUDLP are:

1. Detect USB devices connected to the system.
2. Monitor USB device activity.
3. Identify unauthorized USB devices.
4. Apply predefined device access policies.
5. Maintain detailed security logs.
6. Help prevent unauthorized data transfer.
7. Provide a foundation for a complete USB Data Loss Prevention system.

---

## ✨ Key Features

### 🔌 USB Device Detection

Automatically detects USB devices connected to the computer.

### 👁️ USB Device Monitoring

Monitors USB connection and disconnection events.

### 🔐 Device Access Control

Allows administrators to define policies for USB device access.

### 🚫 Unauthorized Device Detection

Identifies USB devices that are not allowed by the configured security policy.

### 📊 Activity Monitoring

Records important USB-related activities for security analysis.

### 📝 Security Logging

Maintains logs containing information about USB devices and their activities.

### 🛡️ Data Leak Prevention

Helps reduce the possibility of unauthorized data transfer through removable storage devices.

### ⚙️ Policy-Based Security

Security rules can be configured according to organizational requirements.

### 🌐 Open Source

The project can be customized and extended for different security environments.

---

## 🏗️ System Architecture

```text
                   ┌──────────────────────┐
                   │      User/System     │
                   └──────────┬───────────┘
                              │
                              ▼
                   ┌──────────────────────┐
                   │   USB Device Event  │
                   │      Detection      │
                   └──────────┬───────────┘
                              │
                              ▼
                   ┌──────────────────────┐
                   │  USB Device Manager │
                   └──────────┬───────────┘
                              │
                              ▼
                   ┌──────────────────────┐
                   │ Security Policy      │
                   │      Engine          │
                   └──────────┬───────────┘
                              │
                ┌─────────────┴─────────────┐
                │                           │
                ▼                           ▼
       ┌─────────────────┐       ┌─────────────────┐
       │   Authorized    │       │  Unauthorized   │
       │     Device      │       │     Device      │
       └────────┬────────┘       └────────┬────────┘
                │                         │
                ▼                         ▼
       ┌─────────────────┐       ┌─────────────────┐
       │     Allow       │       │  Block / Alert  │
       │     Access      │       │   / Log Event   │
       └────────┬────────┘       └────────┬────────┘
                │                         │
                └────────────┬────────────┘
                             ▼
                   ┌──────────────────────┐
                   │   Security Logging   │
                   └──────────┬───────────┘
                              │
                              ▼
                   ┌──────────────────────┐
                   │ Reports / Monitoring │
                   └──────────────────────┘
```

---

## 🔄 How It Works

```text
USB Device Connected
        │
        ▼
Device Detection
        │
        ▼
Collect Device Information
        │
        ▼
Check Security Policy
        │
        ├───────────────┐
        │               │
        ▼               ▼
   Authorized       Unauthorized
        │               │
        ▼               ▼
  Allow Access      Block / Alert
        │               │
        └───────┬───────┘
                ▼
        Record Security Event
                │
                ▼
          Generate Log
```

---

## 🧩 Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core application development |
| Windows APIs | USB/device interaction |
| WMI / PyUSB | USB device information and monitoring |
| SQLite / JSON | Data and policy storage |
| Tkinter / Web UI | User interface |
| Python Logging | Security event logging |
| Git | Version control |
| GitHub | Source code hosting |

---

## 📂 Project Structure

```text
PyShield-PUDLP/
│
├── main.py
├── requirements.txt
├── README.md
├── LICENSE
│
├── config/
│   └── policy.json
│
├── core/
│   ├── usb_monitor.py
│   ├── device_manager.py
│   ├── policy_engine.py
│   └── security_manager.py
│
├── database/
│   └── database.py
│
├── logs/
│   └── usb_activity.log
│
├── ui/
│   └── dashboard.py
│
└── tests/
    └── test_usb_monitor.py
```

> The exact project structure may differ depending on the implementation.

---

## ⚙️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/Iyyappan-S/PyShield-PUDLP.git
```

### 2. Navigate to the Project

```bash
cd PyShield-PUDLP
```

### 3. Create a Virtual Environment

```bash
python -m venv venv
```

### 4. Activate the Virtual Environment

#### Windows

```bash
venv\Scripts\activate
```

#### Linux / macOS

```bash
source venv/bin/activate
```

### 5. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ Running the Project

Run the main application using:

```bash
python main.py
```

Depending on the project implementation, the application may start a monitoring service, desktop interface, or web interface.

---

## 🔐 Security Policy

PyShield PUDLP can use predefined security policies to determine whether a USB device should be allowed or restricted.

Example policy:

```json
{
    "usb_security": {
        "mode": "restricted",
        "allow_unknown_devices": false,
        "logging_enabled": true,
        "alert_enabled": true
    }
}
```

### Policy Parameters

| Parameter | Description |
|---|---|
| `mode` | Defines the USB security mode |
| `allow_unknown_devices` | Determines whether unknown devices are allowed |
| `logging_enabled` | Enables or disables activity logging |
| `alert_enabled` | Enables or disables security alerts |

---

## 🛡️ Security Policy Workflow

```text
USB Device Detected
        │
        ▼
Read Device Information
        │
        ▼
Compare With Security Policy
        │
        ├───────────────┐
        │               │
        ▼               ▼
    Allowed          Restricted
        │               │
        ▼               ▼
   Continue          Generate
    Access             Alert
                        │
                        ▼
                    Log Event
```

---

## 📋 USB Activity Logging

The system can maintain logs containing important information about USB events.

Example:

| Time | Device | Vendor | Event | Status |
|---|---|---|---|---|
| 10:15:23 | USB Drive | SanDisk | Connected | Allowed |
| 10:18:42 | USB Drive | Kingston | Connected | Blocked |
| 10:22:15 | External HDD | Seagate | Disconnected | Logged |

Example log:

```text
[2026-09-24 10:15:23]
Device: USB Storage Device
Vendor: SanDisk
Event: Connected
Status: Allowed

[2026-09-24 10:18:42]
Device: USB Storage Device
Vendor: Kingston
Event: Connected
Status: Blocked
```

---

## 🚨 Security Events

The system can monitor events such as:

- USB device connected
- USB device disconnected
- Authorized device detected
- Unauthorized device detected
- Security policy violation
- Suspicious device activity
- Access denied
- Device information changed

---

## 🏢 Use Cases

### 🏢 Organizations

Organizations can use USB monitoring to reduce unauthorized data transfer from employee systems.

### 🎓 Educational Institutions

Educational institutions can monitor removable devices in laboratories and computer centers.

### 🏥 Healthcare

Healthcare organizations can use USB access controls to help protect sensitive information.

### 🏦 Financial Organizations

Financial institutions can use USB security policies as part of their broader data protection strategy.

### 💻 Personal Systems

Individual users can monitor USB devices connected to their personal computers.

---

## 🔍 Example Security Scenario

Consider an organization where employees are allowed to use only company-approved USB drives.

```text
Employee connects USB Drive
            │
            ▼
      PyShield detects it
            │
            ▼
    Device identification
            │
            ▼
   Check approved device list
            │
       ┌────┴────┐
       │         │
       ▼         ▼
   Approved   Unknown
       │         │
       ▼         ▼
    Allow     Restrict
    Access     Access
       │         │
       └────┬────┘
            ▼
       Record Event
```

This provides an additional security layer for removable storage devices.

---

## 📊 Benefits

PyShield PUDLP provides several potential benefits:

- Reduces unauthorized USB access.
- Improves visibility of removable devices.
- Provides security event logging.
- Supports policy-based device management.
- Helps organizations monitor removable storage.
- Provides a foundation for USB-based Data Loss Prevention.
- Can be customized according to organizational requirements.
- Can be extended with additional security mechanisms.

---

## 🔮 Future Enhancements

The project can be extended with the following features:

- [ ] Real-time security dashboard
- [ ] Graphical administration panel
- [ ] User authentication
- [ ] Role-Based Access Control
- [ ] USB device whitelist
- [ ] USB device blacklist
- [ ] Automatic USB blocking
- [ ] File type restrictions
- [ ] Sensitive file detection
- [ ] File hash monitoring
- [ ] Real-time security alerts
- [ ] Email notifications
- [ ] Database-based activity storage
- [ ] USB device fingerprinting
- [ ] Centralized administration
- [ ] Multi-system monitoring
- [ ] Security reports
- [ ] CSV report export
- [ ] PDF report generation
- [ ] Machine Learning-based anomaly detection
- [ ] AI-based suspicious activity detection
- [ ] Cloud-based monitoring
- [ ] Enterprise-level policy management

---

## 🤖 Future AI Integration

A future version of PyShield PUDLP could integrate Artificial Intelligence and Machine Learning for advanced USB activity analysis.

Possible workflow:

```text
USB Activity
     │
     ▼
Activity Data Collection
     │
     ▼
Feature Extraction
     │
     ▼
Machine Learning Model
     │
     ▼
Anomaly Detection
     │
     ├──────────────┐
     │              │
     ▼              ▼
 Normal Activity  Suspicious Activity
     │              │
     ▼              ▼
 Continue         Alert
 Monitoring       Administrator
```

Potential AI features include:

- USB behavior analysis
- Anomaly detection
- Suspicious activity identification
- Risk scoring
- Unusual file transfer detection
- User behavior analysis
- Automated security alerts

---

## 🧪 Testing

Basic Python testing can be performed using:

```bash
python -m pytest
```

For a specific test file:

```bash
python -m pytest tests/test_usb_monitor.py
```

---

## 🔧 Troubleshooting

### Python Not Found

Check whether Python is installed:

```bash
python --version
```

or:

```bash
py --version
```

### Virtual Environment Not Activated

Windows:

```bash
venv\Scripts\activate
```

### Dependencies Not Installed

Run:

```bash
pip install -r requirements.txt
```

### Check Installed Packages

```bash
pip list
```

---

## ⚠️ Security Considerations

PyShield PUDLP is intended to be used as a security-supporting application and should be deployed responsibly.

USB blocking, device control, and system-level security operations may require administrator privileges depending on the operating system and implementation.

Before deploying the system in a production environment:

- Test policies carefully.
- Maintain backups.
- Avoid blocking critical system devices.
- Validate device identification.
- Review security logs regularly.
- Use least-privilege access where possible.
- Test the application in a controlled environment.

---

## 🔒 Data Protection

The project should follow responsible data-handling practices.

Recommended practices include:

- Avoid storing unnecessary personal information.
- Protect security logs from unauthorized modification.
- Restrict access to administrative functions.
- Secure stored device information.
- Rotate logs when necessary.
- Protect configuration files.
- Validate user inputs.
- Follow applicable organizational security policies.

---

## 🤝 Contributing

Contributions are welcome.

### Step 1 — Fork the Repository

Create a fork of the project on GitHub.

### Step 2 — Clone Your Fork

```bash
git clone https://github.com/YOUR_USERNAME/PyShield-PUDLP.git
```

### Step 3 — Create a Branch

```bash
git checkout -b feature/new-feature
```

### Step 4 — Make Changes

Implement your feature or improvement.

### Step 5 — Commit Changes

```bash
git add .
git commit -m "Add new USB security feature"
```

### Step 6 — Push Changes

```bash
git push origin feature/new-feature
```

### Step 7 — Create a Pull Request

Create a Pull Request on GitHub describing your changes.

---

## 📜 License

This project is licensed under the **MIT License**.

See the `LICENSE` file for more information.

---

## 👨‍💻 Author

### Iyyappan S

**B.Tech Artificial Intelligence & Data Science**

Interested in:

- Full Stack Development
- Artificial Intelligence
- Machine Learning
- Data Science
- Cybersecurity
- Software Development

GitHub:

https://github.com/Iyyappan-S

---

## ⭐ Support the Project

If you find this project useful:

⭐ Star the repository on GitHub.

🍴 Fork the repository.

🐛 Report issues.

💡 Suggest improvements.

🤝 Contribute to the project.

---

## 📌 Project Keywords

```text
USB Security
USB Data Loss Prevention
DLP
Data Loss Prevention
USB Monitoring
USB Device Monitoring
USB Access Control
Data Leak Prevention
Cybersecurity
Information Security
Endpoint Security
Python Security
Device Security
Removable Media Security
USB Protection
Security Monitoring
Security Logging
Python
Open Source
```

---

## 📖 Project Summary

**PyShield PUDLP (USB Data Leak Protection)** is a Python-based open-source security project focused on monitoring USB devices and helping prevent unauthorized data access through removable storage.

The project provides a foundation for USB device detection, monitoring, policy-based access control, security logging, and future AI-powered anomaly detection.

The long-term goal is to develop PyShield into a comprehensive USB Data Loss Prevention platform that can help organizations monitor removable media and strengthen endpoint data protection.

---

## ⭐ PyShield PUDLP

**Protect your data. Monitor your devices. Control USB access.**

```text
┌──────────────────────────────────────────┐
│             PyShield PUDLP               │
│                                          │
│       USB Data Leak Protection           │
│                                          │
│  Detect → Monitor → Analyze → Protect   │
│                                          │
└──────────────────────────────────────────┘
```

**Built with Python ❤️ for better USB security.**
