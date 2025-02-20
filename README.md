# **Born2BeRoot**

## 📌 Project Overview
Born2BeRoot is a system administration project that involves setting up a secure, properly configured virtual server using **Debian** (or **CentOS**). The project focuses on **partitioning, user management, SSH configuration, security hardening, and automation**.

## ⚙️ Technologies Used
- 🖥️ **Operating System:** Debian 11 *(or CentOS)*
- 🔒 **Security:** UFW (Uncomplicated Firewall), Fail2Ban, SSH Hardening
- 📂 **Partitioning:** LVM (Logical Volume Manager)
- 🤖 **Automation:** Cron Jobs & Scripts

---

## 🚀 Step-by-Step Setup Process

### 1️⃣ Virtual Machine Setup
- Install **Debian** (or CentOS) inside **VirtualBox** or another hypervisor.
- Enable **UEFI mode** in VM settings (important for security and grading).

💡 **Personal Insight:**  
I initially faced issues with **UEFI mode not being detected** in VirtualBox. The fix was to enable it before installing the OS.

### 2️⃣ User & Group Management
- Create a **non-root user** with `sudo` privileges.
- Restrict direct `root` login via SSH (`PermitRootLogin no`).

💡 **Personal Insight:**  
I mistakenly gave my user **full sudo access**, which was **not allowed** in the evaluation. Instead, I limited commands with `visudo`.

### 3️⃣ SSH Configuration
- Change the **default SSH port** (to enhance security).
- Disable **password authentication**, allowing only **SSH key authentication**.

💡 **Personal Insight:**  
I locked myself out by disabling password authentication **before adding my SSH key** 😅. Always test SSH settings before applying strict rules.

### 4️⃣ Firewall & Fail2Ban
- **UFW**: Enable and allow only necessary services (`ssh`, `http`, etc.).
- **Fail2Ban**: Protect SSH from brute-force attacks.

💡 **Personal Insight:**  
The **default Fail2Ban rules didn’t work** on Debian. I had to manually edit `/etc/fail2ban/jail.local`.

### 5️⃣ Partitioning with LVM
- Set up **separate partitions** for `/`, `/home`, `/var`, `/srv`, and `/tmp`.
- Use **LVM** to allow easier resizing in the future.

💡 **Personal Insight:**  
I initially used **fixed partitions**, which was a mistake. **LVM** made resizing much easier when I ran out of space in `/var`.

### 6️⃣ Cron Jobs for System Monitoring
- Automate **disk usage reports** and system uptime logging.
- Configure **custom scripts** to send reports via email.

💡 **Personal Insight:**  
The **mail command** was missing on my system. I had to install `postfix` manually for email notifications.

### 7️⃣ Bonus: Adding AI Chatbot to Born2BeRoot
*(Optional, but a cool addition!)*
- Installed a **lightweight AI chatbot** to run locally.
- Allowed users to interact with an AI for system help.

💡 **Personal Insight:**  
I had to ensure the AI **didn’t consume too many system resources**, so I used **a simple text-based model** instead of a heavy one.

---

## 📌 Common Issues & Fixes

| Issue | Solution |
|--------|---------|
| SSH connection refused | Check UFW rules, restart SSH (`sudo systemctl restart ssh`) |
| User can’t run sudo commands | Edit `/etc/sudoers` and add the user properly |
| Fail2Ban not working | Modify `/etc/fail2ban/jail.local` and restart service |
| UEFI mode not detected | Enable UEFI in VirtualBox settings before installation |

---

## 📜 Final Thoughts
Born2BeRoot was a great **learning experience** in **system administration and security**. The key lessons I learned:  
✅ Always **test security settings** before applying them permanently.  
✅ **LVM is a lifesaver** for flexible storage management.  
✅ **SSH hardening is crucial** for protecting a remote system.  
✅ Adding a **bonus feature (AI chatbot)** made my project unique.

🎯 **Advice to Future Students:**  
- Document **every step** (helps with debugging & evaluation).  
- Read **logs carefully** to troubleshoot errors.  
- Test **all configurations** in a separate VM before applying them to the final one.

---

### 📧 Contact & Questions
If you have any questions or need help, feel free to reach out! 🚀
