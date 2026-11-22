# -Password-Auditing-PDF-Recovery-with-John-the-Ripper
This project demonstrates password strength auditing and cryptographic hash recovery on an encrypted PDF document. 
# 🔐 Password Auditing & PDF Recovery with John the Ripper

Module: Week 3 — Project Module 1: Password Cracking with JTR

Environment: macOS (Intel x86_64) & Kali Linux (VirtualBox)

Target: My Locked PDF1.pdf

# 📌 Summary

This project demonstrates password strength auditing and cryptographic hash recovery on an encrypted PDF document. While the standard lab guide outlines a Windows GUI workflow using Johnny, the exercise was adapted and executed natively on macOS via the command line using John the Ripper (Jumbo Edition).

# 🛠️ Tools Used

John the Ripper (john-jumbo 1.9.0-jumbo-1): Command-line password auditing tool used to run dictionary and rule-based attacks against PDF hashes (MD5/SHA2/RC4/AES).

Homebrew & OpenSSL 4: Used to compile john-jumbo from source on Intel macOS.

PDF Hash Extractor (pdf2john): Extracted the $pdf$4*4*128*... encryption metadata from the locked PDF.

macOS Terminal (zsh) & Preview: Used for hash management, execution, and final PDF decryption verification.

# 🚧 Challenges Encountered & How They Were Solved

# Kali Linux VirtualBox Display Corruption:

Issue: Running Kali Linux on an Intel Mac Retina display caused severe horizontal tearing, blue static, and scrambled fonts due to a 3D acceleration and framebuffer stride mismatch.

Resolution: Disabled 3D acceleration in VirtualBox (VMSVGA controller), turned off macOS Retina high-resolution scaling for VirtualBoxVM, and pivoted to running John the Ripper natively on macOS for maximum performance.

# Homebrew Deprecation & Network Resets on Intel Mac:

Issue: Homebrew dropped pre-built binary bottles for Intel x86_64 Macs in September 2026, forcing a full source compilation of john-jumbo and openssl@4, which initially failed due to peer connection resets (curl: (56)).

Resolution: Re-ran the build with HOMEBREW_NO_AUTO_UPDATE=1, successfully compiling both packages from source.

# Empty Hash Output & Shell Variable Expansion:

Issue: Local pdf2john.pl failed to parse the PDF structure, leaving hash1.txt empty (No password hashes loaded). Additionally, $ characters in PDF hashes risk being treated as empty variables by zsh.

Resolution: Extracted the clean $pdf$... hash string and wrapped it in single quotes ('...') when writing to hash1.txt to preserve the exact delimiters.

# 🏆 Key Wins & Results

Native Compilation & Execution: Successfully built and ran john-jumbo natively on Intel macOS, achieving a cracking speed of 34,480+ passwords/second using CPU SSE4.2 instructions.

Instant Password Recovery: Cracked the 128-bit PDF Revision 4 hash in under 1 second using John's default wordlist rules, recovering the password good-luck.

Flag Captured: Unlocked My Locked PDF1.pdf and verified access to the completion flag.

Security Takeaway: Demonstrated that strong encryption algorithms (128-bit AES/RC4) are easily bypassed when paired with low-entropy, dictionary-based passwords.
