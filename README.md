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

Technical Analysis & Troubleshooting
1. Signal Propagation and Attenuation
The measured signal strength of -45 dBm for the connected Wi-Fi network indicates an Excellent connection. In wireless terms, every 3 dB increase represents a doubling of signal power; therefore, a signal of -45 dBm is significantly more robust than the institutional Savonia signals measured at -73 dBm in the same area.

Observation: The 5 GHz signal is very strong, suggesting the device is in the same room as the Access Point (AP).

Physics Note: Higher frequencies (5 GHz) attenuate faster through walls than lower frequencies (2.4 GHz). While the 5 GHz link is currently superior, moving behind two or more concrete walls would likely cause the device to "failover" to the 2.4 GHz band for better penetration.

2. Spectral Congestion and Interference
The analysis of nearby networks reveals a high density of Access Points on the 2.4 GHz ISM band.

Co-Channel Interference (CCI): Multiple networks (eduroam, Savonia, Savonia-AMK) are seen competing for Channel 1 and Channel 11. This creates a "Wait-to-Talk" scenario where the effective throughput is much lower than the reported link speed because the airtime is shared among all nearby devices.

Bleed-over Interference: Nearby Bluetooth (BLE) devices are active in the same 2.4 GHz spectrum. While BLE is designed for low interference, a high density of these devices can raise the "noise floor," reducing the Signal-to-Noise Ratio (SNR) for Wi-Fi.

3. Network Configuration and Modern Standards
The connected network uses the 802.11ac (Wi-Fi 5) standard.

Bandwidth Efficiency: By using Channel 56 (DFS) in the 5 GHz band, your network avoids the massive congestion seen in the 2.4 GHz band.

Max Theoretical Throughput: The link speed of 866 Mbps is achieved through 256-QAM modulation and multiple spatial streams. If the signal quality drops (lower SNR), the router will automatically "downshift" to a simpler modulation like 16-QAM, significantly reducing speed to maintain a stable connection.

Final Troubleshooting Recommendations
To optimize this specific network environment, the following actions are recommended:

Prioritize 5 GHz for High-Traffic Devices: Since the 2.4 GHz band is saturated by institutional signals (Savonia/eduroam), all bandwidth-heavy devices (laptops/workstations) should be manually pinned to the DNA-WIFI-5GHZ SSID.

Enable DFS (Dynamic Frequency Selection): The current use of Channel 56 is excellent. Staying on DFS channels helps avoid common interference from neighboring residential routers that usually stick to non-DFS channels (36-48).

Router Placement: Ensure the router is not placed near other electronic devices (like microwaves or cordless phones) that operate on 2.4 GHz, as the BLE scanner already shows significant activity in that range.

Security Update: The network currently uses WPA2 (AES). If the hardware supports it, upgrading to WPA3 would provide better protection against modern "offline dictionary" attacks.
Router Repositioning: Given the excellent -45 dBm signal, the current placement is ideal. If dead zones appear, move the router to an elevated, central location.
