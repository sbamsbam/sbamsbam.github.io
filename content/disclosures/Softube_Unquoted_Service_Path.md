---
title: "Softube Helper Unquoted Service Path"
date: 2021-01-03T00:22:03+01:00
draft: false
---

**Unquoted Service Path**

# Software information
* **Software name:** Softube Helper
* **Affected Version:** <= 2.5.9
* **Software Web Page:** [Softube Central Installer Helper](https://softubestorage.b-cdn.net/installerhelper/Softube%20Installer%20Helper%20Installer%20(64-bit)%202.5.9%200924f279.exe "Softube Central Installer Helper")

Softube Central is the all-in-one installer that handles installation and license activation of your Softube products.

# Vulnerability Details

## Unquoted Search Path - CWE-428

* **Summary:** The product uses a search path that contains an unquoted element, in which the element contains whitespace or other separators. This can cause the product to access resources in a parent path.
* **Prerequisites:** Access to the file system is needed with W permission on "C:\"

**POC:**

Softube VP Reseach & Development asked me to not disclose de POC.

**Security Impact:**

A successful attempt would require the local user to be able to insert their code in the system root path undetected by the OS or other security applications where it could potentially be executed during application startup or reboot. If successful, the local user's code would execute with the elevated privileges of the application.
If a malicious individual has access to the file system, it is possible to elevate privileges by inserting such a file as "C:\Program.exe" to be run by a privileged program making use of WinExec. 

# **Timeline**

* **3/12/2020:** First disclosure to Softube info@softube.com
* **3/12/2020:** Received an automatic response from the Zendesk ticketing system.
* **3/12/2020:** Contacted from Customer Support via mail address, informing me about ticket forwarding to right team. 
* **4/12/2020:** Contacted from Softube VP Reseach & Development via mail address, informing me that the issue is going tobe fixed ASAP.
* **5/12/2020:** Pinged Softube VP Reseach & Development to talk about deadlines and disclosure's method.
* **7/12/2020:** Contacted from Softube VP Reseach & Development via mail address, to inform me that they opted me to disclose generic info about vulnerability without POC and they are testing a fix they hope to ship in two days.
* **7/12/2020:** I replied to previous mail  saying that I'd would  have  waited for the fix before publishing on my blog.
* **16/12/2020:** Pinged Softube VP Reseach & Development asking for update.
* **18/12/2020:** Contacted from Softube VP Reseach & Development via mail address, informing me they had some initial problem but the update has been shipped the previous day (17/12/2020) and they sent an update to their customers regarding  the issue.
* **3/1/2021:** Disclosing vulnerability on my blog, I noticed that the software version on softube download page is still version 2.5.9 (informed Softube VP Research about version issue) - Submitted to Mitre
* **4/1/2021:** CVE Request Rejected from Mitre
* **15/1/2021:** Contacted from Softube VP Reseach & Development via mail address, informing me that the
fixed version for windows is 2.5.10, but on download page ther is the link for Mac version that is still 2.5.9.
