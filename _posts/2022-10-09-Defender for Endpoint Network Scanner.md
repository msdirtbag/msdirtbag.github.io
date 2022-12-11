---
layout: post
title: Defender for Endpoint Network Scanner
thumbnail-img: ./assets/img/netscan.jfif
---
Network devices are not managed as standard endpoints since Defender for Endpoint doesn't have a sensor built into the network devices themselves. These types of devices require an agentless approach where a remote scan will obtain the necessary information from the devices. Depending on the network topology and characteristics, a single device or a few devices onboarded to Microsoft Defender for Endpoint will perform authenticated scans of network devices using SNMP (read-only).

1. Do you use MDE for EDR/NGAV❓
2. Did you deploy the MDE network scanner⁉️

MDE Threat & Vulnerability Management supports HPE, Palo Alto, Cisco (non-Meraki), and Juniper hardware today so consolidating your current Vulnerability Management solutions may not make sense. (yet) 🕖

You still need to install the MDE network scanner to get the most out of your EDR purchase.

🖊️Here’s why:

MDE Standard Device Discovery watches ICMP, HTTP, LLMNR, RDP, SMTP, SMB and other popular communication protocols to identify and classify non-onboarded endpoints but it can’t see everything.

👀This is important because MDE has the ability to Contain non-onboarded endpoints by telling all MDE endpoints (with Network Protection in Block Mode) to drop all packets from the "Contained" device.

💡Here’s the trick: MDE has to see the device and generate a deviceid before it can be contained.

If you are only using MDE’s built-in device discovery capabilities, you will miss 40-50% of the discoverable devices on your LAN subnets and you won’t be able to Contain them even if they are actively attacking your hosts. 😬

![Image](/assets/img/netscan.jfif)

🎒Resources:

Device Discovery: https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/device-discovery?view=o365-worldwide#network-device-discovery

Selecting Networks: https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/configure-device-discovery?view=o365-worldwide#select-networks-to-monitor

Installing Scanner: https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/network-devices?view=o365-worldwide#install-the-network-scanner

Device Containment: https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/respond-machine-alerts?view=o365-worldwide#contain-devices-from-the-network

