# **Forage_Cyber: AIG Shields Up - Cybersecurity Virtual Experience Program**

This repository contains all the tasks and solutions I completed during the **AIG Shields Up: Cybersecurity Virtual Experience Program** hosted on **Forage**. The program provided hands-on cybersecurity experience, focusing on vulnerability assessment, incident response, and ethical hacking.

---

## **Program Overview**
The program simulated real-world cybersecurity challenges, requiring technical skills, analytical thinking, and effective communication. Below, I detail the **tasks**, **steps taken**, and **key learnings**.

---

## **📌 Tasks Completed**
### **Task 1: Responding to a Zero-Day Vulnerability**
- **Objective**: Analyze and respond to the **Apache Log4j zero-day vulnerability** by notifying affected teams.
- **Steps**:
  1. Reviewed **CISA advisory** for Log4j vulnerability.
  2. Identified the **Product Development Staging Environment** as the affected infrastructure.
  3. Drafted an **email advisory** to alert the team about the vulnerability, risk impact, and remediation steps.
- **Key Learnings**:
  - How to **analyze** and **assess** cybersecurity threats.
  - **Effective communication** in security incident reporting.
  - Understanding **risk mitigation strategies**.

---

### **Task 2: Bypassing Ransomware**
- **Objective**: Write a **Python script** to brute-force the decryption key of a ransomware-encrypted ZIP file.
- **Steps**:
  1. Used the provided **`bruteforce.py`** template and **Rockyou wordlist**.
  2. Implemented a **brute-force attack** to test passwords from the wordlist.
  3. Successfully decrypted the **ZIP file** and extracted its contents.
  4. Opened the extracted **Word document** and pasted the Python script inside.
- **Key Learnings**:
  - **Python scripting** for ethical hacking.
  - Understanding **brute-force attacks** and password security.
  - **Hands-on experience** with cybersecurity incident response.

---

## **📚 What I Learned**
✅ **Cybersecurity Analysis** – Identifying and responding to vulnerabilities like Log4j.  
✅ **Risk Mitigation** – Learning proactive defense strategies.  
✅ **Python for Ethical Hacking** – Writing scripts to counteract cyber threats.  
✅ **Technical Communication** – Writing effective security advisories.  
✅ **Incident Response** – Applying cybersecurity best practices to real-world threats.  

---

## **⚙️ How to Use This Repository**
1. Open the downloaded zip & extract it. 
2. Run the brute-force decryption script: Through the VS code 
-python bruteforce.py
3. Check the output for the decrypted file.=you will get the .docx file output
4. Edit the .py code to perform the bruteforce attack.

## 📂 Folder Structure

The repository is structured as follows:

1️⃣ **Main Directory: `Forage_Cyber/`**
   - Contains the main files related to the cybersecurity virtual experience program.

2️⃣ **Subdirectory: `EncryptedFilePack/`**
   - This folder contains the encrypted ZIP file, brute-force script, and the password wordlist.

3️⃣ **Files Inside `EncryptedFilePack/`**
   - `bruteforce.py` → Python script to perform brute-force decryption.
   - `enc.zip` → Encrypted ZIP file (target for brute-force decryption).
   - `rockyou.txt` → Wordlist containing potential passwords.

4️⃣ **Root-Level Files**
   - `README.md` → Documentation file explaining the project.


🎯 Conclusion
This program provided real-world cybersecurity experience, equipping me with practical skills in vulnerability assessment, incident response, and ethical hacking. The hands-on approach made learning engaging and applicable to real-world cybersecurity challenges.

If you're interested in cybersecurity or ethical hacking, I highly recommend this program! 🚀

💬 Let's Connect!
Feel free to reach out or explore my GitHub projects! If you have questions or want to collaborate, let’s connect. 🔐


## **🔐 Brute-Force Decryption Script**
The following Python script attempts to brute-force the password of an **encrypted ZIP file** using a wordlist (**rockyou.txt**):

```python
from zipfile import ZipFile

# Attempt to extract the zip file with a given password
def attempt_extract(zf_handle, password):
    """Try to extract the encrypted ZIP file with the given password."""
    try:
        zf_handle.extractall(pwd=password)
        print(f"[+] Password found: {password.decode()}")
        return True
    except:
        return False

def main():
    print("[+] Beginning brute-force attack...")

    # Open the encrypted ZIP file
    with ZipFile('enc.zip') as zf:
        # Open the Rockyou wordlist
        with open('rockyou.txt', 'rb') as f:
            # Iterate through each password in the wordlist
            for password in f:
                password = password.strip()
                if attempt_extract(zf, password):
                    print("[+] File successfully decrypted!")
                    return

    # If no password matches, print this message
    print("[-] Password not found in the wordlist.")

if __name__ == "__main__":
    main()
