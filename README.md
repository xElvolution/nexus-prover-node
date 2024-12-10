# Nexus Setup Guide for Linux VPS 🚀

A comprehensive guide to installing and configuring the Nexus client on a Linux VPS. This guide ensures a clean setup and highlights best practices for a seamless experience.

---

## Prerequisites
Before you begin, ensure you have:
- A Linux VPS with root or sudo access.
- Basic knowledge of using the terminal.
- Installed SSH access to your VPS.

---

## Installation Steps

### 1️⃣ Back Up or Remove Existing Configurations
If you have a previous Nexus installation, back it up or remove it:

- **Back up existing configuration**:
  ```bash
  mv ~/.nexus ~/.nexus_backup
  ```

- **Remove old configuration**:
  ```bash
  rm -rf ~/.nexus
  ```

This ensures a fresh start for the installation.

---

### 2️⃣ Update System Packages
To ensure compatibility, update your system packages:

```bash
sudo apt update && sudo apt upgrade -y
```

Install required dependencies:

```bash
sudo apt install build-essential pkg-config libssl-dev git-all nano -y
```

---

### 3️⃣ Install Nexus CLI
Install the Nexus CLI using the official installation script:

```bash
curl https://cli.nexus.xyz/ | sh
```

Wait for the installation to complete.

---

### 4️⃣ Configure Prover ID
By default, Nexus generates a random Prover ID. Follow these steps to configure it manually:

1. Stop the CLI process by pressing `Ctrl + C`.
2. Edit the Prover ID file:
   ```bash
   nano ~/.nexus/prover-id
   ```
3. Replace the existing ID with your custom Prover ID.
4. Save and exit: Press `Ctrl + X`, then `Y`, and `Enter`.

---

### 5️⃣ Run Nexus in a Persistent Session
To keep Nexus running in the background, use a `screen` session:

1. Start a new screen session:
   ```bash
   screen -S nexus
   ```
2. Re-run the Nexus CLI installation script:
   ```bash
   curl https://cli.nexus.xyz/ | sh
   ```

---

### 6️⃣ Detach and Reattach Screen Session
- **Detach**: Press `Ctrl + A`, then `D` to leave the session running in the background.
- **Reattach**: Return to the session anytime with:
  ```bash
  screen -r nexus
  ```

---

### 7️⃣ Stopping or Killing Nexus
- To stop Nexus, press `Ctrl + C` in the screen session or type:
  ```bash
  exit
  ```

- To forcefully kill the session:
  ```bash
  screen -XS nexus quit
  ```

---

## Troubleshooting
- **Permission Denied**: Ensure you’re using `sudo` for commands that require elevated privileges.
- **Screen Not Installed**: Install it with:
  ```bash
  sudo apt install screen -y
  ```

---

## Support
For additional assistance or to report issues, visit the [Nexus Documentation](https://nexus.xyz/docs) and forget to follow on twiiter https://x.com/0xElvolution
