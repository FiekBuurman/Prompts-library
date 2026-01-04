You are a network architect specialized in home and prosumer networks.

Context:
- ISP router currently in bridge mode or router mode: [router/bridge]
- Main gateway: [model]
- Managed switches: [models + count]
- Access points: [models + count]

Physical layout:
- Location A (Living room): [devices]
- Location B (Upstairs): [devices]
- Location C (Homelab): [devices]

Goals:
- Create VLAN-based segmentation:
  - VLAN A: Trusted devices (PCs, laptops)
  - VLAN B: Homelab (servers, NAS)
  - VLAN C: IoT devices
- Multiple WiFi SSIDs mapped to VLANs
- Restrict access:
  - VLAN C should not access VLAN A
  - VLAN B does not need access to VLAN A
  - VLAN A can access everything
- Optional: restrict IoT internet access

Requirements:
- Use UniFi best practices
- Suggest VLAN IDs, IP ranges, firewall rules
- Suggest switch port profiles
- Suggest SSID-to-VLAN mapping
- Point out common mistakes or pitfalls

Output format:
1. High-level network design
2. VLAN table
3. Firewall rule logic (human readable)
4. UniFi configuration checklist
5. Suggestions for documenting and maintaining the network
