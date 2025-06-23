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
| Risk  | Description                                                                                                                                                                                           |
| ----- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1** | Safe and low-impact payloads. Does not change data or affect performance. (Default)                                                                                                                   |
| **2** | Medium risk. Includes **time-based payloads** and **more complex injections**. May slow down the server slightly.                                                                                     |
| **3** | High risk. Includes **stacked queries**, **heavy time delays**, and **data-altering** payloads. May cause **server instability** or changes to the database (especially if write access is possible). |

---
## level
In SQLMap, the --level option controls how thorough and aggressive SQLMap is when testing different types of parameters for SQL injection.
* The default level is 1.
* Higher levels make SQLMap test more parameters and use more techniques.
* It increases depth and coverage of the SQL injection test.
```
sqlmap -u url --crawl 2 --batch --level 1
```
## level breakdown
| Level | Description                                                                                                |
| ----- | ---------------------------------------------------------------------------------------------------------- |
| **1** | Default. Tests **only basic GET/POST parameters**. Fastest and least intrusive.                            |
| **2** | Also tests **headers like User-Agent and Referer**.                                                        |
| **3** | Adds **more advanced and uncommon parameter types**, including cookies and multipart parameters.           |
| **4** | Extends testing to **all possible inputs**, including deeper nested parameters.                            |
| **5** | Most **aggressive**. Tries **everything possible**, even very unlikely parameters. Slowest and most noisy. |

---
## verbosity
In SQLMap, the --verbosity option controls how much information is displayed in the terminal output during the scan. It’s useful for understanding what SQLMap is doing at each stage of the attack.
| Level | Description                                                                                                 |
| ----- | ----------------------------------------------------------------------------------------------------------- |
| **0** | **Silent mode** – no output unless there's an error.                                                        |
| **1** | Show **basic information** (default).                                                                       |
| **2** | Show each **HTTP request** being sent.                                                                      |
| **3** | Add **payloads** being tested.                                                                              |
| **4** | Include **HTTP responses** as well.                                                                         |
| **5** | Full **debug info** – includes extensive detail about payloads, detection, and results.                     |
| **6** | **Extremely verbose** – shows **everything**, useful for debugging or learning how SQLMap works internally. |

```
sqlmap -u "http://example.com/page.php?id=1" --verbosity=3 --level=2 --risk=2

```
