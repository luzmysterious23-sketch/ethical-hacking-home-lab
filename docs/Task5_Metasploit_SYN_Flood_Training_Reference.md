# Task 5 — SYN Flood Using Metasploit (Training Reference)

**Course:** CS352 — Ethical Hacking and Network Defense  
**Environment:** ACI / Infosec Learning hosted training lab  
**Evidence status:** Assignment instructions shared; independent student execution screenshots not included in this update.

## Purpose

This task introduces a TCP SYN flood in a controlled training environment using the Metasploit Framework. The learning objective is to observe whether a high volume of TCP connection attempts changes the target Windows machine's network activity.

## Environment shown in the instructions

| Role | Device | Details |
| --- | --- | --- |
| Traffic-generation workstation | ACIKALI | Kali Linux, Metasploit Framework |
| Training target | ACIWIN11 | Windows 11 VM, `192.168.0.3` |
| Destination service | Target TCP port 21 | As specified in the task instructions |
| Observation tool | Task Manager → Performance → Ethernet | Shows target network activity |

This hosted lab is **separate from** my [VirtualBox Kali/Metasploitable environment](../README.md).

## Assigned workflow (summary)

1. Open the terminal in ACIKALI and start the Metasploit console.
2. Select the framework's SYN-flood auxiliary module and configure the assigned target and lab parameters.
3. Launch the module **only inside the instructor-authorized training environment**.
4. Open Task Manager on ACIWIN11 and view network activity under **Performance → Ethernet**.
5. Compare the observed Ethernet activity with baseline behavior; document any change.

## What the provided course screenshots show

- The Metasploit console opening successfully.
- Configuration of the target, destination port, source-address setting, and timeout.
- A sample console message stating that SYN flooding has started against the target service.
- A Windows Task Manager example in which Ethernet traffic rises while the exercise is underway; the example reports roughly **1.1 Mbps received**.

**Important distinction:** These images are examples embedded in the course instructions. They do **not** establish the actual packet volume, service availability, or throughput of my own execution. No personal captured results were provided with this GitHub update.

## Technical interpretation

SYN flooding sends a large number of TCP connection-opening requests. An affected service may have to allocate resources while connections remain incomplete, potentially reducing availability. A visible increase in Ethernet throughput alone does **not** prove that the target was unavailable or that a denial of service succeeded.

## Evidence to add from my own lab

- [ ] Original Metasploit console output from the run
- [ ] Task Manager's Ethernet graph during the test
- [ ] Observed changes in responsiveness or availability, if any
- [ ] Recovery or baseline network activity after the test ends

## Skills addressed

- Working with Metasploit in a controlled exercise
- Recognizing TCP SYN flood behavior
- Monitoring Windows Ethernet throughput
- Separating expected outcomes in a handout from directly observed results
- Recording the scope and limitations of a DoS lab

## Scope

This page documents an assigned, isolated coursework exercise; it does not provide an operational playbook for flooding third-party systems. Conduct any traffic-generation work only on instructor-approved targets.

**Source:** User-provided screenshots of “Task 5 — Perform An SYN Flood Attack Using Metasploit Framework” (steps 1–13).
