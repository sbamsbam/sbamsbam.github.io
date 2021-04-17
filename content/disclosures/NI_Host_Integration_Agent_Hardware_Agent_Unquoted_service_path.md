---
title: "NI Host Integration Agent and NI Hardware Agent Unquoted Service Path"
date: 2021-03-23T00:22:03+01:00
draft: false
---

**NI Host Integration Agent and NI Hardware Agent Unquoted Service Path**

# Software information
* **Software name:** NI Host Integration Agent
* **Affected Version:** <= 2.6.1
* **Software name:** NI Hardware Agent 
* **Affected Version:** <= 1.10.1
* **Software Web Page:** [https://www.native-instruments.com/en/](https://www.native-instruments.com/en/)

Native Instruments is a developer, manufacturer, and supplier of music software and hardware for music production, sound design, performance, and DJing.The company's corporate headquarters and main development facilities are located in Berlin, Germany, with additional offices in Los Angeles, Tokyo, London, Paris, and Shenzhen.

# Vulnerability Details

## Unquoted Search Path - CWE-428

* **Summary:** The product uses a search path that contains an unquoted element, in which the element contains whitespace or other separators. This can cause the product to access resources in a parent path.
* **Prerequisites:** Access to the file system is needed with W permission on "C:\"

**POC:**

[NI multiple unquoted service path](https://sbamsbam.github.io/pdf/native_instruments/POC_NI_2x_unquoted_service_path.pdf)


**Security Impact:**

A successful attempt would require the local user to be able to insert their code in the system root path undetected by the OS or other security applications where it could potentially be executed during application startup or reboot. If successful, the local user's code would execute with the elevated privileges of the application.
If a malicious individual has access to the file system, it is possible to elevate privileges by inserting such a file as "C:\Program.exe" to be run by a privileged program making use of WinExec. 

# **Timeline**

* **16/12/2020:** First disclosure to info@native-intruments.de
* **23/3/2021:** Disclosing vulnerability on my blog

