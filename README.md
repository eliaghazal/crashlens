<div align="center">

# CrashLens

### AI-powered crash detection and emergency response platform

[![Website](https://img.shields.io/badge/website-crashlens.org-blue?style=for-the-badge)](https://crashlens.org)
[![Status](https://img.shields.io/badge/status-live%20%26%20deployed-success?style=for-the-badge)]()
[![Stage](https://img.shields.io/badge/stage-commercial%20product-orange?style=for-the-badge)]()

</div>

---

## What is CrashLens?

CrashLens is a real-time crash detection and emergency coordination platform that bridges the moment of impact to the people who need to respond — in seconds, not minutes.

A Raspberry Pi 5 edge device reads live **IMU, GPS, camera, and LTE** data. When a crash is detected, the system instantly:

1. Captures a 15-second pre-crash + 30-second post-crash video clip
2. Uploads GPS coordinates, speed, and impact severity to the cloud
3. Notifies the **insurance dashboard** with AI forensic analysis of the incident

> *"From sensor to responder in under 3 seconds."*

---

## Proven End-to-End

CrashLens has been tested and verified on real hardware:

| Component | Status |
|-----------|--------|
| Camera Module 3 NoIR (1080p30) | Proven |
| GPS Module (NEO-6M, UART) | Proven |
| IMU Crash Detection (100Hz, 2.5G threshold) | Proven |
| Ring Buffer Recording (15s pre + 30s post) | Proven |
| H264 → MP4 Conversion (ffmpeg) | Proven |
| Cloud Upload (metadata + video to R2) | Proven |
| Heartbeat Monitoring | Proven |
| Systemd Auto-Start on Boot | Proven |
| Insurance Dashboard (8 pages) | Proven |

---

## Architecture Overview

```
+------------------------------------------------------------------+
|                     EDGE DEVICE                                   |
|  Raspberry Pi 5 · IMU/GPS/Camera/LTE                             |
|  Real-time crash detection · AI inference on-device              |
+----------------------------+-------------------------------------+
                             |
                          LTE/HTTPS
                             |
                             v
+------------------------------------------------------------------+
|                    CLOUD BACKEND                                  |
|  Cloudflare Workers + Hono.js (edge API)                         |
|  Supabase (Postgres + Auth)                                       |
|  Cloudflare R2 (video evidence storage)                           |
|  Multi-stakeholder routing                                        |
+--------------------+--------------------------+------------------+
                     |                          |
             +-------+------+          +--------+-----------+
             | Flutter App  |          | Next.js Dashboard  |
             | Driver +     |          | Insurance / Fleet  |
             | Responder    |          | Management         |
             +--------------+          +--------------------+
```

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Edge Device | Raspberry Pi 5, Python, OpenCV, TensorFlow Lite |
| Connectivity | LTE (SIM7600G), GPS (NEO-6M), 6-axis IMU |
| Cloud API | Cloudflare Workers + Hono.js (TypeScript) |
| Database | Supabase (PostgreSQL + Row Level Security) |
| Video Storage | Cloudflare R2 |
| Mobile | Flutter (iOS + Android) |
| Dashboard | Next.js 14, TypeScript, Tailwind CSS |
| AI | On-device crash inference, cloud forensics pipeline |

---

## Status

CrashLens is a live, deployed commercial product. The platform is currently in active development and pilot testing.

**Visit:** [crashlens.org](https://crashlens.org)

---

## Team

**Elia Ghazal** — Co-Founder & Lead Engineer
[GitHub](https://github.com/eliaghazal) · eliaghazal777@gmail.com

### Collaborators

- [Bassam Farhat - Co-Founder](https://github.com/bassamfarhat)
- [William Ishak - Co-Founder](https://github.com/williamishak)
- [George Khayat - Co-Founder](https://github.com/georgekhayat)

---

<div align="center">
<sub>Commercial product — source code is proprietary. This repository is a public showcase only.</sub>
</div>
