# task-3-
Sure! Here’s a concise README file for your task:

---

# README

## Task Overview
This document outlines the steps taken to change the username, password, and hostname in Kali Linux, gather network information, and compress the findings into a password-protected zip file.

## Steps

### 1. Change Username, Password, and Hostname
- **Change Username:**
  ```bash
  sudo usermod -l new_username old_username
  ```
- **Change Password:**
  ```bash
  passwd new_username
  ```
- **Change Hostname:**
  ```bash
  sudo hostnamectl set-hostname new_hostname
  ```

### 2. Take a Screenshot
Capture the terminal output after making the changes:
```bash
gnome-screenshot -a
```

### 3. Gather Network Information
- **Public IP:**
  ```bash
  curl ifconfig.me
  ```
- **Private IP:**
  ```bash
  hostname -I
  ```
- **MAC Address:**
  ```bash
  ip link show | grep ether
  ```

### 4. Save Findings to a Text File
```bash
echo "Public IP: $(curl -s ifconfig.me)" > network_info.txt
echo "Private IP: $(hostname -I)" >> network_info.txt
echo "MAC Address: $(ip link show | grep ether | awk '{print $2}')" >> network_info.txt
```

### 5. Compress the Text File
Create a password-protected zip file:
```bash
zip -P ictkerala.org network_info.zip network_info.txt
```

## Conclusion
This README summarizes the steps to modify system settings and gather network information in Kali Linux, followed by securely storing the results.

--- 

Feel free to adjust any details as needed!
