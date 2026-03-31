# VLC-open-source-audit
Open Source Software Audit Project on VLC Media Player including scripts, analysis, and documentation

## Student Information

**Name:** Aditi Yadav
**Registration Number:** 24BAC10070
**Course:** Open Source Software (OSS NGMC Capstone)
**Submission Date:** 31 March 2026

---

## About the Project

This project is a detailed audit of VLC Media Player conducted as part of the Open Source Software course. The aim of this project is to understand how open-source software works, how it is structured in a Linux environment, and how it compares with proprietary software.

The study also includes practical implementation using Linux commands and shell scripting.

---

## Software Selected

**VLC Media Player**

VLC is a free and open-source multimedia player developed by the VideoLAN organization. It supports a wide range of multimedia formats and does not require external codecs.

**License Used:** GNU General Public License (GPL)

---

# Part A — Origin and Philosophy

## Problem Addressed

Before VLC, playing media files required installing multiple codecs manually. This made the process complicated and unreliable. VLC solved this issue by integrating all codecs within the software, allowing users to play media files easily without additional setup.

## License Explanation

VLC is distributed under the GNU General Public License (GPL), which allows:

* Free usage of the software
* Modification of source code
* Redistribution of software

The GPL ensures that any modified version remains open source.

## Ethics of Open Source

Open source promotes transparency, collaboration, and knowledge sharing. It allows developers worldwide to contribute and improve software collectively.

---

# Part B — Linux Footprint


## Installation

VLC can be installed in Linux using:

```bash
sudo apt install vlc
```

---

## File Structure

| Component    | Location     |
| ------------ | ------------ |
| Executable   | /usr/bin/vlc |
| Libraries    | /usr/lib     |
| Config Files | /etc         |
| Logs         | /var/log     |

Check executable location:

```bash
which vlc
```


---

## User and Permissions

```bash
whoami
ps aux | grep vlc
```

VLC runs as a normal user process, improving system security.


---

## Execution and Updates

Run VLC:

```bash
vlc
```

Update system:

```bash
sudo apt update && sudo apt upgrade
```


---

# Part C — FOSS Ecosystem

## Dependencies

VLC depends on:

* FFmpeg
* libavcodec
* libavformat
* libavutil

These libraries help in multimedia decoding and processing.

---

## Community and Development

VLC is maintained by the VideoLAN organization and a global community of developers. Contributions include bug fixes, new features, and performance improvements.

---

## Collaboration Model

Development follows:

* Git-based version control
* Pull requests
* Code review system
* Issue tracking

---

## Impact

VLC has simplified multimedia playback and increased awareness of open-source software among general users.

---

# Part D — Open Source vs Proprietary

## Comparison

| Feature     | VLC (Open Source) | Proprietary Software |
| ----------- | ----------------- | -------------------- |
| Cost        | Free              | Paid                 |
| Source Code | Available         | Not Available        |
| Flexibility | High              | Limited              |
| Control     | User              | Vendor               |
| Support     | Community         | Professional         |

---

## Analysis

Open-source software provides flexibility, transparency, and cost benefits. Proprietary software offers structured support and reliability.

---

## Recommendation

VLC is highly recommended for:

* Students
* General users
* Developers

Proprietary software is more suitable for enterprise-level requirements.

---

# Part E — Shell Scripts

## Script 1 — System Information

```bash
#!/bin/bash
echo "User: $(whoami)"
echo "Kernel Version: $(uname -r)"
echo "System Uptime: $(uptime -p)"
echo "Current Date and Time: $(date)"
```



---

## Script 2 — VLC Check

```bash
#!/bin/bash
if dpkg -l | grep -q vlc
then
  echo "VLC is installed"
else
  echo "VLC is not installed"
fi
```


---

## Script 3 — Disk Usage

```bash
#!/bin/bash
for dir in /etc /home /var
do
  echo "Checking directory: $dir"
  du -sh $dir
done
```


---

## Script 4 — Log Analyzer

```bash
#!/bin/bash
count=0
while read line
do
  if echo "$line" | grep -iq "error"
  then
    count=$((count+1))
  fi
done < $1

echo "Total number of errors: $count"
```

---

## Script 5 — Manifesto Generator

```bash
#!/bin/bash
read -p "Enter your favorite open-source tool: " tool
echo "I believe in open-source software and use $tool." > manifesto.txt
cat manifesto.txt
```


---

# How to Run Scripts (Linux)

```bash
nano script1.sh
chmod +x script1.sh
./script1.sh
```

---

# Dependencies

* Linux Operating System
* Bash Shell
* VLC Media Player

---

# Conclusion

This project provided a clear understanding of open-source software, its working, and its importance. VLC Media Player demonstrates how open-source development can produce powerful, flexible, and widely used software.

---

# References

* https://www.videolan.org
* https://github.com/videolan/vlc
* https://ffmpeg.org
* https://opensource.org
* https://help.ubuntu.com
