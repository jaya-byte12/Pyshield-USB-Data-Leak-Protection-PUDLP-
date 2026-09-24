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



## ✨ Key Features

### 🔌 USB Device Detection

### 👁️ USB Device Monitoring

### 🔐 Device Access Control

### 🚫 Unauthorized Device Detection

### 📊 Activity Monitoring

### 📝 Security Logging

### 🛡️ Data Leak Prevention

### ⚙️ Policy-Based Security

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
---
## 📜 License

This project is licensed under the **MIT License**.

See the `LICENSE` file for more information.

---
