# Resource Monitor

## Features

Display CPU frequency, usage, memory consumption, battery percentage remaining, and memory pressure (macOS only) within the VSCode status bar.

## Screenshots

![Disk space feature](images/disk_space_screenshot.png).

## Requirements

Just the system information node module.

## Extension Settings

- `resmon.show.cpuusage`: Show CPU Usage. In Windows, this percentage is calculated with processor time, which doesn't quite match the task manager figure.
- `resmon.show.cpufreq`: Show CPU Frequency. This may just display a static frequency on Windows.
- `resmon.show.mem`: Show consumed and total memory as a fraction.
- `resmon.show.battery`: Show battery percentage remaining.
- `resmon.show.disk`: Show disk space information.
- `resmon.show.cputemp`: Show CPU temperature. May not work without the lm-sensors module on Linux. May require running VS Code as admin on Windows.
- `resmon.disk.format`: Configures how the disk space is displayed (percentage remaining/used, absolute remaining, used out of totel).
- `resmon.disk.drives`: Drives to show. For example, 'C:' on Windows, and '/dev/sda1' on Linux.
- `resmon.updatefrequencyms`: How frequently to query systeminformation. The minimum is 200 ms as to prevent accidentally updating so fast as to freeze up your machine.
- `resmon.freq.unit`: Unit used for the CPU frequency (GHz-Hz).
- `resmon.mem.unit`: Unit used for the RAM consumption (GB-B).
- `resmon.alignLeft`: Toggles the alignment of the status bar.
- `resmon.color`: Color of the status bar text in hex code (for example, #FFFFFF is white). The color must be in the format #RRGGBB, using hex digits.
- `resmon.show.mempressure`: Show memory pressure value (macOS only). Uses `memory_pressure -Q` command to display system memory pressure.

## Known Issues

A better solution for Windows CPU Usage would be great. I investigated alternatives to counting Processor Time, but none of them seemed to match the Task Manager percentage.

---

## Change Log

### [1.0.0]

- fork from <https://github.com/Njanderson/resmon.git>
- Added memory pressure indicator feature for macOS using `memory_pressure -Q` command output
- Updated all dependencies using `npx npm-check-updates -u`
