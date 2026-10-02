# Cute Vitals

Small native-looking Linux desktop system monitor for KDE/Qt. It refreshes every second and shows CPU and NVIDIA GPU health with compact coloured gauges.

## Dependencies

- Python 3.10+
- PySide6 or PyQt6
- `nvidia-smi` (optional; GPU card disappears gracefully when unavailable)

On Kubuntu:

```bash
cd /home/conner/Documents/GitHub/cute-vitals
python3 -m venv .venv
.venv/bin/pip install PyQt6
.venv/bin/python cute_vitals.py
```

The app reads CPU utilisation from `/proc/stat`, CPU frequency from `/sys/devices/system/cpu`, temperatures from hwmon/thermal sysfs, and GPU values from the supported NVIDIA query interface.

## What it shows

- CPU model, total load, package/main temperature, current frequency, and per-core load
- System RAM usage, calculated from total minus Linux's reclaimable `MemAvailable`
- GPU name, temperature, utilisation, VRAM used/total, and power draw
- One-second refresh timestamp, temporary `nvidia-smi` failure handling, and compact always-on-top toggle
