# Internship Task 4 – Setup and Use a Firewall on Windows/Linux

## Objective
Configure and test basic firewall rules to allow or block traffic.

---

## Tools Used
- **Linux:** UFW (Uncomplicated Firewall)
- **Windows:** Windows Defender Firewall

---

## Steps Performed (Linux Example)

1. **Check firewall status and list current rules**
    ```bash
    sudo ufw status verbose
    ```

2. **Block inbound traffic on port 23 (Telnet)**
    ```bash
    sudo ufw deny 23/tcp
    ```

3. **Test the block rule**
    ```bash
    telnet localhost 23
    ```
    - Expected result: `Connection refused` or `Timeout`.

4. **Allow SSH (Port 22)**
    ```bash
    sudo ufw allow 22/tcp
    ```

5. **Remove Telnet block rule**
    ```bash
    sudo ufw delete deny 23/tcp
    ```

---

## Steps Performed (Windows Example)

1. **Open Firewall Settings**
   - Press `Win + R` → type `wf.msc` → Enter.

2. **View current inbound rules**
   - In **Inbound Rules** tab, review active rules.

3. **Block inbound TCP traffic on port 23**
   - New Rule → Port → TCP → Specific local port: `23` → Block connection.

4. **Test using Telnet**
   ```powershell
   telnet localhost 23
   ```
5. **Allow SSH (Port 22)**

   - New Rule → Port → TCP → Specific local port: 22 → Allow connection.

6. **Remove the block rule**

    - Delete the Telnet inbound block rule.
## Screenshots
Screenshots included in screenshots/ folder:

1.  Firewall status before any rules.

2.  Firewall rule created for blocking port 23,Telnet connection attempt showing block,Rule allowing SSH (port 22),Rule removal confirmation.

3.  In Windows allowing telnet port 22 and bloacking telnet 23
 
## Firewall Filtering Summary

A firewall filters traffic based on pre-configured rules to allow, block, or restrict network connections.
Rules can be set based on:

Protocol (TCP/UDP)

 -  Port number

 -  IP address

 -  Direction (Inbound/Outbound)

It is a critical component of system security to prevent unauthorized access.

## Author
**S.Ajans – Cybersecurity Intern**
