# Changelog

All notable changes to this project are documented here.

---

## [Phase 3] — Planned
### Added
- Tailscale remote access (advertised routes `10.10.1.0/24` and `10.10.10.0/24` pending)
- Replace Netgear R6400 with VLAN-aware AP for proper VLAN 30 guest isolation
- Suricata IDS — alert-only mode across WAN, VLAN10, VLAN20, VLAN30
- Guest Wi-Fi rate limiting on VLAN 30

---

## [Phase 2] — 2026-03-17
### Added
- Router-on-a-Stick topology via single 802.1Q trunk (`igb1`)
- 6 VLANs: Native, Users (10), IoT (20), Guest (30), Lab (40), MGMT (50)
- Dual Mullvad WireGuard tunnels — Chicago (primary) + NYC (failover)
- `VPN_FAILOVER` gateway group with automatic tier promotion
- 5-layer kill switch — zero WAN NAT, DoH/DoT block, RFC1918 isolation, IPv6 block
- DNS locked to Mullvad servers — no leak path during failover
- Netgear GS308E v4 configured with full 802.1Q port assignments
- Netgear R6400 set to strict AP mode on VLAN 10
- Cisco lab gear isolated on VLAN 40
- Verified zero leaks — ipleak.net + Mullvad Check

### Changed
- Switch management restricted to VLAN 50 only — VLAN 10 access permanently removed

### Documented
- `HOME_LAB_v2.pdf`, `FIREWALL_RULES_MANUAL.pdf`, `SWITCH_VLAN_MANUAL.pdf`

---

## [Phase 1] — 2026
### Added
- Initial pfSense 2.8.1 install on Protectli FW6E
- Basic WAN + LAN configuration
- Single Mullvad WireGuard tunnel (Chicago)
- Preliminary VLAN segmentation
- Initial firewall rules and NAT setup
