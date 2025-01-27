---
## Ports
---
## Port Roles
---
### **Root Port (RP)**

- Found on **non-root switches**.
- The port with the **lowest path cost to the root bridge**.
- Used to forward traffic toward the root bridge.

### **Designated Port (DP)**

- Found on **each network segment** (collision domain).
- The port on a switch that **provides the best path to the root bridge** for that segment.
- Always in a **forwarding state**.
- On the root bridge, **all active ports are designated ports**.

### **Blocking / Alternate Port**

- A port that is **neither a root port nor a designated port**.
- Placed in **blocking state** to prevent loops.
- Can transition to a **forwarding state** if needed (e.g., when a root port or designated port fails).
- In **RSTP (Rapid Spanning Tree Protocol)**, this is called the **Alternate Port**.

### **Backup Port (RSTP Only)**

- A **backup** for a designated port in case it fails.
- Only exists if there are **two connections** from the same switch to the same segment.
- It remains in a **discarding state** unless needed.
---
## Port-States
---

| STP Port State | Send/Receive BPDUs | Frame forwarding (regular traffic) | MAC address learning | Stable/Transitional |
| -------------- | ------------------ | ---------------------------------- | -------------------- | ------------------- |
| Discarding     | NO/YES             | NO                                 | NO                   | Stable              |
| Learning       | YES/YES            | NO                                 | YES                  | Transitional        |
| Forwarding     | YES/YES            | YES                                | YES                  | Stable              |

## Toolkits
---
### **PortFast**
### **BPDU-Guard**
### **BPDU-Filter**
### **Root-Guard**

- is meant to prevent **designated ports** from becoming **root ports**
### **Loop-Guard**

- should always be enabled on ports that are suposed to receive BPDU's (**root & non-designated**)
- is meant to prevent **non-designated ports** or **root ports** from becoming **designated ports**



