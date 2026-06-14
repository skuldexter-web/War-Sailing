# WAR SAILING

A high-yield, passive 802.11 wardriving and wireless mapping toolkit wrapped in a Viking-themed interactive CLI. Designed natively for Debian-based systems (Kali Linux, Raspberry Pi OS, Ubuntu).

## Features

* **Intelligent Auto-Sizing Banner:** Automatically detects the terminal width. It seamlessly switches between a large ASCII banner (for SSH via the Termius app) and a compact layout (for physical 3.5-inch Raspberry Pi screens).
* **Noise-Free Live Loot Feed:** Fully sanitized input streams. No more corrupt null-bytes or Bash warnings when encountering hidden SSIDs or stuttering GPS packets.
* **Dynamic GPS Fallback:** Automatically switches to a visual [SIGNAL LOSS] indicator in the cockpit during indoor testing or temporary signal dropouts, preserving data integrity.
* **Automated Rigging & Secure:** Puts your wireless interface into monitor mode and initializes gpsd with a single command. Upon stopping (Ctrl + C or via the menu), all hardware is cleanly released.
* **Integrated Log Viewer:** Review past expeditions and the number of captured Access Points directly from the main menu.
* **Passive Sniffing:** Captures 802.11 Beacon and Probe Response frames without transmitting or altering network states.
* **Automated Background Channel Hopping:** Seamlessly cycles wireless cards through channels 1-13 every 0.5s via background threading to maximize discovery yield.
* **Robust Packet Parsing:** Uses Scapy to directly parse information elements (Dot11Elt), safely extracting SSIDs, BSSIDs, and RSSI metrics even from partial or malformed management frames.
* **Asynchronous GPS Integration:** Couples real-time GPS coordinates directly to network observations via gpsd.
* **WiGLE-Compliant:** Outputs logs directly into standard WigleWifi-1.6 CSV formatting, ready for immediate upload to the global tracking network.
* **PEP 668 Compliant Architecture:** Runs inside an isolated Python virtual environment, keeping your host OS clean and safe.

---

## Prerequisites & Hardware

To effectively launch an expedition, your Linux rig requires:
1. **Wireless Interface:** Supporting passive monitor mode (e.g., Alfa AWUS036ACM or Raspberry Pi internal chip on supported distros).
2. **GPS Receiver:** Any standard NMEA USB serial GPS dongle supported by gpsd (e.g., GlobalSat BU-353-S4 or u-blox).

---

## Installation & Deployment

Clone this repository or download install.sh, then follow the tactical sequence below:

### 1. Provision Execution Rights
chmod +x install.sh

### 2. Run First-Time Setup
Execute with root privileges to automatically resolve core dependencies (aircrack-ng, gpsd, tshark, jq) and configure the Python venv:
sudo ./install.sh --install

### 3. Launch the Cockpit
Run the deployment utility to open the interactive menu and manage your hardware states:
sudo war-sailing

---

## Operational Interface

Upon deployment, choose your tactical fate via the interactive CLI:
* **[1] Start Expedition (Scan):** Prompts interface selection, kicks off the channel hopper, interfaces with gpsd, and opens the live colorized Loot Feed. Press Ctrl + C to drop anchor and safely return to the menu.
* **[2] Stop & Secure Sails:** Safely tears down the monitor interface, turns off injection hooks, and releases background processing layers.
* **[3] View Saved Logs:** Previews stored historical expedition counts and allows terminal inspection of collected CSV files.
* **[4] Update Tool from GitHub:** Instantly pulls the latest tactical updates from the Git repository.
* **[5] Exit:** Closes the menu interface.

All session data is stored safely under /home/sk7ld/.warsailing/logs/.

---

## Disclaimer

This toolkit performs **passive radio frequency monitoring only**. It does not attempt connection, transmission, de-authentication, or disruption of any network infrastructure. Always comply with local laws and telecommunication regulations regarding passive radio signal gathering.

*Fair winds, Viking. Walhalla awaits.*
