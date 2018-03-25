# WPHAX 

WP Version used: **3.8**

## **Exploit 1**

**Description:**
"Upload media" section can be hacked with **XSS**.

**Steps:**

* Go to **Upload Media** menu.
* Upload a file which is more than **20MB** with *"file<img src=x onerror=alert("hacked")>.png"* name.

![Our user is author, so can upload media](https://i.imgur.com/z6pj5HV.png)
![Upload Media](https://i.imgur.com/Ad0wZIt.png)
![XSS](https://i.imgur.com/aRp2L62.png)
