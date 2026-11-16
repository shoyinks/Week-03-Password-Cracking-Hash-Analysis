# Week 03: Password-Cracking & Hash-Analysis
Practical walkthrough of hash identification, dictionary attacks, and password auditing using John the Ripper, complete with command outputs and screenshots.

## Overview
This week focuses on understanding cryptographic hash function in my cybersecurity internship, I extracted and recovered passwords from four encrypted PDF files ($pdf$4*4*128* format) on Windows. To complete the audit, hence I combined the Johnny GUI for John the Ripper and browser-based utilities from Networkwalks Tools.

1. W3-PM1: Password Cracking with John the Ripper (Johnny GUI)
2. W3-PM2: Password Cracking with Networkwalks (NW) Tools

---

## Environment Setup
* **Operating System: ** Windows 11
* **offline cracking Tool:** John the Ripper (`1.9.0-jumbo-1-win64`)
* **Executable Path:** `C:\Users\USER\Downloads\john-1.9.0-jumbo-1-win64\john-1.9.0-jumbo-1-win64\run\john.exe`
Online Auditing Utility: Networkwalks (NW) Hashes & Password Cracking Tools
Target Files:
- My Locked PDF1.pdf (W3-PM1)
- My Locked PDF2.pdf (W3-PM1)
- My Locked PDF3.pdf (W3-PM1)
- My Locked PDF1 (for NW Tools Lab WK3-PM2).pdf (W3-PM2)

---
## Task Breakdown & Methodology

### 1. W3-PM1: Password Cracking with Johnny (JTR GUI)

**Objective:** Extract cryptographic hashes from three password-protected PDF files (`My Locked PDF1.pdf`, `My Locked PDF2.pdf`, and `My Locked PDF3.pdf`), recover their plaintext passwords using the Johnny GUI, and unlock each document to capture the embedded flags.

**Workflow Executed:**
* I Extracted the password hashes from all three target PDF documents into separate text files (`hash1.txt`, `hash2.txt`, and `hash3.txt`).
* Then Loaded each hash file into **Johnny** (**File > Open Passwords File**) and launched a cracking session using **Start new attack**.
* I Achieving a 100% success rate (`1/1: 1 cracked, 0 left`) across all three files, recovering the passwords `good-luck`, `password1`, and `1qaz2wsx`.
* Lastly I Used the recovered passwords to unlock each PDF, verify document access, and retrieve the hidden flags.

**Proof of Execution — Johnny GUI Cracking Results: ** below are my screen shots

1. My Locked PDF1.pdf (good-luck):

<img width="1279" height="674" alt="john the ripper" src="https://github.com/user-attachments/assets/f360e61c-b3e3-4602-bad0-3b4a7fd99079" />

2. My Locked PDF2.pdf (password1):

<img width="1279" height="669" alt="image" src="https://github.com/user-attachments/assets/4a051048-c30f-4190-842e-ee6745c3c615" />

3.My Locked PDF3.pdf (1qaz2wsx):

<img width="1279" height="659" alt="image" src="https://github.com/user-attachments/assets/be446339-31c9-446f-80b8-2be3373e2068" />

Proof of Execution — Unlocked PDFs & Captured Flags:

Flag 1 (my locked PDF1)

<img width="403" height="543" alt="PASSword harsh" src="https://github.com/user-attachments/assets/f23a294b-e7fd-49eb-9c33-da98b65b68f1" />

Flag 2 (my locked PDF 2)

<img width="1279" height="594" alt="image" src="https://github.com/user-attachments/assets/3acc27bf-3b9c-4669-8c62-39b1b59fbd94" />

flag 3 (my locked PDF 3)

<img width="1263" height="548" alt="image" src="https://github.com/user-attachments/assets/6726769a-5dc7-4a48-ba7f-df208481f7b2" />


### 2. W3-PM2: Password Cracking with Networkwalks (NW) Tools

**Objective:** Recover the password for `My Locked PDF1 (for NW Tools Lab WK3-PM2).pdf` using Networkwalks' online password cracking utility and cross-verify the results from the previous task.

**Workflow Performed:**
* I Opened the **Networkwalks Hashes & Password Cracking Tools** portal and uploaded `My Locked PDF1 (for NW Tools Lab WK3-PM2).pdf`.
* Then Ran the online dictionary audit, which successfully matched and recovered the password `password1`.
* Used `password1` to unlock the document and capture the final flag.
* Cross-checked the three PDFs from **W3-PM1** using NW Tools, confirming the exact same passwords across both offline (Johnny) and online utilities.

**Proof of Execution — Networkwalks Tools & Captured Flag:**

1. NW Tools Password Recovery (password1):

   <img width="1273" height="593" alt="image" src="https://github.com/user-attachments/assets/77d8ee72-385a-4714-9aed-a7e6ec1d952d" />

 ## Summary of Recovered Passwords & Flags

| Task ID | Target File | Tool Used | Recovered Password | Captured Flag | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **W3-PM1** | `My Locked PDF1.pdf` | Johnny (JTR GUI) | `good-luck` | `nw{cybersecurity_flag_captured_2608}` | Verified |
| **W3-PM1** | `My Locked PDF2.pdf` | Johnny (JTR GUI) | `password1` | `nw{networkwalks_persistence_jtr_270521}` | Verified |
| **W3-PM1** | `My Locked PDF3.pdf` | Johnny (JTR GUI) | `1qaz2wsx` | `nw{networkwalks_flag_250821_1}` | Verified |
| **W3-PM2** | `My Locked PDF1 (for NW Tools Lab WK3-PM2).pdf` | Networkwalks Tools | `password1` | `nw{networkwalks_flag1_jtr_270521_1}` | Verified |
  

## Key Security Takeaways and Mitigations

* **Weak & Predictable Passwords:** Common dictionary words (`password1`, `good-luck`) and keyboard-walk patterns (`1qaz2wsx`) offer almost no real protection. Once a file's hash is extracted, offline tools can crack them in seconds.
* **Stronger Passphrase Policies:** Organizations should protect sensitive PDFs with long, randomly generated passphrases (14+ characters) and avoid reusing predictable passwords across internal files.
* **Offline vs. Online Auditing:** Both local tools like John the Ripper and web-based utilities like Networkwalks Tools make short work of weak encryption handlers (`$pdf$4*4*128*`), highlighting the need for modern AES-256 encryption alongside strong passwords.

END

---

## Author & Project Information

* **Author: ** Lukman Ademola — Cybersecurity Professional (`B084`)
* **LinkedIn: ** (www.linkedin.com/in/lukman-ademola-08127182)
* **Program:** Cybersecurity Internship Program — Networkwalks
* **Module:** Week 03 — Password Cracking & Hash Analysis
* **Platform:** GitHub

---

