---
layout: default
title: Dataset
permalink: /dataset/
---
<h1>About the dataset</h1>
The dataset is available on <a href="https://drive.google.com/drive/folders/1TwZ_vwJQ6tWXgcp6E0DyBUqqkUBJG24W?usp=drive_link">Google Drive</a> and consists of four zip files:
1. `all_traces_root.zip` includes traces for all 149 patched malwares operating with root privileges. 
2. `all_traces_user.zip` contains traces for all 149 patched malwares running under user privileges. 
3. `ransom_traces.zip` contains traces for 60 ransomware instances that exhibit file read/write/encryption behaviors. 
4. `benign_disk_traces.zip` includes traces for 55 benign disk applications (e.g., zip programs).


For each malware/application, we collect four types of traces: syscall traces, network traces, disk traces, and performance traces. The syscall trace is stored in `*.syscall` files, the disk trace in `*.blktrace` files, the network trace in `*.net` files, and the performance trace in `*.perf` files. Data collection begins upon launching the virtual machine (VM) and initiating the malware sample. It continues until either the malware execution concludes or a timeout of 600 seconds is reached.

<h2>Syscall Trace</h2>

* Monitoring and recording system calls made by a process or processes running on an operating system 
* Well-known trace

<h2>Network Trace</h2>
* Record data transfer between computer and network media (e.g., ethernet)
* Use a popular packet analysis tool <a href="https://www.wireshark.org/">wireshark</a> to capture the data transfer information

<h2>Disk Trace</h2>
* Record data transfer between computer’s motherboard and storage devices (e.g., HDDs)
* Use Linux utility <a href="https://linux.die.net/man/8/blktrace">blktrace</a> to capture data transfer information


<h2>Perf Trace</h2>
* Perf trace is a command in the Linux perf tool suite, which is a powerful set of tools used for performance analysis and debugging  
* Use Linux utility <a href="https://perf.wiki.kernel.org/index.php/Main_Page">perf</a> to capture Performance Counter (HPC) measurements collected over 100ms time intervals



