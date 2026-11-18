<div align="center">

# Week 2 – Password Cracking

Week 3 – Project Modules 1 &amp; 2: Password Cracking
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ver-Virtualbox%20v7.2-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Linux-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Virtualization-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/Kali%20Linux-404040?style=flat-square&labelColor=C00000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ethical%20Hacking-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Waqas%20Karim%20CCIE-C00000?style=flat-square" />
</p>

# Week 3 – Password Cracking

**Internship:** NetworkWalks Cybersecurity
**Intern:** [Awais Sajjad]
**Week:** 3
**Focus:** Password cracking fundamentals — recovering passwords from
protected files using both a professional tool (John the Ripper) and a
lightweight browser-based alternative (NetworkWalks tools).

> All activities were carried out for educational purposes, on sample
> files provided specifically for this lab exercise.

## Overview

This week focused on understanding how password-protected files can be
broken using dictionary attacks — a core technique in password security
auditing. The same underlying concept (extract a crackable hash → run it
against a wordlist) was applied using two different tools, to compare a
traditional offline tool against a modern browser-based one.

## Modules

| Module | Title | Tool(s) Used | Status |
|--------|-------|----------------|--------|
| [Module 1](Week3-Module1-Password-Cracking-JTR) | Password Cracking with JTR | John the Ripper + Johnny GUI | ✅ Complete |
| [Module 2](Week3-Module2-Password-Cracking-NW-Tools) | Password Cracking with NetworkWalks Tools | NW Hash Calculator + NW Password Cracker | ✅ Complete |

## Summary of Results

| PDF File | Cracked Password | Cracked by JTR | Cracked by NW Tools |
|----------|----------------------|:---------------:|:----------------------:|
| My Locked PDF1.pdf | `good-luck` | ✅ | ✅ |
| My Locked PDF2.pdf | `password1` | ✅ | ✅ |
| My Locked PDF3.pdf | `1qaz2wsx` | ✅ | ✅ |
| My Locked PDF1 (for NW Tools Lab WK3-PM2).pdf | `password1` | — | ✅ |

Every password was successfully recovered in both modules, with
**identical results between JTR and the NetworkWalks tools** — confirming
both implement the same core dictionary-attack logic.

## Key Skills Demonstrated
- Extracting crackable hashes from password-protected PDF files
  (pdf2john / hashcat-compatible format)
- Running dictionary attacks using both a command-line/GUI tool (JTR +
  Johnny) and a browser-based tool (NetworkWalks Hash Calculator &
  Password Cracker)
- Comparing tool performance and wordlist behavior (attempt count,
  cracking speed) across different passwords
- Verifying recovered passwords by successfully unlocking the original
  files

## What I Learned
Password cracking tools don't "guess" passwords randomly — they
systematically test words from a wordlist in order, so a password's real
strength depends on how far down that list it sits, not just how it
looks. Common patterns like dictionary words with a number appended
(`password1`), simple phrases (`good-luck`), or keyboard-walk sequences
(`1qaz2wsx`) are cracked in seconds regardless of which tool is used,
because they already exist in standard wordlists. This reinforced why
organizations should enforce passphrase length and randomness rather
than relying on superficial complexity rules.

## Disclaimer
All password cracking in this module was performed on sample files
specifically provided for this training exercise, for educational
purposes only.
