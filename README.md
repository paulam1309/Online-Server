# Data Collection System and Stream Learning Model for ADL Classification

## Overview

This repository contains the complete implementation of the thesis project:

**Data Collection System for Training a Stream Learning Model for Activities of Daily Living (ADL) Classification**

The system was designed to support real-time classification of human activities using inertial data collected from smartphones (accelerometer and gyroscope).

The project integrates:

- Offline supervised training  
- Online incremental (stream) learning  
- Selective label request policy  
- Stability and reaction analysis over time  

The architecture follows a client–server model with persistent storage and incremental adaptation.

---

# Online Server – Real-Time ADL Streaming Backend

## Description

This repository contains the Python WebSocket backend deployed on Render as part of the thesis system.

The server is responsible for:

- Receiving real-time windowed sensor data from the Flutter mobile client  
- Validating incoming JSON payloads  
- Performing optional real-time inference  
- Supporting the online Stream Learning workflow  

**Live Deployment (Render):**  
https://online-sensor-backend.onrender.com

---

## System Role in the Architecture

Client (Flutter App)  
→ Streams feature windows via WebSocket  
→ Online Server (Render)  
→ Prediction + policy logic  
→ Logging / evaluation / incremental update  

This server represents the online experimentation and deployment layer of the thesis architecture.

---

## Key Features

- WebSocket-based real-time communication  
- Structured JSON window payloads  
- Schema validation (optional)  
- Real-time inference (SVM + probability calibrator)  
- Selective labeling policy engine  
- Incremental evaluation compatibility (River – HT / ARF)  
- Cloud-ready deployment (Render)  

---

## Example Payload (Client → Server)

```json
{
  "device_id": "phone_01",
  "position": "pocket",
  "sampling_hz": 20,
  "window_id": "abc123",
  "timestamp": "2025-08-20T15:32:10Z",
  "features": {
    "acc_mean_x": 0.12,
    "acc_std_x": 0.98,
    "gyro_mean_z": -0.03
  },
  "metadata": {
    "session_id": "s01",
    "user_id": "u01"
  }
}
```

---

## Example Payload (Server → Client)

```json
{
  "status": "ok",
  "window_id": "abc123",
  "prediction": "walking",
  "confidence": 0.82,
  "request_label": false
}
```

---

## Technologies Used

- Python  
- Async WebSocket server  
- Scikit-learn (offline baseline model)  
- River (incremental models – optional integration)  
- JSON schema validation  
- Render (cloud deployment)  

---

## Academic Context

This work contributes to research in:

- Real-time Human Activity Recognition (HAR)  
- Activities of Daily Living (ADL) classification  
- Stream Learning methodologies  
- Incremental model evaluation  
- Stability and adaptation analysis in evolving systems  

---

## Author

Paula M.  
Electronic and Telecommunications Engineering  
Universidad del Cauca  

---

## License

This repository is intended for academic and research purposes.
