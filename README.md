# MDE-For-Linux
All about Microsoft Defender for Endpoint Detection in Linux 
	1) Overall process diagram of MDE Linux

<img width="688" height="480" alt="image" src="https://github.com/user-attachments/assets/c23eec6f-a709-4397-a205-ea1f26134b8a" />

fanotify → wdavdaemon gets the event → AV engine (local + cloud) decides. If malicious and RTP is enforcing, access can be blocked at open and the file moved to quarantine; if not enforcing (passive, or excluded), the detection is logged as allowed. The eBPF sensor enriches EDR with process/file telemetry at kernel-safe hook points, replacing auditd rules on modern builds.


Key Components in the Flow:
	• fanotify → kernel event interception.
	• wdavdaemon → orchestrates scanning and enforcement.
	• AV engine → local + cloud intelligence (signatures, heuristics, ML).
	• Policy → determines block vs allow.
	• eBPF sensor → advanced telemetry for EDR (Endpoint Detection & Response).
	• Cloud MAPS → optional reputation and ML verdic
