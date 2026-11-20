# Week 3 – Password Cracking Lab (Networkwalks Cybersecurity Internship)

## Overview
This project covers two approaches to recovering the password of a protected PDF file (`My Locked PDF1.pdf`) as part of the Networkwalks Cybersecurity & Ethical Hacking SOC internship, Week 3.

The goal was to understand how password-protected files store credentials as hashes, and how cracking tools recover the plaintext password from that hash using dictionary/wordlist attacks.

## Module 1: Password Cracking with John the Ripper (JTR)
**Tools used:** John the Ripper (JTR), Johnny (GUI for JTR), Online Hash Crack (PDF hash extractor)

**Steps:**
1. Downloaded and installed John the Ripper + Johnny GUI on Windows.
2. Extracted the PDF's hash using an online PDF hash extractor (pdf2john-compatible), producing a hash in `$pdf$...` format.
3. Saved the hash to `hash1.txt`.
4. Loaded the hash file into Johnny, pointed it to `john.exe`, and ran the attack.
5. JTR recovered the password: **`password1`**
6. Verified by opening the PDF with the recovered password.

## Module 2: Password Cracking with Networkwalks Tools
**Tools used:** Networkwalks Hash Calculator, Networkwalks Password Cracker (browser-based, no installation needed)

**Steps:**
1. Uploaded the locked PDF to the Networkwalks Hash Calculator to extract the `$pdf$...` hash (computed locally in-browser).
2. Copied the full hash value.
3. Pasted the hash into the Networkwalks Password Cracker tool.
4. Ran the dictionary attack (built-in 100-password wordlist).
5. Password cracked successfully: **`password1`**
6. Opened the PDF using the cracked password to confirm.

## Key Takeaways
- **Encryption vs Hashing:** Encryption is reversible with the right key; hashing is a one-way function — cracking tools don't "decrypt" a hash, they guess passwords and compare hashes until a match is found.
- A weak, common password (`password1`) was cracked almost instantly with a small wordlist — demonstrating why password complexity and length matter.
- Both a traditional CLI/GUI tool (JTR/Johnny) and a modern browser-based tool achieved the same result, showing the underlying concept (hash extraction → dictionary attack) is consistent across tools.

## Flag Captured
`nw{networkwalks_flag1_jtr_270521_1}`
![John the Ripper Practical](screenshots/john-ripper.png)
---
*Part of the Networkwalks Academy Cybersecurity & Ethical Hacking training program – www.networkwalks.com*
