# WPHAX 

WP Version used: **3.8**

## **Exploit 1**

**Description:**
"Upload media" can be hacked with **XSS**.

**Steps:**

* Go to **Upload Media** menu.
* Upload a file which is more than **20MB** with *"file<img src=x onerror=alert("hacked")>.png"* name.
