# Password Auditing & PDF Recovery Using John the Ripper

**Networkwalks Cybersecurity & Ethical Hacking Internship | Week 3 – Project Module 1**

A practical password security assessment demonstrating PDF password hash extraction, dictionary-based password auditing, and password recovery using **John the Ripper (Jumbo Edition)**.

## 📌 Project Overview

This project involved auditing the password security of an encrypted PDF document using John the Ripper.

The exercise focused on extracting cryptographic password hashes from an encrypted PDF, analyzing password strength through dictionary-based attacks, and recovering the password in an authorized lab environment.

Although the original lab guide demonstrated a Windows-based workflow using Johnny, I adapted the exercise to work with a macOS environment using command-line tools.

## 🎯 Objectives

- Understand how password-based PDF encryption works.
- Extract password hashes from encrypted PDF documents.
- Configure and use John the Ripper for password auditing.
- Perform dictionary-based password attacks.
- Evaluate the effectiveness of weak passwords against automated attacks.
- Understand the importance of strong password practices.

## 🖥️ Lab Environment

| Component | Configuration |
|---|---|
| Host OS | macOS (Intel x86_64) |
| Virtualization | Oracle VirtualBox |
| Linux Environment | Kali Linux |
| Password Auditing Tool | John the Ripper (Jumbo Edition) |
| Hash Extraction | pdf2john |
| Package Manager | Homebrew |
| Shell | Zsh |
| Target | Encrypted PDF document |

## 🛠️ Tools & Technologies

- **John the Ripper (Jumbo Edition):** Password auditing and hash-cracking tool.
- **pdf2john:** Extracts password hashes from encrypted PDF documents.
- **Homebrew:** Package management and software installation on macOS.
- **OpenSSL:** Cryptographic library used during the native compilation process.
- **macOS Terminal:** Command-line environment for executing the assessment.

## ⚙️ Methodology

### 1. Environment Preparation

Prepared the macOS environment and configured the required dependencies for running John the Ripper.

Due to compatibility and display issues encountered while running Kali Linux in VirtualBox, I adapted the workflow to execute John the Ripper natively on macOS.

### 2. Hash Extraction

Used the PDF hash extraction utility (pdf2john) to extract the password hash from the encrypted PDF document.

The extracted hash contained the encryption metadata required by John the Ripper to perform password auditing.

### 3. Password Auditing

Loaded the extracted hash into John the Ripper and executed a dictionary-based password attack.

The tool compared candidate passwords against the extracted hash to identify a matching password.

### 4. Password Recovery & Verification

John the Ripper successfully recovered the password.

The recovered password was then used to unlock the encrypted PDF document and verify successful access to its contents.

## 🚧 Challenges & Solutions

| Challenge | Solution |
|---|---|
| Kali Linux display corruption in VirtualBox | Disabled 3D acceleration and adjusted display settings. |
| Homebrew source compilation issues | Adjusted the installation process and retried the source compilation. |
| PDF hash extraction failure | Used an alternative extraction approach and verified the extracted hash format. |
| Zsh interpreting special characters | Used single quotes to preserve special characters in the extracted hash. |

## 🏆 Results & Achievements

- Successfully compiled and executed John the Ripper natively on an Intel Mac.
- Achieved a password-auditing speed of **34,480+ passwords per second**.
- Successfully extracted the encryption hash from the target PDF.
- Recovered the PDF password in under one second.
- Verified successful decryption and access to the protected document.
- Captured the lab completion flag.

**Recovered password:** `good-luck`

## 🔍 Key Security Lessons

This exercise demonstrated that encryption strength and password strength are two different security considerations.

Even when a document uses strong encryption, a weak or predictable password can make it vulnerable to dictionary-based attacks.

Key recommendations:

- Use long, unique and unpredictable passwords.
- Avoid dictionary words and commonly used phrases.
- Use password managers to generate and store strong passwords.
- Apply additional protection to sensitive documents.
- Avoid reusing passwords across different platforms.

## 📸 Evidence & Screenshots

Screenshots documenting the practical implementation and results are included below.

1. Environment and tool setup.
2. PDF hash extraction.
3. John the Ripper execution.
4. Password recovery result.
5. Successful PDF decryption and flag verification.

## ⚖️ Ethical Considerations

This exercise was conducted for educational purposes within an authorized cybersecurity training environment.

Password auditing tools should only be used on files, systems and accounts for which permission has been granted.

## 📚 Conclusion

This project provided practical experience in password auditing, cryptographic hash extraction, command-line security tools and password recovery.

It also demonstrated the importance of adapting cybersecurity workflows to different operating systems while troubleshooting technical challenges independently.

---

**Project:** Networkwalks Cybersecurity & Ethical Hacking Internship  
**Module:** Week 3 – Project Module 1  
**Tool:** John the Ripper (Jumbo Edition)
