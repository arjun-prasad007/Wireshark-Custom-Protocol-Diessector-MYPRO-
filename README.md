# Wireshark-Custom-Protocol-Diessector-MYPRO-

A high-performance custom protocol dissector written in Lua for Wireshark. This project demonstrates how to decode a proprietary UDP-based protocol, extract specific data fields, and implement protocol validation using Expert Information.
🚀 Features
Custom Protocol Mapping: Automatically identifies traffic on UDP port 8888.
Field Extraction: Decodes packets to display:
Message Type (e.g., Login, Data)
User ID (16-bit unsigned integer)
Payload (String data)
Expert Analysis: Real-time validation that flags an error if a packet contains an invalid User ID (e.g., ID = 0).
🛠️ Tools Used
Wireshark: Network protocol analyzer.
Lua: Scripting language for the dissector.
Packet Sender: To generate and test custom HEX packets.
VS Code: For writing the Lua script.
📸 Screenshots
![](/assets/Myprotocol.png)
![](/assets/The_Code.png)
![](/assets/Userid.png)
Protocol Decoding:
Description: Wireshark correctly identifying the MYPRO protocol and its fields.
Expert Info Warning:
Description: Wireshark flagging a 'User ID cannot be zero' warning.
⚙️ How to Setup
Download mypro.lua from this repository.
Open Wireshark and go to Help > About Wireshark > Folders.
Double-click on Personal Lua Plugins and paste the mypro.lua file there.
Restart Wireshark or press Ctrl + Shift + L to reload plugins.
🧪 How to Test
Use Packet Sender to send the following HEX to 127.0.0.1 on Port 8888:
Normal Packet: 01000548656c6c6f (Type: 1, ID: 5, Payload: Hello)
Warning Packet: 01000048656c6c6f (Type: 1, ID: 0 -> Triggers Expert Info)
