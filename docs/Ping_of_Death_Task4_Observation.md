# Task 4 — Ping of Death: Large ICMP Traffic Observation

**Coursework status:** Completed by student (reported November 9, 2026)  
**Environment in assigned exercise:** ACIDM01 (source) and ACIWIN11 (target), an instructor-provided Windows training environment  
**Type:** Controlled lab activity; not an internet-facing test

## Purpose

This task examined how a continuous stream of large ICMP echo requests affects the network activity shown on a Windows target. The exercise calls this a *Ping of Death* attack. The screenshots supplied with the task are **instructional reference images**, not captures of my own results.

## What I completed

I followed the assigned Task 4 workflow in the training environment:

1. Used the source machine, **ACIDM01**, to open a Windows command prompt.
2. Ran the assigned continuous, large-payload ping against the designated lab target **ACIWIN11** (`192.168.0.3`), using a 65,500-byte payload.
3. Opened **Task Manager → Performance → Ethernet** on the target to observe network activity while the traffic was running.
4. Stopped the continuous command with **Ctrl+C** on the source.
5. Returned to the target's Ethernet performance view to compare activity after the command ended.

## Expected observation in the provided instructions

The instructional screenshots show Ethernet network activity increasing during the ICMP stream and decreasing after the source command is stopped. The example command output shows replies and a summary with no lost packets.

**Evidence limitation:** I supplied screenshots of the assignment instructions, not personal before/during/after captures from the running lab machines. I therefore have not recorded my own measured throughput, packet-loss statistics, CPU load, or evidence of a system crash here. Those values should only be added if supported by my own lab captures.

## Technical note

Although the task is titled *Ping of Death*, sending repeated ICMP packets with a large payload does not by itself prove that a classic oversized-packet vulnerability was exploited. The observable effect described by the task is **increased network traffic**, not a verified crash or denial of service.

## Skills practiced

- Windows Command Prompt and ICMP troubleshooting
- Network traffic observation with Task Manager
- Comparing network activity during and after a controlled test
- Stopping a running diagnostic command
- Distinguishing instructional examples from recorded lab evidence

## Lab boundaries

This activity belongs to the authorized training environment described in the assignment. It is separate from the VirtualBox Kali/Metasploitable host-only network documented in [Lab 1](../README.md). Do not run disruptive traffic against systems outside an expressly authorized lab.

## Evidence to add if available

- Command output from ACIDM01 during the exercise
- ACIWIN11 Ethernet graph while the traffic runs
- Command statistics after stopping the test
- ACIWIN11 Ethernet graph after the traffic stops
