# 📺 VA-API Configuration for NVIDIA GPUs on WSLg

This guide documents the specific steps to enable hardware-accelerated video (VA-API) using the D3D12 Gallium driver on Windows 11 WSLg. This allows Linux applications to leverage your GPU for video encoding/decoding via the Windows DirectX layer.

---

## 🛠️ Step 1: Environment Setup

We must globally define the drivers so Mesa and VA-API select the correct hardware device.

### 1. Create the driver profile script
```bash
sudo -i
cat <<EOL > /etc/profile.d/nvidia-driver.sh
export GALLIUM_DRIVER=d3d12
export LIBVA_DRIVER_NAME=d3d12
export LD_LIBRARY_PATH=/usr/lib/wsl/lib
EOL
exit
```

### 2. Add kernel module support
Force the `vgem` module to load on WSL startup to assist with memory management.
```bash
echo "vgem" | sudo tee -a /etc/modules
```

### 3. Update Permissions
Ensure your user can access the video hardware.
```bash
sudo usermod -a -G video $USER
sudo usermod -a -G render $USER
```

---

## 📦 Step 2: Driver Installation (Distro-Specific)

Install the required Mesa VA-API drivers and utility tools based on your distribution.

### **Ubuntu / Debian / Kali Linux**
```bash
sudo apt update
sudo apt install mesa-va-drivers vainfo mesa-utils -y
```

### **Arch Linux**
```bash
sudo pacman -Syu
sudo pacman -S libva-mesa-driver libva-utils mesa-utils
```

### **Fedora**
```bash
sudo dnf install mesa-va-drivers-freeworld libva-utils mesa-demos
```

---

## 🔄 Step 3: Apply & Restart

For hardware changes to take effect, the WSLg system distro must be reset.

1.  **Close** all your Linux terminals.
2.  In **Windows PowerShell**, run: 
    ```powershell
    wsl --shutdown
    ```
3.  **Relaunch** your terminal.

---

## 🧪 Step 4: Verification

Verify that your GPU is correctly recognized and that the VA-API entrypoints are active.

### Check 3D Rendering:
```bash
glxinfo -B | grep "Device"
```
*Expected Output: `Device: D3D12 (NVIDIA GeForce ...)`*

### Check Video Acceleration:
```bash
vainfo --display drm --device /dev/dri/renderD128
```
*Expected Result: `va_openDriver() returns 0` and a list of supported profiles (H264, HEVC, AV1).*

---

## ⚠️ Notes
* **Kali Linux Users:** If you face issues with `vainfo`, ensure you have the `non-free` and `contrib` repositories enabled in your `/etc/apt/sources.list`.
* **Hardware ID:** On some systems, the device might be located at `/dev/dri/card0` instead of `renderD128`. Adjust the `vainfo` command accordingly if the first one fails.