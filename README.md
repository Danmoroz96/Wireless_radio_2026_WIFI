# Wireless_radio_2026_WIFI
Wifi task for Wireless and Radiotechnology course

This analysis details my local Wi-Fi and network environment based on the provided Net Analyzer and BLE Scanner data.

Network Device Inventory
The LAN scan identifies several active devices on the local subnet (192.168.101.x):

Gateway (192.168.101.1): The "dna.wifi" router serving as the primary exit point.

Scanning Device (192.168.101.100): A Samsung SM-A346B (Galaxy A34 5G), currently used for the analysis.

Client Device (192.168.101.101): An LG LMG4-IVL5 connected to the same network.

Nearby Wi-Fi & Channel Usage
The 2.4 GHz band is significantly more congested with institutional networks:

Savonia / eduroam: Multiple access points are visible, operating on overlapping channels.

Signal Disparity: A strong eduroam signal is seen at -50 dBm on Channel 1, while other Savonia APs are as weak as -73 dBm on Channel 11.

Analysis & Troubleshooting
Identified Issues
2.4 GHz Congestion: The 2.4 GHz spectrum is crowded with eduroam and Savonia signals. This causes Co-Channel Interference (CCI), where devices must wait for "airtime," slowing down data transfers.

BLE Interference: Several "Non-Connectable" Bluetooth Low Energy devices are active nearby (e.g., at 31m and 112m), which also operate in the 2.4 GHz range and can cause minor noise.

Carrier Anchor: While connected to Wi-Fi, the device also maintains an LTE (4G) connection with Saunalahti (Elisa) at -69 dBm, which is a strong backup for data stability.

Proposed Solutions
Band Steering: Ensure high-bandwidth devices (laptops, TVs) stay on the 5 GHz band (Channel 56) to avoid the 2.4 GHz congestion.

Channel Optimization: In the 2.4 GHz range, networks should stick strictly to Channels 1, 6, or 11 to minimize overlap. Your current connection on the 5 GHz band is already optimal.

Router Repositioning: Given the excellent -45 dBm signal, the current placement is ideal. If dead zones appear, move the router to an elevated, central location.
