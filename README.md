# ARP-AGRI — ROS 2 workspace

**Status:** 🟡 Bootstrap (2026-07-26)
**Repo:** [arp-ros2](https://github.com/Joker22pl/arp-ros2)
**Owner:** Joker (joker22pl)
**Architect:** Gaja
**Powiązane:** [arp-arch](https://github.com/Joker22pl/arp-arch), [arp-firmware](https://github.com/Joker22pl/arp-firmware)

---

## Co tu będzie

Workspace ROS 2 dla ARP-AGRI outdoor robot. Docelowo pakiety:

- `arp_bringup` — launch files + configurations.
- `arp_perception` — ZED2i + RTAB-Map + Object Detection.
- `arp_control` — diff_drive_controller + ros2_control.
- `arp_safety` — heartbeat, e-stop, state machine.
- `arp_diagnostics` — battery, CPU/GPU temp, network.
- `arp_msgs` — message types.
- `arp_description` — URDF + xacros.

## Status (2026-07-26)

- ❌ **Pusty workspace** — bootstrap dzisiaj.
- ✅ **Compute** — Jetson Orin NX 16GB dev-kit (live na .132).
- ✅ **Sensor** — ZED2i (do zainstalowania).
- ✅ **IMU** — BNO085 (wspólny z IMP2).

## Konwencja

- **ROS 2 distro:** Humble (per IMP2 ADR-0011). Rozważ migrację do Jazzy / Kilted w Q4 2026.
- **Domain ID:** planowany `42` (ARP), IMP2 używa `0`. Pozwoli mieć dwa roboty w jednej sieci.
- **Build:** `colcon build` (standard).
- **Test:** `colcon test` (launch_testing dla integracji).

## Stack technologiczny

- **ROS 2:** Humble (JetPack 6.2 / Ubuntu 22.04).
- **SLAM:** RTAB-Map (ten sam co IMP2, inny config).
- **Sensor:** ZED2i (NEURAL mode baseline).
- **Compute:** NVIDIA Jetson Orin NX 16GB dev-kit (CUDA 12.6).
- **mikrokontroler:** ESP32-S3 (wspólny z IMP2).

## Next steps

1. Zainstalować ROS 2 Humble (jest już apt-installed; trzeba `source /opt/ros/humble/setup.bash`).
2. Zainstalować `zed-ros2-wrapper`.
3. Benchmark RTAB-Map z ZED2i 1 kamera.
4. Klony `imp2-ros2` jako referencja struktury (NIE kopia).

---

*Ten README napisany 2026-07-26 przez Gaię. Mirror struktury `imp2-ros2`.*
