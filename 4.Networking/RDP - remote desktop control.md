
- its a protocol
- enabling the rdp = starting a service (a server process) that listens to RDP connections

teamviewer but built into windows

### 🔹 How does it work?

1. **The remote computer (the one you want to control)** runs a service called **Remote Desktop Service** (RDS).
    
2. That service listens on **TCP port 3389**.
    
3. **Your computer (the client)** connects using the Remote Desktop Client (`mstsc.exe`).
    
4. Your input (mouse clicks, keyboard presses) and the other computer’s screen image are sent back and forth — encrypted — over the network

- its recomended to be used with a vpn