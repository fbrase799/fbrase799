# Embedded Software

My view: embedded software succeeds when **resource constraints and real-world interfaces** shape the architecture from day one — timing, memory, safety, and field connectivity are not afterthoughts.

I work with modern **C++** (C++17/20/23), **C**, and **Rust** on Linux and RTOS targets (Yocto, Zephyr) as well as bare-metal. Platforms range from devices on the edge to systems that later connect into cloud backends.

### Connectivity (embedded side)

On the device and field-bus side, connectivity is part of embedded design: **CAN** and similar buses, deterministic messaging, and the software that makes sensors and actuators trustworthy. Protocol choices here are driven by latency, robustness, and hardware reality.

Application-level connectivity (REST, MQTT toward the cloud, WebSockets) belongs primarily under [Application Software](./application-software.md) — the same product often spans both layers.

**Keywords:** Modern C++ (C++17/20/23) · C · Rust · Embedded Linux · Yocto · Zephyr RTOS · Bare-Metal · CAN

---

[← Back to profile](../README.md)
