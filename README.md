🚀 Online Server – Real-Time ADL Streaming Backend

📡 Python WebSocket backend deployed on Render
🎓 Developed for the thesis project:

Data Collection System and Stream Learning Model for Activities of Daily Living (ADL) Classification

🌐 Live Deployment (Render):
🔗 https://online-sensor-backend.onrender.com

🧠 Overview

This backend acts as the real-time communication bridge between:

📱 Flutter Mobile Client
🤖 Classification & Stream Learning Pipeline
💾 Persistence / Logging Layer (optional)

It enables real-time streaming of sensor feature windows and supports incremental learning experimentation.

🏗 System Role in Thesis Architecture
Flutter Client (Smartphone)
        ↓
WebSocket Streaming
        ↓
Online Server (Render)
        ↓
Prediction + Policy Logic
        ↓
Logging / Evaluation / Incremental Update


This server represents the online experimentation layer of the thesis architecture.

✨ Key Features

✅ WebSocket-based real-time communication
✅ JSON-based structured window payloads
✅ Schema validation (optional)
✅ Real-time inference (SVM + probability calibrator)
✅ Selective labeling policy engine (optional)
✅ Incremental evaluation compatibility (River – HT / ARF)
✅ Cloud-ready deployment (Render)

📥 Example Payload (Client → Server)
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

📤 Example Payload (Server → Client)
{
  "status": "ok",
  "window_id": "abc123",
  "prediction": "walking",
  "confidence": 0.82,
  "request_label": false
}

🔬 Integration with Thesis Project

This backend integrates with:

📊 Offline Training Pipeline – Scikit-learn baseline models
🌊 Incremental Learning Models – River (Hoeffding Tree / Adaptive Random Forest)
🧩 Selective Labeling Policy Engine
📱 Flutter-based Sensor Client (Android)

It represents the real-time deployment and experimentation stage of the Stream Learning system.

🛠 Technologies Used

🐍 Python

🔌 Async WebSocket Server

🤖 Scikit-learn (offline baseline)

🌊 River (incremental learning – optional integration)

📄 JSON Schema Validation

☁️ Render (Cloud Deployment)

🎓 Academic Context

This repository supports research in:

Real-time Human Activity Recognition (HAR)

Activities of Daily Living (ADL) Classification

Stream Learning methodologies

Incremental evaluation strategies

Model stability and drift behavior analysis

👩‍💻 Author

Paula M.
Electronic and Telecommunications Engineering
Universidad del Cauca

📜 License

This repository is intended for academic and research purposes only.
