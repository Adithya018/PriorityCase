# Microsoft Training - Day 1: SQL Engine & 911 Triage
**Role:** Partner Technical Advisor (PTA) | **Project:** SkyGate Airlines Recovery

## 🎯 Learning Objective
Mastered the SQL Server Engine architecture and diagnostic workflow to resolve High-Priority (Sev-1) escalations without causing customer dissatisfaction (DSAT).

## 🛠️ Technical Deep-Dive
### 1. SQL Engine Anatomy
* **Protocol Layer:** Managed connectivity via TCP/IP and Shared Memory.
* **Relational Engine:** Analyzed how the Parser and Optimizer create execution plans.
* **Storage Engine:** Deep understanding of the Buffer Pool (RAM) and ACID properties (Atomicity, Consistency, Isolation, Durability).

### 2. Diagnostic Tools Mastered
* **DMVs:** Used `sys.dm_exec_requests` and `sys.dm_os_waiting_tasks` to identify real-time bottlenecks.
* **Wait Stats:** Identified `LCK_M_S` (Locking) as the primary cause for the Airline "System Hang."
* **Error Logs:** Analyzed `xp_readerrorlog` to perform a "Post-Mortem" on server shutdowns and recovery status.

## ✈️ Live Case Simulation: Operation SkyGate
**Scenario:** A Global Airline reported a boarding system hang due to a background audit process.
* **Triage:** Identified Session ID [X] as the "Head Blocker" holding an Exclusive Lock.
* **Resolution:** Performed a surgical `KILL` of the blocking session, restoring the "Path to Green" in seconds.
* **Stakeholder Management:** Drafted an RCA for the CSAM to explain the technical root cause and recommended **Read Committed Snapshot Isolation (RCSI)** as a long-term preventative measure.

## 🚀 Key Takeaways for Role
* **DSAT Prevention:** Learned that consistent communication and "Proactive Guidance" are as important as the technical fix.
* **Escalation Management:** Understanding when to engage PG (Product Group) via IcM versus resolving environmental configuration issues.
