---
title: "ext2fsd Unquoted Service Path"
date: 2021-03-16T00:22:03+01:00
draft: false
---

**ext2fsd Unquoted Service Path**

# Software information
* **Software name:** ext2fsd
* **Affected Version:** <=0.69
* **Software Web Page:** [https://www.ext2fsd.com/](https://www.ext2fsd.com/)

Open source ext3/4 file system driver for Windows (2K/XP/WIN7/WIN8)
# Vulnerability Details

## Unquoted Search Path - CWE-428

* **Summary:** The product uses a search path that contains an unquoted element, in which the element contains whitespace or other separators. This can cause the product to access resources in a parent path.
* **Prerequisites:** Access to the file system is needed with W permission on "C:\"

**POC:**

[EXT2FSD unquoted service path](https://sbamsbam.github.io/pdf/ext2fsd/POC_EXT2FSD_unquoted_service_path.pdf)

**Security Impact:**

A successful attempt would require the local user to be able to insert their code in the system root path undetected by the OS or other security applications where it could potentially be executed during application startup or reboot. If successful, the local user's code would execute with the elevated privileges of the application.
If a malicious individual has access to the file system, it is possible to elevate privileges by inserting such a file as "C:\Program.exe" to be run by a privileged program making use of WinExec. 

# **Timeline**

* **9/12/2020:** First disclosure to matt@ext2fsd.com
* **16/12/2020:** Second email sent to matt@ext2fsd.com
* **16/03/2021:** Disclosing vulnerability on my blog
