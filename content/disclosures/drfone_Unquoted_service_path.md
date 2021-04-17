---
title: "Drfone Unquoted Service Path"
date: 2021-03-17T00:22:03+01:00
draft: false
---

**Drfone Unquoted Service Path**

# Software information
* **Software name:** Drfone
* **Affected Version:** <= 11.0.1.317
* **Software Web Page:** [https://drfone.wondershare.com/](https://drfone.wondershare.com/)

A complete solution for phone data recovery, transfer, screen unlock, system repair, etc.
Apart from the PC-end software, Dr.Fone provides apps for iPhone, iPad, and Android devices to help transfer or recover data, and record screen activities.

# Vulnerability Details

## Unquoted Search Path - CWE-428

* **Summary:** The product uses a search path that contains an unquoted element, in which the element contains whitespace or other separators. This can cause the product to access resources in a parent path.
* **Prerequisites:** Access to the file system is needed with W permission on "C:\"

**POC:**

[drfone unquoted service path](https://sbamsbam.github.io/pdf/wondershare/POC_drfone_unquoted_service_path.pdf) 

**Security Impact:**

A successful attempt would require the local user to be able to insert their code in the system root path undetected by the OS or other security applications where it could potentially be executed during application startup or reboot. If successful, the local user's code would execute with the elevated privileges of the application.
If a malicious individual has access to the file system, it is possible to elevate privileges by inserting such a file as "C:\Program.exe" to be run by a privileged program making use of WinExec. 

# **Timeline**

* **9/12/2020:** First disclosure to support@wondershare.com 
* **9/12/2020:** Received an automatic response from customer_service@wondershare.com via Zendesk ticket(438085)
* **17/12/2020:** Second mail sent to support@wondershare.com  
* **17/12/2020:** Received an automatic response from customer_service@wondershare.com via Zendesk ticket(463016)
* **17/03/2021:** Disclosing vulnerability on my blog
