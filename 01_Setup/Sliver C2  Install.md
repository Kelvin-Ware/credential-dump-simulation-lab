# Sliver C2 Installation on Ubuntu Server (Attacker VM)

This section walks through installing and configuring the Sliver C2 framework on the Ubuntu Server attacker VM, as part of the credential dumping lab.

---

## 🖥️ Step 1: Become Root

Start by switching to the root user to ensure you have the necessary permissions for the installation process:

```
sudo su
whoami  # Confirm that output is 'root'
```

---

## 🌐 Step 2: Verify Network Connectivity

Ping the gateway to confirm your VM is connected to the network:

```
ping _gateway -c 1
```

---

## ⚙️ Step 3: Assign a Static IP

Edit the Netplan configuration file to assign a static IP address:

```
nano /etc/netplan/00-installer-config.yaml
```

Make the necessary changes (IP, gateway, etc.), then save and exit.


## 🔐 Step 4: SSH from Host Machine

Once the static IP is set, connect to your Ubuntu VM from your host machine via SSH:

```
ssh username@<your-static-ip>
```

[SSH From Host](./Screenshots/Ububtu%20ssh.png)

---

## 📁 Step 5: Prepare Directory for Sliver

After connecting via SSH, switch to the root user again if needed, and create a working directory for Sliver:

```
sudo su
mkdir -p /opt/sliver
```

---

## 📦 Step 6: Download Sliver Server

Use `wget` to download the Sliver server binary directly into the correct location:

```
wget https://github.com/BishopFox/sliver/releases/download/v1.5.34/sliver-server_linux -O /usr/local/bin/sliver-server
```

Make it executable:

```
chmod +x /usr/local/bin/sliver-server
```

---

## 🚀 Step 7: Launch Sliver Server

Once installed, you can launch the Sliver server:

```
sliver-server
```

[Screenshot – Sliver Launch](./Screenshots/Run%20SLiver.png)

