---
title: "Fing Agent Unquoted Service Path"
date: 2021-01-18T00:22:03+01:00
draft: false
---

**Fing Agent Unquoted Service Path**

# Software information
* **Software name:** Fing Agent
* **Affected Version:**  <=2.3.1
* **Software Web Page:** [https://www.fing.com/](https://www.fing.com/)

# Vulnerability Details

## Unquoted Search Path - CWE-428

* **Summary:** The product uses a search path that contains an unquoted element, in which the element contains whitespace or other separators. This can cause the product to access resources in a parent path.
* **Prerequisites:** Access to the file system is needed with W permission on "C:\"

**POC:**

<embed-pdf url="https://sbamsbam.github.io/pdf/fing/POC_FING.agent_unquoted_service_path.pdf" >

**Security Impact:**

A successful attempt would require the local user to be able to insert their code in the system root path undetected by the OS or other security applications where it could potentially be executed during application startup or reboot. If successful, the local user's code would execute with the elevated privileges of the application.
If a malicious individual has access to the file system, it is possible to elevate privileges by inserting such a file as "C:\Program.exe" to be run by a privileged program making use of WinExec. 

# **Timeline**

* **11/12/2020:** First disclosure to support@fing.com
* **11/12/2020:**Received an automatic response from support@fing.com via Zendesk ticket(100965)
* **18/03/2021:** Disclosing vulnerability on my blog
