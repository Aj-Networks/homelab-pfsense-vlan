# Switch Port Map

802.1Q port assignments for the **Netgear GS308E v4** managed switch.

- **Management IP:** 10.10.1.100 (static, gateway 10.10.1.1)
- **Accessible via:** VLAN 50 (MGMT) only — VLAN 10 management access permanently disabled

---

## Port Assignments

| Port | Mode | PVID (Untagged) | Tagged VLANs | Connected Device |
|---|---|---|---|---|
| 1 | Trunk | 1 | 10, 20, 30, 40, 50 | pfSense igb1 (Port 7) |
| 2 | Access | 10 | — | Trusted PC |
| 3 | Access | 10 | — | Netgear R6400 (AP) |
| 4 | Access | 20 | — | Printer |
| 5 | Access | 20 | — | IoT device |
| 6 | Access | 40 | — | Cisco Catalyst 3560 |
| 7 | Access | 40 | — | Cisco 1900 Router |
| 8 | Access | 50 | — | MGMT spare — unplugged when not in use |

---

## Notes

- Port 1 carries all VLANs tagged + native VLAN 1 untagged — this is the trunk uplink to pfSense
- Ports 2–8 are untagged access ports — devices on these ports have no awareness of VLANs
- VLAN 40 ports (6 & 7) are fully isolated from all other VLANs via firewall rules
- Port 8 lands on VLAN 50 (MGMT), which has full internal reach and direct WAN access. Physical access to this port = full network access. Keep unplugged when not in active use.
