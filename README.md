# DNS Sinkhole + Unbound
[Pi-hole](https://pi-hole.net/) acts as a network-wide DNS sinkhole that blocks ads and trackers by intercepting unwanted DNS queries before they reach your devices. This improves privacy, security, and network performance by reducing unnecessary traffic.  

[Unbound](https://docs.pi-hole.net/guides/dns/unbound/) complements Pi-hole as a validating, recursive DNS resolver, securely handling and caching DNS queries to further enhance privacy and ensure efficient domain resolution.

## Technology Used

- **Raspberry Pi** (hardware platform)  
- **Raspberry Pi OS / Ubuntu Linux** (operating system)  
- **Network and Router Configuration** (DHCP, static IP, DNS forwarding)  
- **Pi-hole** (DNS sinkhole and ad blocker)  
- **Unbound** (validating recursive DNS resolver)

---

<h2>Setup Walkthrough</h2>

**Step 1:** Prepare your Raspberry Pi by flashing the Raspberry Pi OS image.  
<p align="center">
  <img src="https://i.imgur.com/TdsZU6R.jpeg" alt="Raspberry Pi imaging" width="500" />
</p>

**Step 2:** Install Pi-hole using the official install script.  
<p align="center">
  <img src="https://i.imgur.com/sssrPRm.jpeg" alt="Install Pi-hole command" width="500" />
</p>

**Step 3:** Assign a static IP address to your Raspberry Pi for consistent network access.  
<p align="center">
  <img src="https://i.imgur.com/MqnnUBv.jpeg" alt="Set static IP" width="500" />
</p>

**Step 4:** Configure your router’s DHCP settings to use your Pi’s IP as the primary DNS server, enabling network-wide ad blocking.  
<p align="center">
  <img src="https://i.imgur.com/jmb1D9S.jpeg" alt="Router DNS settings" width="500" />
</p>

**Step 5:** Access the Pi-hole dashboard to monitor blocked queries and network stats.  
<p align="center">
  <img src="https://i.imgur.com/RoV906B.jpeg" alt="Pi-hole dashboard" width="500" />
</p>

---

### Integrating Unbound

**Step 6:** Install Unbound to act as a validating recursive DNS resolver.  
<p align="center">
  <img src="https://i.imgur.com/t29d7rF.jpeg" alt="Install Unbound command" width="500" />
</p>

**Step 7:** Create and edit the Unbound configuration file.  
<p align="center">
  <img src="https://i.imgur.com/pIo0xMc.jpeg" alt="Create Unbound config file" width="500" />
</p>

**Step 8:** Copy the recommended configuration block (source: [Pi-hole Unbound Guide](https://docs.pi-hole.net/guides/dns/unbound/#:~:text=unbound/root.hints-,Configure%20unbound,%C2%B6,-Highlights%3A)) into the file and save.  
<p align="center">
  <img src="https://i.imgur.com/YsdDXlp.jpeg" alt="Unbound config snippet" width="500" />
</p>

**Step 9:** Restart the Unbound service to apply changes.  
<p align="center">
  <img src="https://i.imgur.com/kv04Qwh.jpeg" alt="Restart Unbound" width="500" />
</p>

**Step 10:** In Pi-hole settings, clear any upstream DNS servers and add a custom one pointing to `127.0.0.1#5335` (localhost with Unbound's port). This completes your secure DNS setup!  
<p align="center">
  <img src="https://i.imgur.com/DEJArsd.jpeg" alt="Pi-hole upstream DNS settings" width="500" />
</p>

---

