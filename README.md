# 🛡️ PyShield PUDLP

## USB Data Leak Protection (PUDLP)

PyShield PUDLP is an open-source **USB Data Loss Prevention (DLP)** solution designed to protect systems from unauthorized USB-based data leaks.

The system monitors USB device activity and helps prevent sensitive data from being copied to unauthorized removable storage devices. It provides an additional layer of security by controlling and monitoring USB access, helping organizations reduce the risk of accidental or intentional data exfiltration.

---

## 🚀 Features

- 🔐 **USB Data Loss Prevention** - Helps prevent unauthorized data transfer through USB devices.
- 💾 **USB Device Monitoring** - Detects connected USB storage devices.
- 🛡️ **Device Access Control** - Controls USB device access based on configured security policies.
- 📊 **Activity Monitoring** - Tracks USB connection and disconnection events.
- 🚨 **Unauthorized Device Detection** - Identifies USB devices that are not permitted by the configured security policy.
- 📁 **Data Exfiltration Protection** - Helps prevent sensitive files from being copied to unauthorized USB storage.
- ⚙️ **Policy-Based Security** - Allows administrators to define rules for USB device access.
- 📝 **Security Logging** - Maintains records of USB device activity and security events.
- 🔓 **Open Source** - Can be modified, extended, and customized according to project requirements.

---

## 🎯 Objectives

1. Detect USB storage devices connected to a system.
2. Monitor USB device activity.
3. Restrict unauthorized USB devices.
4. Reduce the possibility of sensitive data leakage.
5. Maintain logs of USB-related security events.
6. Provide a lightweight and customizable USB security solution.
7. Provide an open-source foundation for USB-based Data Loss Prevention.

---

## 🏗️ System Architecture

```text
                    ┌───────────────────────┐
                    │      User System      │
                    └───────────┬───────────┘
                                │
                                ▼
                    ┌───────────────────────┐
                    │   USB Device Monitor  │
                    └───────────┬───────────┘
                                │
                                ▼
                    ┌───────────────────────┐
                    │ Device Identification │
                    │   & Information Check │
                    └───────────┬───────────┘
                                │
                                ▼
                    ┌───────────────────────┐
                    │   Security Policy     │
                    │       Engine          │
                    └───────────┬───────────┘
                                │
                    ┌───────────┴───────────┐
                    │                       │
                    ▼                       ▼
          ┌──────────────────┐    ┌──────────────────┐
          │    Authorized    │    │   Unauthorized   │
          │      Device      │    │      Device      │
          └────────┬─────────┘    └────────┬─────────┘
                   │                       │
                   ▼                       ▼
          ┌──────────────────┐    ┌──────────────────┐
          │   Allow USB      │    │   Restrict USB   │
          │     Access       │    │     Access       │
          └────────┬─────────┘    └────────┬─────────┘
                   │                       │
                   └───────────┬───────────┘
                               │
                               ▼
                    ┌───────────────────────┐
                    │    Activity Logger    │
                    └───────────┬───────────┘
                                │
                                ▼
                    ┌───────────────────────┐
                    │   Security Event Logs │
                    └───────────────────────┘
