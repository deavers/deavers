# 🎮 @deavers — Master Cybersecurity & Systems Engineering Quest Log

> **Character Class:** Systems & Malware Research Engineer (`C++20` / `Linux Internals` / `Local AI` / `Hardware IoT`)  
> **Current Main Quest:** BSc Thesis — *Linux Sandbox for Malware Analysis with Local AI (`FFTE`)* @ FEI VŠB-TUO  

---

## 🔥 MAIN QUEST: Bachelor's Thesis & ZSU Pipeline (Priority #1)

### Act I: Theoretical & Data Science Foundation (Thesis Point 1 & ZSU)
- [x] **Quest 1.1:** Select and validate hybrid Linux/IIoT malware dataset (`CIMD-2024`, 45,289 records, 37 features).
- [x] **Quest 1.2:** Perform physics-consistent missing value reconstruction (`Average Packet Size` & `Packet Arrival Rate`) and engineer 4 domain features (`Throughput_Bps`, `Entropy_Gap`, `Anomaly_Severity_Index`, `Host_Load_Ratio`).
- [x] **Quest 1.3:** Complete Unsupervised Clustering analysis (`K-Means k=4`, `DBSCAN eps=1.15`, `Ward Linkage`) and defend **ZSU Part 1**.
- [ ] **Quest 1.4:** Read *Kyle Cucci — Evasive Malware (2024)* **Ch. 2, 16, 17, 18** & *Bruce Nikkel — Practical Linux Forensics* **Ch. 4, 5, 8**; draft **Chapter 1** of the BSc thesis in LaTeX.
- [ ] **Quest 1.5 (ZSU Part 2):** Train supervised triage models (`LogisticRegression` baseline vs. `RandomForest` & `LightGBM`) using `StratifiedKFold` and `Optuna`; perform False Positives / False Negatives Error Analysis.

### Act II: Expanding C++20 FFTE for Linux (Thesis Point 2)
- [ ] **Quest 2.1 (`ProcNetScanner.cpp`):** Parse `/proc/net/tcp`, `/proc/net/udp`, `/proc/net/raw` (decode hex little-endian IP:Port) and map socket `inode` numbers to PIDs via `/proc/[pid]/fd/*`.
- [ ] **Quest 2.2 (`PayloadEntropyScanner.cpp`):** Implement native `<elf.h>` header/section inspection (`Elf64_Ehdr`, `Elf64_Phdr`, `Elf64_Shdr`, `RWX` segments) and Shannon entropy calculation ($H \in [0.0, 8.0]$).
- [ ] **Quest 2.3 (`LinuxMemHuntScanner.cpp`):** Detect fileless execution (`/memfd:` and `(deleted)` symlinks in `/proc/[pid]/exe`), anonymous `rwxp` regions in `/proc/[pid]/maps`, and `TracerPid` in `/proc/[pid]/status`.
- [ ] **Quest 2.4 (`TempEntropyDiffScanner.cpp` & `HostLoadScanner.cpp`):** Monitor `/tmp` & `/dev/shm` for hidden staging files and sudden file entropy spikes (Ransomware indicator) + read `/proc/stat` & `/proc/meminfo`.
- [ ] **Quest 2.5 (`Pre/Post Diff Engine`):** Add `--baseline pre.json --diff post.json` CLI flags to FFTE to output a compact behavioral delta JSON.

### Act III: Sandbox Topology, Controlled Scenarios & Real Malware (Thesis Points 3, 4, 5)
- [ ] **Quest 3.1 (KVM Topology):** Configure an isolated QEMU/KVM Linux guest with `qcow2` instant snapshot revert and a Host-Only virtual bridge (`virbr_sandbox`) running `tcpdump` / `INetSim`.
- [ ] **Quest 3.2 (12 Controlled Scenarios):** Generate and execute **3 Bash pairs (Plain vs. Raw-Encrypted $H \approx 7.99$)** and **3 Python pairs (Plain vs. Raw-Encrypted $H \approx 7.99$)**; verify detection in FFTE and ZSU ML model.
- [ ] **Quest 3.3 (False Positive Validation):** Run benign system tasks (`apt update`, `tar`, FFTE self-triage) to prove low false-positive rates via `Pre/Post Diff`.
- [ ] **Quest 3.4 (Real Malware Stress Test):** Safely execute 3–5 real Linux ELF malware families (`Mirai`, `Gafgyt`, `Kinsing`, `XorDDoS` from *MalwareBazaar*) inside the isolated KVM environment and collect JSON reports.

### Act IV: JSON Schema, Local AI & Final Defense (Thesis Points 6, 7)
- [ ] **Quest 4.1:** Finalize the unified JSON telemetry schema combining Static/Entropy metrics, ZSU features, and Behavioral Diffs.
- [ ] **Quest 4.2:** Connect `viewer.html` (Split-Screen Dashboard + Chat) to local `Ollama` / `llama.cpp` (`Llama-3.2-3B` / `Qwen-2.5-3B` GGUF) for automated **MITRE ATT&CK** incident report generation.
- [ ] **Quest 4.3:** Evaluate end-to-end accuracy, performance overhead, and memory footprint; write **Chapters 5 & 6** of the BSc thesis.

---

## ⚔️ SIDE QUESTS: Skill Tree Progression (Lv. 1 $\rightarrow$ Lv. 99 God-Tier)

### ⚙️ Track A: Reverse Engineering & Binary Exploitation ([`lowlevel-re-and-exploitation`](https://github.com/deavers/lowlevel-re-and-exploitation))
- [ ] **Lv. 10:** Read *CS:APP* **Ch. 3 & 7** + *Yurichev RE for Beginners* **Part I** $\rightarrow$ Defuse all 6 phases of **CMU Bomb Lab** in `GDB` & `Ghidra`.
- [ ] **Lv. 20:** Complete **CMU Attack Lab** (Buffer Overflows & ROP chains) + solve 10 crackmes on `crackmes.one`.
- [ ] **Lv. 35:** Read *Practical Binary Analysis (Andriesse)* **Ch. 1–7** $\rightarrow$ Build `libffte_hook.so` (`LD_PRELOAD` syscall interceptor) in `/03-ld-preload-and-ptrace`.
- [ ] **Lv. 55:** Read *The Ghidra Book* **Ch. 14–18** & *Tmp.0ut Zine* $\rightarrow$ Build a custom C++20 `ELF64 .text` ChaCha20 packer and an automated Ghidra unpacking script in `/04` & `/05`.
- [ ] **Lv. 85 (God-Tier):** Read *Practical Binary Analysis* **Ch. 8–13** & *Seacord Secure Coding in C/C++* $\rightarrow$ Build an `AFL++` + `ASan` fuzzing harness & `angr` solver in `/06-fuzzing-and-angr` and discover a 0-day bug.

### 📡 Track B: Hardware, Firmware & Wireless Security ([`iot-hardware-arsenal`](https://github.com/deavers/iot-hardware-arsenal))
- [ ] **Lv. 15:** Read *The IoT Hacker's Handbook (Gupta)* **Ch. 1–4** $\rightarrow$ Unpack a router firmware (`binwalk -e`), extract `SquashFS`, and build the **Firmware Entropy & ELF Sink Scanner** in `/01`.
- [ ] **Lv. 35:** Read *IoT Hacker's Handbook* **Ch. 5–7** & *Hardware Hacking Handbook* **Ch. 1–5** $\rightarrow$ Locate PCB `UART` pins, hijack a `U-Boot` shell, and program an **ESP32-S3 SPI Flash Dumper** in `/02`.
- [ ] **Lv. 60:** Read *IoT Hacker's Handbook* **Ch. 9–10** $\rightarrow$ Build the **ESP32-S3 BLE GATT Security Auditor** in `/03` and the **nRF24 2.4GHz Replay Attack & HMAC-SHA256 Defense Testbed** in `/04`.
- [ ] **Lv. 90 (God-Tier):** Read *Hardware Hacking Handbook* **Ch. 7–11** $\rightarrow$ Build an ESP32-controlled **Voltage Glitching** circuit to bypass MCU Read-Out Protection.

### ⚔️ Track C: Network Traffic, Linux PrivEsc & Red Teaming ([`offensive-pentest-labs`](https://github.com/deavers/offensive-pentest-labs))
- [ ] **Lv. 15:** Read *Practical Packet Analysis (Sanders)* **Ch. 1–8, 10–11** $\rightarrow$ Build the Python `.pcap` & `Zeek` flow feature extractor in `/01`.
- [ ] **Lv. 35:** Complete 20 Linux/Windows machines on **Hack The Box** $\rightarrow$ Build the **Atomic Linux Adversary Runner** (15 MITRE ATT&CK techniques) in `/02` & `/03`.
- [ ] **Lv. 60:** Read *Real-World Bug Hunting (Yaworski)* + complete 40 **PortSwigger Web Security Academy** labs $\rightarrow$ Publish OWASP PoC labs and async recon scanner in `/04`.
- [ ] **Lv. 90 (God-Tier):** Read *Container Security (Liz Rice)* $\rightarrow$ Reproduce a kernel/container escape in an isolated VM and write a `Seccomp-BPF` containment profile.

---

## 🏆 Certification Milestones Checklist
- [x] **Cisco Networking Academy** — *Introduction to Cybersecurity*
- [x] **NCSTA** — *Cyber Security 101*
- [x] **CW Labs** — *Blue Team Fundamentals (`BTF`) & Certified Cyber Security Analyst (`C3SA`)*
- [ ] **ISC2 CC** — *Certified in Cybersecurity*
- [ ] **Microsoft SC-900** — *Security, Compliance, and Identity Fundamentals*
- [ ] **CompTIA Security+ (SY0-701)**
- [ ] **BTL1 (Blue Team Level 1)** or **CCD (Certified CyberDefender)**
- [ ] **HTB CPTS (Certified Penetration Testing Specialist)**
- [ ] **OSCP (Offensive Security Certified Professional)**
- [ ] **GIAC GREM (Reverse Engineering Malware)**
