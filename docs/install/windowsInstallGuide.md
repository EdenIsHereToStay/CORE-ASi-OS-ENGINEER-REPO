## ✅ Recommended: Use Windows Subsystem for Linux (WSL2)

This allows you to run Ubuntu natively inside Windows and execute the CORE OS setup as if you're on a Linux machine.

### 🔧 Step 1: Enable WSL & Install Ubuntu
Open **PowerShell (as Administrator)** and run:

```powershell
wsl --install
```

If WSL2 isn’t already set as default, run:

```powershell
wsl --set-default-version 2
```

Then reboot your PC if prompted.

After reboot, go to the **Microsoft Store**, search for **Ubuntu 22.04 LTS**, and click **Install**.

---

### 🧠 Step 2: Launch Ubuntu & Set Up User

After installing Ubuntu, open it from the Start menu and set up your username/password when prompted.

---

### 📦 Step 3: Download and Unzip CORE AI OS Blueprint

In Ubuntu (WSL terminal):

```bash
cd ~
wget https://chat.openai.com/mnt/data/core_ai_os_deployment.zip
unzip core_ai_os_deployment.zip
cd core_ai_os_deployment
```

If you downloaded it through a browser, move the ZIP file to your Ubuntu home directory or `/mnt/c/Users/YourName/Downloads/`.

---

### 🧰 Step 4: Install Dependencies

Inside Ubuntu, run the setup steps listed in the `CORE_AI_OS_Setup.md` file. Begin with:

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y curl wget git tmux htop python3 python3-pip python3-venv redis-server postgresql postgresql-contrib rabbitmq-server
```

Then follow the rest of the sections in the setup blueprint to initialize agents, memory systems, and CLI interface.

---

## 🖥️ Optional GUI: Run with VS Code + WSL

You can open your WSL Ubuntu system directly in Visual Studio Code using the **Remote - WSL** extension, which makes editing and managing files easier.

---

## ⚠️ Alternative Option (Advanced): Use VirtualBox + Ubuntu ISO

If you don’t want to use WSL, you can install Ubuntu 22.04 in a VM using [VirtualBox](https://www.virtualbox.org/), but WSL2 is far more lightweight and tightly integrated with Windows.
