# Building a Compact Raspberry Pi Cluster

This repository documents the creation, configuration, and performance analysis of a lightweight ARM-based Raspberry Pi cluster using:

- **1 Raspberry Pi 4B (4GB)**
- **4 Raspberry Pi Zero 2W**
- **ClusterHAT 2.5** as interconnect

## 🛠️ Hardware Setup

- **Master Node:** Raspberry Pi 4B
- **Worker Nodes:** 4 × Raspberry Pi Zero 2 W
- **Cluster Interface:** ClusterHAT 2.5 (uses USB Gadget Mode)

## ⚙️ Software & Configuration

- OS: Raspberry Pi OS Lite (32-bit debian-based)
- Networking: USB gadget mode (via ClusterHAT)
- Headless configuration via SSH

## 🧠 Computational Capacity (Estimated)

| Node                  | CPU            | MIPS (approx.) | RAM    |
|-----------------------|----------------|----------------|--------|
| Raspberry Pi 4B       | Cortex-A72 @1.5GHz (4-core) | ~5500         | 4GB |
| Raspberry Pi Zero 2 W | Cortex-A53 @1.0GHz (4-core) | ~2500 (each)  | 512MB   |

**Total (Cluster): ~15,500 MIPS**

> ⚠️ Note: Communication between nodes is limited by shared USB 2.0 bandwidth (~480 Mbps total), introducing latency and reducing throughput for I/O-bound tasks.

## 🚦 Performance Considerations

### ✅ Ideal Use Cases
- CPU-bound parallel tasks
- Lightweight distributed simulations
- Edge computing prototypes
- Learning & experimentation with clustering

### ❌ Not Recommended For
- High-throughput I/O workloads
- Latency-sensitive distributed computing
- Memory-intensive applications

## 📸 Images (Optional)

_Add wiring diagrams, photos of the setup, etc._

## 📚 Useful Resources

- [ClusterHAT Documentation](https://clusterhat.com/)
- [Raspberry Pi Zero 2 W Specs](https://www.raspberrypi.com/products/raspberry-pi-zero-2-w/)
- [Raspberry Pi 4 Specs](https://www.raspberrypi.com/products/raspberry-pi-4-model-b/)

## 📍 Next Steps

- Add real-world benchmarks (e.g., stress-ng, sysbench)
- Evaluate orchestration tools (Docker, k3s)
- Explore network optimization options
