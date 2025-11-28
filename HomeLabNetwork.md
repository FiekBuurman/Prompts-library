# Home Network Router/Gateway Selection

## Context
I'm a homelab enthusiast who actively tinkers with:
- Synology NAS systems (specify models if relevant)
- Proxmox server (HP machine with i5-7700, 32GB RAM, running 20+ VMs/containers)
- Current technical skill level: comfortable with networking basics, Linux CLI, Docker, Debian

## Current Situation

**ISP & Connection:**
- Currently: Ziggo cable (400Mbps)
- Future: Planning to switch to KPN fiber (1Gbps)
- Using ISP-provided router for DHCP and DNS

**Current Network Setup:**
- Number of devices: 15+ wired, 10+ wireless
- Key services running: Jellyfin, Home Assistant, Pi-hole, Passbolt, Zigbee2Mqtt
- VLANs: None currently / Planning to segment IoT devices
- Optional: Remote access to homelab / Site-to-site 

**Pain Points:**
- Vendor lock-in with ISP router configurations
- Limited control over DNS/DHCP settings
- Concern about reconfiguring everything when switching ISPs

## Goal
Create an ISP-agnostic network setup that:
1. Survives ISP changes without major reconfiguration
2. Gives me full control over DHCP, DNS, and routing
3. Supports future homelab expansion (more VLANs, VPN, etc.)

## Requirements

**Must Have:**
- Separate modem/ONT and router functions
- Gigabit WAN port
- Multiple gigabit LAN ports OR SFP+ for future expansion
- VLAN support
- VPN server capability (WireGuard/OpenVPN)
- Stable firmware with regular updates
- Low power consumption (<15W idle)

**Nice to Have:**
- PoE ports for future APs or cameras
- 2.5GbE or 10GbE LAN for NAS connectivity
- Hardware offloading for VPN
- Local management (no forced cloud)
- Active community support

**Technical Preferences:**
- Willing to learn: OpenWrt, pfSense, OPNsense, Ubiquiti UniFi
- NOT willing to: Manage complex CLI-only setups daily

## Specific Questions

1. **Ubiquiti Cloud Gateway Ultra evaluation:**
   - Is the UCG-Ultra appropriate for my use case?
   - How does it handle ISP changes (PPPoE for KPN fiber)?
   - Are there better alternatives in the same price range?
   - Concerns about UniFi's cloud dependency vs local management

2. **ISP transition strategy:**
   - What configuration should I document before switching?
   - Should I keep the KPN modem in bridge mode?
   - Any gotchas with KPN fiber + third-party routers?

3. **Alternative solutions:**
   - Should I consider running pfSense/OPNsense on dedicated hardware?
   - Would a Mikrotik device be better value? (e.g., RB5009)
   - Mini PC + OPNsense vs purpose-built router?

4. **Future expansion:**
   - If I add UniFi APs later, does UCG-Ultra make more sense?
   - Best way to add VLANs for IoT isolation?
   - Recommendations for managed switch to pair with router?

## Constraints
- Noise tolerance, it all run in the living area, so it's need to be silent.

## Output Format
Please provide:
1. **Direct answer** to UCG-Ultra suitability (yes/no with reasoning)
2. **3 alternative options** with pros/cons comparison table
3. **ISP migration checklist** for smooth transition
4. **Recommended network topology** diagram or description
5. **Estimated total cost** including any necessary switches/APs
