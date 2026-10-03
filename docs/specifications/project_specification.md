# EdgeGuard AI

## Edge-AI Predictive Maintenance System

### 1. Project Overview

EdgeGuard AI is an Edge-AI predictive maintenance system designed to monitor the condition of an industrial motor using embedded sensors and an STM32 microcontroller.

The system collects temperature, vibration, and current data from the motor, processes the data locally, and uses a machine learning model to detect abnormal operating conditions.

The system will initially be developed as a virtual prototype and will later be adapted to real hardware.

---

### 2. Problem Statement

Industrial machines can develop faults such as overheating, excessive vibration, and abnormal current consumption.

Traditional monitoring systems often rely on fixed thresholds and may detect problems only after a significant abnormality occurs.

EdgeGuard AI aims to develop an intelligent embedded monitoring system capable of analyzing machine behavior and detecting abnormal conditions in real time using Edge AI.

---

### 3. Main Objectives

- Monitor the condition of an industrial motor.
- Acquire temperature, vibration, and current measurements.
- Process sensor data using an STM32 microcontroller.
- Build a dataset representing different machine conditions.
- Train a machine learning model to classify machine states.
- Deploy the AI model on an embedded platform.
- Detect anomalies in real time.
- Calculate a machine health score.
- Transmit monitoring data using MQTT.
- Develop a real-time monitoring dashboard.
- Prepare the system for future physical hardware implementation.

---

### 4. Machine Conditions

The first version of EdgeGuard AI will classify five conditions:

1. NORMAL
2. OVERHEATING
3. HIGH_VIBRATION
4. OVERCURRENT
5. COMBINED_ANOMALY

---

### 5. Main Technologies

#### Embedded

- STM32F4
- STM32CubeIDE
- Embedded C
- ADC
- UART
- Timers

#### Artificial Intelligence

- Python
- NumPy
- Pandas
- Scikit-learn
- Machine Learning
- TinyML / Edge AI

#### Communication

- MQTT

#### Software

- Python
- Streamlit
- SQLite

#### Simulation

- Wokwi

---

### 6. System Architecture

```text
                    EDGEGUARD AI
                         |
                         v
                 +---------------+
                 | Virtual Motor |
                 +-------+-------+
                         |
          +--------------+--------------+
          |              |              |
          v              v              v
    Temperature      Vibration       Current
       Sensor          Sensor         Sensor
          |              |              |
          +--------------+--------------+
                         |
                         v
                 +---------------+
                 |    STM32F4    |
                 |               |
                 | Data          |
                 | Acquisition   |
                 | Processing    |
                 +-------+-------+
                         |
                         v
                    Edge AI Model
                         |
              +----------+----------+
              |          |          |
              v          v          v
           NORMAL     WARNING     ANOMALY
                         |
                         v
                       MQTT
                         |
                         v
                 Python Backend
                         |
                         v
                     Database
                         |
                         v
                    Dashboard