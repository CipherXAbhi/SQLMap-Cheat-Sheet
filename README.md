# SQLMap-Cheat-Sheet
## 📌 What is SQLMap?

**SQLMap** is an advanced SQL injection exploitation tool used by penetration testers and ethical hackers to automate the process of:
- Detecting SQL injection vulnerabilities
- Enumerating databases, tables, and data
- Gaining access to the file system or executing commands (if possible)
- Bypassing WAFs and filters using tamper scripts

---
-u for url
--crawl for crawling the url also show the depth of the url if you want to depth in the url like https://github.com/Cheetsheet use --crawl 2,if you want to depth in the url like https://github.com/Cheetsheet/linux use --crawl 3,<br>
Example:
```
sqlmap -u url --crawl 2 
```
Note: in this technique you do all the things manualy

---
## batch
If you want to do all the things manualy you use --batch
```
sqlmap -u url --crawl 2 --batch
```

---
## technique
If you want to do the specific technique use --technique="" --batch<br>
For Union technique
```
sqlmap -u url --crawl 2 --technique="U" --batch
```

---
## threads
if You you test the bigger weebsite there has so many directories, pages that time the time consumption if so much so wee have an options `threads` <br>
By default 1, max number 100
```
sqlmap -u url --crawl 2 --batch --threads 5
```

---
## risk
it gives three features, so many times you cant see the vulnerabilities that time you try the different type of payloads
so we use risk <br>
1 defualt 3 max
```
sqlmap -u url --crawl 2 --batch --risk 1
```
---
##level
