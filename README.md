# 🛰️ Orbital Telemetry Engine

High-performance, fault-tolerant telemetry packet decoder and orbital trajectory prediction engine engineered for space mission operations and real-time distributed systems.

---

## 🚀 Architecture Overview

```
[Spacecraft Sensors / Ground Station] 
               │
               ▼ (Raw Binary Telemetry Stream)
┌──────────────────────────────────────────────┐
│  Zero-Allocation Binary Packet Decoder       │
└──────────────────────┬───────────────────────┘
                       │
                       ▼
┌──────────────────────────────────────────────┐
│  Kalman Filter & State Estimation Engine     │
└──────────────────────┬───────────────────────┘
                       │
       ┌───────────────┴───────────────┐
       ▼                               ▼
┌───────────────┐             ┌────────────────┐
│ SGP4 Orbital  │             │ Fault-Tolerant │
│ Propagator    │             │ Ring Buffer    │
└───────────────┘             └────────────────┘
```

---

## 🛠️ Core Modules
1. **`TelemetryDecoder`**: Fast binary stream parser handling frame synchronization, checksum validation (CRC-16), and telemetry bit-packing.
2. **`OrbitalPropagator`**: Real-time position and velocity vector calculation based on Keplerian orbital elements and perturbation corrections.
3. **`TelemetryStreamer`**: Low-latency asynchronous socket server broadcasting telemetry telemetry packets to mission control dashboards.

---

## 📦 Quick Start

```python
from telemetry_core import TelemetryEngine

engine = TelemetryEngine(station_id="GS-PATNA-01")
engine.start_stream()
```
