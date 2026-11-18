# Week 3 – Module 2: Password Cracking with NetworkWalks Tools

**Internship:** NetworkWalks-Cybersecurity
**Intern:** [Awais Sajjad]
**Week:** 3

> Performed for educational purposes only, on password-protected PDF
> files provided for this lab exercise.

## Background
This lab uses two free browser-based tools built by NetworkWalks: the
**Hash Calculator** (extracts a crackable hash from a locked PDF) and the
**Password Cracker** (runs a dictionary attack against that hash) —
no installation required, using the same underlying idea as John the
Ripper.

## Objective
Crack the passwords of three provided protected PDF files using the
NetworkWalks Hash Calculator and Password Cracker tools.

## Environment Used
Browser-based — works identically on Windows or Kali Linux since both
tools run entirely client-side.

---

## PDF 1: My Locked PDF1.pdf

**Step 1 — Extract hash:**
Uploaded `My Locked PDF1.pdf` (266.9 KB) to the Hash Calculator, which
extracted a crackable `$pdf$...` hash (128-bit, Revision R4/V4).

![Hash extracted - PDF1](screenshots/01-pdf1-hash.png)

**Step 2 — Run the Password Cracker:**
Pasted the hash and ran the dictionary attack. The tool tried 3,463 of
1,795,707 words before finding a match.

![Password cracked - PDF1](screenshots/02-pdf1-cracked.png)

**Cracked password:** `good-luck`

---

## PDF 2: My Locked PDF2.pdf

**Step 1 — Extract hash:**
Uploaded `My Locked PDF2.pdf` (204.7 KB) and extracted its hash.

![Hash extracted - PDF2](screenshots/03-pdf2-hash.png)

**Step 2 — Run the Password Cracker:**
Pasted the hash and ran the attack. Matched after just 22 attempts.

![Password cracked - PDF2](screenshots/04-pdf2-cracked.png)

**Cracked password:** `password1`

---

## PDF 3: My Locked PDF3.pdf

**Step 1 — Extract hash:**
Uploaded `My Locked PDF3.pdf` (313.5 KB) and extracted its hash.

![Hash extracted - PDF3](screenshots/05-pdf3-hash.png)

**Step 2 — Run the Password Cracker:**
Pasted the hash and ran the attack. Matched after 2,085 attempts.

![Password cracked - PDF3](screenshots/06-pdf3-cracked.png)

**Cracked password:** `1qaz2wsx`

---

## Verification — Flags Captured
Each unlocked PDF revealed a unique congratulatory flag, confirming
successful password recovery for all three files:

![Flag 1](screenshots/07-flag-1.png)
![Flag 2](screenshots/08-flag-2.png)
![Flag 3](screenshots/09-flag-3.png)

---

## Results Summary

| # | PDF File | Hash Extracted | Attempts Needed | Cracked Password |
|---|----------|------------------|---------------------|-----------------------|
| 1 | My Locked PDF1.pdf | ✅ | 3,463 / 1,795,707 | `good-luck` |
| 2 | My Locked PDF2.pdf | ✅ | 22 / 1,795,707 | `password1` |
| 3 | My Locked PDF3.pdf | ✅ | 2,085 / 1,795,707 | `1qaz2wsx` |

## Findings
All three passwords were recovered quickly, but the **number of attempts
needed varied significantly** — `password1` was found almost immediately
(22 attempts) since it appears very early in the wordlist, while
`good-luck` and `1qaz2wsx` needed thousands of attempts despite still
being common patterns. This shows that **wordlist ordering matters**:
passwords placed earlier in a dictionary are cracked faster regardless
of apparent complexity.

## Comparison with Module 1 (JTR)
| Criteria | JTR (Johnny, Module 1) | NetworkWalks Tools (Module 2) |
|----------|---------------------------|-----------------------------------|
| Installation required | Johnny GUI + John binary | None — runs in browser |
| Passwords cracked | good-luck, password1, 1qaz2wsx | good-luck, password1, 1qaz2wsx |
| Processing location | Local on device | Local in-browser (PDF never uploaded) |
| Wordlist size | John's default jumbo wordlist | 1,795,707-word list (same as rockyou-style lists) |
| Speed shown | 100% cracked, time not displayed | Live attempts/sec shown (e.g. 15 pw/s) |

## Summary
The NetworkWalks Hash Calculator and Password Cracker reproduced the
exact same results as JTR in Module 1, using the identical underlying
approach (extract hash → dictionary attack), but packaged as a
browser-based tool with a visible live attempt counter. This made it
easy to directly observe how wordlist position affects cracking speed.

## Key Takeaway
Regardless of which tool is used — professional (JTR) or
browser-based (NetworkWalks Tools) — a password's real strength is
determined by how predictable it is, not by which cracking tool is used
against it. Passwords that resemble dictionary words, common phrases, or
keyboard-walk patterns remain highly vulnerable either way.
