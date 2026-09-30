# MSAFE-AI

**A complete MSAFE AI mine subsidence monitoring and early warning system** for real-time geotechnical analysis, hazard detection, and regulatory compliance in underground mining operations.

---

## 📋 Table of Contents

1. [Overview](#overview)
2. [System Context](#system-context)
3. [Dashboard Features](#dashboard-features)
4. [Architecture](#architecture)
5. [Key Components](#key-components)
6. [Getting Started](#getting-started)
7. [User Roles & Permissions](#user-roles--permissions)
8. [Hardware Integration](#hardware-integration)
9. [Demo Mode](#demo-mode)
10. [Documentation](#documentation)

---

## 🎯 Overview

MSAFE-AI is an intelligent mine subsidence monitoring platform designed to:

- **Monitor Real-Time Vibrations**: Track 2.8Hz+ vibration sensors deployed across mining sites
- **Detect Subsidence Events**: Identify dangerous ground movements before they escalate
- **Generate Early Warnings**: Alert site safety officers and regulatory bodies immediately
- **Maintain Compliance**: Ensure DGMS (Directorate General of Mines Safety) audit trails and documentation
- **Enable Predictive Analysis**: Use historical data patterns to forecast potential hazards

This system integrates IoT sensors, cloud processing, and an intuitive operational dashboard to provide complete visibility into mine stability and worker safety.

### Project Snapshot

MSAFE-AI is built to reduce operational risk in underground mining by combining IoT sensing, edge analytics, and AI-driven decision support. The platform helps mine operators detect ground instability and act before hazardous conditions escalate.

- **24/7 Monitoring**: Continuous visibility into vibration patterns and mining-zone stability
- **Early Warning Capability**: Detect abnormal shifts before a subsidence event becomes critical
- **Actionable Intelligence**: Turn raw sensor data into clear alerts, reports, and operational guidance
- **Safety-First Design**: Support safer mining workflows for operators, geotech teams, and regulators
- **Audit Readiness**: Maintain historical logs, compliance records, and event timelines

### Canva Design Reference

For the visual presentation and concept overview, see the project design here:

[Open Canva Design](https://canva.link/dcblqyg9mhar595)

---

## 🔄 System Context

### The Problem
Mining operations face critical risks from subsidence (ground movement) that can:
- Cause surface collapses
- Endanger worker safety
- Violate regulatory compliance standards
- Result in operational shutdowns and fines

### The Solution
MSAFE-AI provides:
1. **Distributed IoT Monitoring**: LoRa mesh network of vibration sensors across mining zones
2. **Edge Processing**: Real-time noise filtering and anomaly detection
3. **Central Intelligence**: Cloud-based data aggregation and ML analysis
4. **Multi-Role Dashboard**: Tailored views for safety officers, engineers, operators, and auditors
5. **Instant Alerts**: Push notifications and escalation workflows for hazardous conditions

---

## 📊 Dashboard Features

The MSAFE-AI Dashboard is the operational nerve center of the system. It provides role-based views for different stakeholders:

### For Safety Officers
- **Live Hazard Overview**: Real-time map of all mining zones with subsidence risk indicators (GREEN/YELLOW/RED)
- **Alert Management**: Incoming alerts with automated escalation workflows
- **Incident History**: Timeline of past events, causes, and resolutions
- **Site-Wide Statistics**: Aggregate metrics (total sensors online, avg. vibration levels, alert frequency)

### For Geotech Engineers
- **Detailed Waveform Analysis**: Raw vibration data visualization and spectral analysis
- **Predictive Models**: Trend analysis and forecasting based on historical patterns
- **Sensor Health**: Calibration status, signal quality, battery levels
- **Report Generation**: Export compliance reports for DGMS audits

### For Operators
- **Zone Status**: Current operational state of each mining zone
- **Action Logs**: Recorded interventions and manual overrides
- **Quick Access**: Emergency shutdown and alarm silence controls
- **Training Simulations**: Demo mode for staff onboarding

### For DGMS Auditors
- **Compliance Dashboard**: Audit trails with full event traceability
- **Regulatory Reports**: Pre-formatted DGMS submission documents
- **Data Integrity**: Sensor certification and data validation logs
- **Historical Archives**: Multi-year event records and analysis

### Cross-Role Features
- **Real-Time Notifications**: Push alerts for critical events
- **Collaborative Annotations**: Team notes on incidents and resolutions
- **Mobile-Responsive Design**: Accessible from site offices and remote locations
- **Dark/Light Themes**: Optimized for different lighting conditions

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    MSAFE-AI System Pipeline                 │
└─────────────────────────────────────────────────────────────┘

┌──────────────┐        ┌──────────────┐        ┌─────────────┐
│   Hardware   │───────▶│   Gateway    │───────▶│   Cloud     │
│   Sensors    │        │   & Edge     │        │   Backend   │
│   (LoRa)     │        │   Processing │        │   & ML      │
└──────────────┘        └──────────────┘        └─────────────┘
        │                       │                        │
        │                       │                        │
        ▼                       ▼                        ▼
    ESP32 Nodes          Noise Filtering         Alert Engine
    SX1262 Mesh          Anomaly Detection       Data Store
    2.8Hz Sensors        Real-Time Aggregation   ML Models

                                                        │
                                                        ▼
                                             ┌──────────────────┐
                                             │  MSAFE Dashboard │
                                             └──────────────────┘
                                                        │
                         ┌──────────────┬──────────────┼──────────────┐
                         ▼              ▼              ▼              ▼
                   Safety Officer  Geotech Eng.  Operator      DGMS Auditor
                   (Alert Mgmt)    (Analysis)    (Control)     (Compliance)
```

---

## 🔧 Key Components

| Component | Purpose | Technology |
|-----------|---------|-----------|
| **Sensor Network** | Collect ground vibration data | ESP32, LoRa SX1262, 2.8Hz accelerometers |
| **Gateway/Edge** | Real-time filtering and aggregation | Node.js, Edge ML inference |
| **Cloud Backend** | Centralized processing, storage, analytics | Firebase, Cloud Functions |
| **Dashboard** | Multi-role operational UI | React, WebSocket, Material Design |
| **Alert Engine** | Risk assessment and notification dispatch | Custom ML models, FCM push notifications |
| **Audit System** | Compliance tracking and reporting | Firestore event logs, DGMS templates |

---

## 🚀 Getting Started

### Prerequisites
- Node.js 16+
- npm or yarn
- Firebase CLI (for deployment)
- Modern web browser (Chrome, Firefox, Safari, Edge)

### Installation & Setup

```bash
# 1. Clone the repository
git clone https://github.com/mnshreyas4-tech/MSAFE-AI.git
cd MSAFE-AI

# 2. Install dependencies
npm install

# 3. Configure environment variables
cp .env.example .env.local
# Edit .env.local and add your Firebase credentials and API keys

# 4. Start the development server
npm run dev

# 5. Open your browser
# Navigate to http://localhost:3000
```

### Build for Production

```bash
npm run build  # Compile and optimize
npm run lint   # Code quality check
npm run test   # Run test suite
```

---

## 👥 User Roles & Permissions

| Role | Dashboard Access | Key Actions |
|------|------------------|------------|
| **Safety Officer** | Alert Dashboard, Incident History, Site Overview | Acknowledge alerts, trigger evacuations, manage incidents |
| **Geotech Engineer** | Analytics, Waveform Analysis, Predictive Models | Analyze trends, generate reports, configure thresholds |
| **Operator** | Zone Status, Quick Controls, Action Log | Monitor zones, manual interventions, data validation |
| **DGMS Auditor** | Compliance Dashboard, Audit Trails, Historical Records | Review event logs, generate regulatory reports, certify data |

---

## ⚙️ Hardware Integration

### Sensor Network
- **ESP32 Microcontroller**: Low-power, multi-sensor coordinator
- **LoRa SX1262 Transceiver**: Long-range mesh communication (up to 2 - 3km)
- **Vibration Sensors**: 2.8Hz+frequency accelerometers (fixed and mobile)
- **Topology**: Tree/mesh hybrid for redundancy and coverage

### Data Collection
- Sampling Rate: 100Hz per sensor
- Transmission: 30-second aggregated packets
- Noise Rejection: Hardware + firmware filtering (±2mm/s baseline)

---

## 🎮 Demo Mode

Test the system without hardware:

1. **Launch Demo**: Select "Demo Mode" on the login screen
2. **Choose Persona**: 
   - Safety Officer (full alert management)
   - Operator (zone control view)
   - DGMS Auditor (compliance review)
3. **Simulate Events**: Trigger synthetic subsidence events to see alerts and workflows in action
4. **Explore Features**: No sensor hardware required

---

## 📚 Documentation

Full documentation available in the `/docs` folder:

- **[setup.md](docs/setup.md)** — Installation and configuration guide
- **[architecture.md](docs/architecture.md)** — System design, data flow, and component interactions
- **[dashboard.md](docs/dashboard.md)** — Dashboard UI walkthrough and features
- **[hardware.md](docs/hardware.md)** — Sensor deployment and specifications
- **[authentication.md](docs/authentication.md)** — User roles, permissions, and auth flows
- **[demo.md](docs/demo.md)** — Step-by-step guide to using Demo Mode

---

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for:
- Branch strategy
- Pull request guidelines
- Code style and standards
- Commit message conventions

For contributor credits, see [CONTRIBUTORS.md](CONTRIBUTORS.md).

## 👥 Contributors

- Amar B — amardb386@gmail.com
- Dhureen P - dhureenprabhakar@gmail.com

---

## 📞 Support & Issues

- **Bug Reports**: Use [GitHub Issues](https://github.com/mnshreyas4-tech/MSAFE-AI/issues)
- **Feature Requests**: Open a discussion or issue with `[FEATURE]` tag
- **Security Concerns**: Contact the team directly (do not open public issues)

---

## ⚠️ Regulatory Compliance

This system is designed to comply with:
- **DGMS Guidelines**: Directorate General of Mines Safety (India) regulations
- **Safety Standards**: ISM Act, Mining Rules, and geotechnical best practices
- **Data Privacy**: Secure handling of operational and personal data

**Disclaimer**: This system is a monitoring aid and should not replace certified safety equipment or professional geotechnical supervision.

---

**Happy monitoring! Stay safe underground. 🛡️**
