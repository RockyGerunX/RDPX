# RDPX - Free Ubuntu & Windows GUI Access via GitHub Actions

**RDPX** is a GitHub Actions automation project that allows you to run full **Ubuntu Desktop** or **Windows RDP sessions** in the cloud for up to **6–9 hours** for free, using Tailscale for secure connectivity.

---

## ✨ Features

- 🖥️ Ubuntu GUI with XFCE + VNC access
- 🪟 Windows Remote Desktop (RDP) with built-in user authentication
- 🔐 Secure access via [Tailscale](https://tailscale.com/)
- ⏱️ Up to 6 hours runtime per session
- ⚙️ Single-click deployment using GitHub Actions

---

## 📁 Workflow Overview

### Ubuntu GUI (`.github/workflows/Ubuntu.yml`)

- Installs:
  - XFCE4 Desktop Environment
  - TightVNCServer
  - Firefox Browser
- Sets root and VNC password: `admin123`
- Connects via Tailscale using a secret auth key
- Keeps runner alive for 6 hours (21,600 seconds)

### Windows RDP (`.github/workflows/Windows.yml`)

- Enables Remote Desktop (RDP)
- Sets default password: `p@ssw0rd!` for user `runneradmin`
- Opens RDP firewall ports
- Installs and authenticates Tailscale
- Keeps session active for 6 hours

---

## 🚀 How to Use

### Prerequisites

1. A GitHub account
2. A valid [Tailscale Auth Key](https://tailscale.com/kb/1085/auth-keys/) (stored as a GitHub Actions secret named `TS_AUTHKEY`)

### Steps

1. **Fork this repository** to your GitHub account.
2. Go to the **Actions** tab.
3. Select either `RDPX Ubuntu` or `RDPX Windows`.
4. Click **Run workflow**.
5. Wait a few minutes for the environment to initialize.

---

## 🔗 Accessing the Remote Desktop

Once the workflow is running:

- Log into the same Tailscale account you used to generate the auth key.
- Find the device:
  - **Ubuntu**: `ubuntu-gui`
  - **Windows**: `github-runner`
- Connect using:
  - **VNC (Ubuntu)**: `hostname:1` (password: `admin123`)
  - **RDP (Windows)**: Remote Desktop to device IP (user: `runneradmin`, password: `p@ssw0rd!`)

---

## ⚠️ Disclaimer

> This project is for **educational purposes only**.  
> Do not use this for any unethical, unauthorized, or illegal activity.  
> Sessions are temporary and automatically terminate after 6 hours.

---

## 🤝 Contributions

Feel free to open issues or submit pull requests to improve functionality, add features, or enhance security.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
